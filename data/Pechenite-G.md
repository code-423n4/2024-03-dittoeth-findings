**Note:** All instances from the 4naly3er report are removed.

---

|Number|Issue|Instances|Estimated Gas Saved|
|-|:-|:-:|:-:|
| [GAS&#x2011;1](#GAS1->=/<=-costs-less-gas-than->/<) | `>=`/`<=` costs less gas than `>`/`<` | 124 | 372 |
| [GAS&#x2011;2](#GAS2-addressthis-should-be-cached-when-used-multiple-times) | `address(this)` should be cached when used multiple times | 2 | - |
| [GAS&#x2011;3](#GAS3-assigning-state-variables-directly-with-named-struct-constructors-wastes-gas) | Assigning state variables directly with named struct constructors wastes gas | 1 | 28 |
| [GAS&#x2011;4](#GAS4-avoid-contract-existence-checks-by-using-low-level-calls) | Avoid contract existence checks by using low-level calls | 14 | 1,400 |
| [GAS&#x2011;5](#GAS5-cache-external-calls-outside-of-loop-to-avoid-re-calling-function-on-each-iteration) | Cache external calls outside of loop to avoid re-calling function on each iteration | 9 | 900 |
| [GAS&#x2011;6](#GAS6-consider-activating-via-ir-for-deploying) | Consider activating `via-ir` for deploying | 0 | 250 |
| [GAS&#x2011;7](#GAS7-consider-merging-sequential-for-loops) | Consider merging sequential for loops | 2 | - |
| [GAS&#x2011;8](#GAS8-consider-pre-calculating-the-address-of-addressthis) | Consider pre-calculating the address of `address(this)` | 18 | - |
| [GAS&#x2011;9](#GAS9-consider-reducing-redundant-checks-in-each-iteration-of-loops) | Consider reducing redundant checks in each iteration of loops. | 12 | - |
| [GAS&#x2011;10](#GAS10-consider-using-openzeppelins-enumerateset-instead-of-nested-mappings) | Consider using OpenZeppelin's `EnumerateSet` instead of nested mappings | 12 | 12,000 |
| [GAS&#x2011;11](#GAS11-consider-using-soladys-gas-optimized-lib-for-math) | Consider using Solady's gas optimized lib for Math | 14 | - |
| [GAS&#x2011;12](#GAS12-constructors-can-be-marked-payable) | Constructors can be marked `payable` | 3 | 63 |
| [GAS&#x2011;13](#GAS13-counting-down-in-for-statements-is-more-gas-efficient) | Counting down in `for` statements is more gas efficient | 8 | 128 |
| [GAS&#x2011;14](#GAS14-declare-variables-outside-of-loops) | Declare variables outside of loops | 26 | 390 |
| [GAS&#x2011;15](#GAS15-do-not-cache-state-variables-that-are-used-only-once) | Do not cache state variables that are used only once | 4 | 12 |
| [GAS&#x2011;16](#GAS16-do-while-is-cheaper-than-for-loops-when-the-initial-check-can-be-skipped) | `do`-`while` is cheaper than `for`-loops when the initial check can be skipped | 8 | 2,040 |
| [GAS&#x2011;17](#GAS17-function-names-can-be-optimized) | Function names can be optimized | 3 | 384 |
| [GAS&#x2011;18](#GAS18-functions-guaranteed-to-revert-when-called-by-normal-users-can-be-marked-payable) | Functions guaranteed to revert when called by normal users can be marked `payable` | 7 | 147 |
| [GAS&#x2011;19](#GAS19-integer-increments-by-one-can-be-unchecked) | Integer increments by one can be unchecked | 10 | 600 |
| [GAS&#x2011;20](#GAS20-internal-functions-only-used-once-can-be-inlined-so-save-gas) | `internal` functions only used once can be inlined so save gas | 1 | 30 |
| [GAS&#x2011;21](#GAS21-multiple-accesses-of-the-same-mapping/array-key/index-should-be-cached) | Multiple accesses of the same mapping/array key/index should be cached | 33 | 1,386 |
| [GAS&#x2011;22](#GAS22-nesting-if-statements-is-cheaper-than-using-&&) | Nesting `if`-statements is cheaper than using `&&` | 20 | 600 |
| [GAS&#x2011;23](#GAS23-newer-versions-of-solidity-are-more-gas-efficient) | Newer versions of solidity are more gas efficient | 12 | - |
| [GAS&#x2011;24](#GAS24-not-using-the-named-return-variables-when-a-function-returns-wastes-deployment-gas) | Not using the named return variables when a function returns, wastes deployment gas | 52 | - |
| [GAS&#x2011;25](#GAS25-optimize-deployment-size-by-fine-tuning-ipfs-hash) | Optimize Deployment Size by Fine-tuning IPFS Hash | 12 | 127,200 |
| [GAS&#x2011;26](#GAS26-optimize-ether-deposits-using-the-receive-function) | Optimize Ether deposits using the `receive()` function | 1 | 45 |
| [GAS&#x2011;27](#GAS27-order-of-checks-in-a-function-can-be-optimized) | Order of checks in a function can be optimized | 6 | 12,600 |
| [GAS&#x2011;28](#GAS28-pre-increments/pre-decrements-are-cheaper-than-+1/+=1-or--1/-=1) | Pre-increments/pre-decrements are cheaper than `+1`/`+=1` or `-1`/`-=1` | 1 | - |
| [GAS&#x2011;29](#GAS29-prefer-using-storage-instead-of-memory-for-state-variables-saves-gas) | Prefer using `storage` instead of `memory` for state variables saves gas | 1 | 2,100 |
| [GAS&#x2011;30](#GAS30-private-functions-used-once-can-be-inlined) | `private` functions used once can be inlined | 14 | 420 |
| [GAS&#x2011;31](#GAS31-reorder-modifiers-to-save-on-expensive-operations) | Reorder modifiers to save on expensive operations | 10 | 21,000 |
| [GAS&#x2011;32](#GAS32-same-cast-is-done-multiple-times) | Same cast is done multiple times | 1 | - |
| [GAS&#x2011;33](#GAS33-sort-solidity-operations-using-short-circuit-mode) | Sort Solidity operations using short-circuit mode | 57 | - |
| [GAS&#x2011;34](#GAS34-splitting-revert-statements-saves-gas) | Splitting `revert()` statements saves gas | 10 | 20 |
| [GAS&#x2011;35](#GAS35-stack-variable-is-only-used-once) | Stack variable is only used once | 86 | 258 |
| [GAS&#x2011;36](#GAS36-state-variable-read-in-a-loop) | State variable read in a loop | 2 | 194 |
| [GAS&#x2011;37](#GAS37-state-variables-should-be-cached-in-stack-variables-rather-than-re-reading-them-from-storage) | State variables should be cached in stack variables rather than re-reading them from storage | 24 | 2,400 |
| [GAS&#x2011;38](#GAS38-structs-can-be-assigned-more-efficiently) | Structs can be assigned more efficiently | 1 | 130 |
| [GAS&#x2011;39](#GAS39-the-result-of-a-function-call-should-be-cached-rather-than-re-calling-the-function) | The result of a function call should be cached rather than re-calling the function | 5 | 500 |
| [GAS&#x2011;40](#GAS40-update-openzeppelin-dependency-to-the-latest-version) | Update OpenZeppelin dependency to the latest version | 1 | - |
| [GAS&#x2011;41](#GAS41-usage-of-uints/ints-smaller-than-32-bytes-256-bits-incurs-overhead) | Usage of `uints`/`ints` smaller than 32 bytes (256 bits) incurs overhead | 109 | 654 |
| [GAS&#x2011;42](#GAS42-use-arrayunsafeaccess-to-avoid-repeated-array-length-checks) | Use `Array.unsafeAccess()` to avoid repeated array length checks | 9 | 18,900 |
| [GAS&#x2011;43](#GAS43-use-assembly-for-math-equations) | Use assembly for math equations | 1 | 260 |
| [GAS&#x2011;44](#GAS44-use-assembly-scratch-space-to-build-calldata-for-external-calls) | Use assembly scratch space to build calldata for external calls | 11 | 2,420 |
| [GAS&#x2011;45](#GAS45-use-assembly-to-validate-msgsender) | Use assembly to validate `msg.sender` | 6 | 72 |
| [GAS&#x2011;46](#GAS46-use-assembly-to-write-address/contract-storage-values) | Use `assembly` to write address/contract storage values | 15 | 750 |
| [GAS&#x2011;47](#GAS47-use-bitwise-operators-rather-than-boolean-operators-to-save-gas) | Use bitwise operators rather than boolean operators, to save gas | 3 | - |
| [GAS&#x2011;48](#GAS48-use-constants-instead-of-typeuint<n>max-/-min) | Use constants instead of `type(uint<n>).max` / `.min` | 3 | 12 |
| [GAS&#x2011;49](#GAS49-use-gas-efficient-version-of-min/max) | Use gas-efficient version of `min`()/`max`() | 3 | - |
| [GAS&#x2011;50](#GAS50-use-if-statements-instead-of-ternary-operators) | Use `if` statements instead of ternary operators | 12 | - |
| [GAS&#x2011;51](#GAS51-use-revert-to-gain-maximum-gas-savings) | Use `revert()` to gain maximum gas savings | 66 | 18,605 |
| [GAS&#x2011;52](#GAS52-use-sx-=-sx-+-y-instead-of-sx-+=-y-for-structs) | Use `s.x = s.x + y` instead of `s.x += y` for structs | 181 | 18,100 |
| [GAS&#x2011;53](#GAS53-use-scratch-space-when-building-emitted-events) | Use scratch space when building emitted events | 11 | 418 |
| [GAS&#x2011;54](#GAS54-using-storage-instead-of-memory-for-structs/arrays-saves-gas) | Using `storage` instead of `memory` for structs/arrays saves gas | 26 | 54,600 |

**❗ Disclaimer:** Gas totals are estimates based on data from the Ethereum Yellowpaper. The estimates use the lower bounds of ranges and count two iterations of each `for`-loop. All values above are runtime, not deployment, values; deployment values are listed in the individual issue descriptions. The table above as well as its gas numbers do not include any of the excluded findings.


---
### [GAS&#x2011;1] `>=`/`<=` costs less gas than `>`/`<`
The compiler uses opcodes `GT` and `ISZERO` for code that uses `>`, but only requires `LT` for `>=`. A similar behaviour applies for `>`, which uses opcodes `LT` and `ISZERO`, but only requires `GT` for `<=`.


Gas saved per Instance: ~3 *(Total: ~372)*
<details>
<summary><i>There are 124 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize(); 

90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed(); 

156:                 if (incomingBid.ercAmount > lowestSell.ercAmount) { 

221:         uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount; 

292:         if (b.dustAskId > 0) { 

294:         } else if (b.dustShortId > 0) { 

299:         if (matchTotal.shortFillEth > 0) { 

346:             bool shortPriceLessThanAskPrice = lowestShort.price < lowestAsk.price; 

396:         } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) { 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L87), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L90), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L156), [221](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L221), [292](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L292), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L294), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L299), [346](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L346), [396](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L396)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

109:             if (dethAssessable > 0) { 

111:                 if (withdrawalFeePct > 0) { 

150:         if (dethTotal > C.BRIDGE_YIELD_UPDATE_THRESHOLD && amount.div(dethTotal) > C.BRIDGE_YIELD_PERCENT_THRESHOLD) { 
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L64), [83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L83), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L109), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L111), [150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L150)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback(); 

99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback(); 

103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed(); 

174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback(); 

178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral(); 

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount(); 

204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR(); 
```
[53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L103), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L178), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L201), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L204)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

56:         if (shortHintArray.length > 10) revert Errors.TooManyHints(); 

102:             (lowestAskKey == C.TAIL || s.asks[m.asset][lowestAskKey].price > bufferPrice) 

106:                     || s.shorts[m.asset][startingShortId].price > bufferPrice 

169:         if (TAPP.ethEscrowed < m.ethDebt) { 

230:         if (a > type(uint88).max) revert Errors.InvalidAmount(); 
231:         return a < b ? uint88(a) : b;
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L102), [106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L106), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L169), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L230-L231)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) { 

62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals(); 

68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed(); 

78:         for (uint8 i = 0; i < proposalInput.length; i++) { 

93:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue; 

101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break; 

111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) { 

117:             if (p.colRedeemed > currentSR.collateral) { 

140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break; 

143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

181:         if (p.currentCR > 1.7 ether) { 

184:         } else if (p.currentCR > 1.5 ether) { 

188:         } else if (p.currentCR > 1.3 ether) { 

192:         } else if (p.currentCR > 1.2 ether) { 

196:         } else if (p.currentCR > 1.1 ether) { 

205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh(); 

208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed(); 

242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed) 

263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 

279:             if (incorrectIndex > 0) { 

315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed(); 

321:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed(); 

397:         assert(newBaseRate > 0); // Base rate is always non-zero after redemption 
```
[38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L38), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L62), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L68), [70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L70), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L93), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L101), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L111), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L117), [140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L140), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L143), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L181), [184](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L184), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L188), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L192), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L196), [205](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L205), [208](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L208), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L259), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263), [279](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L279), [315](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L315), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321), [354](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L354), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

51:         if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) { 

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset); 

59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize(); 

62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed(); 

85:         if (incomingShort.price < p.oraclePrice) { 
```
[51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L51), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L59), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L62), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L85)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

59:             if (creditSteth < C.ROUNDING_ZERO) { 

63:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) { 

89:             if (creditReth < C.ROUNDING_ZERO) { 

93:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) { 

125:         if (factorReth > factorSteth) { 

131:         } else if (factorSteth > factorReth) { 

156:             if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) { 

161:             if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) { 

163:                 if (creditReth > collateral) { 

170:             } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) { 

172:                 if (creditSteth > collateral) { 

182:                 if (creditTotal > collateral) { 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L59), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L63), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L89), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L93), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L125), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L131), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L156), [161](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L161), [163](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L163), [170](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L170), [172](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L172), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L182)

```solidity
📁 File: contracts/libraries/LibBytes.sol

18:         for (uint256 i = 0; i < slateLength; i++) { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)

```solidity
📁 File: contracts/libraries/LibOracle.sol

30:                 uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0; 

60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice(); 

76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 
77:             || block.timestamp > 2 hours + timeStamp;

79:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth; 
80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

95:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth; 

104:                     if (wethBal < 100 ether) { 

125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool(); 

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76-L77), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L79-L80), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L95), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L104), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125-L126), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169)

```solidity
📁 File: contracts/libraries/LibOrders.sol

45:         if (timeTillMatch > C.MIN_DURATION) { 

71:         for (uint256 i = 0; i < size; i++) { 

90:         if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) { 

111:         if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) { 

132:         if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) { 

239:         bool check2 = _newPrice > s.bids[asset][_nextId].price || _nextId == C.TAIL; 

270:         bool check2 = _newPrice < orders[asset][_nextId].price || _nextId == C.TAIL; 

564:         if (incomingAsk.price > s.bids[asset][startingId].price) { 

583:                 if (incomingAsk.ercAmount > highestBid.ercAmount) { 

608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) { 

712:         uint88 fillErc = incomingSell.ercAmount > highestBid.ercAmount ? highestBid.ercAmount : incomingSell.ercAmount; 

743:             for (uint256 i = 0; i < shortHintArray.length;) { 

762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice; 
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;

792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether; 

794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether; 

821:         } else if (incomingShort.price < startingShortPrice && incomingShort.price >= savedPrice) { 

832:         for (uint256 i; i < orderHintArray.length; i++) { 

904:             if (shortRecord.ercDebt < minShortErc) { 

960:         bool isDiscounted = savedPrice > price.mul(1.01 ether); 

986:         return a < b ? a : b; 

990:         return a > b ? a : b; 
```
[45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L45), [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L90), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L111), [132](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L132), [239](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L239), [270](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L270), [564](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L564), [583](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L583), [608](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L608), [712](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L712), [743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743), [762](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L762-L763), [792](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L792), [794](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L794), [821](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L821), [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832), [904](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L904), [960](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L960), [986](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L986), [990](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L990)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

35:         if (yield > 0) { 

40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS; 

64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) { 

88:                 if (shortOrder.ercAmount < minShortErc) { 

95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount(); 

97:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) { 

110:         if (shortRecordCR < recoveryCR) { 

113:             if (Asset.ercDebt > 0) { 

116:                 if (assetCR < recoveryCR) { 

158:         if (ercDebt > 0) { 
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L40), [64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L64), [88](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L88), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L95), [97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L97), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L110), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L113), [116](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L116), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192); 

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128); 

65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) { 
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

</details>


---
### [GAS&#x2011;2] `address(this)` should be cached when used multiple times

<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit 'address(this)' used 4 times
154:     function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private { 

/// @audit 'address(this)' used 4 times
240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private { 
```
[154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)


---
### [GAS&#x2011;3] Assigning state variables directly with named struct constructors wastes gas
Using named arguments for struct means that the compiler needs to organize the fields in memory before doing the assignment, which wastes gas. Set each field directly in storage (use dot-notation), or use the unnamed version of the constructor.


Gas saved per Instance: ~28 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibBytes.sol

45:             data[i] = MTypes.ProposalData({ 
46:                 shorter: shorter,
47:                 shortId: shortId,
48:                 CR: CR,
49:                 ercDebtRedeemed: ercDebtRedeemed,
50:                 colRedeemed: colRedeemed
51:             });
```
[45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L45-L51)


---
### [GAS&#x2011;4] Avoid contract existence checks by using low-level calls
Prior to 0.8.10 the compiler inserted extra code, including `EXTCODESIZE` (**100 gas**), to check for contract existence for external function calls. In more recent solidity versions, the compiler will not insert these checks if the external call has a return value. Similar behavior can be achieved in earlier versions by using low-level calls, since low-level calls never check for contract existence


Gas saved per Instance: ~100 *(Total: ~1,400)*
<details>
<summary><i>There are 14 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId); 

295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId); 
```
[293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L293), [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L295)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

68:         uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast) 

87:         uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH 

121:         IBridge(bridge).withdraw(msg.sender, ethAmount); 

142:         IBridge(bridge).withdraw(msg.sender, ethAmount); 
```
[68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87), [121](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L121), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L142)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray); 
```
[187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L187)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

188:             IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray); 
```
[188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

63:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) { 

93:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) { 
```
[63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L63), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L93)

```solidity
📁 File: contracts/libraries/LibOracle.sol

87:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice) 

133:         uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133)

```solidity
📁 File: contracts/libraries/LibOrders.sol

982:         IDiamond(payable(address(this)))._updateYieldDiamond(vault); 
```
[982](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L982)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L59)

</details>


---
### [GAS&#x2011;5] Cache external calls outside of loop to avoid re-calling function on each iteration
Performing `STATICCALL` that do not depend on variables incremented in loops should always try to be avoided within the loop. In the following instances, we are able to cache the external calls outside of the loop to save a `STATICCALL` (100 gas) per loop iteration.


Gas saved per Instance: ~100 *(Total: ~900)*
<details>
<summary><i>There are 9 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit disburseCollateral() on line 138
/// @audit concat() on line 129
/// @audit mulU88() on line 116
/// @audit cancelShort() on line 113
/// @audit InvalidShortOrder() on line 112
/// @audit getCollateralRatio() on line 90
/// @audit updateErcDebt() on line 89
78:         for (uint8 i = 0; i < proposalInput.length; i++) { 
79:             p.shorter = proposalInput[i].shorter;
80:             p.shortId = proposalInput[i].shortId;
81:             p.shortOrderId = proposalInput[i].shortOrderId;
82:             // @dev Setting this above _onlyValidShortRecord to allow skipping
83:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84: 
85:             /// Evaluate proposed shortRecord
86: 
87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88: 
89:             currentSR.updateErcDebt(p.asset);
90:             p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91: 
92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94: 
95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96:             if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97:                 p.amountProposed = currentSR.ercDebt;
98:             } else {
99:                 p.amountProposed = redemptionAmount - p.totalAmountProposed;
100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102:             }
103: 
104:             /// At this point, the shortRecord passes all checks and will be included in the slate
105: 
106:             p.previousCR = p.currentCR;
107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
115: 
116:             p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117:             if (p.colRedeemed > currentSR.collateral) {
118:                 p.colRedeemed = currentSR.collateral;
119:             }
120: 
121:             currentSR.collateral -= p.colRedeemed;
122:             currentSR.ercDebt -= p.amountProposed;
123: 
124:             p.totalAmountProposed += p.amountProposed;
125:             p.totalColRedeemed += p.colRedeemed;
126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes
128:             // instead of usual abi.encode to save on extra zeros being written
129:             slate = bytes.concat(
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
137: 
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139:             p.redemptionCounter++;
140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141:         }

/// @audit CannotDisputeWithRedeemerProposal() on line 244
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 
243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244:                 revert Errors.CannotDisputeWithRedeemerProposal();
245:             }
246:         }
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78-L141), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242-L246)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit mul() on line 761
743:             for (uint256 i = 0; i < shortHintArray.length;) { 
744:                 shortHintId = shortHintArray[i];
745:                 unchecked {
746:                     ++i;
747:                 }
748: 
749:                 STypes.Order storage short = s.shorts[asset][shortHintId];
750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }
756: 
757:                 uint80 shortPrice = short.price;
758:                 uint16 prevId = short.prevId;
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;
760:                 // @dev force hint to be within 0.5% of oraclePrice
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764: 
765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {
773:                     Asset.startingShortId = C.HEAD;
774:                     return;
775:                 }
776:             }
```
[743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743-L776)

</details>


---
### [GAS&#x2011;6] Consider activating `via-ir` for deploying
The IR-based code generator was introduced with an aim to not only allow code generation to be more transparent and auditable but also to enable more powerful optimization passes that span across functions.You can enable it on the command line using `--via-ir` or with the option `{"viaIR": true}`.This will take longer to compile, but you can just simple test it before deploying and if you got a better benchmark then you can add --via-ir to your deploy commandMore on: https://docs.soliditylang.org/en/v0.8.17/ir-breaking-changes.html


---
### [GAS&#x2011;7] Consider merging sequential for loops
Merging multiple `for` loops within a function in Solidity can enhance efficiency and reduce gas costs, especially when they share a common iterating variable or perform related operations. By minimizing redundant iterations over the same data set, execution becomes more cost-effective. However, while merging can optimize gas usage and simplify logic, it may also increase code complexity. Therefore, careful balance between optimization and maintainability is essential, along with thorough testing to ensure the refactored code behaves as expected.


<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit consider merging with loops from line: 263
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

/// @audit consider merging with loops from line: 242
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 
```
[242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263)


---
### [GAS&#x2011;8] Consider pre-calculating the address of `address(this)`
It can be more gas-efficient to use a hardcoded address instead of the `address(this)` expression, especially if you need to use the same address multiple times in your contract.

The reason for this, is that using `address(this)` requires an additional `EXTCODESIZE` operation to retrieve the contract’s address from its bytecode, which can increase the gas cost of your contract. By pre-calculating and using a hardcoded address, you can avoid this additional operation and reduce the overall gas cost of your contract.

<details>
<summary><i>There are 18 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId); 

295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId); 
```
[293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L293), [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L295)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

114:                     s.vaultUser[vault][address(this)].ethEscrowed += fee; 

139:         s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount; 
```
[114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L114), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L139)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray); 
```
[187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L187)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

165:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

188:             IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray); 

193:         s.assetUser[m.asset][address(this)].ercEscrowed -= m.ercDebtMatched; 

211:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

263:             if (m.loseCollateral && m.shorter != address(this)) { 

269:                     address(this), 

280:         if (m.shorter != address(this)) { 
```
[165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188), [193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L193), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L263), [269](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L269), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L280)

```solidity
📁 File: contracts/libraries/LibOracle.sol

87:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice) 

133:         uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133)

```solidity
📁 File: contracts/libraries/LibOrders.sol

982:         IDiamond(payable(address(this)))._updateYieldDiamond(vault); 
```
[982](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L982)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

44:                 s.vaultUser[vault][address(this)].ethEscrowed += yield; 
```
[44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L44)

</details>


---
### [GAS&#x2011;9] Consider reducing redundant checks in each iteration of loops.
Having to perform the same check on every iteration of the loop is gas consuming, redundant and unnecessary since the check is not dependent on the loop iteration.

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

139:         while (true) { 
140:             // @dev Handles scenario when no sells left after partial fill
141:             if (b.askId == C.TAIL && b.shortId == C.TAIL) {
/// @audit Check can be moved outside of loop
142:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
144:                 }
145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
146:             }
147: 
148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);
149: 
/// @audit Check can be moved outside of loop
150:             if (incomingBid.price >= lowestSell.price) {
151:                 // Consider bid filled if only dust amount left
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
154:                 }
155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156:                 if (incomingBid.ercAmount > lowestSell.ercAmount) {
157:                     incomingBid.ercAmount -= lowestSell.ercAmount;
158:                     lowestSell.ercAmount = 0;
/// @audit Check can be moved outside of loop
159:                     if (lowestSell.isShort()) {
160:                         b.matchedShortId = lowestSell.id;
161:                         b.prevShortId = lowestSell.prevId;
162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164:                     } else {
165:                         b.matchedAskId = lowestSell.id;
166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167:                         b.askId = lowestSell.nextId;
168:                     }
169:                 } else {
170:                     if (incomingBid.ercAmount == lowestSell.ercAmount) {
/// @audit Check can be moved outside of loop
171:                         if (lowestSell.isShort()) {
172:                             b.matchedShortId = lowestSell.id;
173:                             b.prevShortId = lowestSell.prevId;
174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175:                         } else {
176:                             b.matchedAskId = lowestSell.id;
177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178:                         }
179:                     } else {
180:                         lowestSell.ercAmount -= incomingBid.ercAmount;
/// @audit Check can be moved outside of loop
181:                         if (lowestSell.isShort()) {
182:                             b.dustShortId = lowestSell.id;
183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184:                             lowestShort.ercAmount = lowestSell.ercAmount;
185:                         } else {
186:                             b.dustAskId = lowestSell.id;
187:                             s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188:                         }
189:                         // Check reduced dust threshold for existing limit orders
/// @audit Check can be moved outside of loop
190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191:                             b.dustShortId = b.dustAskId = 0;
192:                         }
193:                     }
194:                     incomingBid.ercAmount = 0;
195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
196:                 }
197:             } else {
/// @audit Check can be moved outside of loop
198:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
200:                 }
201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
202:             }
203:         }
```
[139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L139-L203)

```solidity
📁 File: contracts/libraries/LibOrders.sol

448:         while (true) { 
449:             uint16 nextId = orders[asset][hintId].nextId;
450: 
451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
452:                 return hintId;
453:             }
454: 
/// @audit Check can be moved outside of loop
455:             if (direction == C.PREV) {
456:                 uint16 prevId = orders[asset][hintId].prevId;
457:                 hintId = prevId;
458:             } else {
459:                 hintId = nextId;
460:             }
461:         }

572:         while (true) { 
573:             STypes.Order memory highestBid = s.bids[asset][startingId];
/// @audit Check can be moved outside of loop
574:             if (incomingAsk.price <= highestBid.price) {
575:                 // Consider ask filled if only dust amount left
576:                 if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577:                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578:                     incomingAsk.ercAmount = 0;
579:                     matchIncomingSell(asset, incomingAsk, matchTotal);
580:                     return;
581:                 }
582:                 matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
/// @audit Check can be moved outside of loop
583:                 if (incomingAsk.ercAmount > highestBid.ercAmount) {
584:                     incomingAsk.ercAmount -= highestBid.ercAmount;
585:                     highestBid.ercAmount = 0;
586:                     matchOrder(s.bids, asset, highestBid.id);
587: 
588:                     // loop
589:                     startingId = highestBid.nextId;
590:                     if (startingId == C.TAIL) {
591:                         matchIncomingSell(asset, incomingAsk, matchTotal);
592: 
/// @audit Check can be moved outside of loop
593:                         if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594:                             addSellOrder(incomingAsk, asset, orderHintArray);
595:                         }
596:                         s.bids[asset][C.HEAD].nextId = C.TAIL;
597:                         return;
598:                     }
599:                 } else {
600:                     if (incomingAsk.ercAmount == highestBid.ercAmount) {
601:                         matchOrder(s.bids, asset, highestBid.id);
602:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603:                     } else {
604:                         highestBid.ercAmount -= incomingAsk.ercAmount;
605:                         s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607:                         // Check reduced dust threshold for existing limit orders
608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609:                             cancelBid(asset, highestBid.id);
610:                         }
611:                     }
612:                     incomingAsk.ercAmount = 0;
613:                     matchIncomingSell(asset, incomingAsk, matchTotal);
614:                     return;
615:                 }
616:             } else {
617:                 updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
618:                 matchIncomingSell(asset, incomingAsk, matchTotal);
619: 
/// @audit Check can be moved outside of loop
620:                 if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621:                     addSellOrder(incomingAsk, asset, orderHintArray);
622:                 }
623:                 return;
624:             }
625:         }
```
[448](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L448-L461), [572](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L572-L625)

</details>


---
### [GAS&#x2011;10] Consider using OpenZeppelin's `EnumerateSet` instead of nested mappings
Nested mappings and multi-dimensional arrays in Solidity operate through a process of double hashing, wherein the original storage slot and the first key are concatenated and hashed, and then this hash is again concatenated with the second key and hashed. This process can be quite gas expensive due to the double-hashing operation and subsequent storage operation (sstore).

OpenZeppelin's `EnumerableSet` provides a potential solution to this problem. It creates a data structure that combines the benefits of set operations with the ability to enumerate stored elements, which is not natively available in Solidity. EnumerableSet handles the element uniqueness internally and can therefore provide a more gas-efficient and collision-resistant alternative to nested mappings or multi-dimensional arrays in certain scenarios.


Gas saved per Instance: ~1,000 *(Total: ~12,000)*

<i>There are 12 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOrders.sol

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 

174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 

827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders, 
```
[55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L174), [261](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L261), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L321), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L363), [403](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L403), [441](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L441), [475](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L475), [533](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L533), [827](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L827)


---
### [GAS&#x2011;11] Consider using Solady's gas optimized lib for Math
Utilizing gas-optimized math functions from libraries like [Solady](https://github.com/Vectorized/solady/blob/main/src/utils/FixedPointMathLib.sol) can lead to more efficient smart contracts.
This is particularly beneficial in contracts where these operations are frequently used.

<details>
<summary><i>There are 14 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees 

180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast) 

223:             VaultUser.ethEscrowed += callerFee - m.gasFee + tappFee; 
```
[140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L140), [180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180), [223](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L223)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether); 

187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether); 

191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether); 

195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether); 

198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether); 

388:         uint256 secondsPassed = uint256((protocolTime - Asset.lastRedemptionTime)) * 1 ether; 
```
[183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L388)

```solidity
📁 File: contracts/libraries/LibBytes.sol

20:             uint256 offset = i * 51 + 32; 
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L20)

```solidity
📁 File: contracts/libraries/LibOracle.sol

93:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 

141:         uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 
```
[93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141)

```solidity
📁 File: contracts/libraries/LibOrders.sol

36:         return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES; 

47:             uint88 shares = eth * (timeTillMatch / 1 days); 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47)

</details>


---
### [GAS&#x2011;12] Constructors can be marked `payable`
Payable functions cost less gas to execute, since the compiler does not have to add extra checks to ensure that a payment wasn't provided. A constructor can safely be marked as payable, since only the deployer would be able to pass funds, and the project itself would not pass any funds.


Gas saved per Instance: ~21 *(Total: ~63)*
<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

29:     constructor(address _rethBridge, address _stethBridge) { 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

28:     constructor(address _dusd) { 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

30:     constructor(address _dusd) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

</details>


---
### [GAS&#x2011;13] Counting down in `for` statements is more gas efficient
Counting down is more gas efficient than counting up because neither we are making zero variable to non-zero variable and also we will get gas refund in the last transaction when making non-zero to zero variable. [More info](https://solodit.xyz/issues/g-02-counting-down-in-for-statements-is-more-gas-efficient-code4rena-pooltogether-pooltogether-git)


Gas saved per Instance: ~16 *(Total: ~128)*
<details>
<summary><i>There are 8 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

78:         for (uint8 i = 0; i < proposalInput.length; i++) { 

242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 

321:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321)

```solidity
📁 File: contracts/libraries/LibBytes.sol

18:         for (uint256 i = 0; i < slateLength; i++) { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)

```solidity
📁 File: contracts/libraries/LibOrders.sol

71:         for (uint256 i = 0; i < size; i++) { 

/// @audit increments @ line 746
743:             for (uint256 i = 0; i < shortHintArray.length;) { 
744:                 shortHintId = shortHintArray[i];
745:                 unchecked {
746:                     ++i;
747:                 }
748: 
749:                 STypes.Order storage short = s.shorts[asset][shortHintId];
750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }
756: 
757:                 uint80 shortPrice = short.price;
758:                 uint16 prevId = short.prevId;
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;
760:                 // @dev force hint to be within 0.5% of oraclePrice
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764: 
765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {
773:                     Asset.startingShortId = C.HEAD;
774:                     return;
775:                 }
776:             }

832:         for (uint256 i; i < orderHintArray.length; i++) { 
```
[71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743-L776), [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832)

</details>


---
### [GAS&#x2011;14] Declare variables outside of loops
Variables should be declared outside of loops, and get overriden with each iteration of loop, By doing so we save gas cost for memory variable declaration in each iteration.


Gas saved per Instance: ~15 *(Total: ~390)*
<details>
<summary><i>There are 26 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit loop from line 139 to line 203
148:             STypes.Order memory lowestSell = _getLowestSell(asset, b); 

/// @audit loop from line 139 to line 203
183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id]; 
```
[148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L148), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L183)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit loop from line 78 to line 141
83:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId]; 

/// @audit loop from line 78 to line 141
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId]; 

/// @audit loop from line 263 to line 272
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId]; 

/// @audit loop from line 321 to line 330
322:             MTypes.ProposalData memory currentProposal = decodedProposalData[i]; 
```
[83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L83), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L110), [266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L266), [322](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L322)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit loop from line 18 to line 52
20:             uint256 offset = i * 51 + 32; 

/// @audit loop from line 18 to line 52
22:             address shorter; // bytes20 
/// @audit loop from line 18 to line 52
23:             uint8 shortId; // bytes1
/// @audit loop from line 18 to line 52
24:             uint64 CR; // bytes8
/// @audit loop from line 18 to line 52
25:             uint88 ercDebtRedeemed; // bytes11
/// @audit loop from line 18 to line 52
26:             uint88 colRedeemed; // bytes11
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L20), [22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L22-L26)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit loop from line 448 to line 461
449:             uint16 nextId = orders[asset][hintId].nextId; 

/// @audit loop from line 448 to line 461
456:                 uint16 prevId = orders[asset][hintId].prevId; 

/// @audit loop from line 572 to line 625
573:             STypes.Order memory highestBid = s.bids[asset][startingId]; 

/// @audit loop from line 743 to line 776
749:                 STypes.Order storage short = s.shorts[asset][shortHintId]; 

/// @audit loop from line 743 to line 776
751:                     O shortOrderType = short.orderType; 

/// @audit loop from line 743 to line 776
757:                 uint80 shortPrice = short.price; 
/// @audit loop from line 743 to line 776
758:                 uint16 prevId = short.prevId;
/// @audit loop from line 743 to line 776
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;

/// @audit loop from line 743 to line 776
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice; 
/// @audit loop from line 743 to line 776
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
/// @audit loop from line 743 to line 776
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;

/// @audit loop from line 832 to line 843
833:             MTypes.OrderHint memory orderHint = orderHintArray[i]; 
/// @audit loop from line 832 to line 843
834:             STypes.Order storage order = orders[asset][orderHint.hintId];
/// @audit loop from line 832 to line 843
835:             O hintOrderType = order.orderType;
```
[449](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L449), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573), [749](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L749), [751](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L751), [757](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L757-L759), [761](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L761-L763), [833](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L833-L835)

</details>


---
### [GAS&#x2011;15] Do not cache state variables that are used only once
It's cheaper to access the state variable directly if it is accessed only once. This can save the **3 gas** cost of the extra stack allocation.


Gas saved per Instance: ~3 *(Total: ~12)*
<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id]; 

400:             STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId]; 
```
[183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L183), [400](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L400)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

313:         STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender]; 

363:         STypes.Asset storage Asset = s.asset[asset]; 
```
[313](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L313), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L363)

</details>


---
### [GAS&#x2011;16] `do`-`while` is cheaper than `for`-loops when the initial check can be skipped
Using `do-while` loops instead of `for` loops can be more gas-efficient.
Even if you add an `if` condition to account for the case where the loop doesn't execute at all, a `do-while` loop can still be cheaper in terms of gas.


Gas saved per Instance: ~255 *(Total: ~2,040)*
<details>
<summary><i>There are 8 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

78:         for (uint8 i = 0; i < proposalInput.length; i++) { 

242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 

321:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321)

```solidity
📁 File: contracts/libraries/LibBytes.sol

18:         for (uint256 i = 0; i < slateLength; i++) { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)

```solidity
📁 File: contracts/libraries/LibOrders.sol

71:         for (uint256 i = 0; i < size; i++) { 

743:             for (uint256 i = 0; i < shortHintArray.length;) { 

832:         for (uint256 i; i < orderHintArray.length; i++) { 
```
[71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743), [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832)

</details>


---
### [GAS&#x2011;17] Function names can be optimized
Function that are `public`/`external` and `public` state variable names can be optimized to save gas.

Method IDs that have two leading zero bytes can save **128 gas** each during deployment, and renaming functions to have lower method IDs will save **22 gas** per call, per sorted position shifted. [Reference](https://blog.emn178.cc/en/post/solidity-gas-optimization-function-name/)


Gas saved per Instance: ~128 *(Total: ~384)*
<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit optimized order: getDethTotal(), withdrawTapp(), deposit(), depositEth(), getBridges(), withdraw(), maybeUpdateYield(), _getVault(), _ethConversion()
18: contract BridgeRouterFacet is Modifiers { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit optimized order: exitShortErcEscrowed(), exitShortWallet(), exitShort(), getCollateralRatioNonPrice()
19: contract ExitShortFacet is Modifiers { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit optimized order: validRedemptionSR(), claimRedemption(), proposeRedemption(), claimRemainingCollateral(), disputeRedemption(), _claimRemainingCollateral(), calculateRedemptionFee()
21: contract RedemptionFacet is Modifiers { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21)

</details>


---
### [GAS&#x2011;18] Functions guaranteed to revert when called by normal users can be marked `payable`
If a function modifier such as `onlyOwner` is used, the function will revert if a normal user tries to pay the function. Marking the function as `payable` will lower the gas cost for legitimate callers because the compiler will not include checks for whether a payment was provided.


Gas saved per Instance: ~21 *(Total: ~147)*
<details>
<summary><i>There are 7 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {

87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {

142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

35:     function createLimitShort( 
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)

</details>


---
### [GAS&#x2011;19] Integer increments by one can be unchecked
Using unchecked increments in Solidity can save on gas fees by bypassing built-in overflow checks, thus optimizing gas usage, but requires careful assessment of potential risks and edge cases to avoid unintended consequences.


Gas saved per Instance: ~60 *(Total: ~600)*
<details>
<summary><i>There are 10 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

78:         for (uint8 i = 0; i < proposalInput.length; i++) { 

139:             p.redemptionCounter++; 

242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 

263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 

321:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L139), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321)

```solidity
📁 File: contracts/libraries/LibBytes.sol

18:         for (uint256 i = 0; i < slateLength; i++) { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)

```solidity
📁 File: contracts/libraries/LibOrders.sol

64:             size++; 

71:         for (uint256 i = 0; i < size; i++) { 

210:             s.asset[asset].orderIdCounter += 1; 

832:         for (uint256 i; i < orderHintArray.length; i++) { 
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L64), [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L210), [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832)

</details>


---
### [GAS&#x2011;20] `internal` functions only used once can be inlined so save gas
If a internal function is only used once it doesn't make sense to modularise it unless the function which does call the function would be overly long and complex otherwise


Gas saved per Instance: ~30 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
```
[382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382)


---
### [GAS&#x2011;21] Multiple accesses of the same mapping/array key/index should be cached
The instances below point to the second+ access of a value inside a mapping/array key/index, within a function. Caching a mapping's value in a local storage or calldata variable when the value is accessed [multiple times](https://gist.github.com/IllIllI000/ec23a57daa30a8f8ca8b9681c8ccefb0), saves ~42 gas per access due to not having to recalculate the key's keccak256 hash (Gkeccak256 - 30 gas) and that calculation's associated stack operations. Caching an array's struct avoids recalculating the array offsets into memory/calldata


Gas saved per Instance: ~42 *(Total: ~1,386)*
<details>
<summary><i>There are 33 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit s.asset[asset] is also accessed on line 232
255:             s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth; 

/// @audit s.shorts[asset] is also accessed on line 310
/// @audit s.shorts[asset] is also accessed on line 312
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId; 

/// @audit s.asks[asset] is also accessed on line 343
354:             return s.asks[asset][b.askId]; 

/// @audit s.shorts[asset] is also accessed on line 391
/// @audit s.shorts[asset] is also accessed on line 398
400:             STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId]; 
```
[255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L255), [323](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L323), [354](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L354), [400](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L400)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit s.bids[asset] is also accessed on line 72
73:         STypes.Order storage highestBid = s.bids[asset][p.startingId]; 
```
[73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L73)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit s.vaultUser[vault] is also accessed on line 151
154:             STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to]; 
```
[154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L154)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit s.bids[asset] is also accessed on line 151
152:         s.bids[asset][C.HEAD].creationTime = oracleTime; 
```
[152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L152)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit orders[asset] is also accessed on line 60
/// @audit orders[asset] is also accessed on line 65
/// @audit orders[asset] is also accessed on line 69
/// @audit orders[asset] is also accessed on line 72
/// @audit orders[asset][currentId] is also accessed on line 65
/// @audit orders[asset][currentId] is also accessed on line 72
73:             currentId = orders[asset][currentId].nextId; 

/// @audit s.bids[asset] is also accessed on line 89
90:         if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) { 

/// @audit s.asks[asset] is also accessed on line 110
111:         if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) { 

/// @audit s.shorts[asset] is also accessed on line 131
132:         if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) { 

/// @audit orders[asset][canceledID] is also accessed on line 192
195:             uint16 prevCanceledID = orders[asset][canceledID].prevId; 

/// @audit orders[asset][prevId] is also accessed on line 183
/// @audit orders[asset] is also accessed on line 183
/// @audit orders[asset] is also accessed on line 187
/// @audit orders[asset] is also accessed on line 192
/// @audit orders[asset] is also accessed on line 195
/// @audit orders[asset] is also accessed on line 197
/// @audit orders[asset] is also accessed on line 201
/// @audit orders[asset] is also accessed on line 212
/// @audit orders[asset] is also accessed on line 214
217:         orders[asset][prevId].nextId = incomingOrder.id; 

/// @audit s.bids[asset] is also accessed on line 238
239:         bool check2 = _newPrice > s.bids[asset][_nextId].price || _nextId == C.TAIL; 

/// @audit orders[asset] is also accessed on line 268
270:         bool check2 = _newPrice < orders[asset][_nextId].price || _nextId == C.TAIL; 

/// @audit orders[asset] is also accessed on line 291
/// @audit orders[asset] is also accessed on line 297
/// @audit orders[asset] is also accessed on line 297
/// @audit orders[asset] is also accessed on line 297
/// @audit orders[asset] is also accessed on line 298
/// @audit orders[asset] is also accessed on line 298
/// @audit orders[asset] is also accessed on line 298
/// @audit orders[asset][id] is also accessed on line 297
/// @audit orders[asset][id] is also accessed on line 297
/// @audit orders[asset][id] is also accessed on line 298
/// @audit orders[asset][id] is also accessed on line 298
301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType); 

/// @audit orders[asset][id] is also accessed on line 333
/// @audit orders[asset][id] is also accessed on line 340
/// @audit orders[asset] is also accessed on line 333
/// @audit orders[asset] is also accessed on line 334
/// @audit orders[asset] is also accessed on line 340
347:             orders[asset][id].prevId = C.HEAD; 

/// @audit orders[asset][hintId] is also accessed on line 368
/// @audit orders[asset] is also accessed on line 368
386:             uint16 prevId = orders[asset][hintId].prevId; 

/// @audit orders[asset][hintId] is also accessed on line 449
/// @audit orders[asset] is also accessed on line 449
456:                 uint16 prevId = orders[asset][hintId].prevId; 

/// @audit orders[asset] is also accessed on line 487
488:             orders[asset][C.HEAD].nextId = id; 

/// @audit orders[asset] is also accessed on line 540
/// @audit orders[asset] is also accessed on line 542
544:         orders[asset][headId].nextId = nextAskId; 

/// @audit s.bids[asset][startingId] is also accessed on line 564
573:             STypes.Order memory highestBid = s.bids[asset][startingId]; 

/// @audit s.bids[asset] is also accessed on line 563
/// @audit s.bids[asset] is also accessed on line 564
/// @audit s.bids[asset] is also accessed on line 573
/// @audit s.bids[asset] is also accessed on line 596
605:                         s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount; 

/// @audit s.shorts[asset] is also accessed on line 738
/// @audit s.shorts[asset] is also accessed on line 749
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price; 

/// @audit s.shorts[asset] is also accessed on line 814
815:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL; 

/// @audit s.shorts[asset] is also accessed on line 884
943:             uint256 prevPrice = s.shorts[asset][shortOrder.prevId].price; 
```
[73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L73), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L90), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L111), [132](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L132), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [217](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L217), [239](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L239), [270](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L270), [301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L347), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L386), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [488](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L488), [544](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L544), [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573), [605](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L605), [759](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L759), [815](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L815), [943](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L943)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit s.vaultUser[vault] is also accessed on line 42
44:                 s.vaultUser[vault][address(this)].ethEscrowed += yield; 
```
[44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L44)

</details>


---
### [GAS&#x2011;22] Nesting `if`-statements is cheaper than using `&&`
Using a double if statement instead of logical AND (&&) can provide similar short-circuiting behavior whereas double if is slightly more efficient.


Gas saved per Instance: ~30 *(Total: ~600)*
<details>
<summary><i>There are 20 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) { 

141:             if (b.askId == C.TAIL && b.shortId == C.TAIL) { 

317:             } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) { 

402:             if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) { 
```
[106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L106), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L141), [317](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L317), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L402)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

150:         if (dethTotal > C.BRIDGE_YIELD_UPDATE_THRESHOLD && amount.div(dethTotal) > C.BRIDGE_YIELD_PERCENT_THRESHOLD) { 
```
[150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L150)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

100:         if ( 
101:             // Checks for no eligible asks
102:             (lowestAskKey == C.TAIL || s.asks[m.asset][lowestAskKey].price > bufferPrice)
103:             // Checks for no eligible shorts
104:             && (
105:                 startingShortId == C.HEAD // means no short >= oracleprice
106:                     || s.shorts[m.asset][startingShortId].price > bufferPrice
107:             )

263:             if (m.loseCollateral && m.shorter != address(this)) { 
```
[100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L100-L107), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L263)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) { 

243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) { 

259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed) 

361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort(); 

371:         if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) { 
```
[111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L111), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L259), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L371)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

75:         if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) { 
```
[75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L75)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

156:             if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) { 

170:             } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) { 
```
[156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L156), [170](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L170)

```solidity
📁 File: contracts/libraries/LibOrders.sol

516:             } else if (b.isMovingBack && b.isMovingFwd) { 

821:         } else if (incomingShort.price < startingShortPrice && incomingShort.price >= savedPrice) { 

840:             } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) { 
```
[516](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L516), [821](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L821), [840](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L840)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

97:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) { 
```
[97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L97)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) { 
```
[65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

</details>


---
### [GAS&#x2011;23] Newer versions of solidity are more gas efficient
The solidity language continues to pursue more efficient gas optimization schemes. Adopting a [newer version of solidity](https://github.com/ethereum/solc-js/tags) can be more gas efficient.

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L2)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L2)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L2)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L2)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L2)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L2)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L2)

```solidity
📁 File: contracts/libraries/LibBytes.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L2)

```solidity
📁 File: contracts/libraries/LibOracle.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L2)

```solidity
📁 File: contracts/libraries/LibOrders.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L2)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L2)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

2: pragma solidity 0.8.21; 
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L2)

</details>


---
### [GAS&#x2011;24] Not using the named return variables when a function returns, wastes deployment gas
The solidity compiler outputs more efficient code when the variable is declared in the return statement. There seem to be very few exceptions to this in practice, so if you see an anonymous return, you should test it with a named return instead to determine which case is most efficient.

<details>
<summary><i>There are 52 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
48:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);
49: 
50:         return _createBid(msg.sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray);
51:     }

65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {
70:         // @dev leave empty, don't need hint for market buys
71:         MTypes.OrderHint[] memory orderHintArray;
72: 
73:         // @dev update oracle in callers
74:         return _createBid(sender, asset, price, ercAmount, C.MARKET_ORDER, orderHintArray, shortHintArray);
75:     }

77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
86:         uint256 eth = ercAmount.mul(price);
87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();
88: 
89:         STypes.Asset storage Asset = s.asset[asset];
90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();
91: 
92:         STypes.Order memory incomingBid;
93:         incomingBid.addr = sender;
94:         incomingBid.price = price;
95:         incomingBid.ercAmount = ercAmount;
96:         incomingBid.id = Asset.orderIdCounter;
97:         incomingBid.orderType = isMarketOrder ? O.MarketBid : O.LimitBid;
98:         incomingBid.creationTime = LibOrders.getOffsetTime();
99: 
100:         MTypes.BidMatchAlgo memory b;
101:         b.askId = s.asks[asset][C.HEAD].nextId;
102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
103:         b.shortHintId = b.shortId = Asset.startingShortId;
104: 
105:         STypes.Order memory lowestSell = _getLowestSell(asset, b);
106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109:             b.shortHintId = b.shortId = Asset.startingShortId;
110:             b.oraclePrice = LibOracle.getPrice(asset);
111:             return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112:         } else {
113:             // @dev no match, add to market if limit order
114:             LibOrders.addBid(asset, incomingBid, orderHintArray);
115:             return (0, ercAmount);
116:         }
117:     }

130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
136:         uint256 minBidEth = LibAsset.minBidEth(asset);
137:         MTypes.Match memory matchTotal;
138: 
139:         while (true) {
140:             // @dev Handles scenario when no sells left after partial fill
141:             if (b.askId == C.TAIL && b.shortId == C.TAIL) {
142:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
144:                 }
145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
146:             }
147: 
148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);
149: 
150:             if (incomingBid.price >= lowestSell.price) {
151:                 // Consider bid filled if only dust amount left
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
154:                 }
155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156:                 if (incomingBid.ercAmount > lowestSell.ercAmount) {
157:                     incomingBid.ercAmount -= lowestSell.ercAmount;
158:                     lowestSell.ercAmount = 0;
159:                     if (lowestSell.isShort()) {
160:                         b.matchedShortId = lowestSell.id;
161:                         b.prevShortId = lowestSell.prevId;
162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164:                     } else {
165:                         b.matchedAskId = lowestSell.id;
166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167:                         b.askId = lowestSell.nextId;
168:                     }
169:                 } else {
170:                     if (incomingBid.ercAmount == lowestSell.ercAmount) {
171:                         if (lowestSell.isShort()) {
172:                             b.matchedShortId = lowestSell.id;
173:                             b.prevShortId = lowestSell.prevId;
174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175:                         } else {
176:                             b.matchedAskId = lowestSell.id;
177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178:                         }
179:                     } else {
180:                         lowestSell.ercAmount -= incomingBid.ercAmount;
181:                         if (lowestSell.isShort()) {
182:                             b.dustShortId = lowestSell.id;
183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184:                             lowestShort.ercAmount = lowestSell.ercAmount;
185:                         } else {
186:                             b.dustAskId = lowestSell.id;
187:                             s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188:                         }
189:                         // Check reduced dust threshold for existing limit orders
190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191:                             b.dustShortId = b.dustAskId = 0;
192:                         }
193:                     }
194:                     incomingBid.ercAmount = 0;
195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
196:                 }
197:             } else {
198:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
200:                 }
201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
202:             }
203:         }
204:     }

275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
281:         if (matchTotal.fillEth == 0) {
282:             return (0, incomingBid.ercAmount);
283:         }
284: 
285:         STypes.Asset storage Asset = s.asset[asset];
286:         uint256 vault = Asset.vault;
287: 
288:         LibOrders.updateSellOrdersOnMatch(asset, b);
289: 
290:         // Remove last sell order from order book if under dust threshold
291:         // @dev needs to happen after updateSellOrdersOnMatch()
292:         if (b.dustAskId > 0) {
293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
294:         } else if (b.dustShortId > 0) {
295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
296:         }
297: 
298:         // If at least one short was matched
299:         if (matchTotal.shortFillEth > 0) {
300:             STypes.Vault storage Vault = s.vault[vault];
301: 
302:             // Matched Shares
303:             Vault.dittoMatchedShares += matchTotal.dittoMatchedShares;
304:             // Yield Accounting
305:             Vault.dethCollateral += matchTotal.shortFillEth;
306:             Asset.dethCollateral += matchTotal.shortFillEth;
307:             Asset.ercDebt += matchTotal.fillErc - matchTotal.askFillErc;
308: 
309:             // @dev Approximates the startingShortId after bid is fully executed
310:             STypes.Order storage currentShort = s.shorts[asset][b.shortId];
311:             O shortOrderType = currentShort.orderType;
312:             STypes.Order storage prevShort = s.shorts[asset][b.prevShortId];
313:             O prevShortOrderType = prevShort.orderType;
314: 
315:             if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
316:                 Asset.startingShortId = b.shortId;
317:             } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318:                 Asset.startingShortId = b.prevShortId;
319:             } else {
320:                 if (b.isMovingFwd) {
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }
325:             }
326:         }
327: 
328:         // Match bid
329:         address bidder = incomingBid.addr; // saves 18 gas
330:         s.vaultUser[vault][bidder].ethEscrowed -= matchTotal.fillEth;
331:         s.assetUser[asset][bidder].ercEscrowed += matchTotal.fillErc;
332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
333: 
334:         // @dev match price is based on the order that was already on orderbook
335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);
336:         return (matchTotal.fillEth, incomingBid.ercAmount);
337:     }

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 
341:         if (b.shortId != C.HEAD) {
342:             STypes.Order storage lowestShort = s.shorts[asset][b.shortId];
343:             STypes.Order storage lowestAsk = s.asks[asset][b.askId];
344:             // @dev Setting lowestSell after comparing short and ask prices
345:             bool noAsks = b.askId == C.TAIL;
346:             bool shortPriceLessThanAskPrice = lowestShort.price < lowestAsk.price;
347:             if (noAsks || shortPriceLessThanAskPrice) {
348:                 return lowestShort;
349:             } else {
350:                 return lowestAsk;
351:             }
352:         } else if (b.askId != C.TAIL) {
353:             // @dev Handles scenario when there are no shorts
354:             return s.asks[asset][b.askId];
355:         }
356:     }
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L51), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L75), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L117), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L204), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L337), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340-L356)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Parameter of type 'uint256' at index '0'
40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) { 

/// @audit Parameter of type 'address[]' at index '0'
51:     function getBridges(uint256 vault) external view returns (address[] memory) { 

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) { 
157:         if (bridge == rethBridge) {
158:             vault = VAULT.ONE;
159:         } else if (bridge == stethBridge) {
160:             vault = VAULT.ONE;
161:             bridgePointer = VAULT.BRIDGE_STETH;
162:         } else {
163:             vault = s.bridge[bridge].vault;
164:             if (vault == 0) revert Errors.InvalidBridge();
165:         }
166:     }

/// @audit Parameter of type 'uint88' at index '0'
169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L51), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L156-L166), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
214:         return short.collateral.div(short.ercDebt);
215:     }
```
[213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213-L215)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 

122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 

/// @audit Parameter of type 'uint88' at index '0'
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
383:         internal
384:         returns (uint88 redemptionFee)
385:     {
386:         STypes.Asset storage Asset = s.asset[asset];
387:         uint32 protocolTime = LibOrders.getOffsetTime();
388:         uint256 secondsPassed = uint256((protocolTime - Asset.lastRedemptionTime)) * 1 ether;
389:         uint256 decayFactor = C.SECONDS_DECAY_FACTOR.pow(secondsPassed);
390:         uint256 decayedBaseRate = Asset.baseRate.mulU64(decayFactor);
391:         // @dev Calculate Asset.ercDebt prior to proposal
392:         uint104 totalAssetErcDebt = (ercDebtRedeemed + Asset.ercDebt).mulU104(C.BETA);
393:         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
394:         uint256 redeemedDUSDFraction = ercDebtRedeemed.div(totalAssetErcDebt);
395:         uint256 newBaseRate = decayedBaseRate + redeemedDUSDFraction;
396:         newBaseRate = LibOrders.min(newBaseRate, 1 ether); // cap baseRate at a maximum of 100%
397:         assert(newBaseRate > 0); // Base rate is always non-zero after redemption
398:         // Update the baseRate state variable
399:         Asset.baseRate = uint64(newBaseRate);
400:         Asset.lastRedemptionTime = protocolTime;
401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);
402:         return uint88(redemptionRate.mul(colRedeemed));
403:     }
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L403)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 
114:         IBridge bridgeReth = IBridge(rethBridge);
115:         IBridge bridgeSteth = IBridge(stethBridge);
116: 
117:         // Calculate rETH market premium/discount (factor)
118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);
119:         uint256 unitRethOracle = bridgeReth.getUnitDethValue();
120:         uint256 factorReth = unitRethTWAP.div(unitRethOracle);
121:         // Calculate stETH market premium/discount (factor)
122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);
123:         uint256 unitWstethOracle = bridgeSteth.getUnitDethValue();
124:         uint256 factorSteth = unitWstethTWAP.div(unitWstethOracle);
125:         if (factorReth > factorSteth) {
126:             // rETH market premium relative to stETH
127:             if (bridgePointer == VAULT.BRIDGE_RETH) {
128:                 // Only charge fee if withdrawing rETH
129:                 return factorReth.div(factorSteth) - 1 ether;
130:             }
131:         } else if (factorSteth > factorReth) {
132:             // stETH market premium relative to rETH
133:             if (bridgePointer == VAULT.BRIDGE_STETH) {
134:                 // Only charge fee if withdrawing stETH
135:                 return factorSteth.div(factorReth) - 1 ether;
136:             }
137:         } else {
138:             // Withdrawing less premium LST or premiums are equivalent
139:             return 0;
140:         }
141:     }
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113-L141)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit Parameter of type 'struct MTypes.ProposalData[]' at index '0'
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Parameter of type 'uint256' at index '0'
19:     function getOraclePrice(address asset) internal view returns (uint256) { 

69:     function baseOracleCircuitBreaker( 
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
77:             || block.timestamp > 2 hours + timeStamp;
78:         uint256 chainlinkDiff =
79:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;
81: 
82:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
83:         if (invalidFetchData) {
84:             return twapCircuitBreaker();
85:         } else if (priceDeviation) {
86:             // Check valid twap price
87:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
88:             {
89:                 if (twapPrice == 0) {
90:                     return chainlinkPriceInEth;
91:                 }
92: 
93:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
94:                 uint256 twapPriceInEth = twapPriceNormalized.inv();
95:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
96: 
97:                 // Save the price that is closest to saved oracle price
98:                 if (chainlinkDiff <= twapDiff) {
99:                     return chainlinkPriceInEth;
100:                 } else {
101:                     // Check valid twap liquidity
102:                     IERC20 weth = IERC20(C.WETH);
103:                     uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104:                     if (wethBal < 100 ether) {
105:                         return chainlinkPriceInEth;
106:                     }
107:                     return twapPriceInEth;
108:                 }
109:             } catch {
110:                 return chainlinkPriceInEth;
111:             }
112:         } else {
113:             return chainlinkPriceInEth;
114:         }
115:     }

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) { 
132:         // Check valid price
133:         uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes);
134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice();
135: 
136:         // Check valid liquidity
137:         IERC20 weth = IERC20(C.WETH);
138:         uint256 wethBal = weth.balanceOf(C.USDC_WETH);
139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();
140: 
141:         uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
142:         return twapPriceNormalized.inv();
143:     }

156:     function getTime(address asset) internal view returns (uint256 creationTime) { 
157:         AppStorage storage s = appStorage();
158:         return s.bids[asset][C.HEAD].creationTime;
159:     }

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 
163:         AppStorage storage s = appStorage();
164:         return uint80(s.bids[asset][C.HEAD].ercAmount);
165:     }

/// @audit Parameter of type 'uint256' at index '0'
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L115), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131-L143), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156-L159), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162-L165), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) { 
31:         // shouldn't overflow in 136 years
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)
33:     }

/// @audit Parameter of type 'uint256' at index '0'
35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 

/// @audit Parameter of type 'bool' at index '0'
78:     function isShort(STypes.Order memory order) internal pure returns (bool) { 

231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId) 
232:         internal
233:         view
234:         returns (int256 direction)
235:     {
236:         AppStorage storage s = appStorage();
237:         // @dev: TAIL can't be prevId because it will always be last item in list
238:         bool check1 = s.bids[asset][_prevId].price >= _newPrice || _prevId == C.HEAD;
239:         bool check2 = _newPrice > s.bids[asset][_nextId].price || _nextId == C.TAIL;
240: 
241:         if (check1 && check2) {
242:             return C.EXACT;
243:         } else if (!check1) {
244:             return C.PREV;
245:         } else if (!check2) {
246:             return C.NEXT;
247:         }
248:     }

260:     function verifySellId( 
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {
267:         // @dev: TAIL can't be prevId because it will always be last item in list
268:         bool check1 = orders[asset][_prevId].price <= _newPrice || _prevId == C.HEAD;
269: 
270:         bool check2 = _newPrice < orders[asset][_nextId].price || _nextId == C.TAIL;
271: 
272:         if (check1 && check2) {
273:             return C.EXACT;
274:         } else if (!check1) {
275:             return C.PREV;
276:         } else if (!check2) {
277:             return C.NEXT;
278:         }
279:     }

362:     function findPrevOfIncomingId( 

402:     function verifyId( 
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {
410:         orderType = normalizeOrderType(orderType);
411: 
412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413:             return verifySellId(orders, asset, prevId, newPrice, nextId);
414:         } else if (orderType == O.LimitBid) {
415:             return verifyBidId(asset, prevId, newPrice, nextId);
416:         }
417:     }

420:     function normalizeOrderType(O o) private pure returns (O newO) { 
421:         if (o == O.LimitBid || o == O.MarketBid) {
422:             return O.LimitBid;
423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {
424:             return O.LimitAsk;
425:         } else if (o == O.LimitShort) {
426:             return O.LimitShort;
427:         }
428:     }

440:     function getOrderId( 
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {
448:         while (true) {
449:             uint16 nextId = orders[asset][hintId].nextId;
450: 
451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
452:                 return hintId;
453:             }
454: 
455:             if (direction == C.PREV) {
456:                 uint16 prevId = orders[asset][hintId].prevId;
457:                 hintId = prevId;
458:             } else {
459:                 hintId = nextId;
460:             }
461:         }
462:     }

826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {
831:         bool anyOrderHintPrevMatched;
832:         for (uint256 i; i < orderHintArray.length; i++) {
833:             MTypes.OrderHint memory orderHint = orderHintArray[i];
834:             STypes.Order storage order = orders[asset][orderHint.hintId];
835:             O hintOrderType = order.orderType;
836:             if (hintOrderType == O.Cancelled || hintOrderType == O.Matched) {
837:                 continue;
838:             } else if (order.creationTime == orderHint.creationTime) {
839:                 return orderHint.hintId;
840:             } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
841:                 anyOrderHintPrevMatched = true;
842:             }
843:         }
844: 
845:         if (anyOrderHintPrevMatched) {
846:             // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD
847:             return C.HEAD;
848:         }
849: 
850:         revert Errors.BadHintIdArray();
851:     }

/// @audit Parameter of type 'uint256' at index '0'
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 

/// @audit Parameter of type 'uint256' at index '0'
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30-L33), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L248), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L279), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L417), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420-L428), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L462), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L851), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {
53:         AppStorage storage s = appStorage();
54:         if (initialStatus == SR.PartialFill) {
55:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
56:             STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
58: 
59:             if (shorter == msg.sender) {
60:                 // If call comes from exitShort() or combineShorts() then always cancel
61:                 LibOrders.cancelShort(asset, shortOrderId);
62:                 assert(shortRecord.status != SR.PartialFill);
63:                 return true;
64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
65:                 // If call comes from liquidate() and SR ercDebt under minShortErc
66:                 LibOrders.cancelShort(asset, shortOrderId);
67:                 return true;
68:             }
69:         }
70:     }

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {
76:         AppStorage storage s = appStorage();
77: 
78:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
79:         uint256 minShortErc = LibAsset.minShortErc(asset);
80: 
81:         if (initialStatus == SR.PartialFill) {
82:             // Verify shortOrder
83:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
85: 
86:             if (shortRecord.status == SR.Closed) {
87:                 // Check remaining shortOrder
88:                 if (shortOrder.ercAmount < minShortErc) {
89:                     // @dev The resulting SR will not have PartialFill status after cancel
90:                     LibOrders.cancelShort(asset, shortOrderId);
91:                     isCancelled = true;
92:                 }
93:             } else {
94:                 // Check remaining shortOrder and remaining shortRecord
95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
96:             }
97:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) {
98:             revert Errors.CannotLeaveDustAmount();
99:         }
100:     }

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 
103:         internal
104:         view
105:         returns (bool recoveryViolation)
106:     {
107:         AppStorage storage s = appStorage();
108: 
109:         uint256 recoveryCR = LibAsset.recoveryCR(asset);
110:         if (shortRecordCR < recoveryCR) {
111:             // Only check asset CR if low enough
112:             STypes.Asset storage Asset = s.asset[asset];
113:             if (Asset.ercDebt > 0) {
114:                 // If Asset.ercDebt == 0 then assetCR is NA
115:                 uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt));
116:                 if (assetCR < recoveryCR) {
117:                     // Market is in recovery mode and shortRecord CR too low
118:                     return true;
119:                 }
120:             }
121:         }
122:     }
```
[49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L70), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L100), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L122)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

