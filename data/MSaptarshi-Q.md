# [L-01] Unsafe downcasting 
Although there are many instances where i saw casting done normally, but here in this `ercAmount` is uint88 which is downcasted to uint80, so thought to report it since the probability of this causing a problem is very unlikely, so reporting it in low
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L164
`return uint80(s.bids[asset][C.HEAD].ercAmount);`
# Recommendation 
use OZ safecasting