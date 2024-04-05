# Analysis - DittoETH Contest

![DittoETH-Protocol](https://code4rena.com/_next/image?url=https%3A%2F%2Fstorage.googleapis.com%2Fcdn-c4-uploads-v0%2Fuploads%2FXcKzZ6eSLH9.0&w=96&q=75)

## Description overview of The DittoETH Contest

The Ditto protocol is a new decentralized stable asset protocol for Ethereum mainnet.The protocol is built with the original principals of cryptocurrencies, offering censorship resistance, neutrality, custody-less and permissionless trades, and collateral management. Pegged assets or DittoAssets are collateralized by ETH via liquid staking tokens (LST) of ETH, as opposed to endogenous collateral.DittoETH can support pegged assets for fiat currencies, cryptocurrencies (long and short) and commodities. In order for users to issue pegged assets, a high collateralization of staked ETH must be locked in the contract to maintain protocol solvency and price stability. Additionally, the neutrality of DittoETH ensures open and full-access trading for any user.

**In summary, DittoETH is**:

- DittoETH is an Ethereum-based decentralized protocol designed for pegged asset issuance.

-  It takes in overcollateralized liquid staked ETH (rETH, stETH) to create stablecoins using a gas optimized orderbook 

- The key parts are swap, matching orders, and tokenomics:

  - Facilitates bid order creation and matching in the DeFi system.

  - Manages creation and matching of short orders.

  - Handles depositing and withdrawing LSTs (tokens) & Implements credit mechanism for withdrawals.

**The key contracts of DittoETH protocol for this Audit are**:

- **BidOrdersFacet.sol**: It enables the system to create forced bids. Additionally,  serves as the bid matching algorithm, which is very crucial for bid execution , short matching, and ask matching within the market.

- **RedemptionFacet.sol**: Allows a user to propose redeeming a specified amount of an asset, handling multiple proposals in a batch & allows disputing invalid proposals, adjusting balances with penalties and refunds .Also allows for calculation and deducts redemption fees from the vault.

- **PrimaryLiquidationFacet.sol**: allows forced liquidation of short positions to cover debts, its also responsible for handling fees, distributing them between the caller and the contract.


## System Overview

### Scope

**Facet contracts**

- **BidOrdersFacet.sol**: Contains the core functions `_createForcedBid` and `bidMatchAlgo` that facilitate the creation and matching of bids within the system. The `_createForcedBid` function allows the creation of forced bids by the system & implemention of order creation. On the other hand, the `bidMatchAlgo` function serves as the matching algorithm for bids, handling scenarios such as bid filling, short matching, and ask matching. These functions are vital for the operation of the market, ensuring efficient bid execution and market stability.

- **ShortOrdersFacet.sol**: Allows users to create limit sell orders for shorted assets. It ensures users have enough collateral and verifies order size. Also places the order or attempts an immediate sale depending on market conditions.

- **PrimaryLiquidationFacet.sol**: Facilitates the liquidation of short positions for a specific asset.Targets insolvent users by forcing them to sell their shorted assets through a liquidation auction. The liquidation process covers various scenarios including full and partial liquidation, and handles the distribution of fees and collateral.

- **BridgeRouterFacet**: Acts as a bridge between users and `Lido` for deposits and withdrawals of Lido Staked Ether (LST) and Ether (ETH). It allows users to swap LST or ETH for dETH (denominated Ether) and manages vault balances to maintain a fair exchange rate

- **ExitShortFacet**: Allows users to close out their short positions on a specific asset. Users can exit by directly buying back ERC tokens with their wallet or ERC escrow, or by placing a bid on the market. The contract enforces minimum collateral requirements and checks to ensure the user's collateral ratio remains healthy after exiting a position.

- **RedemptionFacet**:Handles the redemption process for short positions. It allows users to propose redeeming short positions, with collateral and debt immediately removed from the candidates. Disputes can be raised against proposed redemptions, and after the dispute period, the redeemer can claim their collateral. The contract also calculates redemption fees based on factors like elapsed time and redeemed amounts.

**Library contracts**

- **LibBridgeRouter.sol**:Deals with bridging between different dETH tokens (RETH and STETH) on the platform. It handles adding dETH and bridge credit to user accounts, assesses how much dETH is not covered by bridge credits, and calculates bridge fees based on premium/discount differentials. It also handles transferring bridge credit between users.

- **LibBytes.sol**:It extracts details like shorter address and ERC debt redeemed for each proposal and returns them in array format

- **LibOracle.sol**:This library retrieves price data for assets using Chainlink oracles & also provides functionality to save and retrieve oracle prices.

- **LibOrders.sol**:Manages orders in the DEX, allowing users to add, cancel, and match sell orders,Efficiently places new orders and executes matches between buy and sell orders.Also updates the DEX's oracle price and starting short position based on market conditions.also includes functionality for various order management tasks.

- **LibSRUtil.sol**:Assists in managing short positions within the protocol. It facilitates returning collateral to users upon closing their positions. Additionally, it automatically cancels short orders that fall below a minimum collateral threshold.Furthermore, it can assess market recovery and prevent users from exiting unfavorable short positions.It enables transferring short record ownership and updating the associated ERC debt.


- **UniswapOracleLibrary**:Interacts with Uniswap V3 pools to get price information.Calculates the exchange rate between two tokens.It retrieves historical price data from the pool's oracle,helping to estimate a time-weighted average price (TWAP) over a specific time period. TWAP helps account for price fluctuations during the chosen period.

### Roles

 Here are the roles and their associated functionalities in the contract:

1. **OnlyDAO:**

   - Address: `BridgeRouterFacet`
   - Role: This restricts certain functions to only the DAO (Decentralized Autonomous Organization).in this contract `OnlyDAO`can Withdraw LST out of the protocol.

## Approach Taken-in Evaluating The DittoETH Protocol

Accordingly, I analyzed and audited the subject in the following steps;

1.  **Core Protocol Contract Overview**:

    I focused on thoroughly understanding the codebase and providing recommendations to improve its functionality.
    The main goal was to take a close look at the important contracts and how they work together in the DittoETH Protocol.

    I start with the following contracts, which play crucial roles in the DittoETH protocol:

    **Main Contracts I Looked At**

I start with the following contracts, which play crucial roles in the DittoETH protocol:

                BidOrdersFacet.sol
                RedemptionFacet.sol
                PrimaryLiquidationFacet.sol
                LibOrders.sol
                ExitShortFacet.sol
                
I started my analysis by examining the keycontracts, such as `BidOrdersFacet.sol` enables the system to create forced bids & serves as the bid matching algorithm in the Olas protocol. Subsequently,I delved into the `RedemptionFacet.sol`, as this is an entirely new concept to the protocol, to understand how  user is able to propose redeeming an asset,checking the core logic of the specified contract.Also went through `PrimaryLiquidationFacet.sol` learning about forced liquidation of short positions to cover debts and also grasping how fees are  handled and their distribution .Additionally, I scrutinized the library contracts, such as `LibOrders.sol` and its specialized counterparts, which play a crucial role in Manages orders in the protocol, aswell as add, cancel, and match sell orders within the protocol. The facet contract  such as `ExitShortFacet.sol`, `BridgeRouterFacet.sol` were also thoroughly examined to ensure that users are secure to close out their short positions on a specific asset and bridge users and `Lido` for deposits and withdrawals of Lst and Eth (&viceversa).following that i went to `LibOracle.sol` which retrieves price data for assets using Chainlink oracles &  `UniswapOracleLibrary.sol` which Interacts with Uniswap V3 pools to get price information and Calculates the exchange rate between two tokens.Lastly i scrutinized the remaining library contracts including`LibBridgeRouter.sol` which deals with bridging between different dETH tokens ,  `LibBytes.sol` which extracts details like shorter address and ERC debt redeemed  & `LibSRUtil.sol` which assists in managing short positions within the protocol.

24. **Documentation Review**:

    Then went to Review [This Docs](https://dittoeth.com/technical/concepts) for a more detailed and technical explanation of DittoETH protocol.

25. **Compiling code and running provided tests**:

26. **Manuel Code Review** In this phase, I initially conducted a line-by-line analysis, following that, I engaged in a comparison mode.

    - **Line by Line Analysis**: Pay close attention to the contract's intended functionality and compare it with its actual behavior on a line-by-line basis.

    - **Comparison Mode**: Compare the implementation of each function with established standards or existing implementations, focusing on the function names to identify any deviations.

## Codebase Quality

Overall, I consider the quality of the DittoETH protocol codebase to be Good. The code appears to be mature and well-developed. We have noticed the implementation of various standards adhere to appropriately. Details are explained below:

| Codebase Quality Categories              | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Code Maintainability and Reliability** | The DittoETH Protocol contracts demonstrates good maintainability through modular structure, consistent naming, and efficient use of libraries. It also prioritizes reliability by handling errors, conducting security checks. However, for enhanced reliability, consider professional security audits and documentation improvements. Regular updates are crucial in the evolving space.                                                                                                                                                                                                                                                                                                       |
| **Code Comments**                        | During the audit of the DittoETH contracts codebase, I found that some areas lacked sufficient internal documentation to enable independent comprehension. While comments provided high-level context for certain constructs, lower-level logic flows and variables were also mostly explained within the code itself. Following best practices like NatSpec could further strengthen self-documentation. As an auditor without additional context, it will be challenging to analyze code sections without external reference docs. To further understand implementation intent for those complex parts, referencing supplemental documentation was necessary.                                                 |
| **Documentation**                        | The documentation and Whitepaper of the DittoETH project is quite comprehensive and detailed, providing a solid overview of how DittoETH protocol is structured and how its various aspects function. However, we have noticed that there is room for additional details, such as diagrams, to gain a deeper understanding of how different contracts interact and the functions they implement. With considerable enthusiasm. We are confident that these diagrams will bring significant value to the protocol as they can be seamlessly integrated into the existing documentation, enriching it and providing a more comprehensive and detailed understanding for users, developers and auditors. |
                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Code Structure and Formatting**        | The codebase contracts are well-structured and formatted. but some order of functions does not follow the Solidity Style Guide According to the Solidity Style Guide, functions should be grouped according to their visibility and ordered: constructor, receive, fallback, external, public, internal, private. Within a grouping, place the view and pure functions last. For the most part this was followed which is appreciated                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  

## Architecture Review

The control flow of key contracts are depicted in the diagrams below:

### RedemptionFacet.sol
![dgram1](https://github.com/alanfrancis2001/dec/assets/147825828/8aa9aa05-2744-462a-bbb3-b147343516ff)

### PrimaryLiquidationFacet.sol
![dgram2](https://github.com/alanfrancis2001/dec/assets/147825828/63f22d01-69a6-4d49-a433-10d38edbfb24)

### BidOrdersFacet.sol
![dgram3](https://github.com/alanfrancis2001/dec/assets/147825828/7449eda2-5238-4f84-94e7-7dc9a8ff6c49)

### Centralization Risks:

**OnlyDAO:**

   - Address: `BridgeRouterFacet`
   - Role: This restricts certain functions to only the DAO (Decentralized Autonomous Organization).in this contract `OnlyDAO`can Withdraw LST out of the protocol.which can cause serious disruption in financial state of contract

**Properly managing these risks and implementing best practices in security and decentralization will contribute to the sustainability and long-term success of the DittoETH protocol.**

## Conclusion

In general, The DittoETH protocol presents a well-designed architecture. The DittoETH protocol exhibits strengths comprehensive testing, and detailed documentation, we believe the team has done a good job regarding the code. It is also highly recommended that the team continues to invest in security measures such as mitigation reviews, audits, and bug bounty programs to maintain the security and reliability of the project.









### Time spent:
26 hours