11:     function observe(uint32[] calldata secondsAgos) 
12:         external
13:         view
14:         returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);

28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken) 
29:         internal
30:         pure
31:         returns (uint256 quoteAmount)
32:     {
33:         uint160 sqrtRatioX96 = TickMath.getSqrtRatioAtTick(tick);
34: 
35:         // Calculate quoteAmount with better precision if it doesn't overflow when multiplied by itself
36:         if (sqrtRatioX96 <= type(uint128).max) {
37:             uint256 ratioX192 = uint256(sqrtRatioX96) * sqrtRatioX96;
38:             quoteAmount =
39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
40:         } else {
41:             uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);
42:             quoteAmount =
43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
44:         }
45:     }

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
53: 
54:         uint32[] memory secondsAgos = new uint32[](2);
55:         secondsAgos[0] = secondsAgo;
56:         secondsAgos[1] = 0;
57: 
58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos);
60: 
61:         int56 tickCumulativesDelta = tickCumulatives[1] - tickCumulatives[0];
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
63: 
64:         // Always round to negative infinity
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
66:             tick--;
67:         }
68: 
69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
70:         amountOut = getQuoteAtTick(tick, amountIn, baseToken, quoteToken);
71:     }
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11-L14), [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28-L45), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L71)

</details>


