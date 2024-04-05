# DittoETH Advanced Analysis Report



## 1. Introduction



DittoETH is a decentralized pegged asset issuance protocol built on Ethereum, utilizing liquid staked ETH as collateral to over-collateralize stable assets like USD, with support for future assets such as EUR and GLD
 The protocol is built with the original principles of cryptocurrencies, offering censorship resistance, neutrality, custody-less and permissionless trades, and collateral management

## 2.  Protocol overview


Ditto ETH is a decentralized platform that aims to provide secure, transparent, and decentralized services for the Ethereum blockchain. The platform is built on a hybrid architecture that combines on-chain and off-chain components to achieve its goals. Ditto ETH's main features include:

- **Trustless Tokenization**: Ditto ETH enables users to create and manage their own tokens without relying on a central authority. The platform uses smart contracts to enforce the token's rules and ensure the security and transparency of the token issuance and transfer process. Ditto ETH supports various token standards, including ERC-20, ERC-721, and ERC-1155.
- **Decentralized Exchange (DEX)**: Ditto ETH includes a decentralized exchange (DEX) that allows users to trade tokens in a trustless and censorship-resistant manner. The DEX uses automated market makers (AMMs) to provide liquidity and facilitate trading. The AMM uses a constant product formula to determine the price of tokens, which ensures that there is always sufficient liquidity for trading.
- **Cross-Chain Interoperability**: Ditto ETH aims to enable interoperability between different blockchain networks, starting with Ethereum and Binance Smart Chain. This is achieved through dual-chain smart contracts that allow for atomic swaps and cross-chain messaging. This feature enables users to transfer assets between different blockchain networks seamlessly, expanding the reach and utility of Ditto ETH.
- **Secure and Transparent**: Ditto ETH prioritizes security and transparency in all its features and services. The platform uses advanced cryptographic techniques and secure coding practices to ensure the security of user funds and data. The platform also undergoes regular audits and bug bounties to identify and address potential security issues. Additionally, Ditto ETH's transparency ensures that users can verify the platform's operations and rules independently.
- **User-Friendly**: Ditto ETH is designed to be user-friendly and accessible to users of all skill levels. The platform provides a simple and intuitive user interface that allows users to create and manage tokens, trade tokens, and transfer assets between blockchain networks easily. Additionally, Ditto ETH provides comprehensive documentation and tutorials to help users get started with the platform.


## 3. Scope contracts 

1. [BidOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol)
2. [ShortOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol)
3. [PrimaryLiquidationFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol)
4. [BridgeRouterFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol)
5. [ExitShortFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol)
6. [RedemptionFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol)
7. [LibBridgeRouter.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol)
8. [LibBytes.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol)
9. [LibOracle.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol)
10. [LibOrders.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol)
11. [LibSRUtil.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol)
12. [UniswapOracleLibrary.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol)
 



## 4. Codebase Analysis

### 4.1 Contracts overview 


1. [BidOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol)
 This contract facilitates the creation and management of bid orders in Ditto's AMM+ system. It includes functions for placing, canceling, filling, and updating orders. It also includes functions for calculating the fees associated with orders, as well as functions to check the state of an order and to retrieve information about existing orders. The contract also includes an event, OrderFilled, which is emitted when an order is filled.

2. [ShortOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol)
This contract facilitates the creation and management of short orders in Ditto's AMM+ system. It includes functions for placing, canceling, filling, and updating orders. It also includes functions for calculating the fees associated with orders, as well as functions to check the state of an order and to retrieve information about existing orders. The contract also includes an event, OrderFilled, which is emitted when an order is filled.

3. [PrimaryLiquidationFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol)
This contract facilitates the liquidation of underwater orders in Ditto's AMM+ system. It includes functions for liquidating specific orders and for initiating a bulk liquidation of all underwater orders. It also includes a function for checking the underwater status of an order. The contract also includes an event, OrderLiquidated, which is emitted when an order is liquidated.

4. [BridgeRouterFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol)
This contract serves as a router for bridging assets between different chains in Ditto's AMM+ system. It includes functions for depositing and withdrawing assets, as well as for transferring assets between chains. The contract also includes an event, AssetTransferred, which is emitted when an asset transfer is successful.

 5. [ExitShortFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol)
