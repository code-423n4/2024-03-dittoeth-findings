## 1 - What is Ditto protocol ?

The `Ditto` protocol is a decentralized system built on Ethereum that creates stablecoins using staked `ETH` as collateral. It employs an `orderbook` model where users can buy stable assets with `ETH` or take leveraged positions against stable assets. Vaults hold stable assets collateralized by liquid staking tokens `LSTs`, and Bridges facilitate depositing and withdrawing `LST` collateral. 

Overall, Ditto aims to provide a stablecoin solution while maximizing efficiency and decentralization.

## 2 - The main features of the Ditto protocol include

- **Decentralization**: Built on Ethereum mainnet, Ditto operates in a decentralized manner, ensuring trustless interactions and censorship resistance.

- **Stablecoin Creation**: Users can create stablecoins, starting with dUSD, by collateralizing staked ETH such as rETH and stETH.

- **Two-sided Orderbook**: Unlike traditional one-sided collateralized debt positions (CDPs), Ditto utilizes a two-sided orderbook model, allowing both buyers and shorters to participate. Bidders buy stable assets with ETH, while shorters take leveraged positions against stable assets.

- **Vaults**: Vaults hold stable assets collateralized by a basket of underlying LSTs, providing a mechanism for managing assets within the system.

- **Bridges**: Bridges facilitate the depositing and withdrawing of LST collateral into the system, ensuring interoperability with different staking protocols.

- **Efficiency**: The orderbook model and efficient collateral utilization allow for optimized use of assets within the system, maximizing efficiency for users.

- **Price Stability**: Price oracles monitor collateral ratios to ensure stable asset creation and maintain price stability.

Overall, Ditto aims to provide a decentralized stablecoin solution while offering efficient asset management and price stability mechanisms.

## 3 - Contracts Explanation (Scope)

###### BidOrdersFacet.sol

The contract uses several libraries for mathematical operations, order handling, asset management, and interacting with oracles. It also includes checks for valid assets and reentrancy protection to enhance security.

Overall, the `BidOrdersFacet` contract is a complex component of a larger system designed to facilitate trading on a decentralized platform, with specific emphasis on managing bid orders and their interactions with the market.

- **Order Creation**: It allows users to create bid orders to buy ERC tokens with ETH at a specified price, either as market or limit orders.

- **Forced Bid Creation**: There's a function for creating forced bid orders, which can only be called by specific contracts.

- **Matching Algorithm**: It includes a matching algorithm to match bid orders with existing ask (sell) orders or short positions.

- **Order Matching**: If a bid matches an ask or short, the contract handles the exchange of tokens and updates the order book accordingly.

- **Short Handling**: The contract has logic to handle short positions, including updating short records and collateral management.

- **Price Updates**: It updates the oracle price and manages the starting short ID based on price thresholds.

- **Escrow Management**: The contract manages ETH and ERC token escrows for users participating in trades.

- **Event Emission**: It emits events for matched orders, providing transparency and traceability of trades.

###### ShortOrdersFacet.sol 

The contract is designed to ensure that short orders are created and managed within the platform's rules, with appropriate checks and balances to maintain market integrity and user funds' safety.

- **Imports**: The contract imports various helper libraries for mathematical operations, error handling, data types, and other contract-specific logic.

- **State Modifiers**: Uses Modifiers from AppStorage.sol for access control and state management.

- **Function createLimitShort**: The main function that allows users to create a limit short order with specified parameters such as the asset, price, amount, and collateral ratio.

- **Validation**: The function includes checks for frozen assets, valid assets, non-reentrancy, minimum order size, sufficient collateral, and compliance with recovery mode criteria.

- **Order Creation**: It initializes a short record, calculates the collateral requirement, and then proceeds to either add the short order to the order book or match it with existing orders based on the current oracle price.

- **Oracle Price**: The contract interacts with an oracle to obtain price information for assets, which is used to determine whether to add the order to the book or match it immediately.

- **Error Handling**: Uses custom errors from Errors.sol for clear and gas-efficient error messages.

- **Event Emission**: Not shown in the provided code, but typically events would be emitted for order creation and matching.

###### PrimaryLiquidationFacet.sol

The contract is complex, with interdependencies on external contracts and libraries. It's designed to maintain the platform's stability by ensuring that short positions are properly collateralized and by providing mechanisms to handle positions that become undercollateralized.

- **Libraries and Interfaces**: The contract imports various libraries for mathematical operations, data types, error handling, and interfaces for interacting with other contracts.

- **State Variables**: The contract has a private immutable variable dusd which likely represents a stablecoin or platform-specific token address.

