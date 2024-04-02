# L01 - No staleness check for oracleCircuitBreaker

baseTimeStamp represent the last update of the base oracle, which is [correctly checked in `baseOracleCircuitBreaker`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts\libraries\LibOracle.sol#L77-L77) but not in `oracleCircuitBreaker`

```solidity
File: contracts\libraries\LibOracle.sol
117:     function oracleCircuitBreaker(
118:         uint80 roundId,
119:         uint80 baseRoundId,
120:         int256 chainlinkPrice,
121:         int256 baseChainlinkPrice,
122:         uint256 timeStamp,
123:         uint256 baseTimeStamp
124:     ) private view {
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
126: ❌          || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;
127: 
128:         if (invalidFetchData) revert Errors.InvalidPrice();
129:     }
```


# QA01 - console should be removed from imports in `RedemptionFacet.sol`
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L19
The console library used for test and debug should be removed before deployment, as this will increase deployment cost.

```solidity
File: contracts\facets\RedemptionFacet.sol
17: 
18: 	import {SSTORE2} from "solmate/utils/SSTORE2.sol";
19:		import {console} from "contracts/libraries/console.sol";
20: 
21:❌	contract RedemptionFacet is Modifiers {
```

# QA02 - redeemerAssetUser.oraclePrice written twice (L149 + 202)
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts\facets\RedemptionFacet.sol#L201-L201
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts\facets\RedemptionFacet.sol#L148-L148

`redeemerAssetUser.oraclePrice` storage variable is accessed twice for ne reason

```solidity
File: contracts\facets\RedemptionFacet.sol
145:         // @dev SSTORE2 the entire proposalData after validating proposalInput
146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147:         redeemerAssetUser.slateLength = p.redemptionCounter;
148:1️⃣        redeemerAssetUser.oraclePrice = p.oraclePrice; 
149:         redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
```

```solidity
File: contracts\facets\RedemptionFacet.sol200: 
201: 1️⃣       redeemerAssetUser.oraclePrice = p.oraclePrice;
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
```

# QA03 - Eroneous natspec comment in `TWAPFacet.sol`
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts\facets\TWAPFacet.sol#L10-L10

The function do not compute the arithmetic mean, but the geometric mean (see [uniswap doc](https://docs.uniswap.org/concepts/protocol/oracle#tick-accumulator))

```solidity
File: contracts\facets\TWAPFacet.sol09: contract TWAPFacet {
10:     // @dev Computes arithmetic mean of prices between current time and x seconds ago.
11:     // @dev Uses parts of underlying code for OracleLibrary.consult()
12:     function estimateWETHInUSDC(uint128 amountIn, uint32 secondsAgo) external view returns (uint256 amountOut) {
13:         return OracleLibrary.estimateTWAP({
14:             amountIn: amountIn,
```

# QA04 - Missing natspec parameter in `ExitShortFacet::exitShortWallet`
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts\facets\ExitShortFacet.sol#L32-L41
Parameter `shortOderId` is missing from natspec

```solidity
File: contracts\facets\ExitShortFacet.sol
32:     /**
33:      * @notice Exits a short using shorter's ERC in wallet (i.e.MetaMask)
34:      * @dev allows for partial exit via buybackAmount
35:      *
36:      * @param asset The market that will be impacted
37:      * @param id Id of short
38:      * @param buybackAmount Erc amount to buy back
39:      *
40:      */
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {
```