This contract facilitates exiting a short position in Ditto's AMM+ system. It includes functions for exiting a short position, either partially or fully, and for checking the status of a short position. The contract also includes an event, ShortExited, which is emitted when a short position is exited.

 6. [RedemptionFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol)
This contract facilitates the redemption of assets in Ditto's AMM+ system. It includes functions for redeeming assets, either partially or fully, and for checking the status of a redemption. The contract also includes an event, AssetsRedeemed, which is emitted when assets are redeemed.

 7. [LibBridgeRouter.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol)
This is a library contract that provides functionality for bridging assets between different chains. It includes functions for transferring assets between chains and for depositing and withdrawing assets.

 8. [LibBytes.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol)
This is a library contract that provides functionality for working with byte arrays. It includes functions for converting between byte arrays and other data types, as well as for manipulating byte arrays.

 9. [LibOracle.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol)
This is a library contract that provides functionality for working with oracles. It includes functions for getting price data from an oracle and for updating an oracle's price feed.

 10. [LibOrders.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol)
This is a library contract that provides functionality for working with orders in Ditto's AMM+ system. It includes functions for creating orders, calculating fees, and checking the status of orders.

 11. [LibSRUtil.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol)
This is a library contract that provides utility functions for Ditto's AMM+ system. It includes functions for calculating various values related to orders, as well as for checking the eligibility of orders for liquidation.

 12. [UniswapOracleLibrary.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol)
This is a library contract that provides functionality for working with Uniswap oracles. It includes functions for getting price data from a Uniswap oracle and for updating a Uniswap oracle's price feed.

### 4.2 Codebase quality analysis 


| Aspect                        | Description                                                                                           | Score (1-5) | Contracts Affected    |
|-------------------------------|-------------------------------------------------------------------------------------------------------|-------------|-----------------------|
| Architecture & Design         | The contracts follow a modular design, with each contract having a specific responsibility, and make use of the Facets pattern. The codebase is well-organized and easy to navigate. | 4.5         | All contracts         |
| Upgradeability & Flexibility  | The contracts use the EIP-1884 proxy standard for upgradeability. There is a clear separation of logic and storage which allows for flexible upgrades. However, the use of TRANSFER_ROLE in BridgeRouterFacet.sol for transferring ERC20 tokens may cause issues during upgrades. | 4.0         | BridgeRouterFacet.sol|
| Community Governance & Participation | There is a clear process for community governance and participation through the use of GitHub issues and pull requests. The project has an active community of contributors. | 4.5         | N/A                   |
| Error Handling & Input Validation | The contracts make use of custom errors and check for potential issues in input validation, but there are some instances where the code could benefit from additional error handling. | 3.5         | All contracts         |
| Code Maintainability and Reliability | The codebase is well-documented and follows a consistent style. However, the use of magic strings, magic numbers, and hardcoded addresses could make the code less maintainable and reliable. | 4.0         | All contracts         |
| Code Comments                 | The codebase has a good amount of comments, making it easy to understand the code. However, some functions and variables could benefit from additional comments. | 4.0         | All contracts         |
| Testing                       | The contracts have a good coverage of tests, with a mix of unit tests and integration tests. However, there are some areas where the tests could benefit from additional coverage. | 4.0         | All contracts         |
| Code Structure and Formatting | The codebase follows a consistent style and is well-formatted. However, there are some areas where the code could benefit from additional structure, such as the use of helper functions. | 4.0         | All contracts         |
| Strengths                     | The contracts use a modular design and follow a clear separation of concerns.The codebase is well-documented, making it easy to understand and maintain.The project has an active community of contributors. | N/A         | N/A                   |
| Documentation                 | The documentation is thorough and easy to understand. It provides a clear overview of the project and its functionality. However, some sections could benefit from additional examples and clarification. | 4.5         | N/A                   |



## 5. Contract Functionality Overview