---
### [GAS&#x2011;25] Optimize Deployment Size by Fine-tuning IPFS Hash
The Solidity compiler appends 53 bytes of metadata to the smart contract code, incurring an extra cost of 10,600 gas. This additional expense arises from 200 gas per bytecode, plus calldata cost, which amounts to 16 gas for non-zero bytes and 4 gas for zero bytes. This results in a maximum of 848 extra gas in calldata cost.

Reducing this cost is crucial for the following reasons:

The metadata's 53-byte addition leads to a deployment cost increase of 10,600 gas.
It can also result in an additional calldata cost of up to 848 gas.
Ways to Minimize Gas Consumption:

Employ the `--no-cbor-metadata` compiler option to exclude metadata. Be cautious as this might impact contract verification.
Search for code comments that yield an IPFS hash with more zeros, thereby reducing calldata costs.


Gas saved per Instance: ~10,600 *(Total: ~127,200)*
<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L1)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L1)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L1)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L1)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L1)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L1)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L1)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L1)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L1)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Consider optimizing the IPFS hash during deployment.
1: // SPDX-License-Identifier: GPL-2.0-or-later 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L1)

</details>


---
### [GAS&#x2011;26] Optimize Ether deposits using the `receive()` function
Consider using receive() function instead of a specific deposit() (or similar) function. If there are several functions in the contract that can receive Ether, it is recommended to use receive() for the most frequently used function. The receive() or fallback() function can handle incoming Ether transfers directly, providing more gas-efficient way to manage deposits.