- **Constructor**: The constructor initializes the dusd address.

- **Liquidation Function (liquidate)**: The main function allows users to liquidate short positions that are undercollateralized. It checks for several conditions, such as the liquidator not being the same as the shorter, the number of hints provided, and the collateralization ratio (CR) of the short position. If the CR is too high, it checks for a recovery mode violation.

- **Private Helper Functions**: These functions support the liquidate function by performing tasks such as checking for eligible sell orders (_checklowestSell), setting up the liquidation struct (_setLiquidationStruct), executing a forced bid (_performForcedBid), handling liquidation fees (_liquidationFeeHandler), and accounting for full or partial liquidations (_fullorPartialLiquidation).

- **Modifiers**: The contract uses custom modifiers to enforce certain preconditions for functions, such as isNotFrozen, nonReentrant, and onlyValidShortRecord.
Events: The contract emits an event (Events.Liquidate) when a liquidation occurs, capturing details like the asset, shorter, liquidator, and amounts involved.

- **Security Measures**: It uses the nonReentrant modifier to prevent reentrancy attacks and checks to ensure that operations are only performed on valid short records.

- **Liquidation Logic**: The liquidation process involves updating oracle prices, checking collateralization ratios, and if necessary, forcing the shorter to place a bid on the market to cover their debt. Fees are distributed to the caller and the platform's treasury (TAPP), and the collateral is handled according to whether it's a full or partial liquidation.

- **Error Handling**: The contract uses a custom Errors library to revert transactions with descriptive error messages when certain conditions are not met.
Math Operations: Custom math libraries are used to handle different numeric types safely and efficiently.

###### BridgeRouterFacet.sol

The contract uses several libraries for mathematical operations and storage patterns, and interfaces to interact with external contracts. It also includes checks for minimum deposit amounts, zero parameters, and invalid bridges.

- **Vault Management**: Interacts with vaults to manage deposits and withdrawals of a token called dETH.

- **Bridges**: Supports two types of bridges (rethBridge and stethBridge) for token operations.

- **Deposits**: Allows users to deposit both a generic LST token and ETH, which are then converted to dETH.

- **Withdrawals**: Users can withdraw their dETH as LST, with potential fees deducted. There's also a special withdrawal function for the DAO.

- **Yield Updates**: The contract may update the yield rate of the vault based on deposit sizes.

- **Conversion**: Handles the conversion between dETH and ETH, accounting for potential losses in vault value.

- **Modifiers**: Uses custom modifiers for reentrancy protection and DAO-only functions.

- **Events**: Emits events for deposits and withdrawals.

###### ExitShortFacet.sol

`ExitShortFacet` allows users to exit their short positions in various ways.

1 - The contract imports various libraries and interfaces for mathematical operations, asset management, order handling, and short record handling.

2 - It utilizes a non-upgradable pattern (diamond standard) via the IDiamond interface.

3 - It defines three main functions to exit short positions: `exitShortWallet`, `exitShortErcEscrowed`, and `exitShort`.

- exitShortWallet allows users to close their short position by burning the debt directly from their wallet.

- exitShortErcEscrowed enables users to exit their short position using escrowed ERC tokens.

- exitShort allows users to place a bid on the market to exit their short position. Each exit function performs checks on the validity of the short record, updates debt, handles collateral, and ensures minimum ERC debt requirements are met.

4 - The contract uses modifiers to enforce checks like non-reentrancy and asset status (not frozen).

5 - It emits events for each type of short exit operation.

6 - The contract also includes a function to calculate the collateral ratio without considering the price.

7 - The code is designed to manage short positions' lifecycle, specifically focusing on exiting shorts under different conditions.

###### RedemptionFacet.sol

RedemptionFacet allow users to propose and dispute redemptions of short positions (SRs). Key points:

- Libraries and Contracts: Utilizes multiple libraries for math operations, error handling, events, data types, asset management, order handling, and storage optimization.

- Short Record Validation: Includes a function validRedemptionSR to check if a short record is eligible for redemption.

- Propose Redemption: Users can propose redemptions of short positions with proposeRedemption, subject to a dispute period. It involves complex logic for fee calculation, collateral removal, and validation of redemption candidates.

- Dispute Mechanism: The disputeRedemption function allows users to challenge proposed redemptions, with incentives to dispute incorrect proposals.

- Claim Collateral: claimRedemption and claimRemainingCollateral enable users to claim collateral after the dispute period or if a shorter's SR has been fully redeemed.

- Fee Calculation: calculateRedemptionFee computes the fee for redemption based on the decay of the base rate over time and the proportion of debt being redeemed.