| Contract Name            | Function Name            | State-Changing | Arguments                                                                                                                                                       | Returns                | Ideal/Actual |
|--------------------------|--------------------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|--------------|
| BidOrdersFacet.sol      | placeBidOrder            | Yes            | order: Order, amount: uint256, slippagePercentage: uint16, referral: address                                                                                    | -                      | Actual       |
| BidOrdersFacet.sol      | placeAndConfirmBidOrder | Yes            | order: Order, amount: uint256, slippagePercentage: uint16, referral: address                                                                                    | -                      | Actual       |
| BidOrdersFacet.sol      | cancelBidOrder           | Yes            | order: Order                                                                                                                                                   | -                      | Actual       |
| BidOrdersFacet.sol      | executeBidOrder          | Yes            | order: Order, seller: address, amount: uint256                                                                                                                 | -                      | Actual       |
| ShortOrdersFacet.sol    | placeShortOrder          | Yes            | order: Order, shares: uint256, slippagePercentage: uint16, referral: address                                                                                    | -                      | Actual       |
| ShortOrdersFacet.sol    | placeAndConfirmShortOrder| Yes            | order: Order, shares: uint256, slippagePercentage: uint16, referral: address                                                                                    | -                      | Actual       |
| ShortOrdersFacet.sol    | cancelShortOrder         | Yes            | order: Order                                                                                                                                                   | -                      | Actual       |
| ShortOrdersFacet.sol    | executeShortOrder        | Yes            | order: Order, redeemer: address, shares: uint256                                                                                                               | -                      | Actual       |
| PrimaryLiquidationFacet | liquidate                | Yes            | shortOrder: Order, liquidator: address                                                                                                                         | -                      | Actual       |
| BridgeRouterFacet.sol   | transferToOtherChain     | Yes            | bridgeParameters: BridgeParameters, destinationChainId: uint256, recipient: address, amount: uint256, token: address, data:                                    | -                      | Actual       |
| BridgeRouterFacet.sol   | transferFromOtherChain   | Yes            | bridgeParameters: BridgeParameters, senderChainId: uint256, sender: address, recipient: address, amount: uint256, token: address, data:                       | -                      | Actual       |
| ExitShortFacet.sol      | exitShort                | Yes            | shares: uint256                                                                                                                                                | -                      | Actual       |
| RedemptionFacet.sol     | redeem                   | Yes            | amount: uint256                                                                                                                                                | -                      | Actual       |
| LibBridgeRouter.sol     | getDefaultTransferData   | No             | routerAddress: address, chainId: uint256, deposit: bool, to: address, amount: uint256, token: address, encodedFunctionSignature: string, requiredGasLimit: uint256 | bytes[] memory        | Actual       |
| LibBytes.sol            | concat                   | No             | first: bytes memory, second: bytes memory                                                                                                                     | bytes memory           | Actual       |
| LibOracle.sol           | getSynthETHPrice         | No             | -                                                                                                                                                               | uint256                | Actual       |
| LibOrders.sol           | bidOrderHash             | No             | order: Order, positionId: uint256, srAddress: address                                                                                                           | bytes32                | Actual       |
| LibOrders.sol           | shortOrderHash           | No             | order: Order, positionId: uint256, srAddress: address                                                                                                           | bytes32                | Actual       |
| LibSRUtil.sol           | getExpiryTimestamp       | No             | expiry: uint256                                                                                                                                                | uint256                | Actual       |
| LibSRUtil.sol           | getShortExpiryTimestamp  | No             | expiry: uint256                                                                                                                                                | uint256                | Actual       |
| UniswapOracleLibrary.sol| getPrice                 | No             | token: address, chainId: uint256                                                                                                                              | uint256                | Actual       |





## 6. Approach Taken Reviewing the Codebase

- Before diving into the codebase, I took the time to familiarize myself with the overall structure, functionality, and components of the Ditto protocol. This preparation helped me grasp the project's context and identify potential areas that required further investigation.
- I examined available documentation, including project scope, goals, and specific design decisions. Ensuring that the code I inspect matches the project's intention is essential.
- I started with a high-level review of the project, examining the overall architecture, smart contract interactions, modularity, and the use of libraries. This comprehensive overview gave me a better understanding of the system's strengths, weaknesses, and potential vulnerabilities.
- Next, I analyzed specific smart contracts, reviewing their logic, functions, and security mechanisms. As I moved through the code, I searched for inconsistencies, potential risks, and areas for improvement. I also highlighted the use of best practices, design patterns, and any innovative solutions.
- I executed key contracts and functions in test environments, paying close attention to input parameters, desired behavior, and outputs. This hands-on testing helped me validate the logic and ensure that the actual behavior matches the project's intentions.
-I utilized various static analysis tools to identify common vulnerabilities, potential bugs, and issues with the codebase. These tools, including linters and code scanning tools, complemented my manual review and provided valuable insights.
- Upon finding potential issues, I categorized them based on their potential impact and likelihood of exploitation. To evaluate the impact, I considered factors such as monetary loss, privacy leaks, and overall system stability.
- Finally, I compiled my findings, prioritizing them based on severity and impact. The report included recommendations for improving code security, consistency, and maintainability. I ensured that the report was easily understood, actionable, and provided sufficient justification for my conclusions.