Gas saved per Instance: ~45 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

82:     function depositEth(address bridge) external payable nonReentrant { 
```
[82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82)


---
### [GAS&#x2011;27] Order of checks in a function can be optimized
Some of the checks below involve expensive operations, such as SLOAD or external calls. Reorder them so that the validations with expensive operations are prevented from being executed if the initial checks fail.


Gas saved per Instance: ~2,100 *(Total: ~12,600)*
<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Gas efficient order: 2,1
/// @audit  1
54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf(); 
55:         // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
/// @audit  2
56:         if (shortHintArray.length > 10) revert Errors.TooManyHints();
```
[54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54-L56)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Gas efficient order: 3,2,1
/// @audit  1
68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 
69: 
/// @audit  2
70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71: 
72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
/// @audit  3
73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();

/// @audit Gas efficient order: 2,1
/// @audit  1
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
236: 
/// @audit  2
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();

/// @audit Gas efficient order: 2,1
/// @audit  1
314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
/// @audit  2
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

/// @audit Gas efficient order: 2,1
/// @audit  1
353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
/// @audit  2
354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();
```
[68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L68-L73), [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235-L237), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314-L315), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353-L354)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Gas efficient order: 2,1
/// @audit  1
130:         if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled(); 
/// @audit  2
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
```
[130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L130-L131)

</details>


---
### [GAS&#x2011;28] Pre-increments/pre-decrements are cheaper than `+1`/`+=1` or `-1`/`-=1`

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit prefer '++claimIndex'
358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1); 
```
[358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L358)


---
### [GAS&#x2011;29] Prefer using `storage` instead of `memory` for state variables saves gas
When fetching data from a storage location, assigning the data to a `memory` variable causes all fields of the struct/array to be read from storage, which incurs a Gcoldsload (**2100 gas**) for *each* field of the struct/array. If the fields are read from the new memory variable, they incur an additional `MLOAD` rather than a cheap stack read. Instead of declaring the variable with the `memory` keyword, declaring the variable with the `storage` keyword and caching any fields that need to be re-read in stack variables, will be much cheaper, only incurring the Gcoldsload for the fields actually read. The only time it makes sense to read the whole struct/array into a `memory` variable, is if the full struct/array is being returned by the function, is being passed to a function that requires `memory`, or if the array/struct is being read from another `memory` array/struct


Gas saved per Instance: ~2,100 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOrders.sol

573:             STypes.Order memory highestBid = s.bids[asset][startingId]; 
```
[573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573)


---
### [GAS&#x2011;30] `private` functions used once can be inlined

Gas saved per Instance: ~30 *(Total: ~420)*
<details>
<summary><i>There are 14 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

215:     function matchlowestSell( 
216:         address asset,
217:         STypes.Order memory lowestSell,
218:         STypes.Order memory incomingBid,
219:         MTypes.Match memory matchTotal
220:     ) private {

358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 

122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {

154:     function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private { 

209:     function _liquidationFeeHandler(MTypes.PrimaryLiquidation memory m) private { 

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 

240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private { 
```
[96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154), [209](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L209), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
📁 File: contracts/libraries/LibOracle.sol

69:     function baseOracleCircuitBreaker( 
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {

117:     function oracleCircuitBreaker( 
118:         uint80 roundId,
119:         uint80 baseRoundId,
120:         int256 chainlinkPrice,
121:         int256 baseChainlinkPrice,
122:         uint256 timeStamp,
123:         uint256 baseTimeStamp
124:     ) private view {
```
[69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117-L124)

```solidity
📁 File: contracts/libraries/LibOrders.sol

260:     function verifySellId( 
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private { 

668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private { 
```
[260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [652](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L652), [668](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L668)

</details>


---
### [GAS&#x2011;31] Reorder modifiers to save on expensive operations
According to the Solidity documentation, modifiers are executed in the order in which they are presented in the code. Reordering them so that modifiers containing only checks are executed first can prevent execution of expensive operations, such as external calls, SLOADS or SSTORES and **save gas**.


Gas saved per Instance: ~2,100 *(Total: ~21,000)*
<details>
<summary><i>There are 10 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidAsset (expensive operations)
40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidShortRecord (expensive operations)
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidShortRecord (expensive operations)
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidShortRecord (expensive operations)
142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidShortRecord (expensive operations)
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant { 

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit Gas efficient modifier order:
/// @audit  - nonReentrant
/// @audit  - isNotFrozen (expensive operations)
/// @audit  - onlyValidAsset (expensive operations)
35:     function createLimitShort( 
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)

</details>


---
### [GAS&#x2011;32] Same cast is done multiple times
It's cheaper to do it once, and store the result to a variable. The examples below are the second+ instance of a given cast of the variable


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit 'int32(secondsAgo)' is done 2 times total in this same function
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo)); 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62)


---
### [GAS&#x2011;33] Sort Solidity operations using short-circuit mode
In Solidity, boolean expressions utilize short-circuiting. For || (logical OR) operations, the second expression is evaluated only if the first one is false. Similarly, for && (logical AND) operations, the second expression is evaluated only if the first one is true. This optimization saves gas by avoiding unnecessary evaluations. For instance, in require(msg.sender == owner || msg.sender == manager), if msg.sender == owner evaluates to true, msg.sender == manager isn't checked. It's recommended to place the less expensive expression first to optimize gas usage.

<details>
<summary><i>There are 57 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Lines: 106 to 122
/// @audit Lines: 106 to 122
77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
86:         uint256 eth = ercAmount.mul(price);
87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();
88: 
89:         STypes.Asset storage Asset = s.asset[asset];
90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();
91: 
92:         STypes.Order memory incomingBid;
93:         incomingBid.addr = sender;
94:         incomingBid.price = price;
95:         incomingBid.ercAmount = ercAmount;
96:         incomingBid.id = Asset.orderIdCounter;
97:         incomingBid.orderType = isMarketOrder ? O.MarketBid : O.LimitBid;
98:         incomingBid.creationTime = LibOrders.getOffsetTime();
99: 
100:         MTypes.BidMatchAlgo memory b;
101:         b.askId = s.asks[asset][C.HEAD].nextId;
102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
103:         b.shortHintId = b.shortId = Asset.startingShortId;
104: 
105:         STypes.Order memory lowestSell = _getLowestSell(asset, b);
106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109:             b.shortHintId = b.shortId = Asset.startingShortId;
110:             b.oraclePrice = LibOracle.getPrice(asset);
111:             return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112:         } else {
113:             // @dev no match, add to market if limit order
114:             LibOrders.addBid(asset, incomingBid, orderHintArray);
115:             return (0, ercAmount);
116:         }
117:     }

/// @audit Lines: 141 to 149
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
136:         uint256 minBidEth = LibAsset.minBidEth(asset);
137:         MTypes.Match memory matchTotal;
138: 
139:         while (true) {
140:             // @dev Handles scenario when no sells left after partial fill
141:             if (b.askId == C.TAIL && b.shortId == C.TAIL) {
142:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
144:                 }
145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
146:             }
147: 
148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);
149: 
150:             if (incomingBid.price >= lowestSell.price) {
151:                 // Consider bid filled if only dust amount left
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
154:                 }
155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156:                 if (incomingBid.ercAmount > lowestSell.ercAmount) {
157:                     incomingBid.ercAmount -= lowestSell.ercAmount;
158:                     lowestSell.ercAmount = 0;
159:                     if (lowestSell.isShort()) {
160:                         b.matchedShortId = lowestSell.id;
161:                         b.prevShortId = lowestSell.prevId;
162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164:                     } else {
165:                         b.matchedAskId = lowestSell.id;
166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167:                         b.askId = lowestSell.nextId;
168:                     }
169:                 } else {
170:                     if (incomingBid.ercAmount == lowestSell.ercAmount) {
171:                         if (lowestSell.isShort()) {
172:                             b.matchedShortId = lowestSell.id;
173:                             b.prevShortId = lowestSell.prevId;
174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175:                         } else {
176:                             b.matchedAskId = lowestSell.id;
177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178:                         }
179:                     } else {
180:                         lowestSell.ercAmount -= incomingBid.ercAmount;
181:                         if (lowestSell.isShort()) {
182:                             b.dustShortId = lowestSell.id;
183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184:                             lowestShort.ercAmount = lowestSell.ercAmount;
185:                         } else {
186:                             b.dustAskId = lowestSell.id;
187:                             s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188:                         }
189:                         // Check reduced dust threshold for existing limit orders
190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191:                             b.dustShortId = b.dustAskId = 0;
192:                         }
193:                     }
194:                     incomingBid.ercAmount = 0;
195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
196:                 }
197:             } else {
198:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
200:                 }
201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
202:             }
203:         }
204:     }

/// @audit Lines: 315 to 327
/// @audit Lines: 317 to 326
/// @audit Lines: 317 to 326
275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
281:         if (matchTotal.fillEth == 0) {
282:             return (0, incomingBid.ercAmount);
283:         }
284: 
285:         STypes.Asset storage Asset = s.asset[asset];
286:         uint256 vault = Asset.vault;
287: 
288:         LibOrders.updateSellOrdersOnMatch(asset, b);
289: 
290:         // Remove last sell order from order book if under dust threshold
291:         // @dev needs to happen after updateSellOrdersOnMatch()
292:         if (b.dustAskId > 0) {
293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
294:         } else if (b.dustShortId > 0) {
295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
296:         }
297: 
298:         // If at least one short was matched
299:         if (matchTotal.shortFillEth > 0) {
300:             STypes.Vault storage Vault = s.vault[vault];
301: 
302:             // Matched Shares
303:             Vault.dittoMatchedShares += matchTotal.dittoMatchedShares;
304:             // Yield Accounting
305:             Vault.dethCollateral += matchTotal.shortFillEth;
306:             Asset.dethCollateral += matchTotal.shortFillEth;
307:             Asset.ercDebt += matchTotal.fillErc - matchTotal.askFillErc;
308: 
309:             // @dev Approximates the startingShortId after bid is fully executed
310:             STypes.Order storage currentShort = s.shorts[asset][b.shortId];
311:             O shortOrderType = currentShort.orderType;
312:             STypes.Order storage prevShort = s.shorts[asset][b.prevShortId];
313:             O prevShortOrderType = prevShort.orderType;
314: 
315:             if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
316:                 Asset.startingShortId = b.shortId;
317:             } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318:                 Asset.startingShortId = b.prevShortId;
319:             } else {
320:                 if (b.isMovingFwd) {
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }
325:             }
326:         }
327: 
328:         // Match bid
329:         address bidder = incomingBid.addr; // saves 18 gas
330:         s.vaultUser[vault][bidder].ethEscrowed -= matchTotal.fillEth;
331:         s.assetUser[asset][bidder].ercEscrowed += matchTotal.fillErc;
332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
333: 
334:         // @dev match price is based on the order that was already on orderbook
335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);
336:         return (matchTotal.fillEth, incomingBid.ercAmount);
337:     }

