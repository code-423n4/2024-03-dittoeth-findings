# Analysis - DittoETH Contest

![DittoETH](https://code4rena.com/_next/image?url=https%3A%2F%2Fstorage.googleapis.com%2Fcdn-c4-uploads-v0%2Fuploads%2FXcKzZ6eSLH9.0&w=256&q=75)

## Description overview of `DittoETH` Contest

**🤔 What is DittoETH?**

DittoETH is a decentralized stablecoin protocol with an order book design for supercharged staking yield. That pegged asset issuance protocol built on Ethereum. It allows users to create and trade synthetic assets that track the price of real-world assets, such as fiat currencies, cryptocurrencies, and commodities.

The Ditto protocol is a new decentralized stable asset protocol for Ethereum mainnet. It takes in overcollateralized liquid staked ETH (rETH, stETH) to create stablecoins using a gas optimized orderbook (starting with a USD stablecoin, dUSD).

On the orderbook, bidders and shorters bring ETH, askers can sell their dUSD. Bidders get the dUSD, shorters get the bidders collateral and a ShortRecord to manage their debt position (similar to a CDP). Shorters get the collateral of the position (and thus the LST yield), with the bidder getting the stable asset, rather than a CDP where the user also gets the asset.

**Key Features**

- **Collateralized by Staked ETH:** Pegged assets are backed by staked ETH (LST), which provides collateral and ensures protocol solvency.
- **Orderbook Model:** DittoETH uses an orderbook to match buyers and sellers of pegged assets, ensuring liquidity and price stability.
- **Shorter Incentives:** Shorters earn yield in the form of dETH, which is the staked ETH provided by long traders. This incentivizes users to maintain high collateralization ratios.

**How It Works**

**Pegged Asset Issuance:**

- Users can mint pegged assets by providing collateral in the form of staked ETH.
- Shorters take their staked ETH and match on the orderbook with long users who desire the pegged asset.
- The minted pegged asset is backed by the collateralized staked ETH.

**Managing Debt:**

- Shorters incur debt when they facilitate the minting of pegged assets.
- To exit their position, shorters must buy back the debt by acquiring and burning the pegged asset.
- Shorters can adjust their collateralization ratio by adding or removing excess collateral.

**Liquidation:**

- If a shorter's collateralization ratio falls below a certain threshold, their position can be liquidated.
- Liquidators can purchase the pegged asset at a discount and receive a portion of the collateral.

**Treasury Asset Protection Pool (TAPP):**

- The TAPP is a stability fund that supports the protocol in the event of under-collateralized positions.
- It is funded by penalties from liquidations and a small tithe from ETH rewards.

**Orderbook:**

- DittoETH maintains an orderbook for each market, allowing users to place buy or sell orders.
- Orders are filled immediately if there is a matching order on the orderbook.

**Yield Mechanism:**

- Shorters earn yield in the form of dETH, which is the staked ETH provided by long traders.
- The yield is distributed periodically based on the amount of collateralized ETH.

**Benefits**

- **Censorship Resistance:** DittoETH is decentralized and operates on the Ethereum blockchain, ensuring censorship resistance.
- **Neutrality:** The protocol is open and accessible to all users, regardless of their location or affiliation.
- **Collateral Management:** Users can manage their collateralization ratios and earn yield on their staked ETH.
- **Price Stability:** The orderbook model and high collateralization requirements help maintain price stability for pegged assets.

## System Overview

## 1. Scope

### facets/BidOrdersFacet.sol

The `BidOrdersFacet` contract is part of a Diamond storage pattern implementation for a DittoEth. It handles the creation and matching of `bid orders` on a specific market.

- **BidOrdersFacet Contract Functions**

  - **createBid**

    - **Purpose:** Creates a bid order on a specified market.
    - **Parameters:**
      - `asset`: Address of the market.
      - `price`: Unit price in ETH for the ERC token.
      - `ercAmount`: Amount of ERC token to buy.
      - `isMarketOrder`: Boolean indicating whether the order is a limit or market order.
      - `orderHintArray`: Array of hint IDs for gas-optimized sorted placement on the market.
      - `shortHintArray`: Array of hint IDs for gas-optimized short matching above the oracle price.
    - **Returns:**
      - `ethFilled`: Amount of ETH filled.
      - `ercAmountLeft`: Amount of ERC token not matched.

  - **createForcedBid**

    - **Purpose:** Creates a bid order for exiting a short position, only callable by specific contracts.
    - **Parameters:**
      - `sender`: Address of the caller (only for exiting a short).
      - `asset`: Address of the market.
      - `price`: Unit price in ETH for the ERC token.
      - `ercAmount`: Amount of ERC token to buy.
      - `shortHintArray`: Array of hint IDs for gas-optimized short matching above the oracle price.
    - **Returns:**
      - `ethFilled`: Amount of ETH filled.
      - `ercAmountLeft`: Amount of ERC token not matched.

  - **bidMatchAlgo**

    - **Purpose:** The matching algorithm for bid orders.
    - **Parameters:**
      - `asset`: Address of the market.
      - `incomingBid`: Active bid order.
      - `orderHintArray`: Array of hint IDs for gas-optimized sorted placement on the market.
      - `b`: Memory struct used throughout the bid match algorithm.
    - **Returns:**
      - `ethFilled`: Amount of ETH filled.
      - `ercAmountLeft`: Amount of ERC token not matched.

  - **matchlowestSell**

    - **Purpose:** Settles the lowest ask and updates the incoming bid.
    - **Parameters:**
      - `asset`: Address of the market.
      - `lowestSell`: Lowest sell order (ask or short) on the market.
      - `incomingBid`: Active bid order.
      - `matchTotal`: Struct of the running matched totals.

  - **matchIncomingBid**

    - **Purpose:** Final settlement of the incoming bid.
    - **Parameters:**
      - `asset`: Address of the market.
      - `incomingBid`: Active bid order.
      - `matchTotal`: Struct of the running matched totals.
      - `b`: Memory struct used throughout the bid match algorithm.
    - **Returns:**
      - `ethFilled`: Amount of ETH filled.
      - `ercAmountLeft`: Amount of ERC token not matched.

  - **`_getLowestSell`**

    - **Purpose:** Returns the lowest sell order (ask or short) on the market.
    - **Parameters:**
    - `asset`: Address of the market.
    - `b`: Memory struct used throughout the bid match algorithm.
    - **Returns:**
    - `lowestSell`: Lowest sell order.

  - **`_shortDirectionHandler`**

    - **Purpose:** Handles the direction of the short order matching.
    - **Parameters:**
      - `asset`: Address of the market.
      - `lowestSell`: Lowest sell order (ask or short).
      - `incomingBid`: Active bid order.
      - `b`: Memory struct used throughout the bid match algorithm.

### facets/ShortOrdersFacet.sol

The `ShortOrdersFacet` contract handles the creation and matching of `short orders` on a specific market.

- **ShortOrdersFacet Contract Functions**

- **createLimitShort**

  - **Purpose:** Creates a limit short order in the market system.
  - **Parameters:**

    - `asset`: Address of the market.
    - `price`: Unit price in ETH for ERC sold.
    - `ercAmount`: Amount of ERC minted and sold.
    - `orderHintArray`: Array of hint IDs for gas-optimized sorted placement on the market.
    - `shortHintArray`: Array of hint ID for gas-optimized short matching above the oracle price.
    - `shortOrderCR`: Initial Collateral Ratio for a short order, between min/max, converted to uint8.

  - **Implementation Details**

    - **Collateral Ratio Check:** Ensures that the specified `shortOrderCR` is within the allowed range and that the user has enough ETH escrowed to cover the minting of ERC.
    - **Short Record Creation:** Creates an empty short record for the order.
    - **Order Creation:** Initializes the `incomingShort` order with the provided parameters.
    - **Matching:**
      - If the `incomingShort` price is below the oracle price, it is added to the market as a limit short order.
      - If the `incomingShort` price is above or equal to the oracle price, it is immediately matched against existing buy orders using the `sellMatchAlgo` function.
    - **Oracle Price Update:** If the `incomingShort` price is within 0.5% of the oracle price, the starting short ID is updated to optimize matching.
    - **Recovery Mode Check:** Verifies that the `shortOrderCR` does not violate the recovery mode threshold.

### facets/PrimaryLiquidationFacet.sol

This contract, `PrimaryLiquidationFacet` handles the primary liquidation of short positions on a specific market.

- **PrimaryLiquidationFacet Contract Functions**

  - **liquidate**

  - **Purpose:** Liquidates a short position by forcing the shorter to place a bid on the market.
  - **Parameters:**
    - `asset`: Address of the market.
    - `shorter`: Address of the shorter getting liquidated.
    - `id`: Id of the short getting liquidated.
    - `shortHintArray`: Array of hint IDs for gas-optimized matching against shorts.
    - `shortOrderId`: Id of the short order being liquidated.
  - **Returns:**

    - `gasFee`: Estimated cost of gas for the forced bid.
    - `ethFilled`: Amount of ETH filled in the forced bid.

  - **Implementation Details**

    - **Liquidation Criteria:** Ensures that the shorter's Collateral Ratio (CR) is below the liquidation threshold or that the market is in recovery mode and the CR is too low.
    - **Forced Bid:** Creates a forced bid on the market at a price above the oracle price, ensuring that it can be filled.
    - **Fee Distribution:** Distributes liquidation fees to the caller and the TAPP (Treasury and Protocol Protection).
    - **Full or Partial Liquidation:** Handles accounting for both full and partial liquidations, including disbursement of collateral and deletion or modification of short records.
    - **Short Minimum ERC Check:** Verifies that the shorter's remaining ERC debt is above the minimum threshold after liquidation.

  - **Internal Functions**

    - **`_setLiquidationStruct`:** Initializes a memory struct with data about the liquidation.
    - **`_checklowestSell`:** Reverts if there are no eligible sell orders or if the lowest sell price is too high.
    - **`_performForcedBid`:** Sets up and executes the forced bid, handling gas costs and potential socialization of debt.
    - **`_liquidationFeeHandler`:** Distributes liquidation fees to the caller and the TAPP.
    - **`_fullorPartialLiquidation`:** Handles accounting for full or partial liquidations, including disbursement of collateral and modification of short records.

### facets/BridgeRouterFacet.sol

The `BridgeRouterFacet` handles the bridging of assets between the protocol and external liquidity providers.

- **BridgeRouterFacet Contract Functions**

  - **getDethTotal**

    - **Purpose:** Returns the present value of all bridges within a given vault.

  - **getBridges**

    - **Purpose:** Returns an array of the bridge addresses of a vault.

  - **deposit**

    - **Purpose:** Deposits Liquid Staked Token (LST) into the protocol.
    - **Parameters:**
      - `bridge`: Address of the bridge corresponding to the LST being deposited.
      - `amount`: Quantity of LST to deposit.

  - **depositEth**

    - **Purpose:** Deposits ETH into the protocol.
    - **Parameters:**
      - `bridge`: Address of the bridge corresponding to the LST being deposited (via ETH exchange).

  - **withdraw**

    - **Purpose:** Withdraws LST out of the protocol.
    - **Parameters:**
      - `bridge`: Address of the bridge corresponding to the LST being withdrawn.
      - `dethAmount`: Quantity of dETH to withdraw.

  - **withdrawTapp**

    - **Purpose:** Withdraws LST out of the protocol, only callable by the DAO.
    - **Parameters:**
      - `bridge`: Address of the bridge corresponding to the LST being withdrawn.
      - `dethAmount`: Quantity of dETH to withdraw.

  - **Implementation Details**

    - **Bridge Accounting:** Tracks the total dETH value of each bridge within a vault.
    - **Deposit and Withdrawal:** Handles deposits and withdrawals of LST and ETH, updating the vault's dETH balance and issuing withdrawal credits if applicable.
    - **Yield Updates:** Automatically updates the vault yield rate when bridge deposits are sufficiently large.
    - **Loss Accounting:** Accounts for situations when the vault experiences loss in value due to negative yield on bridges.
    - **Bridge Validation:** Checks for invalid bridge inputs and ensures that bridges are associated with the correct vaults.

### facets/ExitShortFacet.sol

`ExitShortFacet` handles the exit of short positions on the platform.

- **ExitShortFacet Contract Functions**

  - **exitShortWallet**

    - **Purpose:** Exits a short position using the shorter's ERC tokens in their wallet.
    - **Parameters:**
      - `asset`: Address of the market being shorted.
      - `id`: ID of the short record.
      - `buybackAmount`: Amount of ERC tokens to buy back.

  - **exitShortErcEscrowed**

    - **Purpose:** Exits a short position using the shorter's ERC tokens held in escrow.
    - **Parameters:**
      - `asset`: Address of the market being shorted.
      - `id`: ID of the short record.
      - `buybackAmount`: Amount of ERC tokens to buy back.

  - **exitShort**

    - **Purpose:** Exits a short position by placing a bid on the market.
    - **Parameters:**
      - `asset`: Address of the market being shorted.
      - `id`: ID of the short record.
      - `buybackAmount`: Amount of ERC tokens to buy back.
      - `price`: Price at which the shorter wants to place the bid.
      - `shortHintArray`: Array of hint IDs for matching against shorts.

- **Implementation Details**

  - **Short Record Validation:** Ensures that the short record exists and is valid for the specified asset and shorter.
  - **ERC Debt Calculation:** Updates the ERC debt of the short record before processing the exit.
  - **Partial Exit:** Allows for partial exits by specifying a `buybackAmount`.
  - **Collateral Refund:** Refunds the remaining collateral to the shorter if the ERC debt is fully paid back.
  - **Bid Placement:** For exits using bids, creates a forced bid on the market to buy back the ERC tokens.
  - **Collateral Ratio Check:** Ensures that the collateral ratio is maintained or improved after a partial exit.
  - **Dust Amount Prevention:** Prevents leaving a dust amount of ERC debt behind.
  - **Event Emission:** Emits events to track exit short activities.

### facets/RedemptionFacet.sol

The `RedemptionFacet` contract provides functionality for `proposing`, `disputing`, and `claiming` redemptions of short positions in a DittoEth Protocol.

- **Key Features**

  - **Propose Redemption:** Users can propose to redeem short positions by submitting a set of short record (SR) candidates. The proposal includes information such as the amount of ERC debt to be redeemed and the maximum redemption fee the proposer is willing to pay.
  - **Dispute Redemption:** Other users can dispute proposed redemptions by providing evidence of incorrect information or invalid SRs. If a dispute is successful, the incorrect proposals will be removed, and the proposer may receive a penalty.
  - **Claim Redemption:** After the dispute period has passed, the proposer can claim the collateral from the verified SRs. If the proposer does not claim, the shorter can claim the remaining collateral.

- **RedemptionFacet Contract Details**

  - **proposeRedemption**

    - **Parameters:**
      - `asset`: Address of the market asset.
      - `proposalInput`: Array of data pertaining to the proposed SRs.
      - `redemptionAmount`: Total amount of ERC debt requested to be redeemed.
      - `maxRedemptionFee`: Maximum fee that the redeemer is willing to pay.
    - **Purpose:** Allows users to propose a set of SRs for redemption. If the proposals are valid and not disputed, the proposer can claim the collateral after the dispute period.

  - **disputeRedemption**

    - **Parameters:**
      - `asset`: Address of the market asset.
      - `redeemer`: Address of the redeemer who proposed the redemption.
      - `incorrectIndex`: Index of the incorrect proposal in the redeemer's slate.
      - `disputeShorter`: Shorter address from the SR used to dispute the redemption.
      - `disputeShortId`: Id of the SR used to dispute the redemption.
    - **Purpose:** Allows users to challenge a proposed redemption by providing evidence of incorrect information or invalid SRs. If the dispute is successful, the incorrect proposals will be removed, and the proposer may receive a penalty.

  - **claimRedemption**

    - **Parameters:**
      - `asset`: Address of the market asset.
    - **Purpose:** Allows the proposer to claim the collateral from the verified SRs after the dispute period has passed.

  - **claimRemainingCollateral**

    - **Parameters:**
      - `asset`: Address of the market asset.
      - `redeemer`: Address of the redeemer who proposed the redemption.
      - `claimIndex`: Index of the proposal pointing to the shorter SR to be resolved.
      - `id`: Shorter address from the SR used to claim the remaining collateral.
    - **Purpose:** Allows the shorter to claim the leftover collateral from a SR that has been fully redeemed but not claimed by the proposer.

  - **calculateRedemptionFee**

    - **Parameters:**
      - `asset`: Address of the market asset.
      - `colRedeemed`: Amount of collateral redeemed.
      - `ercDebtRedeemed`: Amount of ERC debt redeemed.
    - **Purpose:** Calculates the redemption fee based on the amount of collateral and ERC debt redeemed, the current base rate, and the time since the last redemption.

- **Additional Notes**

  - The contract uses the `SSTORE2` library for efficient storage of large data structures.
  - The contract uses the `LibBytes` library for reading and writing proposal data to and from SSTORE2.
  - The contract uses the `console` library for debugging and logging purposes.

### libraries/LibBridgeRouter.sol

`LibBridgeRouter` library handles various operations related to bridge credit management and `dETH` accounting within a DittoEth Protocol.

- **Key Functions**

  - **addDeth**

    - Credits a user's account with dETH and bridge credit if applicable.
    - If the vault is `VAULT.ONE`, which supports mixed liquidity staking tokens (LST), it distinguishes between RETH (Rocket Pool Ether) and STETH (Lido Staked Ether) bridge credits.

  - **assessDeth**

    - Determines the amount of dETH that is not covered by bridge credits during withdrawal.
    - Considers existing bridge credits for RETH and STETH to calculate the amount of dETH that must be withdrawn without using bridge credits.

  - **withdrawalFeePct**

    - Calculates the withdrawal fee percentage for bridging operations in `VAULT.ONE`.
    - Compares the market premiums/discounts of RETH and STETH to determine if a fee should be charged to prevent arbitrage.

  - **transferBridgeCredit**

    - Transfers bridge credits from one user to another when an NFT SR (Senior Rights) is transferred.
    - Ensures that bridge credits are not abused by circumventing the bridge credit system.

  - **removeDeth**

    - Updates the user's account after dETH withdrawal.
    - Decrements the user's escrowed dETH and the total dETH in the vault.

- **Usage**

  The `LibBridgeRouter` library is likely used by other contracts within the DittoEth to handle bridge credit management and dETH accounting. It provides a set of functions that can be called to perform specific operations related to bridge credits and dETH balances.

### libraries/LibBytes.sol

The `LibBytes` library contains a custom decoding function for reading proposal data from a storage pointer.

- **Key Function**

  - **readProposalData**

    - Decodes proposal data from a storage pointer into an array of `MTypes.ProposalData` structs.
    - Each proposal data struct contains information about a proposal, including the shorter address, short ID, collateral ratio (CR), ERC debt redeemed, and collateral redeemed.
    - The decoding is custom-written because the proposal data was written directly to storage using `SSTORE.write` in another contract.

- **Usage**

  The `LibBytes` library is used by other contracts within the DittoEth protoco to read proposal data from storage. It provides a function that can be called to `decode` the proposal data into a structured format that can be easily accessed and processed.

- **Custom Decoding**

  - The custom decoding is necessary because the proposal data was written directly to storage using `SSTORE.write` in another contract. `SSTORE.write` writes data to storage as a raw byte array, without any additional encoding or formatting. This means that the data must be decoded manually in order to extract the individual fields of the proposal data.

  - The custom decoding function in `LibBytes` uses assembly to read the raw byte array and extract the individual fields of the proposal data. It uses bitwise operations to shift and mask the bytes in the byte array to extract the desired values.

### libraries/LibOracle.sol

`LibOracle` library handles `oracle-related` functionality, including fetching and validating oracle prices, and managing oracle prices stored in the contract's storage.

- **Key Functions**

  - **getOraclePrice**

    - Fetches the oracle price for a given asset.
    - Uses a base oracle to fetch the price of ETH in USD and then uses a specific oracle for the asset to fetch the price of the asset in ETH.
    - Implements circuit breakers to handle invalid or stale oracle data.

  - **baseOracleCircuitBreaker**

    - Circuit breaker for the base oracle (ETH/USD).
    - Checks for invalid fetch data and price deviation from the protocol price.
    - If invalid fetch data is detected, it returns the TWAP price.
    - If price deviation is detected, it checks the TWAP price and compares it with the chainlink price.
    - Returns the price that is closest to the saved oracle price.

  - **oracleCircuitBreaker**

    - Circuit breaker for the asset-specific oracle.
    - Checks for invalid fetch data.
    - If invalid fetch data is detected, it reverts with an error.

  - **twapCircuitBreaker**

    - Circuit breaker for the TWAP price.
    - Checks for invalid TWAP price and insufficient ETH liquidity in the liquidity pool.
    - If invalid TWAP price is detected, it reverts with an error.
    - If insufficient ETH liquidity is detected, it reverts with an error.

  - **setPriceAndTime**

    - Sets the oracle price and oracle time for an asset in storage.
    - Uses the `ercAmount` and `creationTime` properties of the `Bid` struct to store the oracle price and oracle time.

  - **getTime**

    - Gets the oracle time for an asset from storage.
    - Uses the `creationTime` property of the `Bid` struct to retrieve the oracle time.

  - **getPrice**

    - Gets the oracle price for an asset from storage.
    - Uses the `ercAmount` property of the `Bid` struct to retrieve the oracle price.

  - **getSavedOrSpotOraclePrice**

    - Gets the saved oracle price for an asset if it is within 15 minutes of the current time.
    - Otherwise, it fetches the spot oracle price from the oracle.

- **Usage**

  The `LibOracle` library fetch and validate oracle prices. It provides a set of functions that can be called to obtain oracle prices for specific assets, as well as to manage oracle prices stored in the contract's storage.

### libraries/LibOrders.sol

This `LibOrders` provides functions for handling orders in a dittoETH.

- **LibOrders Library Functions**

  1.  `getOffsetTime` function: This function returns the time difference between the current block timestamp and a predefined starting time.

  2.  `convertCR` function: This function converts the collateral ratio (CR) from a 16-bit unsigned integer to a 256-bit unsigned integer representation in ether.

  3.  `increaseSharesOnMatch` function: This function increases the matched shares of a user when their order is matched, based on the time difference between order creation and the current time.

  4.  `currentOrders` function: This function returns an array of all current orders for a specific asset.

  5.  `isShort` function: This function checks if an order is a short order.

  6.  `addBid` and `addAsk` functions: These functions add a bid or ask order to the respective order book, updating the user's escrowed ETH or ERC balance accordingly.

  7.  `addShort` function: This function adds a short order to the short order book, updating the user's escrowed ETH balance based on the collateral ratio.

  8.  `addSellOrder` function: This function adds a sell order (ask or short) to the order book.

  9.  `addOrder` function: This function adds an order to the specified order book, reusing order IDs for gas optimization.

  10. `verifyBidId` and `verifySellId` functions: These functions verify if a bid or sell order's price is between the given prevId and nextId.

  11. `cancelOrder` and `matchOrder` functions: These functions handle the reordering of the market when an order is canceled or matched, respectively.

  12. `_reuseOrderIds` function: This function is shared by `cancelOrder` and `matchOrder` to reuse order IDs.

  13. `findPrevOfIncomingId` function: This function finds the previous order ID for an incoming order, optimizing the search using a hint ID if possible.

  14. `getOrderId` function: This function returns the order ID based on the specified direction (next or prev) and the new price.

  15. `verifyId` function: This function verifies if an order's price is between the given prevId and nextId, considering the order type.

  16. `normalizeOrderType` function: This function normalizes the order type to either `LimitBid`, `LimitAsk`, or `LimitShort`.

  17. `updateBidOrdersOnMatch` function: This function updates the bid order book when a bid is matched, removing the matched order.

  18. `updateSellOrdersOnMatch` function: This function updates the ask and short order books when a sell order is matched by an incoming bid.

  19. `_updateOrders` function: This function updates the order book by setting the next and previous order IDs for the specified head ID and last matched ID.

  20. `sellMatchAlgo` function: This function handles the matching algorithm for asks, including bid matching and adding the sell order to the order book.

  21. `matchIncomingSell`, `matchIncomingAsk`, and `matchIncomingShort` functions: These functions handle the final settlement of incoming sell orders, including ask and short orders.

  22. `matchHighestBid` function: This function settles the highest bid and updates the incoming ask or short order.

  23. `_updateOracleAndStartingShort` function: This function updates the oracle price and the starting short ID for a specific asset.

  24. `updateOracleAndStartingShortViaThreshold` function: This function updates the oracle price and starting short ID if the price difference between the order price and the saved price exceeds a threshold.

  25. `updateOracleAndStartingShortViaTimeBidOnly` function: This function updates the oracle price and starting short ID if the time difference between the current time and the oracle time exceeds 15 minutes.

  26. `updateStartingShortIdViaShort` function: This function updates the starting short ID based on the price of an incoming short order.

  27. `findOrderHintId` function: This function finds the order hint ID based on the order hint array.

  28. `cancelBid`, `cancelAsk`, and `cancelShort` functions: These functions handle the cancellation of bid, ask, and short orders, respectively.

  29. `handlePriceDiscount` function: This function approximates the match price compared to the oracle price and accounts for any discount by increasing the dethTithePercent.

### libraries/LibSRUtil.sol

`LibSRUtil` library have helper functions for managing short records in a DittoEth protocol. Short records represent short positions in the protocol, where users borrow an asset (e.g., ETH) and sell it for another asset (e.g., USDC). The library provides functionality for disbursing collateral, checking the validity of short orders, and updating the ERC debt of short records.

- **Key Functions:**

  1.  **disburseCollateral**: Distributes collateral to the shorter (borrower) when they exit a short position or get liquidated. It also calculates and distributes yield earned on the collateral.
  2.  **checkCancelShortOrder**: Checks if a short order should be canceled based on the current status of the short record. It ensures that the short order is valid and that the shorter has sufficient ERC debt to cover the minimum short amount.
  3.  **checkShortMinErc**: Similar to `checkCancelShortOrder`, but it checks if the short record's ERC debt is below the minimum short amount. If so, it cancels the corresponding short order.
  4.  **checkRecoveryModeViolation**: Checks if the short record's collateralization ratio (CR) is below the recovery CR set for the asset. If so, it returns `true`, indicating that the market is in recovery mode and the short record is at risk of liquidation.
  5.  **transferShortRecord**: Transfers a short record from one address to another. It cancels any associated short order, updates the short record's data, and transfers the collateral to the new owner.
  6.  **updateErcDebt**: Updates the ERC debt of a short record based on the current ERC debt rate. It distributes any accrued ERC debt to the shorter.

### libraries/UniswapOracleLibrary.sol

This library contains functions for interacting with the Uniswap V3 oracle to get price quotes and estimate `TWAPs`.

- **Key Functions:**

  1.  **getQuoteAtTick**: Calculates the amount of quote token that can be received for a given amount of base token at a specific tick value. It uses the Uniswap V3 pool's sqrtPriceX96 to calculate the quote amount with high precision.

  2.  **estimateTWAP**: Estimates the TWAP of a token pair over a specified period of time. It uses the Uniswap V3 pool's `observe` function to get the cumulative tick and liquidity data for the specified time period. Then, it calculates the tick value for the TWAP period and uses `getQuoteAtTick` to get the TWAP price.

- **Additional Notes:**

- The `getQuoteAtTick` function rounds the tick value to negative infinity to ensure that the calculated quote amount is always slightly lower than the actual market price. This helps prevent slippage when executing trades.
- The `estimateTWAP` function always rounds the tick value to negative infinity, which means that the estimated TWAP is always slightly lower than the actual TWAP. This is done to account for the fact that the TWAP is calculated using historical data, and the actual TWAP may be higher due to price movements after the TWAP period.

## 2. Additional Context

- [x] Describe any novel or unique curve logic or mathematical models implemented in the contracts
- [x] Please list specific ERC20 that your protocol is anticipated to interact with. Could be "any" (literally anything, fee on transfer tokens, ERC777 tokens and so forth) or a list of tokens you envision using on launch.
  - Lido (stETH) and Rocketpool (rETH) and potentially other LSTs in the future
- [x] Please list specific ERC721 that your protocol is anticipated to interact with.
  - Ditto's own ShortRecord(s) _can_ become an NFT if it's minted/transferred
- [x] Which blockchains will this code be deployed to, and are considered in scope for this audit?
  - Ethereum mainnet only
- [x] Please list all trusted roles (e.g. operators, slashers, pausers, etc.), the privileges they hold, and any conditions under which privilege escalation is expected/allowable
  - Owner: Highest level of access, ability to create new vaults and markets, in addition to parameter changes
  - Admin: Secondary role to allow quicker response time to sensitive actions, includes parameter changes
- [ ] In the event of a DOS, could you outline a minimum duration after which you would consider a finding to be valid? This question is asked in the context of most systems' capacity to handle DoS attacks gracefully for a certain period.
- [ ] Is any part of your implementation intended to conform to any EIP's? If yes, please list the contracts in this format:
  - `Contract1`: Should comply with `ERC/EIPX`
  - `Contract2`: Should comply with `ERC/EIPY`

## 3. Main invariants

### Orderbook

Ditto's orderbook acts similar to central limit orderbook with some changes. In order to make the gas costs low, there is a hint system added to enable a user to place an order in the orderbook mapping. Asks/Shorts are both on the "sell" side of the orderbook. Order structs are reused by implementing the orders as a doubly linked-list in a mapping. `HEAD` order is used as a starting point to match against.

- Ask orders get matched before short orders at the same price.
- Bids sorted high to low
- Asks/Shorts sorted low to high
- Only cancelled/matched orders can be reused (Technically: Left of HEAD (`HEAD.prevId`) these are the only possible OrderTypes: `O.Matched`, `O.Cancelled`, `O.Uninitialized`).
- Since bids/asks/shorts share the same `orderId` counter, every single `orderId` should be unique

### Short Orders

`shortOrders` can only be limit orders. `startingShort` represents the first short order that can be matched. Normally `HEAD.nextId` would the next short order in the mapping, but it's not guaranteed that it is matchable since users can still create limit shorts under the oracle price (or they move below oracle once the price updates). Oracle updates from chainlink or elsewhere will cause the `startingShort` to move, which means the system doesn't know when to start matching from without looping through each short, so the system allows a temporary matching backwards.

- `shortOrder` can't match under `oraclePrice`
- `startingShort` price must be greater than or equal to `oraclePrice`
- `shortOrder` with a non-zero (ie. positive) `shortRecordId` means that the referenced SR is status partialFill

### ShortRecords

ShortRecords are the Vaults/CDPs/Troves of Ditto. SRs represent a collateral/debt position by a shorter. Each user can have multiple SRs, which are stored under their address as a list.

- The only time `shortRecord` debt can be below `minShortErc` is when it's partially filled and the connected `shortOrder` has enough `ercDebt` to make up the difference to `minShortErc` (Technically: `SR.status` == `PartialFill` && `shortOrder.ercAmount` + `ercDebt` >= `minShortErc`)
- Similarly, SR can never be `SR.FullyFilled` and be under `minShortErc`
- `FullyFilled` SR can never have 0 collateral
- Only SR with status `Closed` can ever be re-used (Technically, only `SR.Closed` on the left (prevId) side of HEAD, with the exception of HEAD itself)

### Redemptions

Allows dUSD holders to get equivalent amount of ETH back, akin to Liquity. However the system doesn't automatically sort the SR's lowest to highest. Instead, users propose a list of SRs (an immutable slate) to redeem against. There is a dispute period to revert any proposal changes and a corresponding penalty against a proposer if incorrect. Proposers can claim the ETH after the time period, and shorters can also claim any remaining collateral afterwards.

- Only the first and last proposal can possibly be partially redeemed
- Proposal "slates" are sorted least to highest CR
- All CR in `proposedData` dataTypes should be under 2 CR
- Check before proposal, the `ercDebt` of SR cannot be zero. After proposal, check it cannot be `SR.Closed`` until claimed
- If proposal happens, check to see that there is no issues with SSTORE2 (the way it is saved and read)
- Relationship between proposal and SR's current `collateral` and `ercDebt` amounts. The sum total should always add up to the original amounts (save those amounts)

### BridgeRouter/Bridge

Because the Vault mixes rETH/stETH, a credit system is introduced to allow users to withdraw only what they deposit, anything in excess (due to yield) also checks either LSTs price difference using a TWAP via Uniswap.

- deposit/withdraw gives/removes an appropriate amount of virtual dETH (ETH equivalent), no matter if someone deposits an LST (rETH, stETH), or ETH and accounts for yield that is gained over time.

### Additional Invariants

1. Collateralization Ratio: The system should always maintain a minimum collateralization ratio for stable assets, ensuring that they are properly backed and not under-collateralized.

2. Vault Consistency: The total amount of collateral (ETH and LSTs) in a vault should always equal the sum of the escrowed amounts for all users in that vault.

3. Asset Minting and Burning: The total supply of stable assets (ERC-20 tokens) should always match the sum of the corresponding ercEscrowed amounts for all users.

4. Orderbook Balance: For each stable asset order, the total amount of ETH provided by buyers and sellers should always be equal.

5. dETH Consistency: The total amount of dETH in the system should always equal the sum of the escrowed amounts of ETH and LSTs across all vaults.

6. Vault Count: The number of vaults in the system should always be a non-negative integer, and the ONE constant should always represent the first vault.

7. Bridge Consistency: For each bridge, the total amount of escrowed collateral (ETH and LSTs) should always equal the sum of the corresponding escrowed amounts for all users interacting with that bridge.

8. Fee Structure: The system should always enforce the predefined fee structure for withdrawals, including Bridge.withdrawalFee and stETH/rETH premium fees.

9. Owner Privileges: Only the diamond owner should have access to the withdrawTapp() function to withdraw dETH fees accrued to the TAPP as LST.

## Approach Taken-in Evaluating `DittoETH`

Accordingly, I analyzed and audited the subject in the following steps;

1.  **Core Protocol Contract Overview**:

    I focused on thoroughly understanding the codebase and providing recommendations to improve its functionality.
    The main goal was to take a close look at the important contracts and how they work together in the `DittoETH`.

                     facets/RedemptionFacet.sol
                     facets/BidOrdersFacet.sol
                     facets/ShortOrdersFacet.sol
                     facets/PrimaryLiquidationFacet.sol
                     facets/BridgeRouterFacet.sol
                     libraries/LibBridgeRouter.sol

    I started my analysis by examining the intricate structure and functionalities of the `DittoEth` protocol, focusing on the underlying mechanisms that facilitate the secure and efficient exchange of data between participants. Specifically, I paid close attention to the implementation of the BidOrdersFacet, ShortOrdersFacet, PrimaryLiquidationFacet, BridgeRouterFacet, ExitShortFacet, and RedemptionFacet contracts, which collectively orchestrate the core operations of the protocol, including order matching, short position management, liquidation, bridging, and redemption.

2.  **Documentation Review**:

    Then went to Review these [documentation](https://dittoeth.com/technical/concepts), for a more detailed and technical explanation of `DittoEth`.

3.  **Compiling code and running provided tests**:

4.  **Manuel Code Review** In this phase, I initially conducted a line-by-line analysis, following that, I engaged in a comparison mode.

    - **Line by Line Analysis**: Pay close attention to the contract's intended functionality and compare it with its actual behavior on a line-by-line basis.

    - **Comparison Mode**: Compare the implementation of each function with established standards or existing implementations, focusing on the function names to identify any deviations.

## Architecture

**System Life Cycle**

The system life cycle for the dUSD market on DittoETH involves the following stages:

**Entering:**

- Users deposit ETH or an accepted LST to mint dETH.
- Once a market is established, users can deposit stable assets like dUSD.

**Trading:**

- dUSD is created by shorting dETH.
- Bids can be created to buy dUSD.
- Users can also sell dUSD directly for dETH.

**Exiting:**

- Users can withdraw dUSD and mint ERC-20 equivalents.
- Users can redeem dETH for the underlying LSTs.

**Manage Shorts:**

- Shorters can increase or decrease collateral to maintain a healthy CR.
- Shorters can combine multiple shorts.
- Shorters can close or reduce their debt positions.

**Liquidations:**

- Shorts that fall below the liquidation CR are available for liquidations.
- Liquidations can be incentivized with a fee.
- Users can bring dUSD directly and clear bad debt without a fee.

## Codebase Quality

Overall, I consider the quality of the `DittoEth` protocol codebase to be Good. The code appears to be mature and well-developed. We have noticed the implementation of various standards adhere to appropriately. Details are explained below:

| Codebase Quality Categories              | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Architecture & Design**                | The protocol features a modular design, segregating functionality into distinct contracts (e.g., `RedemptionFacet`, `BidOrdersFacet`, `ShortOrdersFacet`) for clarity and ease of maintenance.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Code Maintainability and Reliability** | The contracts are written with emphasis on sustainability and simplicity. The functions are single-purpose with little branching and low cyclomatic complexity.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Code Comments**                        | There must be different types of comments used in the `DittoEth` protocol: `Single-line comments`, `Multi-line comments`, `Documentation comments` for documentation, explanations, TODOs, and structuring the code for readability. However, the codebase lacks many comments. `NatSpec` tags also allow for automatically generating documentation. The contracts must be accompanied by comprehensive comments to facilitate an understanding of the functional logic and critical operations within the code. Functions must be described purposefully, and complex sections should be elucidated with comments to guide readers through the logic. Despite this, certain areas, particularly those involving intricate mechanics, could benefit from even more detailed commentary to ensure clarity and ease of understanding for developers new to the project or those auditing the code. |
| **Testing**                              | The contracts exhibit a commendable level of test coverage `96%%` but with aim to 100% for indicative of a robust testing regime. This coverage ensures that a wide array of `functionalities` and `edge cases` are tested, contributing to the reliability and security of the code. However, to further enhance the testing framework, the incorporation of fuzz testing and invariant testing is recommended. These testing methodologies can uncover deeper, systemic issues by simulating extreme conditions and verifying the invariants of the contract logic, thereby fortifying the codebase against unforeseen vulnerabilities.                                                                                                                                                                                                                                                         |
| **Code Structure and Formatting**        | The codebase benefits from a consistent structure and formatting, adhering to the stylistic conventions and best practices of solidity programming. Logical grouping of functions and adherence to naming conventions contribute significantly to the readability and navigability of the code. While the current structure supports clarity, further modularization and separation of concerns could be achieved by breaking down complex contracts into smaller, more focused components. This approach would not only simplify individual contract logic but also facilitate easier updates and maintenance.                                                                                                                                                                                                                                                                                   |
| **Strengths**                            | The codebase is a well-structured, modular, and extensible implementation functionality for contract execution, storage management, chain extensions, and more, with a focus on security, performance, and universal compatibility across different blockchain networks.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Documentation**                        | While the `Documentation` provides `comprehensive` details for all functions and the system,However currently `no helpful inline comments` available for `auditors` or developers. It is crucial to develop inline comments to offer a comprehensive understanding of the contract's functionality, purpose, and interaction methods inside the codebase.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## Systemic Risks, Centralization Risks, Technical Risks & Integration Risks

### facets/BidOrdersFacet.sol

1. **Systemic Risks:**

   - `Dust order risk`: The contract handles dust orders (orders below a certain threshold) in a specific way, which could potentially lead to unintended consequences or edge cases related to these small orders.

   - **Short Position Handling**: The contract manages short positions, which can introduce additional risks related to collateral management, liquidation mechanisms, and the interplay between short and long positions.

   - Dust Threshold: The contract includes a dust threshold for limit orders, below which orders are not processed. This could potentially result in orders not being filled if they fall below the dust threshold.

   - **Bid matching algorithm complexity:** The bid matching algorithm in the contract is complex and may be difficult to understand or predict. This could lead to unexpected results or even losses for users who do not fully understand how the algorithm works.

   - **Short selling risk:** The contract allows users to place short orders, which can be risky. If the price of an asset increases, users who have placed short orders may lose money.

2. **Centralization Risks:**

   - `OnlyDiamond` Modifier: The `onlyDiamond` modifier restricts certain functions to be called only by the diamond contract. This creates a centralization risk as it gives special privileges to a single contract.

   - Asset Vault: The contract uses a vault to store assets, which creates a centralization risk as it concentrates assets in a single location.

### facets/ShortOrdersFacet.sol

1. **Systemic Risks:**

   - **Price Manipulation Risk**: The contract allows users to create short orders based on their specified prices. If users can manipulate the prices or exploit pricing mechanisms, it could lead to unfair or malicious trading activities.

   - **Frozen Asset Risk**: The contract includes a mechanism to freeze specific assets, potentially preventing trading or order execution for those assets. If the freezing mechanism is exploited or misused, it could disrupt the normal operations of the system.

   - **Short Order Matching Logic**: The contract includes a logic for matching short orders, which could be difficult to understand and audit. Any errors in this logic could result in incorrect order matching and potential financial losses for users.

   - **Collateral Ratio**: The contract uses a collateral ratio to calculate the amount of collateral required for a short order. If the collateral ratio is set too low, it could result in under-collateralized short orders and potential financial losses for the contract and users.

   - **Minimum Order Size**: The contract includes a minimum order size requirement for short orders. If the minimum order size is set too high, it could prevent smaller orders from being placed and limit the liquidity of the market.

   - **Liquidation Risk**: The contract does not appear to have explicit liquidation mechanisms for undercollateralized positions. If positions become undercollateralized due to price movements or other factors, there is no clear process for managing or liquidating those positions, potentially leading to systemic risks.

2. **Centralization Risks:**

   - `OnlyValidAsset` Modifier: The `onlyValidAsset` modifier restricts certain functions to be called only for valid assets. This creates a centralization risk as it gives special privileges to certain assets.

   - The contract has a centralized design, where the `ShortOrdersFacet` contract is responsible for managing the entire short order system. This centralization introduces a single point of failure.

3. **Technical Risks:**

   - The contract is using complex data structures and algorithms, such as the `STypes.Order` struct and the `LibOrders.addShort` and `LibOrders.sellMatchAlgo` functions. Any bugs or issues in these implementations could lead to technical vulnerabilities.

### facets/PrimaryLiquidationFacet.sol

1. **Systemic Risks:**

   - **Concentration Risk**: If a significant portion of the market shares are controlled by a few participants, it could lead to market manipulation and increase systemic risks.

   - **Forced Bid Execution Risk**: The contract allows the liquidation contract to execute a "forced bid" on the market, which could lead to potential abuse or manipulation by the contract owner.

   - **Socialization of Debt Risk**: The contract has a mechanism to socialize the debt of a liquidated short position, which could create incentives for users to over-leverage or take excessive risks, potentially leading to systemic issues.

   - **Collateral Forfeiture Risk**: The contract has a mechanism to allow the TAPP (Temporary Asset Protection Protocol) to absorb the leftover collateral of a partially liquidated short position, which could be seen as a potential risk to user autonomy and trust in the system.

   - **Debt Socialization Risk**: If the TAPP (liquidity provider) does not have enough funds to cover the debt during liquidation, the debt is socialized across other short positions in the same asset (`Asset.ercDebtRate += ercDebtSocialized.divU64(Asset.ercDebt - ercDebtPrev)`). This can lead to a cascading effect and potentially impact the overall system.

   - **Liquidation Parameter Risk**: The contract relies on several parameters (e.g., `liquidationCR`, `penaltyCR`, `forcedBidPriceBuffer`, `callerFeePct`, `tappFeePct`) that are set by external contracts (`LibAsset`). Any misconfiguration or manipulation of these parameters could lead to incorrect liquidation decisions or unexpected behavior.

   - **Gas Price Risk**: The contract uses a fixed gas price (`block.basefee`) for calculating gas fees, which may not be optimal in certain scenarios, particularly during periods of high gas prices or network congestion.

   - **Liquidation Threshold**: The contract includes a liquidation threshold for short positions. If the threshold is set too low, it could result in unnecessary liquidations and potential financial losses for users. If the threshold is set too high, it could result in under-collateralized positions and potential financial losses for the contract and users.

   - **Liquidation Fee Distribution**: The contract includes a mechanism for distributing liquidation fees between the TAPP and the liquidator. If the fee distribution mechanism is not implemented correctly, it could result in inequitable distribution of fees and potential financial losses for users.

   - **Collateral Withdrawal**: The contract includes a mechanism for withdrawing collateral from a short position. If the withdrawal mechanism is not implemented correctly, it could result in incorrect collateral withdrawals and potential financial losses for users.

2. **Centralization Risks:**

   - **TAPP Ownership**: The contract includes a mechanism for the TAPP to absorb leftover short positions in the event of a partial liquidation. This creates a centralization risk as it concentrates ownership of short positions in the hands of the TAPP.

3. **Integration Risks:**

   - **Integration with other systems:** The contract must be integrated with other systems, such as the oracle and the blockchain, in order to function properly. If these systems are not properly integrated, it could lead to problems with liquidations.

   - **Token Compatibility**: The contract assumes the existence of a `dusd` token, but it does not specify the token standard or any compatibility checks, which could lead to integration issues with other systems.

### facets/BridgeRouterFacet.sol

1. **Systemic Risks:**

   - **Yield Manipulation Risks:** The `maybeUpdateYield` function is designed to deter attempts to take advantage of long delays between updates to the yield rate. However, this function could still be susceptible to manipulation, as it relies on thresholds that could potentially be exploited.

   - **Yield Rate Updates**: The contract includes a mechanism for updating the yield rate based on deposit activity. If the update mechanism is not implemented correctly, it could result in inaccurate yield rate calculations and potential financial losses for users.

   - **Escrow risk:** The contract could hold user funds in escrow, which could increase the risk of loss.

2. **Centralization Risks:**

   - **Vault Configuration**: The contract includes a configuration parameter for each vault that determines the minimum deposit amount and withdrawal fee percentage. If these parameters are not set appropriately, it could result in unfair treatment of users or potential financial losses for the protocol.

   - **Centralization Risk**: The contract relies heavily on the `rethBridge` and `stethBridge` addresses, which are hardcoded in the constructor. If these bridges become compromised or centralized, it could pose a systemic risk to the entire system.

3. **Technical Risks:**

   - **Access Control Risk**: The `withdrawTapp` function is only accessible by the DAO, but there is no explicit access control mechanism implemented in the contract. This could lead to unauthorized access if the access control logic is not properly implemented elsewhere.

   - **Potential Loss of Funds:** The `_ethConversion` function handles situations where the vault (via bridges) experiences a loss in value. However, this function could be improved to provide more robust handling and prevent potential loss of funds.

   - **FrontRunning**: The contract includes functions for depositing and withdrawing dETH that could be vulnerable to front-running attacks, where an attacker executes a transaction before a user's transaction is processed, potentially resulting in financial losses for the user.

4. **Integration Risks:**

   - **Bridge Integration Risk**: The contract heavily relies on the integration with external bridges (`rethBridge` and `stethBridge`). If these bridges are updated, removed, or change their interfaces, it could break the functionality of the contract.

### facets/ExitShortFacet.sol

1. **Systemic Risks:**

   - **Market risk:** The contract is exposed to market risk, as the value of the underlying assets could fluctuate. This could lead to losses for users.

   - **Exit liquidity risk:** Users may have difficulty exiting their positions due to a lack of liquidity in the market.

   - **Short squeeze risk:** A short squeeze could occur if a large number of users try to exit their positions at the same time. This could lead to losses for users who are unable to exit their positions.

   - **Depeg risk:** The value of the underlying asset could depeg from its target price. This could lead to losses for users who are holding the asset.

   - **Frozen Asset Risk**: The `isNotFrozen` modifier is used to check if an asset is frozen. If the logic for determining frozen assets is not implemented correctly, it could lead to unexpected behavior or security issues.

   - **Short Record Validity Risk**: The `onlyValidShortRecord` modifier is used to check if a short record is valid. If the logic for determining valid short records is not implemented correctly, it could lead to unexpected behavior or security issues.

   - **Collateral Ratio Risk**: The `getCollateralRatioNonPrice` function calculates the collateral ratio for a short record. If this calculation is incorrect, it could lead to incorrect decision-making or security issues.

   - **Collateral Disbursal Timing**: The contract disburses collateral based on the `updatedAt` timestamp of the `ShortRecord`. This could be susceptible to time-based attacks or manipulation, where an attacker tries to influence the timing of the collateral disbursal.

   - **Dust Amount Constraints**: The contract enforces a minimum ERC debt amount (`LibAsset.minShortErc(asset)`), and if the remaining ERC debt falls below this threshold, the contract reverts with the `Errors.CannotLeaveDustAmount()` error. This constraint could potentially lead to unexpected behavior or issues for users.

   - **Partial Exit**: The contract allows users to partially exit their short positions by buying back a portion of their ERC debt. If the mechanism is not implemented correctly, it could result in incorrect buyback amounts and potential losses for users.

   - **Minimum ERC Debt**: The contract includes a mechanism for preventing users from leaving a dust amount of ERC debt when exiting their short position. If the mechanism is not implemented correctly, it could result in users being unable to exit their short positions or potential losses for the protocol.

2. **Centralization Risks:**

   - **Single Point of Failure**: The contract has a single constructor parameter, `_dusd`, which is used to initialize the `dusd` variable. If this address is compromised or becomes unavailable, it could impact the entire system.

3. **Technical Risks:**

   - **FrontRunning**: The contract includes functions for buying back ERC tokens, which could be vulnerable to front-running attacks, where an attacker executes a transaction before a user's transaction is processed, potentially resulting in financial losses for the user.

### facets/RedemptionFacet.sol

1. **Systemic Risks:**

   - **Redemption fee:** The contract charges a redemption fee, which is a percentage of the amount of assets being redeemed. This fee could discourage users from redeeming their assets, which could lead to a decrease in liquidity and an increase in the price of the assets.

   - **Dispute period:** The contract has a dispute period during which users can challenge the validity of a redemption proposal. This could lead to delays in the redemption process and could discourage users from redeeming their assets.

   - **Redemption Fee Calculation Complexity**: The `calculateRedemptionFee` function is quite complex, with several calculations and state updates, which could be vulnerable to bugs or unintended consequences.

   - **Redemption Fee Volatility**: The contract calculates the redemption fee based on the base rate and the amount of ERC-20 tokens being redeemed. If the base rate or the amount of ERC-20 tokens being redeemed suddenly changes, this could result in a significant increase in the redemption fee, making it prohibitively expensive for users to redeem their collateral.

2. **Centralization Risks:**

   - **Privileged Roles**: The contract has a few privileged roles, such as the ability to freeze the contract, which could lead to centralization risks if these roles are not properly managed or secured.

   - **Admin Privileges**: The contract includes admin functions that allow certain addresses to perform privileged operations, such as setting the base rate and dispute time. This creates a centralization risk as it concentrates control in the hands of a small group of individuals.

3. **Technical Risks:**

   - **FrontRunning Attacks**: The contract allows users to propose redemptions and dispute redemptions, which could be vulnerable to front-running attacks if not properly guarded against.

   - **External Contract Call Risk**: The contract makes external calls to other contracts (e.g., LibOrders, LibShortRecord), which can introduce potential reentrancy or other security vulnerabilities if those external contracts are not properly secured.

   - **Timestamp Manipulation Risk**: The contract relies on block timestamps for certain calculations (e.g., dispute period), which can be manipulated by miners, potentially leading to unexpected behavior or vulnerabilities.

### libraries/LibBridgeRouter.sol

1. **Systemic Risks:**

   - **Arbitrage opportunities:** The contract could create arbitrage opportunities for users who are able to take advantage of differences in the prices of dETH on different exchanges.

   - **Market manipulation:** The contract could be used to manipulate the market for dETH, which could lead to losses for users.

   - **Asset-specific Functionality**: The contract is designed specifically for rETH and stETH assets, which could make it challenging to extend or adapt to other asset types in the future.

   - **Withdrawal Fee Calculation**: The withdrawal fee calculation logic in the `withdrawalFeePct` function is complex and depends on various external factors, which could lead to potential issues or vulnerabilities if not thoroughly tested and audited.

   - **Bridging Credit Transfer**: The `transferBridgeCredit()` function is used to transfer bridge credits when an asset is transferred. This functionality could be complex and potentially introduce additional risks, such as edge cases or unexpected behavior.

   - **Liquidity risk**: If there is insufficient liquidity in the underlying assets, it may not be possible to process withdrawals or transfers, leading to delays or losses for users.

2. **Centralization Risks:**

   - **Ownership and Control**: The contract uses the `appStorage()` function to access a centralized storage location, which could introduce centralization risks if the ownership or control of this storage is not properly managed.

3. **Integration Risks:**

   - **Bridge failure**: If the bridges used in the system fail or become unavailable, it could result in users being unable to withdraw or transfer their assets.

### libraries/LibOracle.sol

1. **Systemic Risks:**

   - **Liquidity Dependence**: The contract's price calculation logic relies on the availability of sufficient liquidity in the USDC-WETH pool. If the liquidity in this pool is low, it could lead to systemic issues.

   - **Flash loan attacks:** An attacker could use a flash loan to manipulate the price of ETH or USDC on Uniswap and then execute a profitable trade on this contract.

   - **Liquidation risk:** If the price of ETH or USDC falls significantly, it could lead to the liquidation of assets held in the contract.

   - **Price Circuit Breaker Logic**: The contract's complex price circuit breaker logic, which includes checks for invalid Chainlink data, price deviations, and TWAP price validation, could be a source of risks. This logic could be susceptible to edge cases or unexpected behavior.

   - **Price Storage and Retrieval**: The contract stores and retrieves asset prices using a linked list-like data structure, which could introduce risks related to the maintenance and manipulation of this data structure.

   - **Time-Dependent Price Retrieval**: The contract's logic for retrieving the most recent or spot price, based on the time offset from the stored price, could be a source of risks if the time-based logic is not properly implemented.

   - **Stale Price Data**: The contract caches price data for a certain period (15 minutes) to save gas. However, this could lead to situations where the contract operates with stale price data, potentially resulting in inaccurate calculations or exploitable conditions.

   - **Hardcoded Constants**: The contract relies on hardcoded constants (e.g., `C.BASE_ORACLE_DECIMALS`, `C.UNISWAP_WETH_BASE_AMT`) for various calculations. Any changes to these constants in the future might require modifying the contract code.

2. **Centralization Risks:**

   - **Centralized Oracle Source**: The contract relies on a single base oracle (AggregatorV3Interface) for price data. This could lead to centralization risks, as the contract's functionality becomes dependent on a single source of truth for price data.

   - **Uniswap liquidity risk:** The contract relies on Uniswap for liquidity. If the liquidity on Uniswap is insufficient, it could make it difficult for users to withdraw their assets or execute trades at a fair price.

3. **Integration Risks:**

   - **Liquidity Pool Integration**: The contract's dependence on the USDC-WETH pool liquidity introduces integration risks, as changes or issues with this pool could affect the contract's price calculation logic.

### libraries/LibOrders.sol

1. **Systemic Risks:**

   - **Cancelled Order Risks**: If a user cancels an order, the contract must ensure that the order is properly removed from the order book and that any associated funds are returned to the user. If this process is not handled correctly, it could lead to losses for the user.

   - **Starting Short ID Risks**: The contract's starting short ID is used to determine which short orders are eligible for matching. If this ID is not set correctly, it could lead to incorrect order matches, resulting in losses for users.

2. **Technical Risks:**

   - **Front-Running Attacks**: The contract's use of external oracles creates a potential risk of front-running attacks, where an attacker can manipulate the oracle's price information to profit at the expense of other users.

### libraries/LibSRUtil.sol

1. **Systemic Risks**

   - **Short squeeze risk:** If a large number of users try to close their short positions at the same time, it could lead to a short squeeze, which could drive up the price of the underlying asset and cause losses for short sellers.

   - **Liquidation risk:** If the price of the underlying asset falls below a certain level, short sellers could be liquidated, which would result in them losing their collateral.

   - **Yield farming risk:** Users who deposit their collateral into the liquidity pool to earn yield could be exposed to the risk of impermanent loss, which occurs when the price of the underlying asset changes significantly.

   - **Short Record Transfer Logic**: The contract's logic for transferring short records between addresses could introduce risks, especially if there are edge cases or unexpected behaviors during the transfer process.

   - **ERC Debt Updating**: The contract's logic for updating the ERC debt based on the asset's ERC debt rate could be a source of risks if the debt calculation or update logic is not properly implemented.

   - **Short Record Management**: The contract manages short records and their statuses (e.g., `PartialFill`, `FullyFilled`, `Closed`). Errors in handling these statuses or updating short records could result in data inconsistencies or unintended behavior.

1. **Centralization Risks**

   - **Ownership and Control**: The contract uses the `appStorage()` function to access a centralized storage location, which could introduce centralization risks if the ownership or control of this storage is not properly managed.

1. **Integration Risks**

   - **Tight Coupling with External Libraries**: The contract is tightly coupled with various external libraries, which could make it challenging to integrate with other systems or upgrade individual components independently.

   - **Asset Integration**: The contract's heavy reliance on the state and configuration of the underlying assets introduces integration risks, as any changes or issues with these assets could have a significant impact on the contract's functionality.

   - **Yield Distribution Integration**: The contract's logic for distributing yield on the collateral could introduce integration risks if the yield calculation or distribution mechanisms are not properly integrated with the rest of the system.

### libraries/UniswapOracleLibrary.sol

1. **Systemic Risks:**

   - **TWAP calculation limitations:** The contract uses a time-weighted average price (TWAP) to estimate prices, which may not accurately reflect real-time market conditions.

   - **Tick rounding:** The contract rounds the tick value used for price calculation to the nearest negative infinity, which could introduce potential inaccuracies in pricing.

   - **Time-Weighted Average Price (TWAP) Calculation**: The contract implements logic for calculating TWAP using the Uniswap V3 pool's `observe` function. Any issues or vulnerabilities in the TWAP calculation logic could lead to inaccurate price estimations or potential exploits.

   - **Lack of Input Validation**: The contract does not appear to have explicit input validation for certain parameters, such as `secondsAgo` in the `estimateTWAP` function. Improper input values could lead to unexpected behavior or potential vulnerabilities.

   - **Uniswap V3 Pool Reliance**: The contract heavily relies on the Uniswap V3 pool for price estimation and TWAP calculation. Any issues or vulnerabilities in the Uniswap V3 pool could have a systemic impact on the contract's functionality.

   - **Price Manipulation**: The contract's reliance on external price feeds creates a potential risk of price manipulation. If an attacker is able to manipulate the price of the token in the Uniswap V3 pool, they could potentially profit at the expense of the contract and its users.

   - **Tick Cumulatives Calculation**: The contract's logic for calculating the tick cumulatives using the `IUniswapV3Pool.observe` function could be a source of unique risks, as the interpretation and handling of the returned data could be complex.

   - **Rounding and Precision**: The contract's logic for converting between different numerical representations (e.g., `sqrtRatioX96`, `ratioX192`, `ratioX128`) could introduce unique risks related to rounding and precision issues.

2. **Centralization Risks:**

   - **Single point of failure:** The contract relies on a single oracle for price information, which could be a single point of failure if the oracle becomes unavailable or compromised.

   - **Dependence on Uniswap V3**: The contract is heavily dependent on Uniswap V3 pools for price feeds. If Uniswap V3 were to experience an outage, this could result in the contract being unable to function properly.

3. **Technical Risks:**

   - **Front-Running Attacks**: The contract's use of external price feeds creates a potential risk of front-running attacks. If an attacker is able to observe the contract's trading activity and execute trades based on this information before the contract does, they could potentially profit at the expense of the contract and its users.

   - **Tick Calculation**: The contract's tick calculation logic, which involves rounding down to the nearest integer, could introduce technical risks if not properly implemented.

   - **Precision Limitations**: The contract relies on fixed-point arithmetic and rounding mechanisms for handling tick values and price calculations. Precision limitations or rounding errors could lead to inaccuracies in price estimations or other calculations.

4. **Integration Risks:**

   - **Uniswap V3 Pool Integration**: The contract's heavy reliance on the Uniswap V3 pool introduces integration risks, as any changes or issues with the pool could have a significant impact on the contract's functionality.

   - **Token Pair Integration**: The contract's integration with the specific token pair being used could introduce risks if the token pair's characteristics or behavior change over time.

   - **Tight Coupling with Uniswap V3 Protocol**: The contract is tightly coupled with the Uniswap V3 protocol and its interfaces. Integrating the contract with other decentralized exchanges (DEXs) or price oracles would require significant modifications.

## Issues surfaced from Attack Ideas

- Redemptions, as this is an entirely new concept to the protocol.

- Anything related to Orderbook matching logic, can get complicated in terms of what was done to save gas

  - The Orderbook only allows matching a Short Order at or above oracle price, unlike bids/asks so that part acts differently than an usual orderbook
  - Oracle price is cached to 15m, mostly done to allow the hint system to work (placing bids in sorted position in a mapping as a linked list is expensive, so the hint is used to know where in the list an order should go). This is worse with a short order because short orders can't be matched below oracle price. But if the oracle price is always changing, it is difficult to pick a hint that will be valid when the transaction happens, so the system allows for 0.5% buffer and allows matching backwards in this scenario until it reaches the correct "starting short id", which is the short order id that represents the first short order that can be correctly matched (at or above oracle).

- Dust amounts: want to prevent small orders on the orderbook to prevent skyrocketing gas costs for large orders that match with multiple limit orders

- Concept of `minShortErc`: Primary liquidators should always have a large enough incentive to liquidate (`callerFeePct` tied to liquidated collateral) risky debt because every ShortRecord must either contain enough ercDebt or have access to enough ercDebt (through cancelling the associated short order). The one noted exception is listed in known issues (ercDebt requirements met from application of ercDebtRate)

- Anything related to being able to correctly liquidate/exit ShortRecords that are a certain collateral ratio


### Time spent:
10 hours