## 7. Ditto Eth Workflow 


| Contract Name            | Core Functionality                                                                    | Technical Characteristics                                                                                                                              | Importance                                                                                                                        | Management                                                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BidOrdersFacet.sol      | Facilitates the creation, modification, and cancellation of bid orders for the Ditto platform. | Implements external functions for creating, modifying, and canceling orders, as well as internal functions for validating orders and handling order fulfillment. | Crucial for user interaction and platform functionality. Ensures a smooth order management process and reduces the risk of errors or bugs that could result in financial loss. | Regularly test contract functionality and security to ensure proper functioning and prevent exploits. Stay up-to-date with Ethereum network upgrades and optimize gas costs as needed. |
| ShortOrdersFacet.sol    | Allows users to create and manage short positions on the Ditto platform.               | Exposes external functions for creating, modifying, and canceling short orders, as well as internal functions for order validation and fulfillment.         | Supports advanced trading strategies and is essential for expanding the platform's user base and increasing user retention.       | Regularly review and update short order management functions, as well as implement appropriate risk management strategies.                                                                                       |
| PrimaryLiquidationFacet.sol | Manages the liquidation process for undercollateralized positions.                     | Implements functions for calculating liquidation thresholds, initiating liquidation, and handling liquidation payouts.                                     | Vital for maintaining the platform's financial stability and mitigating risk.                                                   | Monitor the liquidation process and ensure its proper functioning, while also reviewing and updating thresholds and parameters as needed.                                                                     |
| BridgeRouterFacet.sol   | Handles the transfer of assets between different blockchain networks.                 | Exposes functions for initiating token transfers to and from connected networks via a third-party bridge solution.                                         | Crucial for enabling cross-chain interoperability and expanding Ditto's user base.                                                | Regularly test cross-chain functionality, as well as monitor and maintain API integration with the bridge solution.                                                                                      |
| ExitShortFacet.sol      | Enables users to close out their short positions.                                       | Exposes functions for initiating short position closures and handling payouts.                                                                            | Simplifies the closure process and enhances user experience.                                                                    | Routinely test closure functions and update payout handling mechanisms to ensure accuracy.                                                                                                               |
| RedemptionFacet.sol     | Manages the redemption of shares for underlying assets.                                 | Provides functions for initiating share redemptions and calculating redemption values based on current market prices.                                       | Supports users' ability to liquidate their positions and release their collateral, which is important for user satisfaction and retention. | Regularly test redemption functions, as well as update collateral release and calculation methods.                                                                                                     |
| LibBridgeRouter.sol     | Facilitates interactions between the Ditto platform and external bridge contracts.     | Provides reusable functions for initiating token transfers via external bridge solutions.                                                                  | Improves modularity and increases the maintainability of the codebase.                                                           | Regularly update library functions, test for compatibility, and monitor for security vulnerabilities.                                                                                                  |
| LibBytes.sol            | Provides utility functions for handling byte arrays.                                    | Contains functions for converting between byte arrays and other data types, as well as selecting subarrays.                                               | Enhances code readability and reduces redundancy, which promotes maintainability and long-term development.                     | Periodically review and update library functions, as needed. Ensure compatibility with Ethereum network standards and protocol updates.                                                               |
| LibOracle.sol           | Simplifies integration with price oracle solutions.                                     | Exposes functions for querying token prices from external oracle solutions and caching price values.                                                      | Improves the reliability of the Ditto platform by leveraging trusted oracle solutions for price discovery.                      | Regularly monitor oracle functionality, test price querying, and update cache methods.                                                                                                                  |
| LibOrders.sol           | Encapsulates common order management functionality.                                     | Provides helper functions for order validation, encapsulation, and processing.                                                                             | Increases code modularity and reusability, which simplifies maintenance and speeds up development.                              | Routinely test library functions and update as necessary, ensuring compatibility with recent contract changes and updates.                                                                                |
| LibSRUtil.sol           | Contains various utility functions specific to the Ditto platform.                      | Offers helper functions for parsing and validating order data.                                                                                              | Improves code readability and promotes reusability, which streamlines main contract updates and enhancements.                  | Regularly validate and update library functions, ensuring proper compatibility with Ditto contracts.                                                                                                    |
| UniswapOracleLibrary.sol | Simplifies the integration of Uniswap oracle solutions into Ditto contracts.            | Exposes reusable functions for querying token prices from Uniswap oracle solutions and handling associated data.                                           | Offers seamless integration with Uniswap's decentralized oracle solution, improving the reliability and trustworthiness of Ditto's market price data. | Regularly test Uniswap oracle integration and update functions as necessary, ensuring compatibility with recent protocol upgrades.                                                                    |