/// @audit Lines: 392 to 408
/// @audit Lines: 396 to 407
/// @audit Lines: 402 to 404
358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
364:         /*
365:         @dev: Table refers to how algo updates the shorts after execution. Refer to updateSellOrdersOnMatch()
366:          +----------------+-------------------------+--------------------------+
367:          |    Direction   |         First ID        |          Last ID         |
368:          +----------------+-------------------------+--------------------------+
369:          | Fwd only       | firstShortIdBelowOracle*| matchedShortId           |
370:          | Back only      | prevShortId             |shortHintId**             |
371:          | Back then fwd  | firstShortIdBelowOracle | shortId                  |
372:          +----------------+-------------------------+--------------------------+
373:         
374:         * firstShortIdBelowOracle directly PRECEDES the first short Id that can be matched.
375:         firstShortIdBelowOracle cannot itself be matched since it is below oracle price
376:         
377:         ** shortHintId will always be first Id matched if valid (within 1% of oracle)
378:         As such, it will be used as the last Id matched (if moving backwards ONLY)
379: 
380:         Example:
381:         BEFORE: HEAD <-> (ID1)* <-> (ID2) <-> (ID3) <-> (ID4) <-> [ID5] <-> (ID6) <-> NEXT
382: 
383:         Assume (ID1) is under the oracle price, therefore (ID2) is technically first eligible short that can be matched
384:         Imagine the user passes in [ID5] as the hint, which corresponds to a price within 1% of the oracle, thus making it valid
385:         If the bid matches BACKWARDS ONLY, lets say to (ID2), then the linked list will look like this after execution
386: 
387:         AFTER: HEAD <-> (ID1)* <-> (ID6) <-> NEXT
388:         
389:         Here, (ID1) becomes the "First ID" and the shortHint ID [ID5] was the "LastID"
390:         */
391:         uint80 prevPrice = s.shorts[asset][b.prevShortId].price;
392:         if (prevPrice >= b.oraclePrice && !b.isMovingFwd) {
393:             // @dev shortHintId should always be the first thing matched
394:             b.isMovingBack = true;
395:             b.shortId = b.prevShortId;
396:         } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) {
397:             b.firstShortIdBelowOracle = b.prevShortId;
398:             b.shortId = s.shorts[asset][b.shortHintId].nextId;
399: 
400:             STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId];
401:             // @dev Only set to true if actually moving forward
402:             if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403:                 b.isMovingFwd = true;
404:             }
405:         } else if (b.isMovingFwd) {
406:             b.shortId = lowestSell.nextId;
407:         }
408:     }
```
[77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L117), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L204), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L337), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L408)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Lines: 150 to 154
148:     function maybeUpdateYield(uint256 vault, uint88 amount) private { 
149:         uint88 dethTotal = s.vault[vault].dethTotal;
150:         if (dethTotal > C.BRIDGE_YIELD_UPDATE_THRESHOLD && amount.div(dethTotal) > C.BRIDGE_YIELD_PERCENT_THRESHOLD) {
151:             vault.updateYield();
152:         }
153:     }
```
[148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148-L153)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Lines: 53 to 55
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {
47:         STypes.Asset storage Asset = s.asset[asset];
48:         STypes.ShortRecord storage short = s.shortRecords[asset][msg.sender][id];
49:         SR initialStatus = short.status;
50: 
51:         short.updateErcDebt(asset);
52:         uint256 ercDebt = short.ercDebt;
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();
54: 
55:         asset.burnMsgSenderDebt(buybackAmount);
56:         Asset.ercDebt -= buybackAmount;
57:         // refund the rest of the collateral if ercDebt is fully paid back
58:         if (buybackAmount == ercDebt) {
59:             uint88 collateral = short.collateral;
60:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;
61:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);
62:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);
63:         } else {
64:             short.ercDebt -= buybackAmount;
65:         }
66: 
67:         LibSRUtil.checkShortMinErc({
68:             asset: asset,
69:             initialStatus: initialStatus,
70:             shortOrderId: shortOrderId,
71:             shortRecordId: id,
72:             shorter: msg.sender
73:         });
74: 
75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);
76:     }

/// @audit Lines: 99 to 101
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {
93:         STypes.Asset storage Asset = s.asset[asset];
94:         STypes.ShortRecord storage short = s.shortRecords[asset][msg.sender][id];
95:         SR initialStatus = short.status;
96: 
97:         short.updateErcDebt(asset);
98:         uint256 ercDebt = short.ercDebt;
99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();
100: 
101:         {
102:             STypes.AssetUser storage AssetUser = s.assetUser[asset][msg.sender];
103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();
104: 
105:             AssetUser.ercEscrowed -= buybackAmount;
106:         }
107: 
108:         Asset.ercDebt -= buybackAmount;
109:         // refund the rest of the collateral if ercDebt is fully paid back
110:         if (ercDebt == buybackAmount) {
111:             uint88 collateral = short.collateral;
112:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;
113:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);
114: 
115:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);
116:         } else {
117:             short.ercDebt -= buybackAmount;
118:         }
119: 
120:         LibSRUtil.checkShortMinErc({
121:             asset: asset,
122:             initialStatus: initialStatus,
123:             shortOrderId: shortOrderId,
124:             shortRecordId: id,
125:             shorter: msg.sender
126:         });
127: 
128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);
129:     }

/// @audit Lines: 174 to 176
142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
150:         MTypes.ExitShort memory e;
151:         e.asset = asset;
152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray);
153: 
154:         STypes.Asset storage Asset = s.asset[e.asset];
155:         STypes.ShortRecord storage short = s.shortRecords[e.asset][msg.sender][id];
156: 
157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder
158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
159:             asset: asset,
160:             initialStatus: short.status,
161:             shortOrderId: shortOrderId,
162:             shortRecordId: id,
163:             shorter: msg.sender
164:         });
165: 
166:         short.updateErcDebt(e.asset);
167: 
168:         // @dev if short order was cancelled, fully exit
169:         e.buybackAmount = e.shortOrderIsCancelled ? short.ercDebt : buybackAmount;
170:         e.beforeExitCR = getCollateralRatioNonPrice(short);
171:         e.ercDebt = short.ercDebt;
172:         e.collateral = short.collateral;
173: 
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
175: 
176:         {
177:             uint256 ethAmount = price.mul(e.buybackAmount);
178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();
179:         }
180: 
181:         // Temporary accounting to enable bid
182:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
183:         VaultUser.ethEscrowed += e.collateral;
184: 
185:         // Create bid with current msg.sender
186:         (e.ethFilled, e.ercAmountLeft) =
187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
189:         e.ercFilled = e.buybackAmount - e.ercAmountLeft;
190:         Asset.ercDebt -= e.ercFilled;
191:         s.assetUser[e.asset][msg.sender].ercEscrowed -= e.ercFilled;
192: 
193:         // Refund the rest of the collateral if ercDebt is fully paid back
194:         if (e.ercDebt == e.ercFilled) {
195:             // Full Exit
196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt);
197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy
198:         } else {
199:             short.collateral -= e.ethFilled;
200:             short.ercDebt -= e.ercFilled;
201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();
202: 
203:             // @dev Only allow partial exit if the CR is same or better than before
204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();
205: 
206:             // @dev collateral already subtracted in exitShort()
207:             VaultUser.ethEscrowed -= e.collateral - e.ethFilled;
208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt);
209:         }
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
211:     }
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L76), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L129), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L211)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Lines: 100 to 109
/// @audit Lines: 100 to 109
/// @audit Lines: 100 to 109
96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 
97:         uint16 lowestAskKey = s.asks[m.asset][C.HEAD].nextId;
98:         uint16 startingShortId = s.asset[m.asset].startingShortId;
99:         uint256 bufferPrice = m.oraclePrice.mul(m.forcedBidPriceBuffer);
100:         if (
101:             // Checks for no eligible asks
102:             (lowestAskKey == C.TAIL || s.asks[m.asset][lowestAskKey].price > bufferPrice)
103:             // Checks for no eligible shorts
104:             && (
105:                 startingShortId == C.HEAD // means no short >= oracleprice
106:                     || s.shorts[m.asset][startingShortId].price > bufferPrice
107:             )
108:         ) {
109:             revert Errors.NoSells();
110:         }
111:     }

/// @audit Lines: 263 to 276
240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private { 
241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
242:         uint88 decreaseCol = min88(m.totalFee + m.ethFilled, m.short.collateral);
243: 
244:         if (m.short.ercDebt == m.ercDebtMatched) {
245:             // Full liquidation
246:             LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt);
247:             LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);
248:             if (!m.loseCollateral) {
249:                 m.short.collateral -= decreaseCol;
250:                 s.vaultUser[m.vault][m.shorter].ethEscrowed += m.short.collateral;
251:                 TAPP.ethEscrowed -= m.short.collateral;
252:             }
253:         } else {
254:             // Partial liquidation
255:             m.short.ercDebt -= m.ercDebtMatched;
256:             m.short.collateral -= decreaseCol;
257:             s.shortRecords[m.asset][m.shorter][m.short.id] = m.short;
258: 
259:             TAPP.ethEscrowed -= m.short.collateral;
260:             LibSRUtil.disburseCollateral(m.asset, m.shorter, decreaseCol, m.short.dethYieldRate, m.short.updatedAt);
261: 
262:             // TAPP absorbs leftover short, unless it already owns the short
263:             if (m.loseCollateral && m.shorter != address(this)) {
264:                 // Delete partially liquidated short
265:                 LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);
266:                 // Absorb leftovers into TAPP short
267:                 LibShortRecord.fillShortRecord(
268:                     m.asset,
269:                     address(this),
270:                     C.SHORT_STARTING_ID,
271:                     SR.FullyFilled,
272:                     m.short.collateral,
273:                     m.short.ercDebt,
274:                     s.asset[m.asset].ercDebtRate,
275:                     m.short.dethYieldRate
276:                 );
277:             }
278:         }
279: 
280:         if (m.shorter != address(this)) {
281:             // Only relevant for non-TAPP SR
282:             LibSRUtil.checkShortMinErc({
283:                 asset: m.asset,
284:                 initialStatus: m.short.status,
285:                 shortOrderId: m.shortOrderId,
286:                 shortRecordId: m.short.id,
287:                 shorter: m.shorter
288:             });
289:         }
290:     }
```
[96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96-L111), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240-L290)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Lines: 38 to 42
/// @audit Lines: 38 to 42
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
32:         internal
33:         view
34:         returns (bool)
35:     {
36:         // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition
37:         // @dev Proposer can't redeem on self
38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
39:             return false;
40:         } else {
41:             return true;
42:         }
43:     }

/// @audit Lines: 93 to 95
/// @audit Lines: 111 to 117
/// @audit Lines: 112 to 114
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {
62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63:         MTypes.ProposeRedemption memory p;
64:         p.asset = asset;
65:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66:         uint256 minShortErc = LibAsset.minShortErc(p.asset);
67: 
68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69: 
70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71: 
72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74: 
75:         p.oraclePrice = LibOracle.getPrice(p.asset);
76: 
77:         bytes memory slate;
78:         for (uint8 i = 0; i < proposalInput.length; i++) {
79:             p.shorter = proposalInput[i].shorter;
80:             p.shortId = proposalInput[i].shortId;
81:             p.shortOrderId = proposalInput[i].shortOrderId;
82:             // @dev Setting this above _onlyValidShortRecord to allow skipping
83:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84: 
85:             /// Evaluate proposed shortRecord
86: 
87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88: 
89:             currentSR.updateErcDebt(p.asset);
90:             p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91: 
92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94: 
95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96:             if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97:                 p.amountProposed = currentSR.ercDebt;
98:             } else {
99:                 p.amountProposed = redemptionAmount - p.totalAmountProposed;
100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102:             }
103: 
104:             /// At this point, the shortRecord passes all checks and will be included in the slate
105: 
106:             p.previousCR = p.currentCR;
107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
115: 
116:             p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117:             if (p.colRedeemed > currentSR.collateral) {
118:                 p.colRedeemed = currentSR.collateral;
119:             }
120: 
121:             currentSR.collateral -= p.colRedeemed;
122:             currentSR.ercDebt -= p.amountProposed;
123: 
124:             p.totalAmountProposed += p.amountProposed;
125:             p.totalColRedeemed += p.colRedeemed;
126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes
128:             // instead of usual abi.encode to save on extra zeros being written
129:             slate = bytes.concat(
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
137: 
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139:             p.redemptionCounter++;
140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141:         }
142: 
143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144: 
145:         // @dev SSTORE2 the entire proposalData after validating proposalInput
146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147:         redeemerAssetUser.slateLength = p.redemptionCounter;
148:         redeemerAssetUser.oraclePrice = p.oraclePrice;
149:         redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150: 
151:         STypes.Asset storage Asset = s.asset[p.asset];
152:         Asset.ercDebt -= p.totalAmountProposed;
153: 
154:         uint32 protocolTime = LibOrders.getOffsetTime();
155:         redeemerAssetUser.timeProposed = protocolTime;
156:         // @dev Calculate the dispute period
157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158: 
159:         /*
160:         +-------+------------+
161:         | CR(X) |  Hours(Y)  |
162:         +-------+------------+
163:         | 1.1   |     0      |
164:         | 1.2   |    .333    |
165:         | 1.3   |    .75     |
166:         | 1.5   |    1.5     |
167:         | 1.7   |     3      |
168:         | 2.0   |     6      |
169:         +-------+------------+
170: 
171:         Creating fixed points and interpolating between points on the graph without using exponentials
172:         Using simple y = mx + b formula
173:         
174:         where x = currentCR - previousCR
175:         m = (y2-y1)/(x2-x1)
176:         b = previous fixed point (Y)
177:         */
178: 
179:         uint256 m;
180: 
181:         if (p.currentCR > 1.7 ether) {
182:             m = uint256(3 ether).div(0.3 ether);
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184:         } else if (p.currentCR > 1.5 ether) {
185:             m = uint256(1.5 ether).div(0.2 ether);
186:             redeemerAssetUser.timeToDispute =
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188:         } else if (p.currentCR > 1.3 ether) {
189:             m = uint256(0.75 ether).div(0.2 ether);
190:             redeemerAssetUser.timeToDispute =
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192:         } else if (p.currentCR > 1.2 ether) {
193:             m = uint256(0.417 ether).div(0.1 ether);
194:             redeemerAssetUser.timeToDispute =
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196:         } else if (p.currentCR > 1.1 ether) {
197:             m = uint256(C.ONE_THIRD.div(0.1 ether));
198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199:         }
200: 
201:         redeemerAssetUser.oraclePrice = p.oraclePrice;
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203: 
204:         uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206: 
207:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209:         VaultUser.ethEscrowed -= redemptionFee;
210:         emit Events.ProposeRedemption(p.asset, msg.sender);
211:     }

/// @audit Lines: 259 to 310
/// @audit Lines: 243 to 247
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230:         MTypes.DisputeRedemption memory d;
231:         d.asset = asset;
232:         d.redeemer = redeemer;
233: 
234:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236: 
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238: 
239:         MTypes.ProposalData[] memory decodedProposalData =
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241: 
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244:                 revert Errors.CannotDisputeWithRedeemerProposal();
245:             }
246:         }
247: 
248:         STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249:         // Match continue (skip) conditions in proposeRedemption()
250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);
251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252: 
253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254:         MTypes.ProposalData memory currentProposal;
255:         STypes.Asset storage Asset = s.asset[d.asset];
256: 
257:         uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258: 
259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260:         {
261:             // @dev All proposals from the incorrectIndex onward will be removed
262:             // @dev Thus the proposer can only redeem a portion of their original slate
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264:                 currentProposal = decodedProposalData[i];
265: 
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267:                 currentSR.collateral += currentProposal.colRedeemed;
268:                 currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269: 
270:                 d.incorrectCollateral += currentProposal.colRedeemed;
271:                 d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272:             }
273: 
274:             s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275:             Asset.dethCollateral += d.incorrectCollateral;
276:             Asset.ercDebt += d.incorrectErcDebt;
277: 
278:             // @dev Update the redeemer's SSTORE2Pointer
279:             if (incorrectIndex > 0) {
280:                 redeemerAssetUser.slateLength = incorrectIndex;
281:             } else {
282:                 // @dev this implies everything in the redeemer's proposal was incorrect
283:                 delete redeemerAssetUser.SSTORE2Pointer;
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);
285:             }
286: 
287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289:             uint256 penaltyPct = LibOrders.min(
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );
292: 
293:             uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294: 
295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296:             redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297:             s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298:         } else {
299:             revert Errors.InvalidRedemptionDispute();
300:         }
301:     }

/// @audit Lines: 361 to 363
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {
352:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];
353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();
355: 
356:         // @dev Only need to read up to the position of the SR to be claimed
357:         MTypes.ProposalData[] memory decodedProposalData =
358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
359:         MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];
360: 
361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
362: 
363:         STypes.Asset storage Asset = s.asset[asset];
364:         _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
365:     }

/// @audit Lines: 371 to 382
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 
369:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortId];
370: 
371:         if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {
372:             // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already
373:             uint88 collateral = shortRecord.collateral;
374:             s.vaultUser[vault][shorter].ethEscrowed += collateral;
375:             // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS
376:             LibSRUtil.disburseCollateral(asset, shorter, collateral, shortRecord.dethYieldRate, shortRecord.updatedAt);
377:             LibShortRecord.deleteShortRecord(asset, shorter, shortId);
378:         }
379:     }
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L43), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L211), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L301), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L365), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368-L379)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit Lines: 51 to 53
/// @audit Lines: 59 to 61
/// @audit Lines: 75 to 80
35:     function createLimitShort( 
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43:         MTypes.CreateLimitShortParam memory p;
44:         STypes.Asset storage Asset = s.asset[asset];
45:         STypes.Order memory incomingShort;
46: 
47:         // @dev create "empty" SR. Fail early.
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49: 
50:         uint256 cr = LibOrders.convertCR(shortOrderCR);
51:         if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52:             revert Errors.InvalidCR();
53:         }
54: 
55:         // @dev minShortErc needs to be modified (bigger) when cr < 1
56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57:         p.eth = price.mul(ercAmount); // 0.00025e18 * 5000e18 = 1.25e36
58:         p.minAskEth = LibAsset.minAskEth(asset);
59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60: 
61:         // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63: 
64:         incomingShort.addr = msg.sender;
65:         incomingShort.price = price;
66:         incomingShort.ercAmount = ercAmount;
67:         incomingShort.id = Asset.orderIdCounter;
68:         incomingShort.orderType = O.LimitShort;
69:         incomingShort.creationTime = LibOrders.getOffsetTime();
70:         incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71: 
72:         p.startingId = s.bids[asset][C.HEAD].nextId;
73:         STypes.Order storage highestBid = s.bids[asset][p.startingId];
74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75:         if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77:         }
78: 
79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81:             revert Errors.BelowRecoveryModeCR();
82:         }
83: 
84:         // @dev reading spot oracle price
85:         if (incomingShort.price < p.oraclePrice) {
86:             LibOrders.addShort(asset, incomingShort, orderHintArray);
87:         } else {
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89:         }
90:     }
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L90)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Lines: 156 to 160
/// @audit Lines: 161 to 205
/// @audit Lines: 170 to 202
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 
145:         AppStorage storage s = appStorage();
146: 
147:         STypes.Asset storage Asset = s.asset[asset];
148:         uint256 vault = Asset.vault;
149: 
150:         if (vault == VAULT.ONE) {
151:             STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
152:             uint88 creditReth = VaultUserFrom.bridgeCreditReth;
153:             uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
154:             STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];
155: 
156:             if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
157:                 // No bridge credits
158:                 return;
159:             }
160: 
161:             if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
162:                 // Only creditReth
163:                 if (creditReth > collateral) {
164:                     VaultUserFrom.bridgeCreditReth -= collateral;
165:                     VaultUserTo.bridgeCreditReth += collateral;
166:                 } else {
167:                     VaultUserFrom.bridgeCreditReth = 0;
168:                     VaultUserTo.bridgeCreditReth += creditReth;
169:                 }
170:             } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
171:                 // Only creditSteth
172:                 if (creditSteth > collateral) {
173:                     VaultUserFrom.bridgeCreditSteth -= collateral;
174:                     VaultUserTo.bridgeCreditSteth += collateral;
175:                 } else {
176:                     VaultUserFrom.bridgeCreditSteth = 0;
177:                     VaultUserTo.bridgeCreditSteth += creditSteth;
178:                 }
179:             } else {
180:                 // Both creditReth and creditSteth
181:                 uint88 creditTotal = creditReth + creditSteth;
182:                 if (creditTotal > collateral) {
183:                     creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
184:                     creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
185:                     VaultUserFrom.bridgeCreditReth -= creditReth;
186:                     VaultUserFrom.bridgeCreditSteth -= creditSteth;
187:                 } else {
188:                     VaultUserFrom.bridgeCreditReth = 0;
189:                     VaultUserFrom.bridgeCreditSteth = 0;
190:                 }
191:                 VaultUserTo.bridgeCreditReth += creditReth;
192:                 VaultUserTo.bridgeCreditSteth += creditSteth;
193:             }
194:         }
195:     }
```
[144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144-L195)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Lines: 60 to 62
/// @audit Lines: 60 to 62
19:     function getOraclePrice(address asset) internal view returns (uint256) { 
20:         AppStorage storage s = appStorage();
21:         AggregatorV3Interface baseOracle = AggregatorV3Interface(s.baseOracle);
22:         uint256 protocolPrice = getPrice(asset);
23: 
24:         AggregatorV3Interface oracle = AggregatorV3Interface(s.asset[asset].oracle);
25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset();
26: 
27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
28:             if (oracle == baseOracle) {
29:                 // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
30:                 uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;
31:                 basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
32:                 return basePriceInEth;
33:             } else {
34:                 // prettier-ignore
35:                 (
36:                     uint80 roundID,
37:                     int256 price,
38:                     /*uint256 startedAt*/
39:                     ,
40:                     uint256 timeStamp,
41:                     /*uint80 answeredInRound*/
42:                 ) = oracle.latestRoundData();
43:                 uint256 priceInEth = uint256(price).div(uint256(basePrice));
44:                 oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp);
45:                 return priceInEth;
46:             }
47:         } catch {
48:             if (oracle == baseOracle) {
49:                 return twapCircuitBreaker();
50:             } else {
51:                 // prettier-ignore
52:                 (
53:                     uint80 roundID,
54:                     int256 price,
55:                     /*uint256 startedAt*/
56:                     ,
57:                     uint256 timeStamp,
58:                     /*uint80 answeredInRound*/
59:                 ) = oracle.latestRoundData();
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
61: 
62:                 uint256 twapInv = twapCircuitBreaker();
63:                 uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv);
64:                 return priceInEth;
65:             }
66:         }
67:     }
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19-L67)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit Lines: 90 to 94
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 
83:         AppStorage storage s = appStorage();
84:         uint16 hintId;
85: 
86:         if (order.orderType == O.MarketBid) {
87:             return;
88:         }
89:         uint16 nextId = s.bids[asset][C.HEAD].nextId;
90:         if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) {
91:             hintId = C.HEAD;
92:         } else {
93:             hintId = findOrderHintId(s.bids, asset, orderHintArray);
94:         }
95: 
96:         addOrder(s.bids, asset, order, hintId);
97: 
98:         uint256 vault = s.asset[asset].vault;
99:         uint88 eth = order.ercAmount.mulU88(order.price);
100:         s.vaultUser[vault][order.addr].ethEscrowed -= eth;
101:     }