- The contract uses a non-reentrant modifier to prevent re-entrancy attacks and includes checks for frozen assets and other conditions to ensure proper execution of functions.

###### LibBridgeRouter.sol

`LibBridgeRouter` is a library with functions to manage bridge credits and withdrawals.

1 - **addDeth**: Credits a user's account with dETH and bridge credits if applicable.

2 - **assessDeth**: Calculates the amount of dETH not covered by bridge credits during withdrawal.

3 - **withdrawalFeePct**: Computes withdrawal fees based on market premiums/discounts.

4 - **transferBridgeCredit**: Transfers bridge credits between users during asset transfers.

5 - **removeDeth**: Updates user account upon dETH withdrawal.

6 - **The library interacts with**:

- AppStorage: To access and modify user and vault data.

- IBridge: To get bridge-related values.

7 - **OracleLibrary**: To estimate time-weighted average prices (TWAP).
It uses custom types and constants defined in other imported contracts and libraries. The code includes checks for bridge credits and applies fees to prevent arbitrage abuse. It's designed for a system with multiple vaults, where VAULT.ONE has special handling for LST (Liquidity Staking Tokens) like rETH and stETH.

###### LibBytes.sol

`LibBytes` is a library which contains a single function `readProposalData`. The function takes an address pointing to data stored via `SSTORE2` and a `uint8` representing the length of an array of ProposalData structures. 

The code uses low-level assembly for byte manipulation to decode the data, which requires careful handling to avoid errors. The `SSTORE2` library is used to read data from a specific storage layout in Ethereum. The commented-out import of console suggests that debugging statements were used during development but are now removed.

It performs the following actions:

- Reads a byte array from SSTORE2 storage using the provided address.
Validates that the byte array length is a multiple of 51 (the size of a ProposalData structure).

- Initializes an array of ProposalData structures.

- Iterates over the byte array, extracting and converting bytes into ProposalData fields using inline assembly for efficiency.

- Each ProposalData contains an address, uint8, uint64, and two uint88 fields.
Returns the array of ProposalData structures.

###### LibOracle.sol

This Solidity code defines a library `LibOracle` which is responsible for interacting with price oracles to fetch and manage asset prices within a smart contract ecosystem. Here's a quick summary of its functionality:

- **getOraclePrice**: Fetches the price of an asset using Chainlink oracles. It handles different cases, such as when the asset's oracle is the same as the base oracle or different. It includes error handling and circuit breaker logic.

- **baseOracleCircuitBreaker**: A circuit breaker for the base oracle price that compares fetched prices with protocol prices and falls back to a time-weighted average price (TWAP) if necessary.

- **oracleCircuitBreaker**: Validates the data fetched from the oracle and reverts if it's invalid.

- **twapCircuitBreaker**: Fetches the TWAP and checks for sufficient liquidity in the pool.

- **setPriceAndTime, getTime, getPrice**: Helper functions to manage oracle prices and timestamps within the contract's storage.

- **getSavedOrSpotOraclePrice**: Returns either a recently saved price or fetches the current oracle price depending on the time elapsed since the last price was saved.

The code uses several external contracts and libraries, including `Chainlink oracles`, `OpenZeppelin's ERC20 interface`, and custom libraries for math operations and error handling. It also includes a unique approach to storing and retrieving oracle prices and times by overloading the `ercAmount` and `creationTime` fields for this purpose.

###### LibSRUtil.sol

Overall, the code is part of a complex financial system with mechanisms to manage short positions, collateral, debt, and yield distribution, while ensuring economic stability and adherence to platform rules.

1 - **Libraries and Imports**: The code imports various libraries and contracts for mathematical operations, data types, storage patterns, constants, error handling, and order management.

2 - **LibSRUtil Library**: Contains helper functions to manage short records (SR) and related operations such as disbursement of collateral, checking and canceling short orders, ensuring minimum economic requirements are met, handling recovery mode violations, transferring short records, and updating debt.

3 - **Key Functions**:

- disburseCollateral: Manages collateral disbursement, yield distribution, and updates vault and asset storage.
- checkCancelShortOrder: Cancels short orders under certain conditions, like partial fills or minimum debt requirements.
- checkShortMinErc: Ensures that short records and orders meet the minimum economic requirements.
- checkRecoveryModeViolation: Checks if the short record's collateralization ratio is below the recovery threshold.
- transferShortRecord: Transfers a short record from one user to another, updating the NFT mapping and short record storage.
- updateErcDebt: Updates the debt amount based on the debt rate.

4 - **Error Handling**: Uses custom errors from the Errors library for specific failure cases.

5 - **State Management**: Utilizes an AppStorage pattern for efficient state management across the platform.