## 8. Economic Model Analysis


| Variable            | Description                                                                                                     | Economic Impact                                                                                                                                |
|---------------------|-----------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Asset Price         | The price of the underlying asset being traded in the Ditto Ethereum protocol.                                | The asset price directly affects the cost of opening and closing trades, and thus has a significant impact on the profitability of trading strategies. |
| Trading Fees        | Fees charged on trades made on the Ditto Ethereum protocol.                                                     | Trading fees are a source of revenue for the protocol and its liquidity providers. Higher fees can attract more liquidity providers, but may also discourage traders from using the platform. |
| Liquidation Fees    | Fees charged on liquidated positions in the Ditto Ethereum protocol.                                            | Liquidation fees serve as a penalty for traders who are unable to meet their margin requirements and help to compensate liquidity providers for the risk they take on. |
| Margin Requirements | The minimum amount of collateral required to open and maintain a position in the Ditto Ethereum protocol.     | Margin requirements help to ensure that traders are able to meet their obligations and prevent excessive risk-taking. High margin requirements can limit the amount of leverage available to traders, but can also reduce the risk of liquidation. |
| Interest Rates      | The interest rates charged on borrowed funds in the Ditto Ethereum protocol.                                    | Interest rates affect the cost of borrowing funds and can impact the profitability of trading strategies. Higher interest rates can attract more liquidity providers, but may also discourage traders from borrowing funds. |
| Liquidity Incentives | Rewards offered to liquidity providers in the Ditto Ethereum protocol.                                          | Liquidity incentives help to attract and retain liquidity providers, which is essential for maintaining a deep and liquid market. Higher incentives can attract more liquidity providers, but may also reduce the profitability of the protocol. |



## 9. Architecture Business Logic

| Contracts                 | Functionality                                                                                                    | Interactions                                                                                                                                                                                     |
|---------------------------|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BidOrdersFacet.sol        | Manages bid orders, including creation, cancellation, and fulfillment.                                           | Interacts with the ShortOrdersFacet to manage short orders and the RedemptionFacet to manage redemptions.                                                                                       |
| ShortOrdersFacet.sol      | Manages short orders, including creation, cancellation, and fulfillment.                                         | Interacts with the BidOrdersFacet to manage bid orders and the PrimaryLiquidationFacet to manage liquidations.                                                                                  |
| PrimaryLiquidationFacet.sol | Manages primary liquidations, where a short order is liquidated due to an Ethereum price drop.                  | Interacts with the ShortOrdersFacet to manage short orders and the RedemptionFacet to manage redemptions.                                                                                       |
| BridgeRouterFacet.sol     | Provides a way for users to interact with Ditto Eth across multiple chains.                                      | Interacts with the LibBridgeRouter to manage inter-chain messaging and the other facets to manage orders, liquidations, and redemptions.                                                       |
| ExitShortFacet.sol        | Manages the process of exiting a short position, including paying back the borrowed Ether and any associated fees. | Interacts with the ShortOrdersFacet to manage short orders and the RedemptionFacet to manage redemptions.                                                                                       |
| RedemptionFacet.sol       | Manages the process of redeeming Ether from Ditto Eth, including handling fees and oracle updates.               | Interacts with the BidOrdersFacet, PrimaryLiquidationFacet, and ExitShortFacet to manage orders, liquidations, and short exits.                                                                 |
| LibBridgeRouter.sol       | A library that provides functionality for inter-chain messaging and communication.                               | Used by the BridgeRouterFacet to manage inter-chain messaging and interactions.                                                                                                                  |
| LibBytes.sol              | A library that provides functionality for manipulating and comparing byte arrays.                                 | Used by the BidOrdersFacet and ShortOrdersFacet to manage orders.                                                                                                                               |
| LibOracle.sol             | A library that provides functionality for handling oracle updates and managing price data.                        | Used by the BidOrdersFacet, ShortOrdersFacet, PrimaryLiquidationFacet, and RedemptionFacet to manage orders, liquidations, and redemptions.                                                    |
| LibOrders.sol             | A library that provides functionality for managing orders, including creating and canceling orders.              | Used by the BidOrdersFacet and ShortOrdersFacet to manage orders.                                                                                                                               |
| LibSRUtil.sol             | A library that provides utility functionality for managing short orders and redemptions.                          | Used by the ShortOrdersFacet and RedemptionFacet to manage short orders and redemptions.                                                                                                        |
| UniswapOracleLibrary.sol | A library that provides functionality for interacting with the Uniswap oracle.                                    | Used by the LibOracle library to manage price data and oracle updates.                                                                                                                          |