/// @audit Lines: 111 to 115
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 
104:         AppStorage storage s = appStorage();
105:         uint16 hintId;
106: 
107:         if (order.orderType == O.MarketAsk) {
108:             return;
109:         }
110:         uint16 nextId = s.asks[asset][C.HEAD].nextId;
111:         if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) {
112:             hintId = C.HEAD;
113:         } else {
114:             hintId = findOrderHintId(s.asks, asset, orderHintArray);
115:         }
116:         addOrder(s.asks, asset, order, hintId);
117: 
118:         s.assetUser[asset][order.addr].ercEscrowed -= order.ercAmount;
119:     }

/// @audit Lines: 132 to 136
128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 
129:         AppStorage storage s = appStorage();
130:         uint16 hintId;
131:         uint16 nextId = s.shorts[asset][C.HEAD].nextId;
132:         if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) {
133:             hintId = C.HEAD;
134:         } else {
135:             hintId = findOrderHintId(s.shorts, asset, orderHintArray);
136:         }
137: 
138:         // @dev: Only need to set this when placing incomingShort onto market
139:         addOrder(s.shorts, asset, order, hintId);
140:         updateStartingShortIdViaShort(asset, order);
141:         uint256 vault = s.asset[asset].vault;
142:         uint88 eth = order.ercAmount.mulU88(order.price).mulU88(LibOrders.convertCR(order.shortOrderCR));
143:         s.vaultUser[vault][order.addr].ethEscrowed -= eth;
144:     }

/// @audit Lines: 371 to 375
362:     function findPrevOfIncomingId( 
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {
368:         uint16 nextId = orders[asset][hintId].nextId;
369: 
370:         // if invalid hint (if the id points to 0 then it's an empty id)
371:         if (hintId == 0 || nextId == 0) {
372:             return getOrderId(orders, asset, C.NEXT, C.HEAD, incomingOrder.price, incomingOrder.orderType);
373:         }
374: 
375:         // check if the hint is valid
376:         int256 direction = verifyId(orders, asset, hintId, incomingOrder.price, nextId, incomingOrder.orderType);
377: 
378:         // if its 0, it's correct
379:         // otherwise it could be off because a tx could of modified state
380:         // so search in a direction based on price.
381:         if (direction == C.EXACT) {
382:             return hintId;
383:         } else if (direction == C.NEXT) {
384:             return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
385:         } else {
386:             uint16 prevId = orders[asset][hintId].prevId;
387:             return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);
388:         }
389:     }

/// @audit Lines: 412 to 418
402:     function verifyId( 
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {
410:         orderType = normalizeOrderType(orderType);
411: 
412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413:             return verifySellId(orders, asset, prevId, newPrice, nextId);
414:         } else if (orderType == O.LimitBid) {
415:             return verifyBidId(asset, prevId, newPrice, nextId);
416:         }
417:     }

/// @audit Lines: 421 to 427
/// @audit Lines: 423 to 427
420:     function normalizeOrderType(O o) private pure returns (O newO) { 
421:         if (o == O.LimitBid || o == O.MarketBid) {
422:             return O.LimitBid;
423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {
424:             return O.LimitAsk;
425:         } else if (o == O.LimitShort) {
426:             return O.LimitShort;
427:         }
428:     }

/// @audit Lines: 506 to 530
/// @audit Lines: 510 to 523
/// @audit Lines: 513 to 523
/// @audit Lines: 516 to 523
499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal { 
500:         AppStorage storage s = appStorage();
501:         if (b.matchedAskId != 0) {
502:             _updateOrders(s.asks, asset, C.HEAD, b.matchedAskId);
503:         }
504: 
505:         if (b.matchedShortId != 0) {
506:             if (!b.isMovingBack && !b.isMovingFwd) {
507:                 // @dev Handles only matching one thing
508:                 // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block
509:                 _updateOrders(s.shorts, asset, b.prevShortId, b.matchedShortId);
510:             } else if (!b.isMovingBack && b.isMovingFwd) {
511:                 // @dev Handles moving forward only
512:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, b.matchedShortId);
513:             } else if (b.isMovingBack && !b.isMovingFwd) {
514:                 //@handles moving backwards only.
515:                 _updateOrders(s.shorts, asset, b.prevShortId, b.shortHintId);
516:             } else if (b.isMovingBack && b.isMovingFwd) {
517:                 uint16 id = b.prevShortId == b.firstShortIdBelowOracle ? b.shortHintId : b.matchedShortId;
518:                 // @dev Handle going backward and forward
519:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, id);
520:             }
521:         }
522:     }

/// @audit Lines: 752 to 756
/// @audit Lines: 752 to 756
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 
729:         AppStorage storage s = appStorage();
730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset);
731:         uint256 savedPrice = asset.getPrice();
732:         asset.setPriceAndTime(oraclePrice, getOffsetTime());
733:         if (oraclePrice == savedPrice) {
734:             return; // no need to update startingShortId
735:         }
736: 
737:         STypes.Asset storage Asset = s.asset[asset];
738:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;
739:         if (shortOrdersIsEmpty) {
740:             Asset.startingShortId = C.HEAD;
741:         } else {
742:             uint16 shortHintId;
743:             for (uint256 i = 0; i < shortHintArray.length;) {
744:                 shortHintId = shortHintArray[i];
745:                 unchecked {
746:                     ++i;
747:                 }
748: 
749:                 STypes.Order storage short = s.shorts[asset][shortHintId];
750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }
756: 
757:                 uint80 shortPrice = short.price;
758:                 uint16 prevId = short.prevId;
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;
760:                 // @dev force hint to be within 0.5% of oraclePrice
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764: 
765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {
773:                     Asset.startingShortId = C.HEAD;
774:                     return;
775:                 }
776:             }
777: 
778:             revert Errors.BadShortHint();
779:         }
780:     }

/// @audit Lines: 821 to 825
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal { 
811:         AppStorage storage s = appStorage();
812:         STypes.Asset storage Asset = s.asset[asset];
813:         uint256 savedPrice = LibOracle.getPrice(asset);
814:         uint256 startingShortPrice = s.shorts[asset][Asset.startingShortId].price;
815:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;
816: 
817:         if (shortOrdersIsEmpty || Asset.startingShortId == C.HEAD) {
818:             if (incomingShort.price >= savedPrice) {
819:                 Asset.startingShortId = incomingShort.id;
820:             }
821:         } else if (incomingShort.price < startingShortPrice && incomingShort.price >= savedPrice) {
822:             Asset.startingShortId = incomingShort.id;
823:         }
824:     }

/// @audit Lines: 836 to 844
/// @audit Lines: 840 to 842
826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {
831:         bool anyOrderHintPrevMatched;
832:         for (uint256 i; i < orderHintArray.length; i++) {
833:             MTypes.OrderHint memory orderHint = orderHintArray[i];
834:             STypes.Order storage order = orders[asset][orderHint.hintId];
835:             O hintOrderType = order.orderType;
836:             if (hintOrderType == O.Cancelled || hintOrderType == O.Matched) {
837:                 continue;
838:             } else if (order.creationTime == orderHint.creationTime) {
839:                 return orderHint.hintId;
840:             } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
841:                 anyOrderHintPrevMatched = true;
842:             }
843:         }
844: 
845:         if (anyOrderHintPrevMatched) {
846:             // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD
847:             return C.HEAD;
848:         }
849: 
850:         revert Errors.BadHintIdArray();
851:     }

/// @audit Lines: 859 to 861
854:     function cancelBid(address asset, uint16 id) internal { 
855:         AppStorage storage s = appStorage();
856:         STypes.Order storage bid = s.bids[asset][id];
857: 
858:         O orderType = bid.orderType;
859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
860: 
861:         uint256 vault = s.asset[asset].vault;
862:         uint88 eth = bid.ercAmount.mulU88(bid.price);
863:         s.vaultUser[vault][bid.addr].ethEscrowed += eth;
864: 
865:         cancelOrder(s.bids, asset, id);
866:     }

/// @audit Lines: 873 to 875
868:     function cancelAsk(address asset, uint16 id) internal { 
869:         AppStorage storage s = appStorage();
870:         STypes.Order storage ask = s.asks[asset][id];
871: 
872:         O orderType = ask.orderType;
873:         if (orderType == O.Cancelled || orderType == O.Matched) {
874:             revert Errors.NotActiveOrder();
875:         }
876: 
877:         s.assetUser[asset][ask.addr].ercEscrowed += ask.ercAmount;
878: 
879:         cancelOrder(s.asks, asset, id);
880:     }

/// @audit Lines: 887 to 889
882:     function cancelShort(address asset, uint16 id) internal { 
883:         AppStorage storage s = appStorage();
884:         STypes.Order storage shortOrder = s.shorts[asset][id];
885: 
886:         O orderType = shortOrder.orderType;
887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
888: 
889:         uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));
890: 
891:         STypes.Asset storage Asset = s.asset[asset];
892:         uint256 vault = Asset.vault;
893: 
894:         uint8 shortRecordId = shortOrder.shortRecordId;
895:         address shorter = shortOrder.addr;
896:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
897: 
898:         if (shortRecord.status == SR.Closed) {
899:             // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId
900:             // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId
901:             LibShortRecord.deleteShortRecord(asset, shorter, shortRecordId);
902:         } else {
903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset));
904:             if (shortRecord.ercDebt < minShortErc) {
905:                 // @dev prevents leaving behind a partially filled SR is under minShortErc
906:                 // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc
907:                 uint88 debtDiff = minShortErc - shortRecord.ercDebt;
908:                 {
909:                     STypes.Vault storage Vault = s.vault[vault];
910: 
911:                     uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));
912: 
913:                     LibShortRecord.fillShortRecord(
914:                         asset,
915:                         shorter,
916:                         shortRecordId,
917:                         SR.FullyFilled,
918:                         collateralDiff,
919:                         debtDiff,
920:                         Asset.ercDebtRate,
921:                         Vault.dethYieldRate
922:                     );
923: 
924:                     Vault.dethCollateral += collateralDiff;
925:                     Asset.dethCollateral += collateralDiff;
926:                     Asset.ercDebt += debtDiff;
927: 
928:                     // @dev update the eth refund amount
929:                     eth -= collateralDiff;
930:                 }
931:                 // @dev virtually mint the increased debt
932:                 s.assetUser[asset][shorter].ercEscrowed += debtDiff;
933:             } else {
934:                 shortRecord.status = SR.FullyFilled;
935:             }
936:         }
937: 
938:         s.vaultUser[vault][shorter].ethEscrowed += eth;
939: 
940:         // Approximating the startingShortId, rather than expecting exact match
941:         if (id == Asset.startingShortId) {
942:             uint256 savedPrice = LibOracle.getPrice(asset);
943:             uint256 prevPrice = s.shorts[asset][shortOrder.prevId].price;
944:             if (prevPrice >= savedPrice) {
945:                 Asset.startingShortId = shortOrder.prevId;
946:             } else {
947:                 Asset.startingShortId = shortOrder.nextId;
948:             }
949:         }
950: 
951:         cancelOrder(s.shorts, asset, id);
952:     }
```
[82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82-L101), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103-L119), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128-L144), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L389), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L417), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420-L428), [499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499-L522), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728-L780), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810-L824), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L851), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854-L866), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868-L880), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882-L952)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Lines: 57 to 59
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {
53:         AppStorage storage s = appStorage();
54:         if (initialStatus == SR.PartialFill) {
55:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
56:             STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
58: 
59:             if (shorter == msg.sender) {
60:                 // If call comes from exitShort() or combineShorts() then always cancel
61:                 LibOrders.cancelShort(asset, shortOrderId);
62:                 assert(shortRecord.status != SR.PartialFill);
63:                 return true;
64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
65:                 // If call comes from liquidate() and SR ercDebt under minShortErc
66:                 LibOrders.cancelShort(asset, shortOrderId);
67:                 return true;
68:             }
69:         }
70:     }

/// @audit Lines: 97 to 101
/// @audit Lines: 84 to 86
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {
76:         AppStorage storage s = appStorage();
77: 
78:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
79:         uint256 minShortErc = LibAsset.minShortErc(asset);
80: 
81:         if (initialStatus == SR.PartialFill) {
82:             // Verify shortOrder
83:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
85: 
86:             if (shortRecord.status == SR.Closed) {
87:                 // Check remaining shortOrder
88:                 if (shortOrder.ercAmount < minShortErc) {
89:                     // @dev The resulting SR will not have PartialFill status after cancel
90:                     LibOrders.cancelShort(asset, shortOrderId);
91:                     isCancelled = true;
92:                 }
93:             } else {
94:                 // Check remaining shortOrder and remaining shortRecord
95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
96:             }
97:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) {
98:             revert Errors.CannotLeaveDustAmount();
99:         }
100:     }
```
[49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L70), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L100)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Lines: 65 to 67
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
53: 
54:         uint32[] memory secondsAgos = new uint32[](2);
55:         secondsAgos[0] = secondsAgo;
56:         secondsAgos[1] = 0;
57: 
58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos);
60: 
61:         int56 tickCumulativesDelta = tickCumulatives[1] - tickCumulatives[0];
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
63: 
64:         // Always round to negative infinity
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
66:             tick--;
67:         }
68: 
69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
70:         amountOut = getQuoteAtTick(tick, amountIn, baseToken, quoteToken);
71:     }
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L71)

</details>


---
### [GAS&#x2011;34] Splitting `revert()` statements saves gas
Splitting the conditions into two separate checks [saves](https://gist.github.com/IllIllI000/7e25b0fca6bd9d57d9b9bcb9d2018959) 2 **gas**


Gas saved per Instance: ~2 *(Total: ~20)*
<details>
<summary><i>There are 10 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback(); 

99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback(); 

174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback(); 
```
[53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder(); 
```
[112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L112)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize(); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L59)

```solidity
📁 File: contracts/libraries/LibOracle.sol

60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice(); 
```
[60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60)

```solidity
📁 File: contracts/libraries/LibOrders.sol

859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 

887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 
```
[859](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L859), [887](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L887)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 
```
[57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L57), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84)

</details>


---
### [GAS&#x2011;35] Stack variable is only used once
If the variable is only accessed once, it's cheaper to use the assigned value directly that one time, and save the 3 gas the extra stack assignment would spend.


Gas saved per Instance: ~3 *(Total: ~258)*
<details>
<summary><i>There are 86 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

71:         MTypes.OrderHint[] memory orderHintArray; 

183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id]; 

345:             bool noAsks = b.askId == C.TAIL; 
346:             bool shortPriceLessThanAskPrice = lowestShort.price < lowestAsk.price;

400:             STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId]; 
```
[71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L71), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L183), [345](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L345-L346), [400](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L400)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

119:         uint88 ethAmount = _ethConversion(vault, dethAmount); 

137:         uint88 ethAmount = _ethConversion(vault, dethAmount); 
```
[119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L119), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L137)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

49:         SR initialStatus = short.status; 

95:         SR initialStatus = short.status; 

177:             uint256 ethAmount = price.mul(e.buybackAmount); 
```
[49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L49), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L95), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L177)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

155:         uint256 startGas = gasleft(); 

181:             uint96 ercDebtSocialized = ercDebtPrev - m.short.ercDebt; 

196:         uint256 gasUsed = startGas - gasleft(); 
```
[155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L155), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L181), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L196)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

250:         uint256 minShortErc = LibAsset.minShortErc(d.asset); 

253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex]; 

289:             uint256 penaltyPct = LibOrders.min( 

313:         STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender]; 

357:         MTypes.ProposalData[] memory decodedProposalData = 

363:         STypes.Asset storage Asset = s.asset[asset]; 

388:         uint256 secondsPassed = uint256((protocolTime - Asset.lastRedemptionTime)) * 1 ether; 
389:         uint256 decayFactor = C.SECONDS_DECAY_FACTOR.pow(secondsPassed);
390:         uint256 decayedBaseRate = Asset.baseRate.mulU64(decayFactor);

392:         uint104 totalAssetErcDebt = (ercDebtRedeemed + Asset.ercDebt).mulU104(C.BETA); 

394:         uint256 redeemedDUSDFraction = ercDebtRedeemed.div(totalAssetErcDebt); 

401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether); 
```
[250](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L250), [253](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L253), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L289), [313](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L313), [357](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L357), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L363), [388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L388-L390), [392](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L392), [394](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L394), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

43:         AppStorage storage s = appStorage(); 

114:         IBridge bridgeReth = IBridge(rethBridge); 
115:         IBridge bridgeSteth = IBridge(stethBridge);

118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH); 
119:         uint256 unitRethOracle = bridgeReth.getUnitDethValue();

122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH); 
123:         uint256 unitWstethOracle = bridgeSteth.getUnitDethValue();

