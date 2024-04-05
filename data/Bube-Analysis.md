# DittoETH Audit Analysis

The DittoETH mints pegged assets (stablecoins) using an orderbook, using over-collateralized staked ETH (rETH, stETH).

# Approach to Auditing

1. Read the provided documentation for `DittoETH` protocol: the documentation is well written and structured. It was easy to navigate to different sections and to understand important functions and concepts of the protocol. I made notes of the important information and tried to understand how should the protocol work.

2. Use of statyc analyzers: I ran static analyzers such as `Slither` and `Aderyan` in order to find basic issues and non critical errors. The found issues were then compared to the known issues from the `4naly3er-report`.

3. Read the known issues: I have participated in the prevous audit in CodeHawks. But it was a several months ago, so I read again the final report from the audit as well as the known issues described on the contest page in Code4rena.

4. Manual Review: After reviewing the documentation and familiarizing myself with the known issues, I started with the manual review of the codebase. I read again about Diamond proxy and the issues that can arise. I studied each function in the contracts, wrote comments and compared the behaviour of the function with that described in the documentation.

5. Tests: After the manual analysis I ran the foundry tests and studied each test function and its behaviour. That helped me to understand some parts of the code that were a little bit unclear by the manual review.

6. Write report: At the end I summarized my notes and studied each potential vulnerability that I found. I wrote tests for some of them and prepared the reports.

# System overview

The protocol uses `Diamond` proxy pattern, therefore it can be separated to `facets` and `libraries`:

# Facets

### `BidOrdersFacet`:

The `BidOredersFacet` contract is responsible for creation and matching of bid orders within the protocol. Here is a summary of important functionality:

**Order Creation**: Users can create bid orders to buy a specified `ercAmount` of an asset at a given price, with the option to make it a market or limit order (isMarketOrder). There are two entry points for creating bids: `createBid` for regular users and `createForcedBid` for specific contracts.

**Order Matching**: When a bid is created, it attempts to match with existing sell orders (asks or shorts) in the order book. If the bid price is equal to or higher than the lowest sell price, matching occurs.

**Matching Algorithm**: The `bidMatchAlgo` function is responsible for the logic of matching bids with the lowest available sell orders. It handles partial fills, dust thresholds, and updates the order book accordingly.

**Short Handling**: The contract also supports short selling, with specific logic to handle the matching and filling of short orders.

**Price and Oracle Updates**: The contract interacts with an oracle to fetch prices and updates the starting short ID based on price thresholds.

**Escrow and Settlement**: The contract manages escrowed funds (`ETH` and `ERC`) for users and settles trades by updating balances upon successful matches.

### `ShortOrdersFacet`:

The `ShortOrdersFacet` contract allows users to create limit short orders on a given asset. The main function in this contract is `createLimitShort`. This function is responsible for creating limit short orders in the market system. It takes various parameters such as the asset, price, ERC amount, order hint array, short hint array, and short order collateral ratio (`shortOrderCR`). It performs several validations and calculations related to the short order before creating it:

- It initializes some local variables and storage references.
- It calculates the collateral ratio (`cr`) based on the provided `shortOrderCR`.
- It checks if the provided collateral ratio is valid and within certain limits.
- It calculates the minimum short ERC (`minShortErc`) required based on the collateral ratio.
- It checks if the order size meets minimum requirements.
- It verifies if the sender has enough collateral escrowed to cover the short order.
- It sets up the incoming short order with necessary details.
- It updates the starting ID for bid orders if there's a potential match.
- It checks for recovery mode violation based on the collateral ratio and oracle price.
- Depending on whether the short order price is below the oracle price, it calls different functions (`addShort` or `sellMatchAlgo`) to handle the short order placement.

### `PrimaryLiquidationFacet`:

The `PrimaryLiquidationFacet` contract handles the liquidation of undercollateralized short positions.The `liquidate` is the main function that allows users to liquidate shorts that fall below a certain collateralization ratio. It performs several checks, updates prices, calculates fees, and executes forced bids. The contract includes several internal functions: `_checklowestSell`, `_setLiquidationStruct`, `_performForcedBid`, `_liquidationFeeHandler`, and `_fullorPartialLiquidation` that support the main liquidation logic.

### `BridgeRouterFacet`:

The `BridgeRouterFacet` contract interacts with external bridge contracts to facilitate the `deposit` and `withdrawal` of tokens (referred to as `LST`) and `ETH`, converting them into a representation called `dETH`. Here's a quick summary of its functionality:

- `getDethTotal`: Returns the total `dETH` value in a vault.
- `getBridges`: Returns an array of bridge addresses associated with a vault.
- `deposit`: Accepts `LST` deposits, converts to `dETH`, and updates the vault.
- `depositEth`: Accepts `ETH` deposits, assumes a 1:1 conversion to `dETH`, and updates the vault.
- `withdraw`: Withdraws `LST` from the protocol, potentially applying a fee.
- `withdrawTapp`: Withdraws `LST` from the protocol, callable only by the DAO.
- `maybeUpdateYield`: Conditionally updates the vault's yield rate based on deposit size.
- `_getVault`: Determines the vault and `bridgePointer` based on the bridge address.
- `_ethConversion`: Calculates the amount of `ETH` equivalent to a given amount of `dETH` (decentralized ETH) based on the current value of the assets within a vault. This function is used during the withdrawal process to determine how much `ETH` should be sent to the user in exchange for their `dETH`.

### `ExitShortFacet`:

The `ExitShortFacet` contract facilitates the exiting of short positions in a system. The important functions of the contract are:

- `exitShortWallet`: Allows a user to exit a short position using `ERC` tokens from their wallet, with the option for a partial exit.
- `exitShortErcEscrowed`: Similar to `exitShortWallet`, but uses `ERC` tokens from the user's escrowed balance.
- `exitShort`: Allows a user to exit a short position by placing a bid on the market, with the option for a partial exit and price specification.
- `getCollateralRatioNonPrice`: Internal view function to calculate the collateral ratio of a short position without considering the price.

### `RedemptionFacet`:

The `RedemptionFacet` contract handles the redemption of short positions. Here's a summary of its functionality:

**Redemption Process**: Allows users to propose redemptions of short positions, dispute proposed redemptions, and claim collateral after redemptions are verified.
**Validation**: Includes checks for valid redemption conditions, such as status, debt minimums, and proposer identity.
**Fee Calculation**: Implements a fee mechanism for redemption based on the system's base rate and the amount of debt redeemed.
**Dispute Mechanism**: Provides a way for users to challenge redemption proposals within a certain time frame.
**Collateral Claiming**: Allows users to claim collateral after the dispute period has passed or if a redemption proposal is incorrect.
**State Management**: Uses `SSTORE2` for efficient storage management and updates various state variables such as asset user data, vault user data, and short records.

# Libraries:

### `LibBridgeRouter`:

The library `LibBridgeRouter` manages operations related to bridging assets in the protocol. The library includes functions to:

- Credit and debit a user's account with an asset called `dETH`.
- Assess the amount of `dETH` not covered by bridge credits during `withdrawal`.
- Calculate withdrawal fees based on market premiums/discounts of `rETH` and `stETH` compared to `dETH`.
- Transfer bridge credits between users when an NFT short record is transferred.
- Update user account balances upon `dETH` withdrawal.

The library is designed to work with two types of bridged assets, `rETH` and `stETH`, and includes checks to prevent abuse of the bridging system for arbitrage. It also integrates with `Uniswap` oracles for price data to calculate fees.

### `LibBytes`:

The main function in the library `LibBytes` is a `readProposalData` that decodes an array of `ProposalData` structures from a byte array stored at an `SSTORE2` address. It uses inline assembly for efficient data manipulation. The function can be summarized like that:

- `readProposalData` function takes an `SSTORE2Pointer` and `slateLength`, returning an array of `ProposalData`.
- It reads from `SSTORE2` storage.
- It validates the byte array length to ensure it matches the expected size of `ProposalData` structures.
- It decodes each `ProposalData` entry from the byte array using inline assembly, extracting fields like `shorter`, `shortId`, `CR`, `ercDebtRedeemed`, and `colRedeemed`.
- It constructs an array of `ProposalData` and returns it.

### `LibOracle`:

The library `LibOracle` interacts with price oracles to fetch asset prices and implements circuit breaker logic to handle price discrepancies or oracle failures. Key points of the contract are:

**Oracle Interaction**: It uses `Chainlink's AggregatorV3Interface` to get the latest price data for assets.
**Circuit Breaker Logic**: It contains functions to handle situations where the fetched data may be invalid or when there's a significant price deviation from a protocol-defined price.
**TWAP Fallback**: In case of issues with `Chainlink`, it falls back to a Time-Weighted Average Price (TWAP) fetched from a Uniswap.
**Price and Time Storage**: It uses an `AppStorage` pattern to store and retrieve the latest price and timestamp for assets.

### `LibOrders`:

The library `LibOrders` handles trading, specifically focusing on order matching and management for assets. It includes functions for:

- Time calculations based on a constant starting time.
- Order creation, cancellation, and matching for bids, asks, and shorts.
- Price conversions and share calculations for matched orders.
- Order book maintenance, including adding and updating orders.
- Oracle price updates and adjustments based on market conditions.
- Handling of short positions, including record updates and collateral management.
- Discount handling for price deviations from oracle prices.

### `LibSRUtil`:

The library `LibSRUtil` involves short selling, asset management, and yield distribution. `LibSRUtil` contains helper functions for managing short records and interacting with various data structures and contracts. The functions of the library are:

- `disburseCollateral`: Manages collateral distribution when a short position is closed or modified, including yield distribution based on a delay condition.
- `checkCancelShortOrder`: Checks if a short order can be canceled based on its status, order details, and minimum `ERC` debt requirements.
- `checkShortMinErc`: Ensures that remaining short orders and records meet the minimum `ERC` debt requirement to avoid dust amounts.
- `checkRecoveryModeViolation`: Checks if the short record's collateralization ratio violates the recovery mode conditions of the market.
- `transferShortRecord`: Transfers a short record from one user to another, handling the cancellation of partially filled orders and updating ownership in the NFT mapping.
- `updateErcDebt`: Updates the `ERC` debt of a short record based on the current debt rate.

### `UniswapOracleLibrary`:

The library `UniswapOracleLibrary` is designed to work with `Uniswap V3` pools. It provides functions to calculate token exchange amounts based on pool prices and to estimate the time-weighted average price (TWAP). The functionality of the library is:

- `getQuoteAtTick`: Calculates the amount of `quoteToken` received for a given `baseAmount` of `baseToken` at a specific tick.
- `estimateTWAP`: Estimates the TWAP starting from `secondsAgo` until the current block timestamp for a given `amountIn` of `baseToken`.
- Uses `TickMath` library to compute square root price from tick value.
- Uses `PRBMathHelper` for precision-safe math operations.
- Checks for valid `secondsAgo` input to prevent invalid TWAP calculations.
- Handles potential rounding errors when computing the average tick.


# Security concerns and Recommendations:

During the described auditing process I found some petential security issues:

- In `BridgeRouterFacet` is used type casting from uint256 to uint88 in several places. It is recommended this casts to be used with caution, because they can lead to unintended truncation of values.
- The `LibBytes` library uses bitwise operations which is optimized for gas efficiency, but when the `colRedeemed` variable is retrived, there is a mistake in the bitwise operation. It is used `add` instead of `and`.
- The TWAP calculation in `UniswapOracleLibrary` can be susceptible to manipulation. For example, in low-liquidity pools, large trades can cause significant price slippage, affecting the TWAP. Also, attackers can use flash loans to acquire large amounts of assets temporarily to move the price within a short period. Therefore, additional checks and measures like using longer time periods for TWAP calculations or combining multiple oracles can be used.
- In `LibOrders::increasesSharesOnMatch` there is a multiplication if a result of division. That leads to rounding issues due to the way that Solidity performs division.
- It is recommended to consider each part of the code when subtraction is made. In some places there is a posibility of reverting due to the underflow.
- There are places where the comments in the code and the implementation of the code are different. That leads to confusion when auditing.
- In the `RedemptionFacet::proposeRedemtion` function there are variables that are assigned twice. This is not neccessary and leads to gas costs.
- In `RedemptionFacet` there are some functions that don't check one of the input parameter (this parameter is index in the array). If these parameters are out of bound, the functions will revert.
- There is an unlimited approval of `stETH` tokens in `BridgeSteth` contract that can lead to loss of all tokens of `BridgeSteth`. It is recommended to approve only the required amount of tokens before a given transaction and after the transaction to clear the approval.

These and others security issues are briefly described in my reports.

### Time spent:
50 hours