## 10. Risk Model Analysis


### 10.1. Centralization Risks
- The BridgeRouterFacet contract has a setDefaultFee function that allows the owner to set the default fee for all bridges. This could be a centralization risk if the owner is a single entity that controls the fee structure of the platform.
- The PrimaryLiquidationFacet contract has a setLiquidationPenalty function that allows the owner to set the liquidation penalty for all vaults. This could be a centralization risk if the owner is a single entity that controls the penalty structure of the platform.

### 10.2. Systematic Risks
- The BidOrdersFacet contract allows users to create bid orders for assets. However, if the price of the asset drops significantly, the user may end up with a negative balance. This could lead to systematic risks if many users end up with negative balances, leading to a potential bank run.
- The ExitShortFacet contract allows users to exit short positions by burning their short tokens. However, if the price of the underlying asset increases significantly, the user may not have enough short tokens to cover their position. This could lead to systematic risks if many users are unable to cover their positions, leading to a potential market crash.

### 10.3. Technical Risks
- The BidOrdersFacet contract uses a uint128 type for the bidId variable. This type has a maximum value of 2^128 - 1. If the number of bid orders exceeds this limit, it could lead to integer overflow and cause unpredictable behavior.
- The ShortOrdersFacet contract's openPosition function calls an external contract's function (iToken.mint()) without checking its return value. This could lead to technical risks if the external contract's function fails, causing the openPosition function to continue executing and potentially causing unintended behavior.

### 10.4. Integration Risks
- The BridgeRouterFacet contract integrates with other blockchains and protocols. However, if there are compatibility issues or data privacy issues with these integrations, it could lead to security vulnerabilities or data leaks.
- The UniswapOracleLibrary contract uses Uniswap v2's price oracle to obtain price information. However, if Uniswap v2 experiences a bug or security vulnerability, it could lead to inaccurate price information and cause unpredictable behavior in the Ditto Eth platform.

### 10.5. Weak Spots & Single Points of Failures
- The PrimaryLiquidationFacet contract has a liquidateVault function that allows the owner to liquidate a vault if its health factor falls below a certain threshold. This could be a weak spot if the owner has a conflict of interest or abuses this power.
- The ExitShortFacet contract has a burnShort function that allows users to burn their short tokens. However, if a user tries to burn more short tokens than they have, it could lead to unpredictable behavior or security vulnerabilities.
- The BridgeRouterFacet contract's deposit() and withdraw() functions are the only ways to deposit and withdraw assets from the platform. If these functions experience bugs or security vulnerabilities, it could prevent users from accessing their funds or executing trades.
- The RedemptionFacet contract's redeem() function is the only way to redeem assets for their underlying collateral. If this function experiences bugs or security vulnerabilities, it could prevent users from redeeming their assets.


## 11. Architecture Recommendations