147:         STypes.Asset storage Asset = s.asset[asset]; 
```
[43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L43), [114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L114-L115), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L118-L119), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122-L123), [147](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L147)

```solidity
📁 File: contracts/libraries/LibBytes.sol

12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer); 

22:             address shorter; // bytes20 
23:             uint8 shortId; // bytes1
24:             uint64 CR; // bytes8
25:             uint88 ercDebtRedeemed; // bytes11
26:             uint88 colRedeemed; // bytes11
```
[12](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L12), [22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L22-L26)

```solidity
📁 File: contracts/libraries/LibOracle.sol

22:         uint256 protocolPrice = getPrice(asset); 

62:                 uint256 twapInv = twapCircuitBreaker(); 

76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 

80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether; 

93:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 

95:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth; 

102:                     IERC20 weth = IERC20(C.WETH); 
103:                     uint256 wethBal = weth.balanceOf(C.USDC_WETH);

125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 

137:         IERC20 weth = IERC20(C.WETH); 
138:         uint256 wethBal = weth.balanceOf(C.USDC_WETH);

141:         uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 

157:         AppStorage storage s = appStorage(); 

163:         AppStorage storage s = appStorage(); 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L22), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L62), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L95), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L102-L103), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L137-L138), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141), [157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L157), [163](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L163)

```solidity
📁 File: contracts/libraries/LibOrders.sol

50:             uint256 vault = s.asset[asset].vault; 

98:         uint256 vault = s.asset[asset].vault; 
99:         uint88 eth = order.ercAmount.mulU88(order.price);

141:         uint256 vault = s.asset[asset].vault; 
142:         uint88 eth = order.ercAmount.mulU88(order.price).mulU88(LibOrders.convertCR(order.shortOrderCR));

179:         AppStorage storage s = appStorage(); 

291:         uint16 prevHEAD = orders[asset][C.HEAD].prevId; 

315:         uint16 prevHEAD = orders[asset][C.HEAD].prevId; 

386:             uint16 prevId = orders[asset][hintId].prevId; 

456:                 uint16 prevId = orders[asset][hintId].prevId; 

517:                 uint16 id = b.prevShortId == b.firstShortIdBelowOracle ? b.shortHintId : b.matchedShortId; 

677:         SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill; 

711:         AppStorage storage s = appStorage(); 

731:         uint256 savedPrice = asset.getPrice(); 

738:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL; 

761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice; 
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;

804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset); 

814:         uint256 startingShortPrice = s.shorts[asset][Asset.startingShortId].price; 
815:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;

861:         uint256 vault = s.asset[asset].vault; 
862:         uint88 eth = bid.ercAmount.mulU88(bid.price);

942:             uint256 savedPrice = LibOracle.getPrice(asset); 
943:             uint256 prevPrice = s.shorts[asset][shortOrder.prevId].price;

960:         bool isDiscounted = savedPrice > price.mul(1.01 ether); 

965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether)); 

971:             bool titheWasChanged = Vault.dethTitheMod != C.INITIAL_TITHE_MOD; 
```
[50](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L50), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L98-L99), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L141-L142), [179](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L179), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L291), [315](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L315), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L386), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [517](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L517), [677](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L677), [711](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L711), [731](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L731), [738](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L738), [761](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L761-L763), [804](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L804), [814](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L814-L815), [861](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L861-L862), [942](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L942-L943), [960](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L960), [965](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L965), [971](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L971)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS; 

107:         AppStorage storage s = appStorage(); 

115:                 uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt)); 

142:         uint8 id = LibShortRecord.createShortRecord( 

152:         AppStorage storage s = appStorage(); 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L40), [107](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L107), [115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L115), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L142), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L152)

</details>


---
### [GAS&#x2011;36] State variable read in a loop
The state variable should be cached in and read from a local variable, or accumulated in a local variable then written to storage once outside of the loop, rather than reading/updating it on every iteration of the loop, which will replace each Gwarmaccess (**100 gas**) with a much cheaper stack read.


Gas saved per Instance: ~97 *(Total: ~194)*

<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit s, s
78:         for (uint8 i = 0; i < proposalInput.length; i++) { 
79:             p.shorter = proposalInput[i].shorter;
80:             p.shortId = proposalInput[i].shortId;
81:             p.shortOrderId = proposalInput[i].shortOrderId;
82:             // @dev Setting this above _onlyValidShortRecord to allow skipping
83:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84: 
85:             /// Evaluate proposed shortRecord
86: 
87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88: 
89:             currentSR.updateErcDebt(p.asset);
90:             p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91: 
92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94: 
95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96:             if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97:                 p.amountProposed = currentSR.ercDebt;
98:             } else {
99:                 p.amountProposed = redemptionAmount - p.totalAmountProposed;
100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102:             }
103: 
104:             /// At this point, the shortRecord passes all checks and will be included in the slate
105: 
106:             p.previousCR = p.currentCR;
107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
115: 
116:             p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117:             if (p.colRedeemed > currentSR.collateral) {
118:                 p.colRedeemed = currentSR.collateral;
119:             }
120: 
121:             currentSR.collateral -= p.colRedeemed;
122:             currentSR.ercDebt -= p.amountProposed;
123: 
124:             p.totalAmountProposed += p.amountProposed;
125:             p.totalColRedeemed += p.colRedeemed;
126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes
128:             // instead of usual abi.encode to save on extra zeros being written
129:             slate = bytes.concat(
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
137: 
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139:             p.redemptionCounter++;
140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141:         }

/// @audit s
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) { 
264:                 currentProposal = decodedProposalData[i];
265: 
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267:                 currentSR.collateral += currentProposal.colRedeemed;
268:                 currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269: 
270:                 d.incorrectCollateral += currentProposal.colRedeemed;
271:                 d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272:             }
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78-L141), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263-L272)


---
### [GAS&#x2011;37] State variables should be cached in stack variables rather than re-reading them from storage
When performing multiple operations on a state variable in a function, it is recommended to cache it first. Either multiple reads or multiple writes to a state variable can save gas by caching it on the stack. Caching of a state variable replaces each Gwarmaccess (100 gas) with a much cheaper stack read. Other less obvious fixes/optimizations include having local memory caches of state variable structs, or having local caches of state variable contracts/addresses. *Saves 100 gas per instance*.


Gas saved per Instance: ~100 *(Total: ~2,400)*
<details>
<summary><i>There are 24 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit s: 3 reads (3 in modifiers)
40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit s: 3 reads 
77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit s: 5 reads 
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit s: 4 reads 
215:     function matchlowestSell( 
216:         address asset,
217:         STypes.Order memory lowestSell,
218:         STypes.Order memory incomingBid,
219:         MTypes.Match memory matchTotal
220:     ) private {

/// @audit s: 7 reads 
275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit s: 3 reads 
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 

/// @audit s: 3 reads 
358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit s: 2 reads (1 in modifiers)
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant { 

/// @audit s: 2 reads 
133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO { 
```
[101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit s: 5 reads (2 in modifiers)
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {

/// @audit s: 6 reads (2 in modifiers)
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {

/// @audit s: 6 reads (2 in modifiers)
142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit s: 3 reads (2 in modifiers)
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {

/// @audit s: 4 reads 
96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 

/// @audit s: 2 reads 
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {

/// @audit s: 4 reads 
154:     function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private { 

/// @audit s: 2 reads 
209:     function _liquidationFeeHandler(MTypes.PrimaryLiquidation memory m) private { 

/// @audit s: 3 reads 
240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private { 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53), [96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154), [209](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L209), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit s: 7 reads (2 in modifiers)
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

/// @audit s: 8 reads (2 in modifiers)
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {

/// @audit s: 5 reads (2 in modifiers)
310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant { 

/// @audit s: 4 reads (2 in modifiers)
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {

/// @audit s: 2 reads 
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit s: 7 reads (3 in modifiers)
35:     function createLimitShort( 
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)

</details>


---
### [GAS&#x2011;38] Structs can be assigned more efficiently
Rather defining the struct in a single line, it is more efficient to declare an empty struct and then assign each struct element individually. This can net quite a large gas saving of **130 per instance**.


Gas saved per Instance: ~130 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibBytes.sol

45:             data[i] = MTypes.ProposalData({ 
46:                 shorter: shorter,
47:                 shortId: shortId,
48:                 CR: CR,
49:                 ercDebtRedeemed: ercDebtRedeemed,
50:                 colRedeemed: colRedeemed
51:             });
```
[45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L45-L51)


---
### [GAS&#x2011;39] The result of a function call should be cached rather than re-calling the function
External calls are expensive. Results of external function calls should be cached rather than call them multiple times. Consider caching the following:


Gas saved per Instance: ~100 *(Total: ~500)*
<details>
<summary><i>There are 5 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit lowestSell.isShort() called on lines 159, 181, 171
130:     function bidMatchAlgo( 
```
[130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit gasleft() called on lines 155, 196
154:     function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private { 
```
[154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit LibOrders.getOffsetTime() called on lines 154, 202
56:     function proposeRedemption( 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit oracle.latestRoundData() called on lines 42, 59
/// @audit twapCircuitBreaker() called on lines 62, 49
19:     function getOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19)

</details>


---
### [GAS&#x2011;40] Update OpenZeppelin dependency to the latest version
Every release contains new gas optimizations. Use the [latest version](https://github.com/OpenZeppelin/openzeppelin-contracts/releases) to take advantage of this.

 Current version is : `4.9.0`


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOracle.sol

7: import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol"; 
```
[7](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L7)


---
### [GAS&#x2011;41] Usage of `uints`/`ints` smaller than 32 bytes (256 bits) incurs overhead
Citing the [documentation](https://docs.soliditylang.org/en/latest/internals/layout_in_storage.html):

> When using elements that are smaller than 32 bytes, your contract’s gas usage may be higher.This is because the EVM operates on 32 bytes at a time.Therefore, if the element is smaller than that, the EVM must use more operations in order to reduce the size of the element from 32 bytes to the desired size.

For example, each operation involving a `uint8` costs an extra ** 22 - 28 gas ** (depending on whether the other operand is also a variable of type `uint8`) as compared to ones involving`uint256`, due to the compiler having to clear the higher bits of the memory word before operating on the`uint8`, as well as the associated stack operations of doing so.

Consider using a larger size, then downcast where needed.


Gas saved per Instance: ~6 *(Total: ~654)*
<details>
<summary><i>There are 109 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

42:         uint80 price, 

47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) { 

65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 

68:         returns (uint88 ethFilled, uint88 ercAmountLeft) 

80:         uint80 price, 

85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) { 

135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) { 

221:         uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount; 

226:             uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR)); 

280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) { 

391:         uint80 prevPrice = s.shorts[asset][b.prevShortId].price; 
```
[42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L42), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L80), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [221](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L221), [226](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L226), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [391](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L391)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

63:     function deposit(address bridge, uint88 amount) external nonReentrant { 

87:         uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH 

101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant { 

108:             uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge); 

119:         uint88 ethAmount = _ethConversion(vault, dethAmount); 

133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO { 

137:         uint88 ethAmount = _ethConversion(vault, dethAmount); 

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private { 

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L108), [119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L119), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L137), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 

87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 

111:             uint88 collateral = short.collateral; 

146:         uint80 price, 

148:         uint16 shortOrderId 
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L111), [146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L146), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L148)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 

52:         returns (uint88, uint88) 

97:         uint16 lowestAskKey = s.asks[m.asset][C.HEAD].nextId; 

156:         uint88 ercAmountLeft; 

171:             uint96 ercDebtPrev = m.short.ercDebt; 

213:         uint88 tappFee = m.ethFilled.mulU88(m.tappFeePct); 

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 

242:         uint88 decreaseCol = min88(m.totalFee + m.ethFilled, m.short.collateral); 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L52), [97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L97), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L156), [171](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L171), [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L213), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L242)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

59:         uint88 redemptionAmount, 

154:         uint32 protocolTime = LibOrders.getOffsetTime(); 

204:         uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed); 

320:         uint88 totalColRedeemed; 

373:             uint88 collateral = shortRecord.collateral; 

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 

384:         returns (uint88 redemptionFee) 

387:         uint32 protocolTime = LibOrders.getOffsetTime(); 

392:         uint104 totalAssetErcDebt = (ercDebtRedeemed + Asset.ercDebt).mulU104(C.BETA); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L59), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L154), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L204), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L320), [373](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L373), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382), [384](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L384), [387](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L387), [392](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L392)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

37:         uint80 price, 

41:         uint16 shortOrderCR 
```
[37](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L37), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L41)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal { 

41:         returns (uint88) 

46:         uint88 creditReth; 

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 

152:             uint88 creditReth = VaultUserFrom.bridgeCreditReth; 

181:                 uint88 creditTotal = creditReth + creditSteth; 

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L41), [46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L46), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L152), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L181), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
📁 File: contracts/libraries/LibBytes.sol

25:             uint88 ercDebtRedeemed; // bytes11 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L25)

```solidity
📁 File: contracts/libraries/LibOracle.sol

27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) { 

53:                     uint80 roundID, 

71:         uint80 roundId, 

119:         uint80 baseRoundId, 

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 
```
[27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27), [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L53), [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L71), [119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L119), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162)

```solidity
📁 File: contracts/libraries/LibOrders.sol

35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal { 

44:         uint32 timeTillMatch = getOffsetTime() - order.creationTime; 

47:             uint88 shares = eth * (timeTillMatch / 1 days); 

84:         uint16 hintId; 

105:         uint16 hintId; 

130:         uint16 hintId; 

177:         uint16 hintId 

182:         uint16 prevId = findPrevOfIncomingId(orders, asset, incomingOrder, hintId); 

186:         uint16 id = incomingOrder.id; 

195:             uint16 prevCanceledID = orders[asset][canceledID].prevId; 

231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId) 

263:         uint16 _prevId, 

265:         uint16 _nextId 

289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

291:         uint16 prevHEAD = orders[asset][C.HEAD].prevId; 

314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

323:         uint16 id, 

366:         uint16 hintId 

368:         uint16 nextId = orders[asset][hintId].nextId; 

405:         uint16 prevId, 

407:         uint16 nextId, 

447:     ) internal view returns (uint16 _hintId) { 

477:         uint16 id, 

535:         uint16 headId, 

540:         uint16 nextAskId = orders[asset][lastMatchedId].nextId; 

563:         uint16 startingId = s.bids[asset][C.HEAD].nextId; 

712:         uint88 fillErc = incomingSell.ercAmount > highestBid.ercAmount ? highestBid.ercAmount : incomingSell.ercAmount; 

742:             uint16 shortHintId; 

757:                 uint80 shortPrice = short.price; 

759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price; 

830:     ) internal view returns (uint16 hintId) { 

854:     function cancelBid(address asset, uint16 id) internal { 

868:     function cancelAsk(address asset, uint16 id) internal { 

882:     function cancelShort(address asset, uint16 id) internal { 

889:         uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR)); 

903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset)); 

907:                 uint88 debtDiff = minShortErc - shortRecord.ercDebt; 

911:                     uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR)); 

955:     function handlePriceDiscount(address asset, uint80 price) internal { 
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L44), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L84), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L105), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L130), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L177), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L182), [186](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L186), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L263), [265](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L265), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L291), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [323](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L323), [366](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L366), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L368), [405](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L405), [407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L407), [447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L447), [477](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L477), [535](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L535), [540](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L540), [563](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L563), [712](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L712), [742](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L742), [757](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L757), [759](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L759), [830](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L830), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [889](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L889), [903](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L903), [907](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L907), [911](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L911), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 

34:         uint88 yield = collateral.mulU88(Vault.dethYieldRate - dethYieldRate); 

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal { 

155:         uint64 ercDebtRate = s.asset[asset].ercDebtRate; 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22), [34](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L34), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L155)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken) 

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 

61:         int56 tickCumulativesDelta = tickCumulatives[1] - tickCumulatives[0]; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47), [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L61)

</details>


---
### [GAS&#x2011;42] Use `Array.unsafeAccess()` to avoid repeated array length checks
When using storage arrays, solidity adds an internal lookup of the array's length (a Gcoldsload **2100 gas**) to ensure you don't read past the array's end. You can avoid this lookup by using [`Array.unsafeAccess()`](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/94697be8a3f0dfcd95dfb13ffbd39b5973f5c65d/contracts/utils/Arrays.sol#L57) in cases where the length has already been checked, as is the case with the instances below


Gas saved per Instance: ~2,100 *(Total: ~18,900)*
<details>
<summary><i>There are 9 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

79:             p.shorter = proposalInput[i].shorter; 
80:             p.shortId = proposalInput[i].shortId;
81:             p.shortOrderId = proposalInput[i].shortOrderId;

243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) { 

264:                 currentProposal = decodedProposalData[i]; 

322:             MTypes.ProposalData memory currentProposal = decodedProposalData[i]; 
```
[79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L79-L81), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243), [264](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L264), [322](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L322)

```solidity
📁 File: contracts/libraries/LibOrders.sol

744:                 shortHintId = shortHintArray[i]; 

833:             MTypes.OrderHint memory orderHint = orderHintArray[i]; 
```
[744](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L744), [833](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L833)

</details>


---
### [GAS&#x2011;43] Use assembly for math equations
It is cheaper to use `div(mul(a, b), c)` instead of `(a * b) / c`. https://gist.github.com/notbozho/9ca20f4c6c837a33fab723fecd861f24


Gas saved per Instance: ~260 

<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOrders.sol

35:     function convertCR(uint16 cr) internal pure returns (uint256) { 
36:         return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;
37:     }
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35-L37)


---
### [GAS&#x2011;44] Use assembly scratch space to build calldata for external calls
Using Solidity's assembly scratch space for constructing calldata in external calls with one or two arguments can be a gas-efficient approach. This method leverages the designated memory area (the first 64 bytes of memory) for temporary data storage during assembly operations. By directly writing arguments into this scratch space, it eliminates the need for additional memory allocation typically required for calldata preparation. This technique can lead to notable gas savings, especially in high-frequency or gas-sensitive operations. However, it requires careful implementation to avoid data corruption and should be used with a thorough understanding of low-level EVM operations and memory handling. Proper testing and validation are crucial when employing such optimizations.


Gas saved per Instance: ~220 *(Total: ~2,420)*
<details>
<summary><i>There are 11 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId); 

295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId); 
```
[293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L293), [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L295)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

68:         uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast) 

121:         IBridge(bridge).withdraw(msg.sender, ethAmount); 

142:         IBridge(bridge).withdraw(msg.sender, ethAmount); 
```
[68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68), [121](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L121), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L142)

```solidity
📁 File: contracts/libraries/LibOracle.sol

87:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice) 

103:                     uint256 wethBal = weth.balanceOf(C.USDC_WETH); 

133:         uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes); 

138:         uint256 wethBal = weth.balanceOf(C.USDC_WETH); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L103), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133), [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L138)

```solidity
📁 File: contracts/libraries/LibOrders.sol

982:         IDiamond(payable(address(this)))._updateYieldDiamond(vault); 
```
[982](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L982)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L59)

</details>


---
### [GAS&#x2011;45] Use assembly to validate `msg.sender`
We can use assembly to efficiently validate msg.sender with the least amount of opcodes necessary. For more details check the following report [Here](https://code4rena.com/reports/2023-05-juicebox#g-06-use-assembly-to-validate-msgsender)


Gas saved per Instance: ~12 *(Total: ~72)*
<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf(); 
```
[54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue; 

229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself(); 

361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort(); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L87), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L229), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed(); 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L62)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

59:             if (shorter == msg.sender) { 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L59)

</details>


---
### [GAS&#x2011;46] Use `assembly` to write address/contract storage values
Using `assembly { sstore(state.slot, addr) }` instead of `state = addr` can save gas.


Gas saved per Instance: ~50 *(Total: ~750)*
<details>
<summary><i>There are 15 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

93:         incomingBid.addr = sender; 
```
[93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L93)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

30:         rethBridge = _rethBridge; 
31:         stethBridge = _stethBridge;
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L30-L31)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

29:         dusd = _dusd; 

151:         e.asset = asset; 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L29), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L151)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

31:         dusd = _dusd; 

129:             m.asset = asset; 

133:             m.shorter = shorter; 
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L31), [129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L129), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L133)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

