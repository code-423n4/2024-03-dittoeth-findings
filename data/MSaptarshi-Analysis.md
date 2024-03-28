## overview
`DittoETH` is a decentralized pegged asset issuance protocol built on Ethereum. DittoETH supports pegged assets for fiat currencies, cryptocurrencies (long and short) and commodities, offering censorship resistance, neutrality, custody-less and permissionless trades, and collateral management. In order for users to trade pegged assets, a high collateralization of staked ETH must be locked in the contract. The price of each pegged asset are fetched via two oracle set up system.

## Approach Taken while auditing
Understanding the codebase through the test coverage and provided docs
Debugging (line by line) test cases that are pretty crucial in a system
Generating Invariants with an intention to put the system into unexpected state
Receiving the context needed from sponsors in order to avoid the future problems
Testing locally && Reporting

## Protocol Uniqueness
### Orderbook Matching Logic
> This is the only unique feature of the protocol, which sets it apart from other orderbook type protocol.
> Ask orders get matched before short orders at the same price.
> Bids sorted high to low
> Asks/Shorts sorted low to high
> Only cancelled/matched orders can be reused (Technically: Left of HEAD (HEAD.prevId) these are the only possible OrderTypes: O.Matched, O.Cancelled, O.Uninitialized).
> Since bids/asks/shorts share the same orderId counter, every single orderId should be unique

### Hints
> The protocol uses `hint..Array` type variables which maybe for the $UI$ part to save gas on short/ask/bid orders . This is done to not iterate over every order there is present , Only to save gas

### Dust
> Is used to prevent small orders on the orderbook to prevent skyrocketing gas costs for large orders that match with multiple limit orders. There is a `minAskEth` and a `minBidEth` as well as a `minShortErc`. These minimums are necessary to reduce the gas costs of matching against a bunch of smaller order amounts or unnecessary spam orders. There is also another type of dust amount called `ercAmount` which is used for partialFill orders.One can read more about [DUST ORDERS HERE](https://dittoeth.com/technical/misc#orderbook-dust)

## Code Architecture

The Ditto protocol is a new decentralized stable asset protocol for Ethereum mainnet. It takes in overcollateralized liquid staked ETH (rETH, stETH) to create stablecoins using a gas optimized orderbook (starting with a USD stablecoin, dUSD).
On the orderbook, bidders and shorters bring ETH, askers can sell their dUSD. Bidders get the dUSD, shorters get the bidders collateral and a ShortRecord to manage their debt position (similar to a CDP). Shorters get the collateral of the position (and thus the LST yield), with the bidder getting the stable asset, rather than a CDP where the user also gets the asset.








### Contracts
`facets/BidOrdersFacet.sol` 
> Orders can only be bid through this contract and orders can be bid  by two ways ,one is by calling `createBid` which is done for creating the incomming bid, with hints, and the other is by calling `createForcedBid` which can only be called by the proxy, which doesn't need any hints.
	
`facets/ShortOrdersFacet.sol` 
> shortOrders can only be limit orders. startingShort represents the first short order that can be matched. Normally HEAD.nextId would the next short order in the mapping, but it's not guaranteed that it is matchable since users can still create limit shorts under the oracle price (or they move below oracle once the price updates). Oracle updates from chainlink or elsewhere will cause the startingShort to move, which means the system doesn't know when to start matching from without looping through each short, so the system allows a temporary matching backwards.
	
`facets/PrimaryLiquidationFacet.sol` 
>Among the two types of liquidation possible by the protocol only the primary Liquidation was only in the scope for the contest. The primary Liquidation..... 

`facets/BridgeRouterFacet.sol` 
> Because the Vault mixes rETH/stETH, a credit system is introduced to allow users to withdraw only what they deposit, anything in excess (due to yield) also checks either LSTs price difference using a TWAP via Uniswap

`libraries/LibBridgeRouter.sol:`
> Helper library used in BridgeRouterFacet

`facets/ExitShortFacet.sol:Facet`
> for a shorter to exit their short	

`facets/RedemptionFacet.sol:` 
>Allows dUSD holders to get equivalent amount of ETH back, akin to Liquity. However the system doesn't automatically sort the SR's lowest to highest. Instead, users propose a list of SRs (an immutable slate) to redeem against. There is a dispute period to revert any proposal changes and a corresponding penalty against a proposer if incorrect. Proposers can claim the ETH after the time period, and shorters can also claim any remaining collateral afterwards.
		

`libraries/LibBytes.sol:`
>Library in RedemptionFacet to save proposals in SSTORE2	
	
`libraries/LibOracle.sol`
> Library to get price with Chainlink + backup. If the price deviates from Chainlink fetched price and saved price by 50% i.e by  0.5ETH , it goes towards the fallback or backup `TWAP`

`libraries/LibOrders.sol`
> Library Order Facets to do matching	

`libraries/LibSRUtil.sol`
> Library of misc SR fns: recovery CR, minShortErc, transfer	
	
`libraries/UniswapOracleLibrary.sol`
> Acts as a fallback ORACLE for the chainlink oracle, Used to get TWAP from Uniswap	


## Privileged roles
`onlyDAO`: verifies the caller is the owner of the diamond contract. The current owner is DittoTimeLockController, which is governed by the DittoDAO .It has priviled access to store funds into treasury by withdrawing

`onlyAdminOrDAO`: Verifies that the caller is the admin or the DittoDAO, which allows for quicker responses to time sensitive actions

`Proxy.OnlyDiamond` : Checks that the caller is the diamond contract. This is to give priviliged access to certain external functions. It has priviliged access to call `createForceBid` , `depositETH` , `depositLST` etc. [due to limited scope there are other function some of them is not named here]


## Ecosystem dependencies
### AMM
> Double Oracle setup system, with chainlink ETH/USD as the primary setup, and Uniswap TWAP as the fallback oracle, If the savedprice( saved price in the protocol maybe from the last cached price ) and the chainlink price ,the difference between the two becomes > 0.5 ether(i.e 50%), then the protocol fetches the TWAP , even after the price is fetched the protocol still checks the validity TWAP price with the chainlink and saved price. The proctocol also encourages users to have knowledge of the price of the asset before coming to the protocol
Although the protocol expects the price to be in pair of ETH/USD and that's why it scales it to the power of 10, but if in the future if other assets are used this can lead to a serious issue.

### Bridge Router
> deposit/withdraw gives/removes an appropriate amount of virtual dETH (ETH equivalent), no matter if someone deposits an LST (rETH, stETH) through`deposit`, or ETH through `depositETH` and accounts for yield that is gained over time.

### Liquid Staking Tokens[LST]
> The protocol uses two LST rETH(rocketpool ETH), stETH[..] ,Users can come with this also and directly deposit them with `deposit` function which is totally aware of rETH rebasing feature, that's why it also has implemented the recieved amount be less in inline docs

## Centralization risk 
The protocol has only one has only governance role, which belongs to the DAO. No other party is allowed to change contract settings.

## Summary
Overall the design and health of the codebase are satisfactory. The use of mostly small , encapsulated function and isolated contracts are very helpful.`DittoETH` team have used innovative designs, especially with the AMM (use of fallback oracle) and liquidation(properly dividing the reward) that encourage decentralization, user incentive  and user control, as well as recognizing the risks associated with the system.
The main concern of the system will be
 > some function-level documentation 
 > variable names

## Recommendation
> **More function-level documentation**
> **Use of safecasting from OZ**
> **Change some of the variable names**

### Time spent:
100 hours