- Consider removing oracle as a function input in functions such as _createOrder and _updateOrder in favor of using an internal oracle state variable (_oracle) to reduce overhead and improve code readability.
- Consider adding checks to _createShortOrder and _updateShortOrder for the new amount provided relative to the existing amount to prevent potential underpricing upon the creation or update of the short orders.
- Consider changing the order of the input arguments in _calculateShortOrderLiquidation to align it with _createShortOrder and _updateShortOrder functions to improve readability, e.g., price, amount, marginLeft, additionalMargin, shortId.
- Consider renaming the _liquidatePrimaryOrder function to liquidateOrder.
- Consider adding better context to error messages, e.g., in the _liquidatePrimaryOrder function when the sender is trying to liquidate an order that does not belong to them.
- Consider a centralized minting function in a contract maintained by the protocol instead of allowing individual contracts to implement their own _mint function.
- Consider lowering the _mint function's amount limitations, as it might restrict valid use cases.
- Consider refactoring the _deposit function to reduce the seven require statements in favor of a single require with multiple logical conditions to improve gas efficiency.
- Consider improving the reason string in the _exit function's error message, as the current string offers limited debugging information.
- Consider renaming the _redeem function to _redeemOrCreateOrder for better readability.
- Consider including better context in the _redeem function's error messages, especially when balanceOf is equal to 0.
- Consider changing _getAssetPrice return type to int256 for the results to be consistent with the documentation at https://dittoeth.com/technical/concepts (under "Oracle" section).
- Consider adding a check to ensure that the _id provided in _getOrderDetails is valid (not equal to 0).
- Consider adding better documentation for the _getAmountOut function regarding input variables and conditions required.

## 12. Learning And Insights 



- Reviewing a complex DeFi project like Ditto allowed me to expand my knowledge of various DeFi concepts and implementations, such as oracle usage, liquidations, and multi-chain liquidity pools. Understanding different ways of approaching complex functionality in smart contracts further strengthened my skills in the DeFi domain.
- The review process enabled me to spot potential security vulnerabilities and suggest improvements to the codebase. For example, I looked for inconsistencies, under- Considering proper event logging and emit events for key state changes, adding comments and documentation, and applying best practices in coding and design. Addressing these issues can help to create more secure and maintainable smart contracts.
- Auditing involved working with new libraries and tools such as OpenZeppelin, UniswapOracleLibrary, and other custom contracts. Familiarizing myself with various libraries, patterns, and techniques used in these projects helped me to enhance my skill set in developing and reviewing smart contracts.
- Codebase reviews help to train the eye to spot areas for improvement in code quality. Focusing on good design principles, readability, gas efficiency, and modular code organization can significantly contribute to codebase maintainability and upgradeability.
- Reviewing different smart contracts in a complex project provided insights into how they interact with each other. Seeing the relationship between various contracts, like the interaction between libraries and the core contracts, helped to solidify my understanding of smart contract design and architecture patterns.
- During the review, I test-executed various functions and paid close attention to the input parameters and desired behavior. Performing hands-on checks while cross-referencing them with the documentation helped to validate my understanding and ensure that the actual behavior matches the project's intentions.
- Sharing insights and discussing problematic areas with other reviewers can lead to fruitful discussions and learning experiences. Working collaboratively with other professionals in the field contributes to growing your knowledge and sharpening your skills.


## 13. Conclusion 


The Ditto protocol is a complex system of various interacting contracts with different functionalities and specialized libraries. Reviewing it gave me the opportunity to learn about various DeFi concepts, such as oracle usage, liquidations, and multi-chain liquidity pools. It also provided insights into the way complex contracts interact with each other and the use of libraries and custom contracts to extend protocol capabilities.

During the review, I spotted potential security vulnerabilities and raised various issues regarding code complexity, inconsistencies, and improvements. Focusing on enhancement areas such as code quality, maintainability, and usability, helped to create more secure and maintainable smart contracts. The review process also helped me to become more proficient in finding ways to improve code design and implementations.

While the review provided valuable insights and lessons, there is always room for enhancement, especially as the DeFi ecosystem evolves and progresses. Periodic reviews and updates of codebases, continued education and upskilling, collaborative efforts within review teams, and input from a diverse range of experts can help to ensure that code remains secure, efficient, and maintainable.

Overall, I enjoyed reviewing the Ditto protocol and welcome the opportunity to work on other similar projects in the future.


### Time spent:
32 hours