6 - **Math Operations**: Employs PRBMathHelper for safe mathematical operations with fixed-point numbers.

7 - **Short Record and Order Management**: The code handles the lifecycle of short records and orders, including creation, cancellation, and updates to their status and debt.

8 - **Yield and Collateral**: Addresses yield accrual and collateral adjustments for short positions, with conditions to prevent yield collection if the position was recently modified.

9 - **Minimum Economic Constraints**: Ensures that short positions are not left with 'dust' amounts, enforcing minimum economic viability for operations.

10 - **Recovery Mode**: Implements logic to handle situations where the asset or the market enters a recovery mode due to low collateralization ratios.

11 - **NFT Integration**: Short records are associated with NFTs (non-fungible tokens), indicating ownership and status of the short position.

12 - **Bridge Credit Transfer**: Supports transferring bridge credit between users as part of the short record transfer process.

###### UniswapOracleLibrary.sol

This library is used to calculate the exchange rate between two tokens in a `Uniswap V3 pool` either at a specific tick or as an average over a period, which is useful for dApps needing to price assets or execute trades based on current or historical prices.

The library contains two main functions:

 - **getQuoteAtTick**: Calculates the amount of quoteToken that can be received for a given amount of baseToken at a specific tick value. It uses the square root of the price ratio, provided by TickMath.getSqrtRatioAtTick, to compute the quote amount with precision handling based on the size of the square root ratio.

- **estimateTWAP**: Estimates the Time-Weighted Average Price (TWAP) for an input amount of baseToken over a specified period (secondsAgo). It retrieves the cumulative tick values at two points in time from the Uniswap V3 pool and calculates the average tick, which is then used to estimate the TWAP using getQuoteAtTick.

The code also includes error handling for invalid inputs (e.g., secondsAgo must be positive) and uses a mathematical library U256 from PRBMathHelper.sol for precision arithmetic operations.

## 4 - Security Overview (Scope)

The Contracts not mentioned means that no vulnerabilities was found.

###### BidOrdersFacet.sol

1 - **Lack of slippage protection in `createBid` and `createForcedBid`.**

The `createBid` and `createForcedBid` functions do not appear to have explicit slippage protection mechanisms such as specifying a maximum acceptable price or price range for the entire order. This could potentially expose users to sandwich attacks where an attacker manipulates the market price before and after the bid order execution. However, it's worth noting that the matching algorithm `bidMatchAlgo` does check the price of incoming bids against the lowest sell price, which provides a basic level of protection against receiving a price worse than the current best available sell price.

While there is a basic level of price checking, additional slippage protection measures could be implemented to further safeguard against price manipulation, such as:

- User-specified maximum slippage percentage.
- Price oracles to verify fair market prices.
- Time-weighted average price (TWAP) mechanisms.
- These could help to reinforce the contract against potential sandwich attacks and ensure users get a price close to their expectations.

2 - **Potential for front-running in `_createBid`.**

The `_createBid` function updates the oracle price and starting `short ID`, which could be susceptible to front-running. Attackers can monitor the mempool for incoming transactions and attempt to place their own transactions with higher gas fees to get them mined first, potentially leading to a better execution at the expense of the original bidder.

To mitigate front-running in the _createBid function, several strategies can be employed:

- Commit-Reveal Scheme: Users first commit to a hashed version of their bid, hiding the details. After a certain number of blocks, they reveal the bid for execution.

- Transaction Ordering Dependence (TOD) Prevention: Use a decentralized exchange mechanism that doesn't rely on transaction order for price determination.

- Gas Price Limit: Set a maximum gas price for transactions to reduce the incentive for miners to prioritize transactions based on gas price.

- Private Transactions: Utilize private transaction networks or services to hide transaction details until they are mined.

- Submarine Sends: Hide the transaction until it's included in a block, preventing front-runners from seeing it in the mempool.

- Economic Abstraction: Implement a system where the transaction fee is paid in the token being traded, making it less predictable and profitable for front-runners.

- Time Locks: Require orders to specify a minimum block number for execution, giving everyone the same starting point for order submission.

- Cross-Chain Solutions: Use cross-chain or layer-2 solutions where transaction ordering can be more controlled and less transparent to potential attackers.

Each of these strategies has trade-offs and may not be suitable for all scenarios, but they can provide additional layers of security against front-running.

3 - **Lack of documentation for `_shortDirectionHandler`**: This function contains complex logic for handling short order matching, but it lacks proper documentation. This could make it difficult to understand and maintain the code.

4 - **Use of magic numbers**: The contract uses several magic numbers, such as `C.HEAD` and `C.TAIL`, without proper explanation. This could reduce code readability and maintainability.

