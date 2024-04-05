## **Conceptual Overview**

The Ditto Protocol Is a `Decentralized Stable Asset Protocol` (marketplace) For Ethereum Mainnet, Where Anyone Can Trade ETH For StableCoin dUSD. It Takes in OverCollateralized Liquid Staked ETH (rETH, stETH) to Create StableCoins Using a `Gas Optimized Orderbook (Starting With a USD Stablecoin, dUSD)`

**Here's How It Works:**

- Individuals Who Want To Get dUSD (referred to as bidders) Put Up Some ETH as Collateral
- Individuals Who Have dUSD (referred to as askers) Exchange It For ETH
- Askers Offer Their dUSD For Sale, & Bidders Buy It Using Their ETH Collateral.
- If Anyone Wants To Borrow dUSD Without Owning Any, They Can Do It By Shorting.
- Then Get dUSD, Also Receive ShortRecord To Keep Track Of Their Debt Position.
- Shorters Earn a Yield On Their Collateral, & Bidders Get the Stable dUSD.

## DittoETH Analyis (InScope)

| List | Contract                           | nSLOC | Purpose                                                    |
| :--- | :--------------------------------- | :---- | :--------------------------------------------------------- |
| 1    | facets/BidOrdersFacet.sol          | 234   | Facet for creating and matching bids                       |
| 2    | facets/ShortOrdersFacet.sol        | 54    | Facet for creating and matching short orders               |
| 3    | facets/PrimaryLiquidationFacet.sol | 173   | Facet for liquidation using ob                             |
| 4    | facets/BridgeRouterFacet.sol       | 101   | Facet to handle depositing and withdrawing LSTs            |
| 5    | facets/ExitShortFacet.sol          | 126   | Facet for a shorter to exit their short                    |
| 6    | facets/RedemptionFacet.sol         | 241   | Ability to swap dUSD for ETH, akin to Liquity              |
| 7    | libraries/LibBridgeRouter.sol      | 151   | Helper library used in BridgeRouterFacet                   |
| 8    | libraries/LibBytes.sol             | 35    | Library in RedemptionFacet to save proposals in SSTORE2    |
| 9    | libraries/LibOracle.sol            | 125   | Library to get price with Chainlink + backup               |
| 10   | libraries/LibOrders.sol            | 575   | Library Order Facets to do matching                        |
| 11   | libraries/LibSRUtil.sol            | 112   | Library of misc SR fns: recovery CR, minShortErc, transfer |
| 12   | libraries/UniswapOracleLibrary.sol | 34    | Used to get TWAP from Uniswap                              |

## **CodeBase Analysis (InScope)**

_Let's Take a Look On The Contracts (inScope)_

🔗 **facets/BidOrdersFacet.sol**

This Contract `Creates Bid Orders` in the Orderbook, With Options for Limit or Market Orders, Along With Gas-Optimized Placement hints. This Works By Using a Complex Algorithm Which Takes Factors Like Price, Order Types, & Available Liquidity To Match Bid Orders. Bids Have Been Verified After Matching & Then User Balance's are Updated Accordingly.

🔗 **facets/ShortOrdersFacet.sol**

This Contract Verifies the Creation Of Short Orders By Initializing Func. `createLimitShort` & Checks If the Asset isnotFrozen/Valid. Also Checks the Required Amount For Short Order Based on Collateral Ratio. Verifies if the Sender Has Sufficient Amount.
It Also Adds the Short Order Directly or Uses a Sell Match Algorithm, Depending on How Much It Costs When Compared to the Oracle Price.

🔗 **facets/PrimaryLiquidationFacet.sol**

This Contract Consist some Private Func.s Including an External Func. named as `liquidate` that Verifies If the Assests are Valid, then There are some Requirements Such as Shorter Cannot Liquidate Himself also If the Length Exceeds then 10 It will Revert By Giving an Error Of `TooManyHints` , Also Ensures the Enough Collateral. One Can Liquidate as Long as CR is Low Enough or If CR is too High, Check For Recovery Mode & Violation To Continue Liquidation.

🔗 **facets/BridgeRouterFacet.sol**

This Contract Works As a Router Interacting With Other Bridges, Constructor Has Two Specific Bridges `rethBridge` & `stethBridge`,
The Contract Allow Users To Deposit LST Tokens into the Protocol, & Also By Withdraw Them Out Of The Protocol. `maybeUpdateYield` Func. Automatically Update the Vault Yield Rate When Bridge Deposits Are Sufficiently Large.

🔗 **facets/ExitShortFacet.sol**

This Contract Conssists Three Methods of Exiting Shorts: `exitShortWallet` Exits a Short Using Shorter's ERC in Wallet (i.e.MetaMask), `exitShortErcEscrowed` Using Shorter's ERC in Balance (ErcEscrowed) , `exitShort` By Placing Bid on Market.

🔗 **facets/RedemptionFacet.sol**

This Contract is About Ability to swap dUSD for ETH, akin to Liquity , Also Calculates Redemption Fees Based on the amount of Collateral & Debt In the Redemption Process.

🔗 **libraries/LibBridgeRouter.sol**

This is a `Helper Library` Contract Including Some Funcs Like _addDeth, assessDeth, withdrawalFeePct, transferBridgeCredit & removeDeth._

🔗 **libraries/LibBytes.sol**

This Library Facilitates The Decoding Of Proposal Data Stored In An Encoded Format, (Utilized in a Redemption Process) .

🔗 **libraries/LibOracle.sol**

This Contract Offers Func.s Related to `Fetching & Managing` Oracle Prices For Assets.

🔗 **libraries/LibOrders.sol**

This Contracts is About `Matching Orders` such as Dust, Oracle Price Changes Or Auto Adjust.

🔗 **libraries/LibSRUtil.sol**

This Contract Includes Several Functions For Managing the Disbursement Of Collateral, Checks Cencellation of Short Orders, Recovery Mode Violation, Minimum Erc Amount, Transfer & Update of ERC Debt

🔗 **libraries/UniswapOracleLibrary.sol**

This Serves As a Library Providing Func.s to Interact With Uniswap V3 Pool Oracle. Calculates Amount of a Quote Token Received in Exchange for a given Token Amount at specific tick value. It Employs Precise Calculations According to Square Root of the Ratio & Token Denominations.

## **Risk Factor Analysis**

```

  - Admin abuse risks
  - Systemic risks
  - Technical risks
  - Integration risks
  - Non-standard token risks (if in scope)

```

- There are some Functions Ssuch as `proposeRedemption` & `disputeRedemption` , That Have Control Over Funds, So There is a Risk of Misuse by Admins.
- Also Ther are Some Risks According to Systematic Point Of View, as The Protocol relies on oracle of Price Feed, Redemption Proposal, Collateral Distribution, etc.
- Technically the Protocol has an interaction with External Libs, so There is a Chance of Techical Risks.
- Integration with Other External systems or Bridges May Poses integration risks Related to Data Consistency, Changes/Updates.

_This is a short descriptiion about Vulnerabilities as There May be More Chances of Risk Factors That Can Be Arise Through Regular Testings_

---


### Time spent:
15 hours