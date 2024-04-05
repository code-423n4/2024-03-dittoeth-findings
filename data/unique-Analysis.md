# Introduction

DittoETH is a protocol built on the Ethereum blockchain that enables the creation of decentralized pegged assets. These assets, known as DittoAssets, are backed by Ethereum (ETH) through liquid staking tokens (LST) rather than internal collateral. The protocol upholds key principles of cryptocurrencies, such as censorship resistance, neutrality, and permissionless trading, while also offering custody-less transactions and effective collateral management.

Users will be able to deposit staked ETH onto the DittoETH exchange platform to either enter a long or short position against a particular pegged asset. Short traders that successfully enter a position will be able to earn yield in the form of dETH, which will come from the staked ETH. They will also be loaned staked ETH from the long trader, and this additional collateral earns them staking rewards beyond their own staked ETH.

# The approach I followed when reviewing the code

Accordingly, I analyzed and audited the subject in the following steps;

**1\. Initial Scope and Documentation Review**:

&nbsp;          Thoroughly went through the Contest Readme File and project documentation to understand the protocol's objectives and functionalities.

**2\. High-level Architecture Understanding**:

&nbsp;       Performed an initial architecture review of the codebase by going through all files without going into function details.

3.   **Missing knowledge:**

&nbsp;        After familiarizing myself with the protocol, I recognized that there are certain concepts that I don't fully grasp. Therefore, before proceeding with the audit, it's essential for me to gain a thorough understanding of these concepts.

#### *I used these resource for understanding those concepts.*

- Diamond
     https://github.com/mudgen/awesome-diamonds?tab=readme-ov-file 
- Lido DAO
    - https://docs.lido.fi/lido-dao/
- Rocket Pool
    - https://docs.rocketpool.net/overview/glossary#reth-rocket-pool-staking-deposit-token
- Lido vs. Rocket Pool
    - https://coincodex.com/article/27799/lido-vs-rocket-pool-which-eth-staking-solution-is-best/
- Liquid staking
- - https://www.okx.com/learn/what-is-liquid-staking  
        \- https://www.youtube.com/watch?v=WHjXz6hFUSU

4\. **Code Review**:

&nbsp;          Conducted a line-by-line code review focusing on understanding code functionalities.

  - Understand Codebase Functionalities: Began by going through the functionalities of the codebase to gain a clear understanding of its operations.
            - Identify Access Control Issues: Thoroughly examined the codebase for any access control problems that might allow unauthorized users to execute critical functions.
            - Evaluate Function Execution Order: Checked random sequence of function executions to ensure the protocol's logic cannot be disrupted by changing the order of calls.

**5\. Report Writing**:

&nbsp;           Write Report by compiling all the insights I gained throughout the line by line code review.

# System Overview

## Scope

### Overview of Each Contract:

1.  **BidOrdersFacet.sol:**
    
    - Manages bid orders in a decentralized exchange.
    - Creates bid orders and handles order matching.
    - Ensures order validity, sufficient funds, and correct order matching algorithms.
2.  **ShortOrdersFacet.sol:**
    
    - Implements creating limit short orders in a market system.
    - Handles collateral ratio, order size, and price validations.
    - Matches short orders with existing asks based on price and oracle price.
3.  **PrimaryLiquidationFacet.sol:**
    
    - Facilitates liquidation of short positions in a DeFi application.
    - Forces shorts to place bids on the market for liquidation.
    - Handles liquidation fees, collateral distribution, and event emission.
4.  **BridgeRouterFacet.sol:**
    
    - Manages depositing and withdrawing Liquid Staked Token (LST) collateral through various bridges.
    - Handles LST deposit, ETH deposit, and withdrawal functionalities.
    - Updates vault yield rate based on deposit size.
5.  **ExitShortFacet.sol:**
    
    - Provides functions for exiting short positions in a DeFi application.
    - Allows exiting shorts using ERC tokens from wallet or escrow, or by placing bids on the market.
    - Handles collateral and debt updates, order execution, and error handling.
6.  **RedemptionFacet.sol:**
    
    - Manages short position redemptions in a DeFi application.
    - Allows proposing, disputing, and claiming redemptions.
    - Calculates redemption fees, updates collateral and debt balances, and emits events.
7.  **LibBridgeRouter.sol:**
    
    - Handles bridge credits, withdrawal fees, and user account updates in a decentralized Ethereum system.
    - Adds and removes dETH from user accounts, calculates withdrawal fees, and transfers bridge credits.
