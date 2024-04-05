1. `redeemerAssetUser.timeProposed` is set twice in `RedemptionFacet::proposeRedemption()`. Furthermore, `LibOrders::getOffsetTime()` is called for both cases.

```solidity
uint32 protocolTime = LibOrders.getOffsetTime();
redeemerAssetUser.timeProposed = protocolTime;
```

```solidity
redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
```

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L154-L155
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L202



2. Unsafe cast in `UniswapOracleLibrary::estimateTWAP`
This line includes an unsafe cast:
```solidity
int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
```
`secondsAgo` is a variable of type `uint32` and it is being casted to type `int32`. The maximum value for `uint32` is `4294967295` while the maximum value for `int32` is `2147483647`.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L62