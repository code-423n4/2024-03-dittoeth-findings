
# Analysis - DittoETH Contest

![DitttoETH Protocol](https://code4rena.com/_next/image?url=https%3A%2F%2Fstorage.googleapis.com%2Fcdn-c4-uploads-v0%2Fuploads%2FXcKzZ6eSLH9.0&w=256&q=75)


## Index
| NO.  | Particulars  |
|-------|----------|
| 1   |  Conceptual Overview  |
| 2  | Approach taken in evaluating the codebase  |
| 3  | Testing suites  |
| 4  | Architecture Assessment|
| 5  | Software Engineering Considerations |
| 6  | Quality of codebase   |
| 7  | Risks related to the project  |
| 8  | Recommendations  |
| 9  | Conclusion  |
| 10  | Time Spent|



## 1. Conceptual Overview

DittoETH is a decentralized pegged asset issuance protocol built on Ethereum, inspired by Bitshares' original implementation of polymorphic digital assets (PMDA). It aims to offer censorship resistance, neutrality, custody-less and permissionless trades, and collateral management. DittoETH supports pegged assets for fiat currencies, cryptocurrencies (both long and short positions), and commodities. To issue pegged assets, users must lock a high collateralization of staked ETH in the contract to ensure protocol solvency and price stability. The protocol's neutrality ensures open and full-access trading for any user.

Users can mint DittoAssets by providing collateral in the form of staked ETH, which allows them to gain price exposure to the pegged asset while enjoying the benefits of decentralized cryptocurrencies. The protocol uses an orderbook for matching shorters with long traders, where shorters mint pegged assets by matching with long traders, earning staking rewards and additional collateral. DittoAssets are backed by staked ETH, used as collateral when shorters match with long positions on the orderbook.

DittoAssets track the price of the underlying asset, enabling exposure to various asset classes. They are backed by a 170% collateralization ratio, facilitating DittoAsset minting and managing debt. Shorters must burn DittoAssets to exit, paying off debt and maintaining market stability. The protocol includes unique shorting rules, such as limit orders, to ensure standby liquidity and healthy short positions.

To maintain the peg of dUSD to USD, DittoETH employs mechanisms like redemptions, dynamic tithe adjustments, and forced bids. Liquidation parameters allow for liquidating under-collateralized short positions below 150% and 140% CR. The Treasury Asset Protection Pool (TAPP) supports stability by covering underpayments from under-collateralized short positions.

DittoETH maintains an orderbook for every market, with an automated matching engine for buying and selling pegged assets. It provides interest to collateralized shorts in the form of dETH, with yield distributions periodically updated. The value of DittoAssets is determined by on-chain Chainlink oracle price feeds.


## 2. Approach taken in evaluating the code base

**DittoETH Overview from Code4rena:**
I began by exploring the Code4rena audit overview for DittoETH ([link]( https://code4rena.com/audits/2024-03-dittoeth#toc-1-overview)). This provided a high-level understanding of the project's goals and key components. 

**Blog Documentation:**
Next, I examined the documentation on [DittoETH’s blog]( https://dittoeth.com/blog) to get more insights about the protocol.

**4naly3er Report Analysis:**
The [4naly3er report]( https://github.com/code-423n4/2024-03-dittoeth/blob/main/4naly3er-report.md) provided a useful external perspective. The report provides critical technical insights, particularly highlighting areas for gas optimization and security enhancements. Key issues include how `a = a + b` is more gas effective than `a += b` for state variables (excluding arrays and mappings) (GAS-1), Using assembly to check for `address(0)` (GAS-2),  Using `calldata` instead of `memory` for function arguments that do not get mutated (GAS-5), etc. Additionally, the report underscores the importance of why `require()` should be used instead of `assert()` (NC-3), why `constants` should be defined rather than using magic numbers (NC-4), etc. These findings are pivotal for refining the DittoETH codebase, focusing on optimizing contract efficiency while maintaining robust security protocols.

**In-Depth Codebase Review:**
Armed with comprehensive project knowledge, I delved into the codebase, file by file and I ran several tests on the contracts.
I first explored the scope of audit. I discovered that the project can be categorized into two(2) main groups: ``Facets and Libraries``. This categorization is based on the typical structure of smart contracts in Ethereum, where Facets are used to implement the logic of the protocol, and Libraries are reusable pieces of code that can be called by Facets to perform common tasks.



### Facets

Facets are contracts that contain the business logic of the protocol. They are designed to be modular, allowing for the addition or modification of functionality without affecting the rest of the system. Here's a brief overview of each of DittoETH's Facets:

- `BidOrdersFacet.sol`: This Facet is responsible for creating and matching bids. It includes functions for placing bids, matching bids with orders, and executing trades based on the bids.

- `ShortOrdersFacet.sol`: This Facet handles the creation and matching of short orders. Short orders are typically used in options trading to sell assets that the trader does not currently own, with the expectation that the price will decrease.

- `PrimaryLiquidationFacet.sol`: This Facet is focused on liquidation. 

- `BridgeRouterFacet.sol`: This Facet manages depositing and withdrawing LSTs .

- `ExitShortFacet.sol`: This Facet allows short sellers to exit their positions.

- `RedemptionFacet.sol`: This Facet provides the ability to swap dUSD for ETH, similar to the mechanism provided by Liquidity. 


### Libraries

Libraries are reusable pieces of code that can be called by Facets to perform common tasks. They help in reducing code duplication and improving code maintainability. Here's a brief overview of each Library:

- `LibBridgeRouter.sol`: A helper library used in the BridgeRouterFacet. 

- `LibBytes.sol`: A library used in the RedemptionFacet to save proposals in SSTORE2. 

- `LibOracle.sol`: This library is used to get price information, possibly leveraging Chainlink oracles for price feeds and providing backup mechanisms.

- `LibOrders.sol`: A library used by Order Facets to perform matching. 

- `LibSRUtil.sol`: A library of miscellaneous functions, including recovery functions, minimum short ERC requirements, and transfer functions. 

- `UniswapOracleLibrary.sol`: A library used to get Time-Weighted Average Price (TWAP) from Uniswap. 




## 3. Testing Suites

### Dependencies / External Imports: 
| Dependency / Import Path	| Count |
|-------------------------------|-------|
|@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol	|1|
|@openzeppelin/contracts/token/ERC20/IERC20.sol	|1|
|contracts/interfaces/IBridge.sol	|2|
|contracts/libraries/AppStorage.sol	|10|
|contracts/libraries/Constants.sol	|9|
|contracts/libraries/DataTypes.sol	|9|
|contracts/libraries/Errors.sol	|11|
|contracts/libraries/Events.sol	|6|
|contracts/libraries/LibAsset.sol	|7|
|contracts/libraries/LibBridge.sol	|1|
|contracts/libraries/LibBridgeRouter.sol	|2|
|contracts/libraries/LibBytes.sol	|1|
|contracts/libraries/LibOracle.sol	|5|
|contracts/libraries/LibOrders.sol	|7|
|contracts/libraries/LibSRUtil.sol	|4|
|contracts/libraries/LibShortRecord.sol	|7|
|contracts/libraries/LibVault.sol	|2|
|contracts/libraries/PRBMathHelper.sol	|11|
|contracts/libraries/UniswapOracleLibrary.sol	|1|
|contracts/libraries/UniswapTickMath.sol	|1|
|contracts/libraries/console.sol	|1|
|interfaces/IDiamond.sol	|5|
|solmate/utils/SSTORE2.sol	|2|


### Exposed Functions
This section lists functions that are explicitly declared public or payable. Please note that getter methods for public stateVars are not included.
|Public	|Payable|
|--------|------|
|18	|1|


|External|	Internal|	Private	|Pure|	View|
|-------|--------|---------|------|-----|
|18	|113	|29|	7	|29|

### StateVariables
|Total	|Public|
|---|---|
|4	|0|


### Source Units in Scope
**Source Units Analyzed**: 12
**Source Units in Scope**: 12 (100%)


|Type|File|Logic Contracts|Interfaces|Lines|nLines|nSLOC|Comment Lines|Complexity Score|
|-----|----|-------|------|-----|-----|-----|------|------|
|Library|contracts/libraries/LibBridgeRouter.sol|	1||	 	203|	200|	150|	30|	47|
|Library|	contracts/libraries/UniswapOracleLibrary.sol|	1|	1|	72|	54|	32|	15|	35|
|Library|contracts/libraries/LibOrders.sol|	1||	 	992|	919|	567|	242|	238|
|Library|contracts/libraries/LibOracle.sol|	1||	 	175|	162|	119|	22|	67|
|Library|contracts/libraries/LibSRUtil.sol|	1||	 	163|	151|	108|	19|	49|
|Library|contracts/libraries/LibBytes.sol|	1||	 	56|	56|	35|	22|	66|
|Facet	|contracts/facets/PrimaryLiquidationFacet.sol|	1||	 	291|	282|	166|	82|	81|
|Facet|	contracts/facets/RedemptionFacet.sol|	1||	 	404|	384|	232|	94|	169|
|Facet|	contracts/facets/BidOrdersFacet.sol|	1||	 	409|	370|	224|	112|	98|
|Facet|	contracts/facets/ShortOrdersFacet.sol|	1||	 	91|	84|	52|	20|	35|
|Facet|	contracts/facets/ExitShortFacet.sol|	1||	 	216|	199|	125|	42|	66|
|Facet|	contracts/facets/BridgeRouterFacet.sol|	1||	 	182|	182|	101|	56	|78|
||Totals	|12	|1	|3254	|3043	|1911	|756	|1029|



##  4. Architecture Assessment


<details>
  <summary>Details of each contract and details of each function</summary> 


## BidOrdersFacet.sol
The `BidOrdersFacet.sol` contract is specifically designed for managing bid orders in a marketplace. It is designed to work with the Ethereum blockchain. The contract is structured to handle the creation, matching, and settlement of bid orders, which are crucial for trading activities in the platform. It leverages several libraries and interfaces to ensure functionality and security.

##### Language:
Solidity

##### Roles and Access Mechanisms:
`Modifiers:` The contract uses modifiers like `isNotFrozen`, `onlyValidAsset`, and `nonReentrant` to control access and ensure certain conditions are met before executing functions. These modifiers help in preventing reentrancy attacks, ensuring that the contract is not frozen, and that the asset being interacted with is valid.

##### Access Control:
Functions like `createBid` and `createForcedBid` have specific access controls. For example, `createBid` can only be called by addresses that are not frozen and have a valid asset. `createForcedBid` is restricted to contracts that implement the `IDiamond` interface, ensuring that only authorized contracts can create bids on behalf of users.

##### Functions Overview:
- `createBid:` Allows users to create a bid order in the market. It checks for minimum bid size, updates the oracle price, and matches the bid with existing sell orders if possible.
- `createForcedBid:` Similar to `createBid` but is intended for exiting a short position. It is restricted to contracts that implement the `IDiamond` interface.
- `_createBid:` A private function that handles the core logic of creating a bid, including calculating the total ETH required, checking for sufficient ETH escrowed, and adding the bid to the market if no match is found.
- `bidMatchAlgo:` The matching algorithm for bids, which iterates through sell orders to find matches for the incoming bid. It handles partial fills and updates the state accordingly.
- `matchlowestSell:` Settles the lowest sell order and updates the incoming bid based on the match. It handles both short and ask orders, updating the state and balances accordingly.
- `matchIncomingBid:` Finalizes the settlement of the incoming bid, updating the state and balances based on the match. It also handles the removal of dust orders and updates the oracle price if necessary.
- `_getLowestSell:` A private function that retrieves the lowest sell order (either a short or an ask) based on the current state of the market.
- `_shortDirectionHandler:` A private function that determines the direction of short order matching based on the current state and the incoming bid.


##### Constants:
- `C.MARKET_ORDER:` A constant used to indicate that a bid is a market order.
- `C.TAIL:` A constant used to indicate the end of a linked list in the order book.
- `C.HEAD:` A constant used to indicate the beginning of a linked list in the order book.
- `C.DUST_FACTOR:` A constant used to determine the dust threshold for limit orders.

##### Variables:
- `s:` A storage struct that holds the state of the contract, including assets, vaults, and user balances.
- `LibOrders:` A library used for various order-related operations, such as updating the oracle price, adding bids, and matching orders.
- `LibOracle:` A library used for fetching and updating the oracle price.
- `LibAsset:` A library used for asset-related operations, such as checking the minimum bid size.
- `LibShortRecord:` A library used for managing short records, which are crucial for tracking short positions.

##### Important Libraries, Interfaces, and External Contracts:
- `PRBMathHelper:` A library providing fixed-point arithmetic operations, used for precise calculations in the contract.
- `IDiamond:` An interface that contracts must implement to be able to create forced bids.
- `LibOrders, LibOracle, LibAsset, LibShortRecord:` Libraries used for various operations related to orders, oracle prices, assets, and short records.
- `C:` A constants contract that holds various constants used throughout the contract.





## ShortOrdersFacet.sol
The `ShortOrdersFacet.sol` contract is designed for managing short orders. It is designed to be used within a larger contract system, as indicated by the use of modifiers and the import of various libraries and contracts. The contract is structured to handle the creation of limit short orders, which are a type of financial derivative that allows traders to profit from a decrease in the price of an asset.

##### Language:
 Solidity

##### Roles and Access Mechanisms:
`Modifiers:` The contract uses modifiers to enforce certain conditions before executing functions. For example, `isNotFrozen(asset)` ensures that the asset is not frozen before proceeding with the function, `onlyValidAsset(asset)` checks if the asset is valid, and `nonReentrant` prevents re-entrancy attacks.

##### Access Control:
The contract does not explicitly define roles or access control. However, the use of modifiers suggests that access control is implemented at a higher level, possibly in the contract that inherits from Modifiers or in the contract that uses ShortOrdersFacet.

##### Functions:
- `createLimitShort:` This function is the core of the contract. It allows users to create a limit short order. It takes several parameters, including the asset to be shorted, the price at which the short order is placed, the amount of the asset to be shorted, and arrays for order and short hint IDs. It performs several checks and calculations to ensure the order is valid and then adds the order to the system.

##### Constants:
- `C:` A constant contract that likely holds various configuration values, such as minimum collateral ratios (CRATIO_MAX_INITIAL) and other constants used in the contract.

##### Variables:
- `s:` A storage variable that refers to the state of the contract or the system it's part of. It's used to access and modify various aspects of the system, such as assets, orders, and user balances.

##### Libraries:
- `PRBMathHelper:` Provides mathematical operations for fixed-point arithmetic, which is crucial for financial calculations in DeFi applications.
- `Errors:` Contains custom error messages or codes used throughout the contract for error handling.
- `DataTypes:` Contains data type definitions used in the contract, such as `STypes`, `MTypes`, `O`, and `SR`.
- `AppStorage:` Contains the Modifiers contract that ShortOrdersFacet inherits from, which includes storage layout and access control mechanisms.
- `LibOrders:` Contains functions related to order management, such as creating orders and matching orders.
- `LibAsset:` Handles asset-related operations, such as calculating minimum ERC amounts and minimum ask ETH.
- `LibOracle:` Provides functions for fetching and updating oracle prices, which are crucial for determining the current market price of assets.
- `LibShortRecord:` Manages short records, which track the details of short orders.
- `LibSRUtil:` Contains utility functions for the contract, related to system recovery mode checks.



## PrimaryLiquidationFacet.sol
The `PrimaryLiquidationFacet` contract is designed to handle the liquidation of short positions. The contract is structured to facilitate the liquidation of short positions by forcing the shorters to place bids on the market. This process is crucial in maintaining the stability of the platform by ensuring that short positions do not become unsustainable.

##### Language:
 Solidity

##### Roles and Access Mechanisms:
- `Shorter:` The entity that holds a short position. Shorters are the ones being liquidated.
- `Liquidator:` The entity that initiates the liquidation process. In this contract, the liquidator is implicitly the caller of the liquidate function.
- `TAPP:` A special entity within the system that acts as a buffer for liquidations. It is responsible for absorbing the leftover collateral from partially liquidated shorts.

##### Access Control:
The contract uses modifiers like `isNotFrozen`, `nonReentrant`, and `onlyValidShortRecord` to control access to its functions. These modifiers ensure that the contract's functions can only be called under specific conditions, such as when the contract is not frozen, when the caller is not the shorters themselves, and when the short record is valid.


##### Functions:
- `Constructor:` Initializes the contract with the address of `dusd`, a stablecoin used within the platform.
- `liquidate:` The main function that initiates the liquidation process. It checks conditions, updates oracle prices, performs a forced bid, handles fees, and manages the liquidation outcome.
- `_checklowestSell:` Checks if there are eligible sells or if the lowest sell price is too high, which would prevent liquidation.
- `_setLiquidationStruct:` Sets up a memory struct with initial data needed for the liquidation process.
- `_performForcedBid:` Handles the setup and execution of making a forced bid. It calculates the bid price, updates the escrowed ETH, and performs the bid.
- `_liquidationFeeHandler:` Manages the distribution of liquidation fees between the TAPP and the caller.
- `_fullorPartialLiquidation:` Handles the accounting in the event of full or partial liquidations. It disburses collateral, updates short records, and manages the absorption of leftover shorts by TAPP.
- `min88:` A utility function that returns the minimum of two `uint88` values.

##### Constants:
- `C.HEAD, C.TAIL, C.SHORT_STARTING_ID:` Constants used to navigate data structures within the contract.

##### Variables:
- `dusd:` The address of the dusd stablecoin.
- `s:` A storage struct that holds the state of the contract, including short records, asks, and vault user data.

##### Libraries:
- `PRBMathHelper:` Provides fixed-point arithmetic operations.
- `Errors:` Contains custom error types for the contract.
- `Events:` Defines custom events for the contract.
- `DataTypes:` Contains data type definitions used throughout the contract.
- `AppStorage:` Provides modifiers and storage structs for the contract.
- `LibAsset:` Handles asset-related operations.
- `LibOrders:` Manages order-related operations.
- `LibOracle:` Interacts with the oracle for price data.
- `LibShortRecord:` Manages short record operations.
- `LibSRUtil:` Contains utility functions for short records.
- `Constants:` Contains constant values used in the contract.

##### Interfaces:
- `IDiamond:` An interface for interacting with the Diamond contract, which is a contract that can have multiple facets attached to it.


## BridgeRouterFacet.sol
The `BridgeRouterFacet` contract is designed to facilitate the bridging of assets between different blockchain networks. It is part of a larger system that involves multiple facets and libraries to handle various aspects of asset management, bridging, and yield optimization. 

##### Language:
 Solidity

##### Roles and Access Mechanisms:
- `Constructor:` The contract is initialized with the addresses of two bridges `(rethBridge and stethBridge)`. These addresses are stored as immutable variables, meaning they cannot be changed after the contract is deployed.

- `Modifiers:`
The contract uses modifiers for function access control. For example, `nonReentrant` and `nonReentrantView` are used to prevent reentrancy attacks. The `onlyDAO` modifier is used to restrict certain functions to be callable only by the DAO (Decentralized Autonomous Organization).

##### Functions:
- `getDethTotal:` Returns the total value of dETH in a given vault. This function is read-only and does not modify the state.
- `getBridges:` Returns an array of bridge addresses associated with a given vault. This function is also read-only.
- `deposit:` Allows users to deposit LST into the protocol, receiving equivalent value in dETH. It checks for minimum deposit requirements and updates the vault's dETH total.
- `depositEth:` Similar to deposit, but allows users to deposit ETH directly, which is then converted to dETH at a 1:1 ratio.
- `withdraw:` Allows users to withdraw LST from the protocol by specifying the amount of dETH to withdraw. It calculates any withdrawal fees and updates the vault's dETH total.
- `withdrawTapp:` A special withdrawal function callable only by the DAO, which withdraws LST from the protocol using the TAPP balance.
- `maybeUpdateYield:` Updates the vault's yield rate if the deposit amount is sufficiently large, deterring attempts to exploit yield rate updates.
- `_getVault:` A private helper function to determine the vault associated with a given bridge address.
- `_ethConversion:` A private helper function to calculate the ETH equivalent of a given amount of dETH, accounting for yield changes.

##### Constants:
- `C.MIN_DEPOSIT:` The minimum deposit amount required for deposits.
- `C.BRIDGE_YIELD_UPDATE_THRESHOLD:` The threshold for updating the vault's yield rate based on the total dETH amount.
- `C.BRIDGE_YIELD_PERCENT_THRESHOLD:` The percentage threshold for updating the vault's yield rate based on the deposit amount.

##### Variables:
- `rethBridge:` The address of the reth bridge.
- `stethBridge:` The address of the steth bridge.

##### Libraries
- `U256 and U88:` Libraries for handling uint256 and uint88 types with additional functionality.
- `LibBridge:` A library for operations related to bridges.
- `LibBridgeRouter:` A library for operations related to the bridge router.
- `LibVault:` A library for operations related to vaults.

##### Interfaces:
- `IBridge:` An interface for interacting with bridge contracts.



## ExitShortFacet.sol
The `ExitShortFacet` contract is designed for managing the exit of short. It involves short selling of assets, where users can short sell assets by providing collateral and borrowing the asset to sell. The contract is designed to handle the exit of these short positions, allowing users to either exit completely or partially, and ensuring that the system's integrity and security are maintained throughout the process.

##### Language:
Solidity

##### Roles and Access Mechanisms:
- `Constructor:` The contract is initialized with an address for `dusd`, which is a stablecoin or a token used within the platform.
- `Modifiers:` The contract uses several modifiers to restrict access to certain functions. These include `isNotFrozen`, `nonReentrant`, and `onlyValidShortRecord`. These modifiers ensure that the contract's state cannot be manipulated in unauthorized ways, such as by freezing the contract, preventing reentrancy attacks, and ensuring that only valid short records can be accessed or modified.

##### Functions:
- `exitShortWallet:` Allows a user to exit a short position by burning ERC tokens from their wallet. It updates the ERC debt, checks if the buyback amount is valid, and if the debt is fully paid, it refunds the collateral.
- `exitShortErcEscrowed:` Similar to exitShortWallet, but it allows the user to exit a short position by burning ERC tokens from their escrowed balance. It also checks for sufficient ERC escrowed and updates the collateral and debt accordingly.
- `exitShort:` This function allows a user to exit a short position by placing a bid on the market. It involves updating the oracle price, checking if the short order is cancelled, and then proceeding with the bid. It handles partial exits and ensures that the collateral ratio is maintained.
- `getCollateralRatioNonPrice:` A helper function that calculates the collateral ratio of a short position without considering the price.

##### Constants:
- `dusd:` An immutable address for the dusd token, likely a stablecoin used within the platform.

##### Variables:
- `Asset:` A storage variable representing the asset being shorted.
- `short:` A storage variable representing the short record of a user.
- `ercDebt:` A variable representing the ERC debt of a short position.
- `collateral:` A variable representing the collateral of a short position.

##### Libraries:
- `U256, U80, U88:` Libraries for handling fixed-size unsigned integers used for precise arithmetic operations.
- `LibSRUtil:` A library for utility functions related to short records, such as updating ERC debt and disbursing collateral.
- `LibAsset:` A library for asset-related operations, such as burning ERC tokens.
- `LibOrders:` A library for handling orders, used for placing bids in the exitShort function.
- `LibShortRecord:` A library for managing short records, including deleting short records.

##### Interfaces:
- `IDiamond:` An interface for interacting with the Diamond contract, which is a contract that implements the Diamond pattern for upgradable smart contracts


## RedemptionFacet.sol
The `RedemptionFacet.sol` contract focuses on the redemption process, allowing users to redeem their short positions under certain conditions. The contract uses a modular approach, importing various libraries and utilities to perform its operations. It also interacts with other contracts and libraries to manage assets, orders, and user data.

##### Language:
Solidity

##### Roles and Access Mechanisms:
- `Modifiers:` The contract uses modifiers like `isNotFrozen` and `nonReentrant` to control access and prevent reentrancy attacks. These modifiers are applied to functions to ensure that they can only be called under specific conditions, such as when the contract is not frozen and when the function is not being re-entered.
- `Access Control:` The contract uses a combination of internal and external functions to control access. Internal functions can only be called from within the contract or contracts that inherit from it, while external functions can be called from other contracts or externally by users.

##### Functions:
- `validRedemptionSR:` Checks if a short record is valid for redemption based on its status, ercDebt, and whether the proposer is not the shorter.
- `proposeRedemption:` Allows users to propose redemption for an array of short records. It performs various checks, updates the state, and calculates the redemption fee.
- `disputeRedemption:` Allows users to dispute a proposed redemption. It checks the validity of the dispute and updates the state accordingly.
- `claimRedemption:` Allows the redeemer to claim the collateral from verified redemption candidates after the dispute period has passed.
- `claimRemainingCollateral:` Allows the shorter to claim the leftover collateral from a short record that has been fully redeemed but not claimed by the redeemer.
- `_claimRemainingCollateral:` A private function used to handle the logic of claiming remaining collateral.
- `calculateRedemptionFee:` Calculates the redemption fee based on the collateral redeemed and the `ercDebt` redeemed.


##### Constants:
- `C:` A library that contains various constants used throughout the contract, such as `MAX_REDEMPTION_CR`, `ONE_THIRD`, and `SECONDS_DECAY_FACTOR`.

##### Variables:
- `s:` A storage pointer to the contract's state, which includes mappings for assets, users, and short records.

##### Libraries:
- `PRBMathHelper:` Provides various mathematical operations for fixed-point arithmetic.
- `Errors:` Contains custom error types for the contract.
- `Events:` Defines custom events for the contract.
- `LibAsset:` Handles asset-related operations.
- `LibShortRecord:` Manages short record data.
- `LibSRUtil:` Utility functions for short records.
- `LibOracle:` Interacts with the oracle for price data.
- `LibOrders:` Manages order-related operations.
- `LibBytes:` Utility functions for bytes manipulation.
- `Constants:` Contains various constants used in the contract.
- `SSTORE2:` Utility for writing to storage using `SSTORE2`.
- `console:` Provides console logging capabilities.

##### Interfaces and External Contracts:
- `Modifiers:` Inherits from a contract that defines modifiers like `isNotFrozen` and `nonReentrant`.
- `LibSRUtil`, `LibShortRecord`, `LibOracle`, `LibOrders`, `LibBytes`, `Constants`, `SSTORE2`, and console are all external libraries or contracts that the RedemptionFacet contract interacts with to perform its operations.


## LibBridgeRouter.sol
The `LibBridgeRouter` is designed to facilitate operations related to bridging specifically within a vault system. It involves bridging assets between different blockchains or within the same blockchain but across different vaults. 

##### Language:
 Solidity

##### Roles and Access Mechanisms:

- `Access Control:` The library does not explicitly implement access control mechanisms like Ownable or AccessControl. Instead, it relies on the context in which it is used to determine access. For example, the `addDeth` function modifies the state of the contract based on the `msg.sender`, which is the address of the caller. This implies that the contract using this library must have its own access control mechanisms in place to ensure that only authorized users can call these functions.

##### Functions:
- `addDeth:` This function is used to credit a user's account with dETH and bridge credit if applicable. It updates the user's bridge credit and the total dETH in the vault.
- `assessDeth:` Determines how much dETH is not covered by bridge credits during withdrawal. It calculates the amount of dETH that needs to be withdrawn from the vault, considering the user's bridge credits.
- `withdrawalFeePct:` Calculates the withdrawal fee percentage based on the premium/discount differential between `rETH` and `stETH` markets. This function is only applicable to `VAULT.ONE`, which has mixed LST.
- `transferBridgeCredit:` Transfers bridge credit from one user to another when an NFT SR is transferred. This function is used to deter workarounds to the bridge credit system.
- `removeDeth:` Updates the user's account upon dETH withdrawal, reducing the amount of dETH escrowed and the total dETH in the vault.

##### Constants:
- `VAULT:` Constants representing different vaults within the system.
- `C.ROUNDING_ZERO:` A constant used for rounding purposes, likely to avoid floating-point issues.

##### Variables:
- `AppStorage:` A struct that holds the global state of the application, including vaults and user data.
- `STypes.VaultUser:` A struct that represents a user within a vault, including their bridge credits and escrowed ETH.

##### Libraries Used:
- `U256 and U88:` Libraries for handling fixed-point arithmetic with 256-bit and 88-bit precision, respectively.
- `OracleLibrary:` A library for fetching and calculating time-weighted average prices (TWAPs) for assets.

##### Interfaces:
- `IBridge:` An interface for interacting with bridge contracts used to fetch the current dETH value for bridging assets.


## LibBytes.sol
`LibBytes.sol` is designed to facilitate operations related to byte manipulation, specifically tailored for the context of reading proposal data from a storage system. It's designed to work with a specific data structure, MTypes.ProposalData, which is not defined within this library but is imported from another contract, DataTypes.sol.

##### Language:
 Solidity

##### Library:
The contract is a library, which means it's a collection of functions that can be used by other contracts but cannot be deployed as a standalone contract. Libraries are often used to encapsulate reusable code.

##### Functions:
- `readProposalData:` This function reads proposal data from a storage system. It takes two parameters: an address `SSTORE2Pointer` which points to the location of the data in storage, and a uint8 `slateLength` which specifies the number of proposal data entries to read. The function returns an array of `MTypes.ProposalData` structs, which are decoded from the byte data read from storage.

##### Libraries Used:
- `MTypes:` Imported from contracts/libraries/DataTypes.sol. This library contains the definition of the MTypes.ProposalData struct used in the readProposalData function.
- `SSTORE2:` Imported from solmate/utils/SSTORE2.sol. This library provides functionality for reading data from storage, specifically using a method called read.

## LibOracle.sol
The `LibOracle` contract is designed to interact with price oracles, specifically Chainlink oracles, to fetch and manipulate price data for various assets. The library is designed to be used within a smart contract system, providing functionalities related to price fetching, circuit breaker mechanisms for price data validation, and utilities for handling price data.

##### Language:
Solidity


##### Functions:
- `getOraclePrice:` Fetches the price of an asset from a Chainlink oracle. It first checks if the asset has a specific oracle set; if not, it uses a base oracle. It includes circuit breaker logic to handle invalid or deviated prices.
- `baseOracleCircuitBreaker:` A private function that implements circuit breaker logic for the base oracle. It checks for invalid data fetches and price deviations, and if necessary, falls back to a Time-Weighted Average Price (TWAP) calculation.
- `oracleCircuitBreaker:` Another private function that implements circuit breaker logic for non-base oracles. It checks for invalid data fetches.
- `twapCircuitBreaker:` A private function that calculates the TWAP price as a fallback mechanism when other price sources are invalid or deviated.
- `setPriceAndTime:` Sets the price and time for an asset. This is likely used to store the latest fetched price and its timestamp.
- `getTime:` Retrieves the timestamp of the last price update for an asset.
- `getPrice:` Retrieves the latest price of an asset.
- `getSavedOrSpotOraclePrice:` Determines whether to return a saved price or fetch the current spot price based on the time elapsed since the last update.

##### Constants:
- `C.BASE_ORACLE_DECIMALS:` A constant used for adjusting the precision of the base oracle price.
- `C.UNISWAP_WETH_BASE_AMT:` A constant related to the amount of WETH used for TWAP calculations.
- `C.DECIMAL_USDC:` A constant related to the decimal precision of USDC, used in TWAP calculations.

##### Variables:
- `AppStorage storage s:` A reference to the application's storage, like a struct that holds various state variables related to the contract's functionality.

##### Libraries:
- `U256:` A library for handling unsigned 256-bit integers, providing arithmetic operations with overflow/underflow checks.

##### Interfaces:
- `AggregatorV3Interface:` Interface for interacting with Chainlink oracles.
- `IERC20:` Interface for interacting with ERC20 tokens, used for checking WETH balance in the TWAP calculations.
- `IDiamond:` Interface for interacting with a diamond contract, which is a pattern for managing contract upgrades and storage.


## LibOrders.sol

The `LibOrders.sol` contract is a library designed for managing orders in the protocol. It provides a set of functions for handling various aspects of order management, including adding, matching, and canceling orders, as well as updating the state of the market based on these actions. The contract is structured to be used within a larger system, as it imports several other libraries and interfaces, indicating a modular design approach.

##### Language:
Solidity

##### Functions:
- `getOffsetTime:` Calculates the time difference between the current block timestamp and a predefined starting time. This function is used for time-based calculations or restrictions within the contract.
- `convertCR:` Converts a collateralization ratio (CR) from a uint16 format to a uint256 format, adjusting for decimal places.
- `increaseSharesOnMatch:` Increases the shares of a user based on the matched order. This function is crucial for rewarding users for their participation in the market.
- `currentOrders:` Returns an array of current orders for a given asset. This function is useful for displaying the current state of the market to users.
- `isShort:` Determines if an order is a short order. This function is used to differentiate between different types of orders.
- `addBid, addAsk, addShort:` These functions add a bid, ask, or short order to the market. They handle the logic for adding new orders, including updating the state of the market and the user's account.
- `addSellOrder:` A private function that adds a sell order to the market, differentiating between short and ask orders.
- `addOrder:` A private function that adds an order to the market, reusing order IDs for gas optimization.
- `cancelOrder, matchOrder:` These functions handle the cancellation and matching of orders, respectively. They update the state of the market and the user's account accordingly.
- `findPrevOfIncomingId:` Finds the previous order ID for a new incoming order, ensuring the order is placed in the correct position in the market.
- `verifyId:` Verifies the position of an order based on its price and order type.
- `getOrderId:` Returns the ID of an order based on its price and order type.
- `_updateOrders:` Updates the order IDs after a match, ensuring the market state is correctly updated.
- `sellMatchAlgo:` The matching algorithm for sell orders, including handling the logic for matching bids with incoming asks.
- `matchIncomingSell, matchIncomingAsk, matchIncomingShort:` These functions handle the final settlement of incoming sell, ask, or short orders, updating the state of the market and the user's account accordingly.
- `matchHighestBid:` Matches the highest bid with an incoming sell order, updating the state of the market and the user's account accordingly.
- `_updateOracleAndStartingShort:` Updates the oracle price and the starting short ID based on the current market conditions.
- `updateOracleAndStartingShortViaThreshold, updateOracleAndStartingShortViaTimeBidOnly:` These functions update the oracle price and the starting short ID based on specific conditions, such as price deviations or time intervals.
- `updateStartingShortIdViaShort:` Updates the starting short ID based on the incoming short order.
- `findOrderHintId:` Finds the hint ID for an order, which is used to optimize the order placement process.
- `cancelBid, cancelAsk, cancelShort:` These functions handle the cancellation of bid, ask, or short orders, updating the state of the market and the user's account accordingly.
- `handlePriceDiscount:` Handles the logic for price discounts, adjusting the tithe percentage based on the discount.
- `min, max:` Utility functions for finding the minimum and maximum of two values.

##### Constants:
The contract uses several constants defined in the Constants.sol library, such as `C.STARTING_TIME`, `C.HEAD`, `C.TAIL`, `C.MIN_DURATION`, `C.TWO_DECIMAL_PLACES`, `C.EXACT`, `C.PREV`, `C.NEXT`, `C.MAX_TITHE`, and `C.INITIAL_TITHE_MOD`. These constants are used throughout the contract for various purposes, such as defining the starting time of the market, the head and tail IDs for the order list, the minimum duration for an order, and the maximum tithe percentage.

##### Libraries:
- `PRBMathHelper:` Provides mathematical operations with overflow and underflow checks.
- `AppStorage:` Manages the global state of the application.
- `DataTypes:` Defines the data types used throughout the contract.
- `Errors:` Defines error messages for the contract.
- `Events:` Defines events that the contract can emit.
- `LibAsset:` Provides functions related to asset management.
- `LibOracle:` Provides functions related to oracle data.
- `LibShortRecord:` Provides functions related to short record management.
- `LibVault:` Provides functions related to vault management.
- `Constants:` Provides constant values used throughout the contract.

##### Interfaces:
- `IDiamond:` An interface for interacting with the Diamond pattern, a design pattern for upgradable contracts.


## LibSRUtil.sol
The contract `LibSRUtil.sol` provides utility functions for managing short records. It involves short selling and yield farming, given the context of collateral, yield rates, and asset management. 

##### Access Mechanisms:
The contract does not explicitly define roles or access mechanisms.

##### Functions:
- `disburseCollateral:` This function is used to distribute collateral from a short position. It calculates yield based on the collateral and the difference in yield rates, then distributes this yield to the appropriate parties.
- `checkCancelShortOrder:` Checks if a short order should be cancelled based on its status and other conditions. It's used to ensure that short orders are only cancelled under the right circumstances.
- `checkShortMinErc:` Ensures that a short record does not leave a "dust" amount of ERC debt, which could be too small to be worthwhile. It cancels the short order if the remaining ERC debt is below a minimum threshold.
- `checkRecoveryModeViolation:` Checks if a short record violates the recovery collateral ratio (CR) during a recovery mode. This is a safety mechanism to prevent excessive risk during volatile market conditions.
- `transferShortRecord:` Transfers a short record from one address to another. This function handles the transfer of collateral and updates the short record's status and ownership.
- `updateErcDebt:` Updates the ERC debt of a short record based on the current debt rate. This is used to adjust the debt as the yield rate changes.

##### Constants:
- `C.YIELD_DELAY_SECONDS:` A constant that likely defines the delay before yield can be distributed to a short position. This is used to prevent immediate distribution of yield to the short position's owner.

##### Variables:
- `AppStorage storage s:` A reference to the global state of the application. This is used throughout the contract to access and modify the state.

##### Libraries and Interfaces:
- `U88 and U256:` Libraries for handling 88-bit and 256-bit unsigned integers, respectively. These are used for precise arithmetic operations.
- `STypes and SR:` Custom types and enums likely defined elsewhere in the system. These are used to represent various data structures and states within the contract.
- `AppStorage and appStorage:` The global state of the application and a function to access it. This is crucial for managing the state of short records and other data.
- `LibOrders, LibShortRecord, LibAsset, Errors, LibBridgeRouter:` Other libraries and contracts that `LibSRUtil` interacts with. These provide additional functionality for managing orders, short records, assets, error handling, and bridging between different blockchain networks or contracts.


## UniswapOracleLibrary.sol
The `UniswapOracleLibrary.sol` contract is designed to provide utility functions for interacting with Uniswap V3 pools, specifically for calculating token amounts and prices based on pool data. This library is particularly useful for developers looking to integrate Uniswap V3's advanced features, such as concentrated liquidity and time-weighted average price (TWAP) calculations, into their own smart contracts.

##### Roles and Access Mechanisms:
This contract does not define any roles or access mechanisms as it is a library. Libraries in Solidity are collections of functions that can be used by other contracts. They do not have their own state or storage, and thus do not have roles or access controls. Instead, the contracts that import and use this library will define and manage access controls.

##### Functions:
- `getQuoteAtTick:` This function calculates the amount of a quote token that can be obtained for a given amount of a base token, given a specific tick value. It uses the `TickMath.getSqrtRatioAtTick` function to get the square root price ratio at the given tick, and then calculates the quote amount based on this ratio. The calculation is done with high precision to avoid overflow issues.
- `estimateTWAP:` This function estimates the time-weighted average price (TWAP) of a token pair over a specified period. It takes into account the amount of the base token and the time in seconds ago from which to calculate the TWAP. It uses the `IUniswapV3Pool.observe` function to get the cumulative tick and liquidity values at the specified time and the current block timestamp. It then calculates the tick difference and uses it to estimate the price.

##### Constants:
- `Errors:` An imported library that defines custom error types for the contract.
- `TickMath:` An imported library that provides mathematical operations related to ticks in Uniswap V3.
- `U256:` An imported library that provides high-precision arithmetic operations.

##### Libraries:
- `Errors:` Used for defining custom error types.
- `TickMath:` Used for mathematical operations related to ticks.
- `U256:` Used for high-precision arithmetic operations.

##### Interfaces:
- `IUniswapV3Pool:` An interface that defines the functions that a Uniswap V3 pool contract must implement. This interface is used to interact with Uniswap V3 pools.

</details>




## 5. Software Engineering Considerations

### Modularity and Reusability:
The contracts in DittoETH exhibit modularity by inheriting from several interfaces and contracts, suggesting components are designed for reuse and extension. This approach aligns with solid software engineering principles, promoting maintainability and scalability.

### Design Patterns and Best Practices:
Utilization of established design patterns, such as interface-based programming and reentrancy guards, indicates adherence to industry best practices. These patterns enhance the contract’s robustness and security.

### Code Readability and Maintainability:
The protocol's structure, naming conventions, and comments suggest an emphasis on readability and maintainability, crucial for long-term management and updates.

### Security:
Security is a critical aspect, especially given the DeFi context. The contract shows awareness of common vulnerabilities (like reentrancy attacks) and includes mechanisms to mitigate them. Continuous security audits and reviews are essential due to the evolving nature of smart contract exploits.

### Efficiency and Optimization:
Given the contract's complexity, there's a need for thorough analysis and testing to ensure efficiency, especially in gas usage.

### Error Handling and Input Validation:
The use of custom error messages and checks indicates a proactive approach to error handling and input validation, critical for robustness and user trust.

### Inter-operability and Standards Compliance:
Compliance with ERC standards and the ability to interact with multiple token types demonstrate a high level of interoperability, a significant factor in the Ethereum ecosystem.

### Testing and Documentation:
Given the complexity, comprehensive testing (unit tests, integration tests) and detailed documentation are vital for ensuring the contract works as intended and to facilitate future development.

### Upgradeability:
The potential for future upgrades and modifications should be considered, especially in a rapidly evolving domain like DeFi. However, the contracts doesn’t explicitly mention upgrade mechanisms.

### Dependency Management:
Reliance on external libraries like `OpenZeppelin` means the contract's security and functionality are partly dependent on these external components. Keeping these dependencies updated and secure is crucial.


## 6. Quality of Codebase
In general, the quality of DittoETH’s code base is quite high and easy to understand. The huge number of comments makes it very easy to determine what a particular function is intended for. After an in-depth analysis of the DittoETH codebase, it's clear that the quality is Excellent, showcasing thoughtful architecture and intricate inter-function logic. The codebase demonstrates a sophisticated understanding of blockchain mechanics.



## 7. Risks related to the project
Evaluating the DittoETH project's risk model involves a thorough analysis of various aspects, including administrative, systemic, technical, and integration risks. These risks must be carefully considered to understand their impact on the project's security, functionality, and reliability.


### Administrative risk

The presence of modifiers in `BidOrdersFacet.sol` like `isNotFrozen`, `onlyValidAsset`, `nonReentrant`, and `onlyDiamond` are used to restrict access to certain functions. These are good practices for preventing unauthorized access  and similar administrative functions in other contracts imply a level of centralization.
The `createForcedBid` function in the `BidOrdersFacet.sol` is only callable by contracts that implement the `onlyDiamond` modifier. This function allows for the creation of bid orders for exiting a short, which could be a point of centralization if the decision to exit a short is centralized. However, the mitigation here is that this function is explicitly designed to be callable only by specific contracts, reducing the risk of abuse.

##### Mitigation Strategies:

-	Introduce time-locks for sensitive operations, providing users with a window to react to unfavorable changes.
-	For critical functions that require admin privileges, consider implementing multi-signature wallets to require approval from multiple parties before executing sensitive operations.
-	 Implement a decentralized governance model where proposals to change critical parameters or logic are voted on by token holders.


### Systemic Risks

##### Dependencies on External Protocols: 
The Project imports several libraries and interfaces, such as `U256`, `U88`, `U80` from `PRBMathHelper.sol`, `IDiamond` from `IDiamond.sol`, `PRBMathHelper.sol`, `Errors.sol`, `Events.sol`, `AppStorage.sol`, `DataTypes.sol`, `LibAsset.sol`, `LibShortRecord.sol`, `LibSRUtil.sol`, `LibOracle.sol`, `LibOrders.sol`, `LibBytes.sol`, `Constants.sol`, `SSTORE2.sol`, `console.sol`,etc some of which have been previously audited and are not in scope in this audit. These dependencies proof that the contract relies on external libraries for mathematical operations and for interacting with other contracts or protocols. If any of these libraries or the protocols they interact with are compromised, it could introduce systemic risks.


##### Inter-Contract Dependencies:
The functionality of the system heavily relies on the seamless interaction between contracts like `LibOracle.sol`, `LibOrders.sol`, and various libraries


##### Mitigation Strategies:
- Regularly update and audit the list of supported protocols and bridges to ensure their security and reliability.
- Implement robust error handling and fallback mechanisms to manage failures in inter-contract calls.


### Technical Risks:
##### Smart Contract Vulnerabilities: 
Common risks like reentrancy attacks, overflow/underflow, and unhandled exceptions are pertinent. Although the project demonstrates good security practices, the complexity of functions like `claimRedemption`  and  `exitShort` increases the surface area for potential exploits.

##### Gas Optimization: 
As highlighted in the 4naly3er report, there are several areas where gas optimization can be improved. Inefficient gas usage could make the system economically unviable in the long term, especially during high network congestion.

##### Mitigation Strategies:
- Continuously audit and test the smart contracts, especially after major updates or integration of new features.
- Implement the suggested gas optimizations to ensure economic efficiency.



### Integration Risks
##### Inter-operability with Multiple Chains:
As a cross-chain solution, integration risks include handling different blockchain protocols, transaction finality times, and consensus mechanisms.

##### External Dependency: 
The project's reliance on prices from the Oracle, OpenZeppelin and other protocols for cross-chain functionality introduces risks associated with these external systems.


##### Mitigation Strategies:
- Conduct thorough testing for each blockchain integration, considering their unique characteristics and potential edge cases.
- Monitor the external protocols and adapt to changes or updates in their systems.




## 8. Recommendations:

1. Consider using OpenZeppelin’s SafeCast library to prevent unexpected overflows when casting from various type int/uint values

File: contracts/libraries/LibOracle.sol

//@audit `price` is getting converted from `int256` to `uint256`
```solidity
43:             uint256 priceInEth = uint256(price).div(uint256(basePrice));
```

//@audit `basePrice` is getting converted from `int256` to `uint256`
```solidity
43:             uint256 priceInEth = uint256(price).div(uint256(basePrice));
```

//@audit `oraclePrice` is getting converted from `uint256` to `uint80`
```solidity
151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
```


2.  File: contracts/facets/RedemptionFacet.sol
The `claimRemainingCollateral` function needs a little tweak in the way the function reads the `decodedProposalData` array.

Here's the relevant code snippet:

```solidity
MTypes.ProposalData[] memory decodedProposalData =
    LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];
```

The function reads the `decodedProposalData` array up to `claimIndex + 1`, but then it accesses the element at `claimIndex`. This means that if `claimIndex` is equal to the length of the array, it will result in an out-of-bounds access, causing the contract to revert with an error.

This can affect the contract's logic in the following way:

1. If a shorter tries to call `claimRemainingCollateral` with a `claimIndex` that is equal to the length of the `decodedProposalData` array, the contract will revert, and the shorter will not be able to claim their remaining collateral.

2. This could potentially lead to situations where collateral is locked in the contract, unable to be claimed by the rightful owner (the shorter).

The code should be modified to read the `decodedProposalData` array up to the correct length, or it should include a check to ensure that `claimIndex` is always within the bounds of the array. This will prevent out-of-bounds accesses and ensure that the `claimRemainingCollateral` function works as intended.

Overall, while this issue may not completely break the contract's functionality, it can lead to unexpected behavior, potential exploits, and collateral being locked in the contract. It's important to address this issue to ensure the contract's reliability and security.



## 9. Conclusion
In general, The DittoETH’s protocol presents a well-designed architecture. The DittoETH protocol exhibits strengths, comprehensive testing, and detailed documentation, we believe the team has done a good job regarding the code. However, there is room for improvement, including governance features, optimization, and code documentation. Systemic risks include dependencies on external protocols and inter-contract dependencies, while technical risks involve certain contracts and functions and gas optimization. It is also highly recommended that the team continues to invest in security measures such as mitigation reviews, audits, and bug bounty programs to maintain the security and reliability of the project.


## 10. Time Spent
36 hours


### Time spent:
36 hours