64:         p.asset = asset; 

79:             p.shorter = proposalInput[i].shorter; 

146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate); 

231:         d.asset = asset; 
232:         d.redeemer = redeemer;
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L64), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L79), [146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L146), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L231-L232)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

64:         incomingShort.addr = msg.sender; 
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L64)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

146:         nft.owner = to; 
```
[146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L146)

</details>


---
### [GAS&#x2011;47] Use bitwise operators rather than boolean operators, to save gas
Instead of `((a != b) || (c != d))` use `((a ^ b) | (c ^ d))`

<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder(); 
```
[112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L112)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 
```
[57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L57), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84)

</details>


---
### [GAS&#x2011;48] Use constants instead of `type(uint<n>).max` / `.min`

Gas saved per Instance: ~4 *(Total: ~12)*
<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit 0xFFFFFFFFFFFFFFFFFFFFFF
230:         if (a > type(uint88).max) revert Errors.InvalidAmount(); 
```
[230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L230)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit 0xFF
62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals(); 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L62)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
36:         if (sqrtRatioX96 <= type(uint128).max) { 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L36)

</details>


---
### [GAS&#x2011;49] Use gas-efficient version of `min`()/`max`()
Prefer using `xor(a, mul(xor(a, b), gt(b, a)))` instead of `a > b ? a : b`

<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
230:         if (a > type(uint88).max) revert Errors.InvalidAmount();
231:         return a < b ? uint88(a) : b;
232:     }
```
[229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229-L232)

```solidity
📁 File: contracts/libraries/LibOrders.sol

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 
986:         return a < b ? a : b;
987:     }

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
990:         return a > b ? a : b;
991:     }
```
[985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985-L987), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989-L991)

</details>


---
### [GAS&#x2011;50] Use `if` statements instead of ternary operators
https://gist.github.com/notbozho/0d9f4dbc0026f8e7771a4fa39244f57e

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

97:         incomingBid.orderType = isMarketOrder ? O.MarketBid : O.LimitBid; 

221:         uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount; 
```
[97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L97), [221](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L221)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

169:         e.buybackAmount = e.shortOrderIsCancelled ? short.ercDebt : buybackAmount; 
```
[169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L169)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset); 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56)

```solidity
📁 File: contracts/libraries/LibOracle.sol

30:                 uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0; 

78:         uint256 chainlinkDiff = 
79:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;

95:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth; 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L78-L79), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L95)

```solidity
📁 File: contracts/libraries/LibOrders.sol

517:                 uint16 id = b.prevShortId == b.firstShortIdBelowOracle ? b.shortHintId : b.matchedShortId; 

677:         SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill; 

712:         uint88 fillErc = incomingSell.ercAmount > highestBid.ercAmount ? highestBid.ercAmount : incomingSell.ercAmount; 
```
[517](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L517), [677](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L677), [712](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L712)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

38:             quoteAmount = 
39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

42:             quoteAmount = 
43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
```
[38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L38-L39), [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L42-L43)

</details>


---
### [GAS&#x2011;51] Use `revert()` to gain maximum gas savings
If you dont need Error messages, or you want gain maximum gas savings - `revert()` is the cheapest way to revert a transaction in terms of gas.

```solidity
	revert(); // 117 gas
	require(false); // 132 gas
	revert CustomError(); // 157 gas
	assert(false); // 164 gas
	revert("Custom Error"); // 406 gas
	require(false, "Custom Error"); // 421 gas
```
The gas savings are calculated based on the average gas cost of the total instances of these functions in the contract, minus the gas cost of `revert()` which is 117 gas.


Gas saved per Instance: ~281.894 *(Total: ~18,605)*
<details>
<summary><i>There are 66 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize(); 

90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed(); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L87), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L90)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

102:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

134:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

164:             if (vault == 0) revert Errors.InvalidBridge(); 
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L64), [83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L83), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback(); 

99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback(); 

103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed(); 

174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback(); 

178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral(); 

188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow(); 

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount(); 

204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR(); 
```
[53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L103), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L178), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L188), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L201), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L204)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf(); 

56:         if (shortHintArray.length > 10) revert Errors.TooManyHints(); 

75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral(); 

109:             revert Errors.NoSells(); 

174:                 revert Errors.CannotSocializeDebt(); 

230:         if (a > type(uint88).max) revert Errors.InvalidAmount(); 
```
[54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L75), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L109), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L174), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L230)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals(); 

68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed(); 

73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions(); 

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder(); 

143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh(); 

208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed(); 

229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself(); 

235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 

237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed(); 

244:                 revert Errors.CannotDisputeWithRedeemerProposal(); 

251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption(); 

299:             revert Errors.InvalidRedemptionDispute(); 

314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort(); 

397:         assert(newBaseRate > 0); // Base rate is always non-zero after redemption 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L62), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L68), [70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L70), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L73), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L112), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L143), [205](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L205), [208](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L208), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L229), [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235), [237](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L237), [244](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L244), [251](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L251), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L299), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314-L315), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353-L354), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

52:             revert Errors.InvalidCR(); 

59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize(); 

62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed(); 

81:             revert Errors.BelowRecoveryModeCR(); 
```
[52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L52), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L59), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L62), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L81)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

75:                     revert Errors.MustUseExistingBridgeCredit(); 

105:                     revert Errors.MustUseExistingBridgeCredit(); 
```
[75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L75), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L105)

```solidity
📁 File: contracts/libraries/LibBytes.sol

14:         require(slate.length % 51 == 0, "Invalid data length"); 
```
[14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14)

```solidity
📁 File: contracts/libraries/LibOracle.sol

25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset(); 

60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice(); 

128:         if (invalidFetchData) revert Errors.InvalidPrice(); 

134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice(); 

139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool(); 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L25), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L128), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139)

```solidity
📁 File: contracts/libraries/LibOrders.sol

778:             revert Errors.BadShortHint(); 

850:         revert Errors.BadHintIdArray(); 

859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 

874:             revert Errors.NotActiveOrder(); 

887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 
```
[778](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L778), [850](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L850), [859](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L859), [874](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L874), [887](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L887)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

62:                 assert(shortRecord.status != SR.PartialFill); 

84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount(); 

98:             revert Errors.CannotLeaveDustAmount(); 

130:         if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled(); 
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
```
[57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L57), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L62), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L95), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L98), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L130-L131)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo(); 
```
[52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52)

</details>


---
### [GAS&#x2011;52] Use `s.x = s.x + y` instead of `s.x += y` for structs
Using the `s.x = s.x + y` instead of `s.x += y` for structs can save **100 gas**. The same applies to `-=`, `*=`, etc.


Gas saved per Instance: ~100 *(Total: ~18,100)*
<details>
<summary><i>There are 181 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

157:                     incomingBid.ercAmount -= lowestSell.ercAmount; 

180:                         lowestSell.ercAmount -= incomingBid.ercAmount; 

229:             matchTotal.shortFillEth += shortFillEth; 

255:             s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth; 
256:             matchTotal.askFillErc += fillErc;

259:         matchTotal.fillErc += fillErc; 
260:         matchTotal.fillEth += fillEth;

303:             Vault.dittoMatchedShares += matchTotal.dittoMatchedShares; 

305:             Vault.dethCollateral += matchTotal.shortFillEth; 
306:             Asset.dethCollateral += matchTotal.shortFillEth;
307:             Asset.ercDebt += matchTotal.fillErc - matchTotal.askFillErc;

330:         s.vaultUser[vault][bidder].ethEscrowed -= matchTotal.fillEth; 
331:         s.assetUser[asset][bidder].ercEscrowed += matchTotal.fillErc;
```
[157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L157), [180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L180), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L229), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L255-L256), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L259-L260), [303](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L303), [305](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L305-L307), [330](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L330-L331)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

114:                     s.vaultUser[vault][address(this)].ethEscrowed += fee; 

139:         s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount; 
140:         s.vault[vault].dethTotal -= dethAmount;
```
[114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L114), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L139-L140)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

56:         Asset.ercDebt -= buybackAmount; 

60:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral; 

64:             short.ercDebt -= buybackAmount; 

105:             AssetUser.ercEscrowed -= buybackAmount; 

108:         Asset.ercDebt -= buybackAmount; 

112:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral; 

117:             short.ercDebt -= buybackAmount; 

183:         VaultUser.ethEscrowed += e.collateral; 

190:         Asset.ercDebt -= e.ercFilled; 
191:         s.assetUser[e.asset][msg.sender].ercEscrowed -= e.ercFilled;

199:             short.collateral -= e.ethFilled; 
200:             short.ercDebt -= e.ercFilled;

207:             VaultUser.ethEscrowed -= e.collateral - e.ethFilled; 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L56), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L60), [64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L64), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L105), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L108), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L112), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L117), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L183), [190](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L190-L191), [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L199-L200), [207](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L207)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

166:         TAPP.ethEscrowed += m.short.collateral; 

183:             Asset.ercDebtRate += ercDebtSocialized.divU64(Asset.ercDebt - ercDebtPrev); 

193:         s.assetUser[m.asset][address(this)].ercEscrowed -= m.ercDebtMatched; 
194:         s.asset[m.asset].ercDebt -= m.ercDebtMatched;

216:         m.totalFee += tappFee + callerFee; 

219:             TAPP.ethEscrowed -= callerFee; 
220:             VaultUser.ethEscrowed += callerFee;

223:             VaultUser.ethEscrowed += callerFee - m.gasFee + tappFee; 
224:             m.totalFee -= m.gasFee;
225:             TAPP.ethEscrowed -= m.totalFee;

249:                 m.short.collateral -= decreaseCol; 
250:                 s.vaultUser[m.vault][m.shorter].ethEscrowed += m.short.collateral;
251:                 TAPP.ethEscrowed -= m.short.collateral;

255:             m.short.ercDebt -= m.ercDebtMatched; 
256:             m.short.collateral -= decreaseCol;

259:             TAPP.ethEscrowed -= m.short.collateral; 
```
[166](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L166), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L183), [193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L193-L194), [216](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L216), [219](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L219-L220), [223](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L223-L225), [249](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L249-L251), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L255-L256), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L259)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

121:             currentSR.collateral -= p.colRedeemed; 
122:             currentSR.ercDebt -= p.amountProposed;

124:             p.totalAmountProposed += p.amountProposed; 
125:             p.totalColRedeemed += p.colRedeemed;

149:         redeemerAssetUser.ercEscrowed -= p.totalAmountProposed; 

152:         Asset.ercDebt -= p.totalAmountProposed; 

209:         VaultUser.ethEscrowed -= redemptionFee; 

267:                 currentSR.collateral += currentProposal.colRedeemed; 
268:                 currentSR.ercDebt += currentProposal.ercDebtRedeemed;

270:                 d.incorrectCollateral += currentProposal.colRedeemed; 
271:                 d.incorrectErcDebt += currentProposal.ercDebtRedeemed;

274:             s.vault[Asset.vault].dethCollateral += d.incorrectCollateral; 
275:             Asset.dethCollateral += d.incorrectCollateral;
276:             Asset.ercDebt += d.incorrectErcDebt;

296:             redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt); 
297:             s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;

331:         redeemerVaultUser.ethEscrowed += totalColRedeemed; 

374:             s.vaultUser[vault][shorter].ethEscrowed += collateral; 
```
[121](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L121-L122), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L124-L125), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L149), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L152), [209](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L209), [267](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L267-L268), [270](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L270-L271), [274](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L274-L276), [296](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L296-L297), [331](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L331), [374](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L374)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

28:                 VaultUser.bridgeCreditReth += amount; 

30:                 VaultUser.bridgeCreditSteth += amount; 

34:         VaultUser.ethEscrowed += amount; 
35:         s.vault[vault].dethTotal += amount;

52:                 VaultUser.bridgeCreditReth -= amount; 

66:                         VaultUser.bridgeCreditSteth -= amount; 

82:                 VaultUser.bridgeCreditSteth -= amount; 

96:                         VaultUser.bridgeCreditReth -= amount; 

164:                     VaultUserFrom.bridgeCreditReth -= collateral; 
165:                     VaultUserTo.bridgeCreditReth += collateral;

168:                     VaultUserTo.bridgeCreditReth += creditReth; 

173:                     VaultUserFrom.bridgeCreditSteth -= collateral; 
174:                     VaultUserTo.bridgeCreditSteth += collateral;

177:                     VaultUserTo.bridgeCreditSteth += creditSteth; 

185:                     VaultUserFrom.bridgeCreditReth -= creditReth; 
186:                     VaultUserFrom.bridgeCreditSteth -= creditSteth;

191:                 VaultUserTo.bridgeCreditReth += creditReth; 
192:                 VaultUserTo.bridgeCreditSteth += creditSteth;

200:         s.vaultUser[vault][msg.sender].ethEscrowed -= (amount + fee); 
201:         s.vault[vault].dethTotal -= amount;
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L28), [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L30), [34](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L34-L35), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L52), [66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L66), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L82), [96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L96), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L164-L165), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L168), [173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L173-L174), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L177), [185](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L185-L186), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L191-L192), [200](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L200-L201)

```solidity
📁 File: contracts/libraries/LibOrders.sol

48:             matchTotal.dittoMatchedShares += shares; 

51:             s.vaultUser[vault][order.addr].dittoMatchedShares += shares; 

100:         s.vaultUser[vault][order.addr].ethEscrowed -= eth; 

118:         s.assetUser[asset][order.addr].ercEscrowed -= order.ercAmount; 

143:         s.vaultUser[vault][order.addr].ethEscrowed -= eth; 

210:             s.asset[asset].orderIdCounter += 1; 

584:                     incomingAsk.ercAmount -= highestBid.ercAmount; 

604:                         highestBid.ercAmount -= incomingAsk.ercAmount; 

656:         s.assetUser[asset][asker].ercEscrowed -= matchTotal.fillErc; 
657:         s.vaultUser[vault][asker].ethEscrowed += matchTotal.fillEth;
658:         s.vault[vault].dittoMatchedShares += matchTotal.dittoMatchedShares;

674:         s.vaultUser[vault][incomingShort.addr].ethEscrowed -= matchTotal.colUsed; 
675:         matchTotal.fillEth += matchTotal.colUsed;

690:         Vault.dittoMatchedShares += matchTotal.dittoMatchedShares; 
691:         Vault.dethCollateral += matchTotal.fillEth;
692:         Asset.dethCollateral += matchTotal.fillEth;
693:         Asset.ercDebt += matchTotal.fillErc;

718:             matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR)); 

720:         matchTotal.fillErc += fillErc; 
721:         matchTotal.fillEth += fillEth;

725:         s.assetUser[asset][highestBid.addr].ercEscrowed += fillErc; 

863:         s.vaultUser[vault][bid.addr].ethEscrowed += eth; 

877:         s.assetUser[asset][ask.addr].ercEscrowed += ask.ercAmount; 

924:                     Vault.dethCollateral += collateralDiff; 
925:                     Asset.dethCollateral += collateralDiff;
926:                     Asset.ercDebt += debtDiff;

932:                 s.assetUser[asset][shorter].ercEscrowed += debtDiff; 

938:         s.vaultUser[vault][shorter].ethEscrowed += eth; 
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L48), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L51), [100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L100), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L118), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L143), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L210), [584](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L584), [604](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L604), [656](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L656-L658), [674](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L674-L675), [690](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L690-L693), [718](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L718), [720](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L720-L721), [725](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L725), [863](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L863), [877](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L877), [924](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L924-L926), [932](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L932), [938](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L938)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

31:         Vault.dethCollateral -= collateral; 
32:         Asset.dethCollateral -= collateral;

42:                 s.vaultUser[vault][shorter].ethEscrowed += yield; 

44:                 s.vaultUser[vault][address(this)].ethEscrowed += yield; 

159:             short.ercDebt += ercDebt; 
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L31-L32), [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L42), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L44), [159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L159)

</details>


---
### [GAS&#x2011;53] Use scratch space when building emitted events
We can use assembly to emit events efficiently by utilizing `scratch space` and the `free memory pointer`. This will allow us to potentially avoid memory expansion costs.
Note: In order to do this optimization safely, we will need to cache and restore the free memory pointer.

For example, for a generic `emit` event for `eventSentAmountExample`: 
```solidity
// uint256 id, uint256 value, uint256 amount
emit eventSentAmountExample(id, value, amount);
```



Gas saved per Instance: ~38 *(Total: ~418)*
<details>
<summary><i>There are 11 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

72:         emit Events.Deposit(bridge, msg.sender, dethAmount); 

90:         emit Events.DepositEth(bridge, msg.sender, dethAmount); 

122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee); 

143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount); 
```
[72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L72), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L90), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L122), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L143)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount); 

128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount); 

210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled); 
```
[75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L75), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L128), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L210)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

210:         emit Events.ProposeRedemption(p.asset, msg.sender); 

284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer); 

333:         emit Events.ClaimRedemption(asset, msg.sender); 
```
[210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L210), [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L333)

```solidity
📁 File: contracts/libraries/LibOrders.sol

301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType); 
```
[301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301)

</details>


---
### [GAS&#x2011;54] Using `storage` instead of `memory` for structs/arrays saves gas
When fetching data from a storage location, assigning the data to a `memory` variable causes all fields of the struct/array to be read from storage, which incurs a Gcoldsload (**2100 gas**) for *each* field of the struct/array. If the fields are read from the new memory variable, they incur an additional `MLOAD` rather than a cheap stack read. Instead of declearing the variable with the `memory` keyword, declaring the variable with the `storage` keyword and caching any fields that need to be re-read in stack variables, will be much cheaper, only incuring the Gcoldsload for the fields actually read. The only time it makes sense to read the whole struct/array into a `memory` variable, is if the full struct/array is being returned by the function, is being passed to a function that requires `memory`, or if the array/struct is being read from another `memory` array/struct


Gas saved per Instance: ~2,100 *(Total: ~54,600)*
<details>
<summary><i>There are 26 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

71:         MTypes.OrderHint[] memory orderHintArray; 

92:         STypes.Order memory incomingBid; 

100:         MTypes.BidMatchAlgo memory b; 

105:         STypes.Order memory lowestSell = _getLowestSell(asset, b); 

137:         MTypes.Match memory matchTotal; 

148:             STypes.Order memory lowestSell = _getLowestSell(asset, b); 
```
[71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L71), [92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L92), [100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L100), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L105), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L137), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L148)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

150:         MTypes.ExitShort memory e; 
```
[150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L150)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

70:         MTypes.PrimaryLiquidation memory m = _setLiquidationStruct(asset, shorter, id, shortOrderId); 

128:             MTypes.PrimaryLiquidation memory m; 
```
[70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L70), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L128)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

63:         MTypes.ProposeRedemption memory p; 

230:         MTypes.DisputeRedemption memory d; 

239:         MTypes.ProposalData[] memory decodedProposalData = 
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex]; 
254:         MTypes.ProposalData memory currentProposal;

317:         MTypes.ProposalData[] memory decodedProposalData = 
318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

322:             MTypes.ProposalData memory currentProposal = decodedProposalData[i]; 

357:         MTypes.ProposalData[] memory decodedProposalData = 
358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
359:         MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];
```
[63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L63), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L230), [239](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L239-L240), [253](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L253-L254), [317](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L317-L318), [322](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L322), [357](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L357-L359)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

43:         MTypes.CreateLimitShortParam memory p; 

45:         STypes.Order memory incomingShort; 
```
[43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L43), [45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L45)

```solidity
📁 File: contracts/libraries/LibBytes.sol

16:         MTypes.ProposalData[] memory data = new MTypes.ProposalData[](slateLength); 
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L16)

```solidity
📁 File: contracts/libraries/LibOrders.sol

68:         STypes.Order[] memory list = new STypes.Order[](size); 

571:         MTypes.Match memory matchTotal; 

573:             STypes.Order memory highestBid = s.bids[asset][startingId]; 

833:             MTypes.OrderHint memory orderHint = orderHintArray[i]; 
```
[68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L68), [571](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L571), [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573), [833](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L833)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

54:         uint32[] memory secondsAgos = new uint32[](2); 
```
[54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L54)

</details>

