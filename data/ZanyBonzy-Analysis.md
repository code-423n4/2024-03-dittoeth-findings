#  **Advanced Analysis Report for DittoETH**

## **1. Protocol Overview**

- DittoETH protocol allows users to create and manage on special pegged positions that represent various financial instruments including fiat/cryptocurrencies and commodities by allowing users to enter a long or short position against the asset.
- The protocol issues these pegged assets - `dUSD`(ERC-20 tokens that track prices) to users who in-turn provide a liquid staking token (LST) of ETH to act as collateral to the pegged assets.
- The protocol works by having users deposit their LST to receive the protocol's own `dETH`, longers can then open trades on the basis of the `dETH` for upon which they're matched with a shorter from the order book. After a successful match, they are minted the `dUSD`, whereas the shorter is given their(longer's) `dETH` from which they (shorter) can earn yield and boost their collateral ratio.
***
## **2. Architecture and Scope Overview**

<h3 align="center">
    <b>Facets</b>
</h3> 
<p align="center">
   The facets are the gateways through which users interact with the protocol. 
</p> 


#### **[BidOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol)**

- This facet allows for bid creations in the market. 

*Bid creation using the `createBid` and `createForcedBid` functions* - Users can call the `createBid` function, passing in the needed parameters to create a bid(including if they would like a market or limit order type) for an asset on the market. Upon short position exit and liquidation, a call is made by the `Diamond` contract to the `createForcedBid`  function in which bids are forcefully created to be matched with a corresponding position. Important to note that bids can only be created on valid/non frozen assets, and that only market order type is available for forced bids.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/211cc1fa-3c0b-4008-aa47-8291afcef279" alt="BidOrdersFacet"> <br> BidOrdersFacet.sol, 234 sLOC
</p> 

***

#### **[ShortOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol)**

- In this facet, users can for creating and matching short orders. Only limit short orders can be created. Upon creating a short, users are matched with a bidder who gains their stable asset. The shorter on the other hands gets the bidder's collateral from which they can earn yield.

*Short order creation through the `createLimitShort` function* - Short orders on a valid and unfrozen asset can be created when users call the `createLimitShort` function, passing in the requires parameters. The function creates a record of the short, updates the protocol's oracle and matches with corresponding orders.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/0eb985c8-551e-4971-a1be-4dcd7ef82ec8" alt="ShortOrdersFacet.sol"> <br> ShortOrdersFacet , 54 sLOC
</p> 

***

#### **[PrimaryLiquidationFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol)**	

- This facet allows liquidators to liquidate undercollateralized shorters by forcefully placing a bid on the market on their behalf. The shorter will bear the cost of forcedBid on market 

*Liquidating undercollateralized positions by calling the `liquidate` function* - Liquidators can call the `liquidate` function passing in the shorter address and short record id to forcefully create a bid on behalf of the shorter. The function, while open to all users is blocked from the shorter-owner of the short record to disable short liquidation. This is to prevent gaming the protocol by self liquidating. The protocol allows for full and partial liquidation of short orders.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/ba1bd3f7-a173-4446-82bd-a5f167ad3363" alt="PrimaryLiquidationFacet.sol"> <br> PrimaryLiquidationFacet.sol, 173 sLOC
</p> 

***

#### **[BridgeRouterFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol)**

- This is the facet through which users deposit and withdraw their LSTs in to the protcol. It routes the transaction to the bridge corresponding to the needed LST.

*LSTs/`ETH` deposit* - Via the `deposit` and `deposit` functions, users can deposit a specified amount of LST/ETH into the protocol to receive the protcols `dETH` which is pegged at a 1 to 1 ratio.  

*LST/`ETH` withdrawal* - By calling the `withdraw` function, users can withdraw their `dETH` for a corresponding amount of the deposited LST. A fee can be charged upon withdrawal by the protocol. The DAO can also use the `withdrawTapp` function to withdraw a portion of the LST from the protocol. 

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/17d752d8-5fd4-4689-9fe8-b577d06bce37" alt=""> <br> BridgeRouterFacet.sol, 101 sLOC
</p> 

***

#### **[ExitShortFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol)**

- Shorters interact with this facet to effectively reduce/close their short orders. This decreases their ercDebt and claws back their underlying collateral plus yield. The main way to this is by bidding on the order book. Another method incolves using their ercEscrowed amount or an amount of the ercDebt from their wallet.

*Primary and secondary short exits* - A shorter will call the `exitShort` function which allows forceful placing of bids in the market to partially or fully exit the short via the buyback mechanism. This is the primary method of short exit. Users with extra collateral to spare in the protocol or extra funds in their private wallets can call the `exitShortErcEscrowed` and `exitShortWallet` functions. These extra funds serve as buyback for the debt incured by the short position.


<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/beebf933-f9af-48fd-b46d-cbac4ab4b9bd" alt="ExitShortFacet.sol"> <br> ExitShortFacet.sol, 126 sLOC
</p> 

***

#### **[RedemptionFacet.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol)**

- The redemption facet allows users to "redeem" their dUSD for ETH at a 1 to 1 ratio to help maintain its stable peg to the USD. The facet allows for redemption proposals and disputes at a cost, and also for redemption and collateral claims. 

*Redemption proposals and dispute* - Users can call the `proposeRedemption` function to submit an array of short records as candidates for redemption, subject to a dispute period. This can be done for a small fee, of which the caller can set a maxmimum limit. After the redemption proposal is made, a dispute period is opened depending on the collateral ratio of the short positions, between which other users can dispute the status of the proposal by calling the `disputeRedemption` function. A successful dispute penalizes the proposer and removes the invalid short record.

*Redemption and collateral claims* - If the redemption proposal is successful, the `claimRedemption` function can be called to claim the ETH collateral sfrom the verified redemption candidates. The shorters can then finally call the `claimRemainingCollateral` to claim whatever collateral is left of their short record that was fully redeemed.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/cb9eaad3-79f6-47fd-895c-5190bcafb161"
alt="RedemptionFacet"> <br> RedemptionFacet.sol, 241 sLOC
</p> 

***
<h3 align="center">    <b>Libraries</b></h3> 
<p align="center"> Additional contracts that assist in performing the various protocol duties.</p> 


#### **[LibBridgeRouter.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol)**

- This functions as an extension to the BridgeRouterFacet and handles the accounting of `dETH` upon deposits, assessments and withdrawal of ETH/LSTs through the router. Upon deposits, withdrawals, transfers, various accounting calculations are updated here in this contract.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/d4cee597-5b84-46ae-92b5-8815b670ee54" alt="LibBridgeRouter"> <br> LibBridgeRouter.sol, 151 sLOC
</p> 

***
#### **[LibBytes.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol)**

- This library is used to encode and decode proposals from the RedemptionFacet solmates's SSTORE2.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/d38fd0f2-691d-4f72-93a9-4f3eef080bef" alt="LibBytes"> <br> LibBytes.sol, 35 sLOC
</p> 

***

#### **[LibOracle.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol)**

- This library provides token prices from chainlink, protocol pool and uniswap twap. It also provides circuit breakers for these prices to handle cases of deviation and manipulation.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/fee408ae-92a6-47b2-a42a-e986ab1285ad" alt="LibOracle"> <br>LibOracle.sol, 125 sLOC
</p> 

***

#### **[LibOrders.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol)**

- This stores and helps in matching various orders. It helps in order storing, verification, cancellation, matching and reusing of order ids.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/24668b78-0ab9-4c2b-b90d-bb66387fe1cb" alt="LibOrders"> <br>LibOrders.sol, 575 sLOC
</p> 


***
#### **[LibSRUtil.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol)**	

- This holds the various utility function needed when handling short orders records, including collateral disbursement, record transfers, various checks for recovery mode violation, handling or erc debt and so on.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/3eeb7ad7-6b5b-41f2-ba7e-f9e09a0199ff" alt="LibSRUtil"> <br>LibSRUtil.sol	112 sLOC
</p> 

***
#### **[UniswapOracleLibrary.sol](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol)**	

- This provides functions to get TWAP by integrating with Uniswap v3 pool oracle.

<p align="center">
    <img width= auto src="https://gist.github.com/assets/112232336/ef0b1758-a5c8-4ab6-9926-6aec0c74cf44" alt="UniswapOracleLibrary"> <br> UniswapOracleLibrary.sol, 34 sLOC
</p>

***

## **3. Codebase Overview**

- *Audit Information* - For the purpose of this audit, the DittoETH codebase comprises twelve smart contracts with a total of 1961 SLoC. It holds eight external imports, eighteen external calls and eight structs. Its core design principle is composition and holds a number of integrations including chainlink and uniswap. It is scheduled to be deployed to the Ethereum mainnet subjecting its network conditions.

- *Attack Vectors* - As requested by the sponsors, the orderbook logic requires crosschecking, issues dust and redemptions, small unliquidatable positions and so on. Oracle and TWAP manipulation, malicious liquidations or avoidance of liquidations, invalid validations and so on are other notable attack vectors.

- *Token Support* - The protocol aims to work with the ETH and its various LSTs, notable stETH and rETH. The contracts implementations is mostly suited for this as well as other standard ERC20 token types. The protocol also features the ERC20 stablecoin asset dUSD, and ETH equivalent dETH. The protocol's shortrecords are of the ERC721 token types.  

- *Testability* - Test coverage is about 96% which is very good. The implemented tests include unit test which tests the functions and helped with basic bugs. Fuzz tests, invariant tests and integration/simulation tests were also performed.

- *Documentation and NatSpec* - There codebase offers an official, slightly outdated documentation. The contracts are also well commented, not strictly to NatSpec but each function is reasonably well explained.

***

## **4. Protocol Risks** 

- *Centralization* - The protocol is mostly controlled by the DAO, hence mostly free from centralization. However, the DAO can still be taken over by malicious actors and the funcitons available to the DAO can be used in malicious ways. One notable example is the `withdrawTapp` function which allows for withdrawals of eth reserves in the TAPP. Due to the importance of the TAPP in socializing debt during liquidation, withdrawal at a wrong time, or malicious withdrawal can negatively affect the protocol.

- **Systemic Risks** 

     1. Risks paramount to Ethereum mainnet including high gas fees, frontrunning issues and so on.
     2. Malicious users looking to grief other users through shorts and liquidations.
     3. Issues with external integrations, compiler issues, inherited contracts.
     4. Vulnerabilities from other smart contracts, which at best may be contained in the erring contracts, at worst affect the whole protocol.
     5. Issues stemming from LSTs depegging and losing their values as the protocol for the most part handles their value against ETH in a 1 to 1 ratio.

***

## **5. Audit Recommendations**

- The codebase should be sanitized, and the comments should also be brought up to date to conform with NatSpec. The documentation should be brought up to date to include the newly added contracts.

- The use of PRB math library to handle `mulDiv` function in the oracle library is not advisable due to its inability to provide overflow behaviour that is desired when estimating TWAP prices. A more suitable alternative is to switch to the FullMath library instead, or modify the PRM math library to not revert on overflow.

- The normalization of base oracle prices by an estimate of 10**10 is based on the incorrect assumption that all chainlink USD feeds return 8 decimals. This isn't so as certain feeds return 18, some less. This normalization will cause gross overestimations of the prices of these tokens if their prices are ever desired.

- While users can deposit ETH and its LST derivatives, there seems to be no direct way of withdrawing ETH from the protocol. A functionality for this can be introduced.

- Issues related to the LSTs, particularly `stETH` should be taken into consideration. Treating it as a 1 to 1 derivative of `ETH` is not advisable, due to its rebasing nature and the possibility of a depeg. Using `wstETH` can help protect against this property. A pause functionality as described above can also help mitigate against that.

- SLashing events for `rETH` is also a risk to consider and keep in mind while dealing with it as its rate against ETH can be significantly affected.

- Issues with liquidation, oracle update and closing short frontrunning can be mitigated by allowing for deployments into L2s with private memepools. They also offer more advantages for users in terms of scalability, gas fees, network issues and so on. This might require some refactorings in the codebase but it's worth it in the long run.
    
- Finally, reported issues and bugs should be mitigated against, timely audits should be conducted.

***

## **6. Resources**

- [C4 ReadMe](https://code4rena.com/audits/2024-03-dittoeth#top)
- [Code Repository](https://github.com/code-423n4/2024-03-dittoeth)
- [Technical Documentation](https://dittoeth.com/technical/concepts)
- [LitePaper](https://dittoeth.com/litepaper)
- [Glossary](https://dittoeth.com/overview/glossary)

### Time spent:
18 hours