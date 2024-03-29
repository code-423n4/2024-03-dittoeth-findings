# [L-01] Unsafe downcasting 
Although there are many instances where i saw casting done normally, but here in this `ercAmount` is uint88 which is downcasted to uint80, so thought to report it since the probability of this causing a problem is very unlikely, so reporting it in low
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L164
`return uint80(s.bids[asset][C.HEAD].ercAmount);`
# Recommendation 
use OZ safecasting

# [L-02] No checking of price deviation
The protocol does a great job in checking every stale price or incorrect price checks like ;
Using twap as a fallback oracke when this happen :
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L80
But during this check , the price deviation can be equal to 0.05 eth in that case  it will record as no price deviation.
 ``` if (incomingOrder.price >= savedPrice) {
            orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
        } else {
            orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
        } 
```
Though i don't think the price deviation will be much of a problem since during liquidation there is a fee which may equate it , do not much of a difference . So this is the reason though of reporting it in low
# Recommendation 
Use this type of check 
` _require(minPrice <= price && price <= maxPrice, Errors.PRICE_INVALID);
` 
Or change this type of  line to 
` orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) => 0.005 ether`