8.  **LibBytes.sol:**
    
    - Defines a function for reading and decoding data from a bytes array stored in a contract.
    - Decodes data into an array of custom structs.
9.  **LibOracle.sol:**
    
    - Interacts with Chainlink oracles and calculates prices.
    - Retrieves oracle price, calculates TWAP, and manages price deviation.
10. **LibOrders.sol:**
    
    - Provides functionality for order management, matching, and settlement in a decentralized exchange.
    - Supports limit order book model, order cancellation, and vault system for asset management.
11. **LibSRUtil.sol:**
    
    - Manages short positions on the Ethereum blockchain.
    - Provides functions for collateral disbursement, short order cancellation, and recovery mode violation checks.
12. **UniswapOracleLibrary.sol:**
    
    - Estimates the Time-Weighted Average Price (TWAP) of a token pair using the Uniswap V3 pool oracle.
    - Calculates TWAP based on cumulative tick values and liquidity.

### Privileged Roles

Some privileged roles exercise powers over the DittoETH contracts:

- <span style="color: #ffd173;">DAO</span>

```
modifier onlyDAO() {
        LibDiamond.enforceIsContractOwner();
        _;
    }
```

- <span style="color: #ffd173;">Admin Or</span> <span style="color: #ffd173;">DAO</span>

```
modifier onlyAdminOrDAO() {
        if (msg.sender != LibDiamond.contractOwner() && msg.sender != s.admin) revert Errors.NotOwnerOrAdmin();
        _;
    }
```

- <span style="color: #ffd173;">Diamond</span>

```
modifier onlyDiamond() {
        if (msg.sender != address(this)) revert Errors.NotDiamond();
        _;
    }
```

- <span style="color: #ffd173;">Valid Asset</span>

```
modifier onlyValidAsset(address asset) {
        if (s.asset[asset].vault == 0) revert Errors.InvalidAsset();
        _;
    }
```

- <span style="color: #ffd173;">ValidShortRecord</span>

```
modifier onlyValidShortRecord(address asset, address shorter, uint8 id) {
        _onlyValidShortRecord(asset, shorter, id);
        _;
    }
```

&nbsp;

# Centralization Risk:

No Centralization Risk

&nbsp;

## Codebase Quality

Overall, I consider the quality of the `DittoETH` codebase to be Good, with well-structured contracts and libraries. It employs appropriate design patterns such as the Diamond Standard (EIP-2535) for upgradeability and utilizes libraries for modularization and code reuse. Additionally, the contracts employ error handling mechanisms, extensive documentation, and consistent naming conventions, enhancing readability and maintainability.

Details are explained below:

| Codebase Quality Categories | Comments |
| --- | --- |
| **Code Maintainability and Reliability** | The DittoETH contracts demonstrates good maintainability through modular structure, consistent naming. It also prioritizes reliability by handling errors, conducting security checks. However, for enhanced reliability, consider professional security audits and documentation improvements. Regular updates are crucial in the evolving space. |
| ****Testing**** | The audit scope of the contracts to be audited is 86% and it should be aimed to be 100%. |
| **Code Comments** | Some functions and structs in the code are not well-documented, making it harder for developers to understand their purpose and behavior. Adding appropriate comments and documentation can improve code maintainability and understandability. |
| **Documentation** | The documentation of DittoETH  was very clear and helpful. It addressed my questions thoroughly and provided valuable insights, and it was very easy to find the details about each contract. |
| **Code Structure and Formatting** | The  contracts are well-structured and formatted. but some order of functions does not follow the Solidity Style Guide According to the Solidity Style Guide, functions should be grouped according to their visibility and ordered: constructor, receive, fallback, external, public, internal, private. Within a grouping, place the view and pure functions last. |
| **Error** | Use custom errors, custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain. |
| **Gas Optimization** | DittoETH demonstrates a strong commitment to gas optimization, incorporating many widely accepted techniques. |

## Conclusion

In general, the DittoETH project exhibits an interesting and well-developed architecture I believe the team has done a good job regarding the code, but the identified risks need to be addressed, and measures should be implemented to protect the protocol from potential malicious use cases. Additionally, it is recommended to improve the documentation and comments in the code to enhance understanding and collaboration among developers. It is also highly recommended that the team continues to invest in security measures such as mitigation reviews, audits, and bug bounty programs to maintain the security and reliability of the project.

## Time Spend

It took me longer than expected because there were some concepts that I needed to understand. If we exclude the time spent on understanding the missing knowledge, I estimate that it would have taken me approximately 34 to 38 hours to complete.

&nbsp;



### Time spent:
35 hours