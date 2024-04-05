

# Analysis - DittoETH Audit

## Description overview of The DittoETH Contest

The DittoETH system is a decentralized stable asset protocol designed for the Ethereum mainnet. It leverages overcollateralized liquid staked ETH (rETH, stETH) to generate stablecoins, with a focus on optimizing gas costs through a gas-optimized orderbook, initially starting with a USD stablecoin, dUSD. The protocol's orderbook facilitates transactions between bidders and shorters,

### The protocol has Three components phases:

- **bidders,Shorter and ShortRecord**

   - bidders In the DittoETH system, bidders play a crucial role in facilitating the creation and management of stablecoins and pegged assets. Their primary function is to provide liquidity and collateral for shorters, who are essentially borrowing against their staked ETH to speculate on the future price of the DittoAsset relative to ETH. Bidders participate in the system by placing bids in the orderbook, where they offer ETH in exchange for dUSD or other pegged assets. This process involves matching bids with short orders, which are limit orders placed by shorters on the orderbook.When a bid matches with a short order, the requisite amount of dUSD (or the pegged asset) is minted, and the dETH from the long user (the bidder) is included in the collateral balance of the newly formed position. This mechanism ensures that the system remains over-collateralized, maintaining its solvency and price stability. Bidders are incentivized through the yield mechanism, where they earn interest in the form of dETH, which is distributed periodically. This yield distribution is designed to be cost-effective, with gas fees kept low and reasonable.
   - Shorter In the DittoETH system, shorters components is used for creation and management of pegged assets, which are ERC-20 tokens that track the price of a targeted asset. Their primary function involves taking a short position against a particular pegged asset by providing collateral in the form of staked ETH. Here are the key points regarding the work of shorters in the DittoETH system:
        - **Creating Pegged Assets**
        - **Earning Yield and Collateral**
        - **Managing and Burning Debt**
        - **Unique Shorting Rules**
   - ShortRecord In the DittoETH system, the ShortRecord plays a pivotal role in managing the debt positions created by shorters when they place short orders. Unlike traditional systems that allow only one CDP, Vault, or Trove per address, DittoETH's orderbook model enables multiple ShortRecords per address, offering flexibility and complexity in managing positions. Here are the key points regarding the work of the ShortRecord:
        - **Multiple ShortRecords**
        - **CombineShorts Function**
        - **ExitShort Function**
        - **Collateralization Ratio (CR)**
        - **ShortRecord Structure**
        - **Yield and Penalty Management**


## System Overview

###  Scope

- **BidOrdersFacet.sol** The contract is designed to facilitate the creation and matching of bid orders within the DittoETH system. It operates on the Ethereum mainnet

- **ShortOrdersFacet.sol** The contract is designed to facilitate the creation and matching of short orders within the DittoETH system.

- **PrimaryLiquidationFacet.sol** The contract is designed to facilitate the liquidation of short positions within the DittoETH system.

- **BridgeRouterFacet.sol** The contract is designed to facilitate the deposit and withdrawal of LSTs within the DittoETH system.

- **ExitShortFacet.sol** The contract is designed to facilitate the exit of short positions within the DittoETH system.

- **RedemptionFacet.sol** The contract facilitates the redemption of short positions by allowing users to swap dUSD for ETH, similar to the mechanism used in Liquity. It operates on the Ethereum mainnet

- **LibBridgeRouter.sol** The contract is a helper library designed to facilitate operations related to bridging assets in a decentralized finance (DeFi) system.

- **LibBytes.sol** The contract is a library designed to facilitate the reading of proposal data from SSTORE2, a mechanism used in the RedemptionFacet to store and retrieve proposal data efficiently. 

- **LibOracle.sol** The contract is a library designed to facilitate the retrieval of asset prices from Chainlink oracles with a backup mechanism

- **LibSRUtil.sol** The contract is a library designed to facilitate various operations related to Short Records in a decentralized finance (DeFi) system


## Roles

### Roles in the DittoETH protocol:

#### BidOrdersFacet.sol

 - **Owner Roles** The system  includes modifiers like isNotFrozen(asset) and onlyValidAsset(asset) which suggest that certain operations can be restricted or modified by the contract owner or specific roles within the system.

 ```solidity

76  modifier isNotFrozen(address asset) {
        if (s.asset[asset].frozen != F.Unfrozen) revert Errors.AssetIsFrozen();
        _;
    }


71  modifier onlyValidAsset(address asset) {
        if (s.asset[asset].vault == 0) revert Errors.InvalidAsset();
        _;
    }

 ```

 - **User Roles** Users can create bids through the createBid function, which is subject to certain conditions like asset validity and non-reentrancy.

 - **Privileged Roles** The createForcedBid function is only callable by specific contracts, indicating a privileged role that can force bid creation for exiting a short position.

#### ShortOrdersFacet.sol

 - **User Roles** the  ShortOrdersFacet.sol contract   Users can create short orders through the createLimitShort function, which is subject to certain conditions like asset validity, minimum size requirements, and non-reentrancy.

#### PrimaryLiquidationFacet.sol

 - **Owner Roles** The contract includes modifiers like isNotFrozen(asset) and onlyValidShortRecord(asset, shorter, id) which suggest that certain operations can be restricted or modified by the contract owner or specific roles within the system.

```solidity

95  modifier onlyValidShortRecord(address asset, address shorter, uint8 id) {
        _onlyValidShortRecord(asset, shorter, id);
        _;
    }

```

 - **User Roles** Users can initiate liquidations through the liquidate function, which is subject to certain conditions like asset validity, non-reentrancy, and specific role checks.
 
#### BridgeRouterFacet.sol

 - **Owner Roles** The contract includes modifiers like nonReentrant and onlyDAO which suggest that certain operations can be restricted or modified by the contract owner or specific roles within the system.
 - **Router Roles** The contract acts as a router for bridging LSTs, facilitating the movement of assets between different vaults and bridges.
 - **User Roles** Users can deposit and withdraw LSTs through the deposit, depositEth, withdraw, and withdrawTapp functions, which are subject to certain conditions like minimum deposit amounts and non-reentrancy.

 ##  Systemic Risk && Centralization Risks:

 ### Systemic Risk

The system reliance on external libraries and the use of complex logic in functions like bidMatchAlgo introduce potential vulnerabilities. Thorough testing and auditing are crucial to identify and mitigate such risks.
Oracle Dependency: The system relies on external oracles for price information, which introduces a point of failure and potential manipulation risks.

### Centralization Risks:

Single Point of Failure: The system reliance on specific roles and external systems (e.g., oracles) introduces centralization risks. Any failure or manipulation in these systems could impact the contract's functionality.
Governance Risks: The system includes privileged roles that can force bid creation, which could be exploited if these roles are not properly secured or if they act maliciously.

## Codebase Quality

| Codebase Quality Categories | Comments | 
|-----------------------------|----------|
|Code Maintainability and Reliability | The system uses libraries and modifiers for code organization and reusability, which is a good practice for maintainability. However, the extensive use of custom types and libraries without detailed documentation can pose challenges for maintainability.  |
|Code Comments |The contract includes detailed comments explaining the purpose and functionality of each function, which is beneficial for understanding the codebase. The contract uses libraries and modifiers for code organization and reusability, which is a good practice for maintainability. However, the extensive use of custom types and libraries without detailed documentation can pose challenges for maintainability. |
|Documentation | While the provided code snippet does not include external documentation, the comments within the code are comprehensive, providing insights into the logic and purpose of each function. |
|Code Structure and Formatting |The contract is well-structured, with clear separation of concerns and use of libraries for specific functionalities. However, the extensive use of custom types and libraries without external documentation can make it challenging for new developers to understand the codebase. |
|Error Handling |The contract uses revert statements with custom error messages for error handling, which is a good practice for clarity and debugging |

## Conclusion:

The DittoETH system's contract for creating and matching bids demonstrates a sophisticated approach to decentralized finance, leveraging Ethereum's capabilities for asset management and order matching. While the contract shows a strong foundation in code organization and error handling, it also highlights areas for improvement in documentation and external auditing to ensure security and reliability. The system's reliance on external oracles and privileged roles introduces centralization risks that need careful management.

### Time spent:
19 hours