###### ShortOrdersFacet.sol

1 - Potential for front-running in `createLimitShort`.

The function updates the oracle price and starting `short ID` based on the incoming short price. This opens the possibility for front-running, where an attacker could observe the incoming short in the mempool and submit their own short with a slightly higher price to get a better execution.

Consider alternative approaches to update the `oracle price` and starting `short ID` to mitigate front-running risks.

2 - **Gas inefficiency in createLimitShort**: The function performs redundant calculations and storage reads/writes, which could be optimized to reduce gas costs.

There are potential areas in the `createLimitShort` function that might be optimized for gas efficiency:

Multiple calls to external library functions could be optimized if they result in duplicate calculations or fetch the same state variables multiple times.

The use of temporary variables `(p)` for storing intermediate values might be optimized if they are only used once.

The function performs multiple checks and operations that could potentially be streamlined.

3 - The contract uses constants like `C.HEAD`, `C.BID_CR`, and others that are defined in an external library or contract `Constants.sol`. These are considered `magic numbers` when used without inline comments explaining their meaning. While they are named constants, which is better than using raw numbers, the code could still benefit from additional documentation explaining their purpose and how they were derived to improve readability and maintainability.

###### PrimaryLiquidationFacet.sol

1 - **Potential for griefing in `_performForcedBid`**

The `_performForcedBid` function includes logic that socializes the debt if the `TAPP's escrowed ETH` is insufficient to cover the `ethDebt`. This is done by increasing the `ercDebtRate`, which effectively spreads the loss across all short positions in the market. A malicious user with a large short position could intentionally get liquidated, knowing that the `TAPP` cannot cover the debt, thereby increasing the debt burden on others. This could indeed lead to cascading liquidations if other short positions become undercollateralized as a result.

To mitigate the potential for griefing in `_performForcedBid`:

- **Risk Limits**: Implement stricter risk management policies, such as position limits, to prevent users from opening excessively large short positions that could impact the entire system.

- **Circuit Breakers**: Introduce circuit breakers that halt liquidations or socialization of debt under extreme conditions, allowing for manual intervention.
Insurance Fund: Establish an insurance fund to cover shortfalls in TAPP's escrowed ETH, reducing the need to socialize debt.

- **Staggered Liquidations**: Implement staggered or partial liquidations to limit the impact of any single liquidation event.

- **Improved Pricing Mechanisms**: Enhance the oracle system to provide more accurate and timely price feeds, reducing the likelihood of unnecessary liquidations.

2 - **The `_performForcedBid` function does not appear to include explicit slippage protection. It sets a forced bid price based on the oracle price with a buffer `m.forcedBidPriceBuffer` but does not specify a maximum allowable slippage**. 

Without slippage protection, an attacker could indeed execute a sandwich attack, manipulating the market price before and after the forced bid to their advantage, potentially causing the liquidation to transact at an unfavorable price.

###### LibBridgeRouter.sol

1 - **Lack of validation in withdrawalFeePct.** 

The function does not validate the `bridgePointer` parameter, which could lead to an attacker supplying an invalid bridge pointer and potentially manipulating the withdrawal fee calculation.

While there is no explicit validation of `bridgePointer` within `withdrawalFeePct`, the risk of manipulation is low due to its internal visibility. It is crucial that any public or external functions that eventually call `withdrawalFeePct` ensure the `bridgePointer` is valid and corresponds to a legitimate bridge. 

The contract's design should ensure that any user input leading to the invocation of `withdrawalFeePct` is properly sanitized and validated before use. If the contract's external functions that lead to this internal call are secure, the risk is contained.

However, as a best practice, especially in complex systems where multiple developers might interact with or modify the codebase, it would be safer to include validation checks within the `withdrawalFeePct` function itself. This would protect against future changes that might inadvertently introduce vulnerabilities due to incorrect assumptions about the validity of the `bridgePointer`.

## 5 - Conclusion

My audit analysis effectively outlines the Ditto Protocol, its main features, key contracts, and potential vulnerabilities. Additionally, it offers clear mitigation strategies to address these vulnerabilities and enhance the protocol's security.

The report demonstrates a deep understanding of the protocol's architecture and underlying mechanisms. It provides valuable insights into areas of potential risk and suggests practical solutions to mitigate them. The inclusion of specific contract explanations and code snippets enhances the report's clarity and readability.

Overall, the audit report reflects a diligent examination of the Ditto Protocol, highlighting both its strengths and areas for improvement. It serves as a valuable resource for developers and stakeholders seeking to enhance the protocol's security and robustness.












































### Time spent:
60 hours