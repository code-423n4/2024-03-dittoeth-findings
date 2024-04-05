The content section shows only 10 examples, subsequent cases are listed as links.

## Summary

### Low Risk Issues

|                 | Issue                                                                           | Instances |
| --------------- | :------------------------------------------------------------------------------ | :-------: |
| [[L-01](#l-01)] | Chainlink oracle will return the wrong price if the aggregator hits `minAnswer` |     3     |
| [[L-02](#l-02)] | Array lengths not checked                                                       |     3     |
| [[L-03](#l-03)] | Code does not follow the best practice of check-effects-interaction             |    23     |
| [[L-04](#l-04)] | Consider bounding input array length                                            |     3     |
| [[L-05](#l-05)] | Privileged functions can create points of failure                               |     3     |

### NonCritical Risk Issues

|                 | Issue                                                                                                                                                      | Instances |
| --------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------: |
| [[N-01](#n-01)] | Functions which are either private or internal should have a preceding _ in their name                                                                     |    65     |
| [[N-02](#n-02)] | Private and internal state variables should have a preceding _ in their name unless they are constants                                                     |     4     |
| [[N-03](#n-03)] | Emits without `msg.sender` parameter                                                                                                                       |     1     |
| [[N-04](#n-04)] | A function which defines named returns in it's declaration doesn't need to use `return`                                                                    |    22     |
| [[N-05](#n-05)] | Use multiple `require()` and `if` statements instead of `&&`                                                                                               |    29     |
| [[N-06](#n-06)] | `Constants` in comparisons should appear on the left side                                                                                                  |    98     |
| [[N-07](#n-07)] | Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables                                                 |     4     |
| [[N-08](#n-08)] | Consider using `delete` rather than assigning zero/false to clear values                                                                                   |    17     |
| [[N-09](#n-09)] | Large numeric literals should use underscores for readability                                                                                              |    12     |
| [[N-10](#n-10)] | Unused contract variables                                                                                                                                  |    13     |
| [[N-11](#n-11)] | `else`-block not required                                                                                                                                  |    38     |
| [[N-12](#n-12)] | Convert simple if-statements to ternary expressions                                                                                                        |    28     |
| [[N-13](#n-13)] | Remaining eth may not be refunded to users                                                                                                                 |     1     |
| [[N-14](#n-14)] | External calls in an un-bounded `for`-loop may result in a DOS                                                                                             |     4     |
| [[N-15](#n-15)] | `constructor` missing zero address check                                                                                                                   |     3     |
| [[N-16](#n-16)] | Variable initialization with default value                                                                                                                 |     6     |
| [[N-17](#n-17)] | Large multiples of ten should use scientific notation                                                                                                      |    24     |
| [[N-18](#n-18)] | Complex math should be split into multiple steps                                                                                                           |     4     |
| [[N-19](#n-19)] | Duplicated `require/if` statements should be refactored                                                                                                    |    54     |
| [[N-20](#n-20)] | Variable names don't follow the Solidity naming convention                                                                                                 |    37     |
| [[N-21](#n-21)] | Contract functions should use an `interface`                                                                                                               |    17     |
| [[N-22](#n-22)] | State variables should include comments                                                                                                                    |     4     |
| [[N-23](#n-23)] | Consider implementing two-step procedure for updating protocol addresses                                                                                   |     6     |
| [[N-24](#n-24)] | Constant redefined elsewhere                                                                                                                               |     2     |
| [[N-25](#n-25)] | Function names should use lowerCamelCase                                                                                                                   |     3     |
| [[N-26](#n-26)] | Overflows in unchecked blocks                                                                                                                              |     1     |
| [[N-27](#n-27)] | Events may be emitted out of order due to reentrancy                                                                                                       |    10     |
| [[N-28](#n-28)] | Function can return unassigned variable                                                                                                                    |     2     |
| [[N-29](#n-29)] | Simplify complex require statements                                                                                                                        |     1     |
| [[N-30](#n-30)] | Events should be emitted before external calls                                                                                                             |    12     |
| [[N-31](#n-31)] | Contract name does not follow the Solidity Style Guide                                                                                                     |     1     |
| [[N-32](#n-32)] | Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES                                                                                     |     4     |
| [[N-33](#n-33)] | Contracts should have full test coverage                                                                                                                   |     1     |
| [[N-34](#n-34)] | Large or complicated code bases should implement invariant tests                                                                                           |     1     |
| [[N-35](#n-35)] | Codebase should implement formal verification testing                                                                                                      |     1     |
| [[N-36](#n-36)] | Unsafe `uint` to `int` conversion                                                                                                                          |     2     |
| [[N-37](#n-37)] | State variables not capped at reasonable values                                                                                                            |     7     |
| [[N-38](#n-38)] | Consider adding a block/deny-list                                                                                                                          |     1     |
| [[N-39](#n-39)] | Typos                                                                                                                                                      |     2     |
| [[N-40](#n-40)] | Alternative Solady library can be used instead of OpenZeppelin to save gas                                                                                 |     1     |
| [[N-41](#n-41)] | Setting the `constructor` to `payable`                                                                                                                     |     3     | 
| [[N-42](#n-42)] | `++i`/`i++` should be `unchecked{++i}`/`unchecked{i++}` when it is not possible for them to overflow, as is the case when used in `for`- and `while`-loops |     8     | 
| [[N-43](#n-43)] | `Internal` functions only called once can be inlined to save gas                                                                                           |    14     | 
| [[N-44](#n-44)] | Usage of `uint`/`int` smaller than 32 bytes (256 bits) incurs overhead                                                                                     |    191    | 
| [[N-45](#n-45)] | `>=` costs less gas than `>`                                                                                                                               |    26     | 
| [[N-46](#n-46)] | Using `storage` instead of `memory` for structs/arrays saves gas                                                                                           |     1     | 
| [[N-47](#n-47)] | Stack variable used as a cheaper cache for a state variable is only used once                                                                              |    47     | 
| [[N-48](#n-48)] | Newer versions of solidity are more gas efficient                                                                                                          |    12     |
| [[N-49](#n-49)] | Consider activating `via-ir` for deploying                                                                                                                 |     1     |
| [[N-50](#n-50)] | Function calls should be cached instead of re-calling the function                                                                                         |    12     | 
| [[N-51](#n-51)] | Consider pre-calculating the address of `address(this)`                                                                                                    |    18     |
| [[N-52](#n-52)] | Optimize Zero Checks Using Assembly                                                                                                                        |    51     | 
| [[N-53](#n-53)] | Consider Caching Multiple Accesses to Mappings/Arrays                                                                                                      |    51     | 
| [[N-54](#n-54)] | Optimize Gas by Using Do-While Loops                                                                                                                       |    12     | 
| [[N-55](#n-55)] | Use Assembly for Efficient Event Emission                                                                                                                  |    15     |
| [[N-56](#n-56)] | Optimize External Calls with Assembly for Memory Efficiency                                                                                                |    22     | 
| [[N-57](#n-57)] | Consider Using Solady's Gas Optimized Lib for Math                                                                                                         |    25     |
| [[N-58](#n-58)] | Trade-offs Between Modifiers and Internal Functions                                                                                                        |    32     | 
| [[N-59](#n-59)] | Optimize Unsigned Integer Comparison With Zero                                                                                                             |    11     | 
| [[N-60](#n-60)] | Delete Unused State Variables                                                                                                                              |    13     |
| [[N-61](#n-61)] | Optimize Gas by Using Only Named Returns                                                                                                                   |    17     |
| [[N-62](#n-62)] | Optimize Address Storage Value Management with `assembly`                                                                                                  |     4     |
| [[N-63](#n-63)] | Gas savings can be achieved by changing the model for assigning value to the structure                                                                     |     1     |
| [[N-64](#n-64)] | Use `Array.unsafeAccess` to avoid repeated array length checks                                                                                             |    125    |
| [[N-65](#n-65)] | Consider using OpenZeppelin's `EnumerateSet` instead of nested mappings                                                                                    |    12     |
| [[N-66](#n-66)] | Counting down in `for` statements is more gas efficient                                                                                                    |     8     |


### Low Risk Issues

### [L-01]<a name="l-01"></a> Chainlink oracle will return the wrong price if the aggregator hits `minAnswer`

Chainlink aggregators have a built-in circuit breaker if the price of an asset goes outside of a predetermined price band.

The result is that if an asset experiences a huge drop in value (i.e. LUNA crash) the price of the oracle will continue to return the `minPrice` instead of the actual price of the asset.

This would allow users to continue borrowing with the asset but at the wrong price. This is exactly what happened to Venus on BSC when LUNA [crashed](https://rekt.news/venus-blizz-rekt/).

*There are 3 instance(s) of this issue:*


---

	 - contracts/libraries/LibOracle.sol

```solidity
42	                ) = oracle.latestRoundData();
...
59	                ) = oracle.latestRoundData();
...
27	        try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
```

*GitHub* : [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L42), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L59), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27)

### [L-02]<a name="l-02"></a> Array lengths not checked

If the length of the arrays are not required to be of the same length, user operations may not be fully executed due to a mismatch in the number of items iterated over, versus the number of items provided in the second array

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
40	    function createBid(
41	        address asset,
42	        uint80 price,
43	        uint88 ercAmount,
44	        bool isMarketOrder,
45	        MTypes.OrderHint[] calldata orderHintArray,
46	        uint16[] calldata shortHintArray
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
77	    function _createBid(
78	        address sender,
79	        address asset,
80	        uint80 price,
81	        uint88 ercAmount,
82	        bool isMarketOrder,
83	        MTypes.OrderHint[] memory orderHintArray,
84	        uint16[] memory shortHintArray
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [40..47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [77..85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
35	    function createLimitShort(
36	        address asset,
37	        uint80 price,
38	        uint88 ercAmount,
39	        MTypes.OrderHint[] memory orderHintArray,
40	        uint16[] memory shortHintArray,
41	        uint16 shortOrderCR
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

*GitHub* : [35..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)

### [L-03]<a name="l-03"></a> Code does not follow the best practice of check-effects-interaction

Code should follow the best-practice of [check-effects-interaction](https://blockchain-academy.hs-mittweida.de/courses/solidity-coding-beginners-to-intermediate/lessons/solidity-11-coding-patterns/topic/checks-effects-interactions/), where state variables are updated before any external calls are made. Doing so prevents a large class of reentrancy bugs.

*There are 23 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
// @audit Some statements does not follow CEI
215	    function matchlowestSell(
216	        address asset,
217	        STypes.Order memory lowestSell,
218	        STypes.Order memory incomingBid,
219	        MTypes.Match memory matchTotal
220	    ) private {
...
// @audit Statement out of CEI order
261	        matchTotal.lastMatchPrice = lowestSell.price;
```

*GitHub* : [261](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L261)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
// @audit Some statements does not follow CEI
96	    function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {
...
// @audit Statement out of CEI order
109	            revert Errors.NoSells();
...
// @audit Some statements does not follow CEI
122	    function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123	        private
124	        returns (MTypes.PrimaryLiquidation memory)
125	    {
...
// @audit Statement out of CEI order
140	            m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
```

*GitHub* : [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L109), [140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L140)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
// @audit Some statements does not follow CEI
156	    function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
...
// @audit Statement out of CEI order
164	            if (vault == 0) revert Errors.InvalidBridge();
```

*GitHub* : [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit Some statements does not follow CEI
56	    function proposeRedemption(
57	        address asset,
58	        MTypes.ProposalInput[] calldata proposalInput,
59	        uint88 redemptionAmount,
60	        uint88 maxRedemptionFee
61	    ) external isNotFrozen(asset) nonReentrant {
...
// @audit Statement out of CEI order
209	        VaultUser.ethEscrowed -= redemptionFee;
```

*GitHub* : [209](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L209), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L299), [331](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L331), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L105)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [45..51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L45-L51)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [27..66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27-L66), [87..111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87-L111), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L128)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L100), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L118), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L143), [488](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L488), [693](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L693), [725](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L725), [778](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L778), [850](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L850)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L98), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L148)

### [L-04]<a name="l-04"></a> Consider bounding input array length

The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to `require()` that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit array parameter `proposalInput` is used as loop condition and length is not cheched in function
58	        MTypes.ProposalInput[] calldata proposalInput,
...
// @audit loop uses unbounded parameter
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
```

*GitHub* : [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78)


---

	 - contracts/libraries/LibOrders.sol

```solidity
// @audit array parameter `shortHintArray` is used as loop condition and length is not cheched in function
728	    function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
...
// @audit loop uses unbounded parameter
743	            for (uint256 i = 0; i < shortHintArray.length;) {
```

*GitHub* : [743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743)


---

	 - contracts/libraries/LibOrders.sol

```solidity
// @audit array parameter `orderHintArray` is used as loop condition and length is not cheched in function
829	        MTypes.OrderHint[] memory orderHintArray
...
// @audit loop uses unbounded parameter
832	        for (uint256 i; i < orderHintArray.length; i++) {
```

*GitHub* : [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832)

### [L-05]<a name="l-05"></a> Privileged functions can create points of failure

Ensure such accounts are protected and consider implementing multi sig to prevent a single point of failure

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
// @audit Modifiers that checks `msg.sender`: `onlyDiamond`, `onlyOwner`, `onlyRole`
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66	        external
67	        onlyDiamond
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
69	    {
```

*GitHub* : [65..69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
// @audit `msg.sender` is checked in function body
47	    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48	        external
49	        isNotFrozen(asset)
50	        nonReentrant
51	        onlyValidShortRecord(asset, shorter, id)
52	        returns (uint88, uint88)
53	    {
...
// @note `msg.sender` is checked here
54	        if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
```

*GitHub* : [47..53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit `msg.sender` is checked in function body
224	    function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225	        external
226	        isNotFrozen(asset)
227	        nonReentrant
228	    {
...
// @note `msg.sender` is checked here
229	        if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
```

*GitHub* : [224..228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228)

### NonCritical Risk Issues

### [N-01]<a name="n-01"></a> Functions which are either private or internal should have a preceding _ in their name

Add a preceding underscore to the function name, take care to refactor where there functions are called

*There are 65 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
130	    function bidMatchAlgo(
131	        address asset,
132	        STypes.Order memory incomingBid,
133	        MTypes.OrderHint[] memory orderHintArray,
134	        MTypes.BidMatchAlgo memory b
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
215	    function matchlowestSell(
216	        address asset,
217	        STypes.Order memory lowestSell,
218	        STypes.Order memory incomingBid,
219	        MTypes.Match memory matchTotal
220	    ) private {
...
275	    function matchIncomingBid(
276	        address asset,
277	        STypes.Order memory incomingBid,
278	        MTypes.Match memory matchTotal,
279	        MTypes.BidMatchAlgo memory b
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [130..135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215..220](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275..280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
229	    function min88(uint256 a, uint88 b) private pure returns (uint88) {
```

*GitHub* : [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
148	    function maybeUpdateYield(uint256 vault, uint88 amount) private {
```

*GitHub* : [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
213	    function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```

*GitHub* : [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
31	    function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32	        internal
33	        view
34	        returns (bool)
35	    {
...
382	    function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383	        internal
384	        returns (uint88 redemptionFee)
385	    {
```

*GitHub* : [31..35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35), [382..385](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
21	    function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
...
39	    function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40	        internal
41	        returns (uint88)
42	    {
```

*GitHub* : [21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [39..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69..75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [117..124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117-L124), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [55..59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [153](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L153), [173..178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [231..235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [260..266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [362..367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [402..409](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L409), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [440..447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [474..479](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L474-L479), [499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499), [556..561](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [628](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L628), [652](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L652), [668](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L668), [705..710](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L705-L710), [783..788](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783-L788), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [826..830](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [22..24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72..75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [102..106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [28..32](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28-L32), [47..51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

### [N-02]<a name="n-02"></a> Private and internal state variables should have a preceding _ in their name unless they are constants

Add a preceding underscore to the state variable name, take care to refactor where there variables are read/wrote

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
28	    address private immutable dusd;
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
26	    address private immutable rethBridge;
...
27	    address private immutable stethBridge;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
26	    address private immutable dusd;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

### [N-03]<a name="n-03"></a> Emits without `msg.sender` parameter

If `msg.sender` play a part in the functionality of a function, any emits of this function should include msg.sender to ensure transparency with users

*There are 1 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit Current function use `msg.sender`, but do not emit it
284	                emit Events.DisputeRedemptionAll(d.asset, redeemer);
```

*GitHub* : [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284)

### [N-04]<a name="n-04"></a> A function which defines named returns in it's declaration doesn't need to use `return`

Once the return variable has been assigned (or has its default value), there is no need to explicitly return it at the end of the function, since it's returned automatically.
Remove the return statement once ensuring it is safe to do so

*There are 22 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
40	    function createBid(
41	        address asset,
42	        uint80 price,
43	        uint88 ercAmount,
44	        bool isMarketOrder,
45	        MTypes.OrderHint[] calldata orderHintArray,
46	        uint16[] calldata shortHintArray
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66	        external
67	        onlyDiamond
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
69	    {
...
77	    function _createBid(
78	        address sender,
79	        address asset,
80	        uint80 price,
81	        uint88 ercAmount,
82	        bool isMarketOrder,
83	        MTypes.OrderHint[] memory orderHintArray,
84	        uint16[] memory shortHintArray
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
130	    function bidMatchAlgo(
131	        address asset,
132	        STypes.Order memory incomingBid,
133	        MTypes.OrderHint[] memory orderHintArray,
134	        MTypes.BidMatchAlgo memory b
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
275	    function matchIncomingBid(
276	        address asset,
277	        STypes.Order memory incomingBid,
278	        MTypes.Match memory matchTotal,
279	        MTypes.BidMatchAlgo memory b
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
340	    function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
```

*GitHub* : [40..47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65..69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69), [77..85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130..135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [275..280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
213	    function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```

*GitHub* : [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
382	    function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383	        internal
384	        returns (uint88 redemptionFee)
385	    {
```

*GitHub* : [382..385](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
113	    function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
```

*GitHub* : [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113)


---

	 - contracts/libraries/LibOracle.sol

```solidity
69	    function baseOracleCircuitBreaker(
70	        uint256 protocolPrice,
71	        uint80 roundId,
72	        int256 chainlinkPrice,
73	        uint256 timeStamp,
74	        uint256 chainlinkPriceInEth
75	    ) private view returns (uint256 _protocolPrice) {
```

*GitHub* : [69..75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [231..235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [260..266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [402..409](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L409), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [440..447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [826..830](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [49..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [102..106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106)

### [N-05]<a name="n-05"></a> Use multiple `require()` and `if` statements instead of `&&`

Using multiple `require()` and `if` improves code readability and makes it easier to debug.

*There are 29 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
106	        if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107	            // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108	            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109	            b.shortHintId = b.shortId = Asset.startingShortId;
110	            b.oraclePrice = LibOracle.getPrice(asset);
111	            return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112	        } else {
113	            // @dev no match, add to market if limit order
114	            LibOrders.addBid(asset, incomingBid, orderHintArray);
115	            return (0, ercAmount);
116	        }
...
141	            if (b.askId == C.TAIL && b.shortId == C.TAIL) {
142	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143	                    LibOrders.addBid(asset, incomingBid, orderHintArray);
144	                }
145	                return matchIncomingBid(asset, incomingBid, matchTotal, b);
146	            }
...
315	            if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
316	                Asset.startingShortId = b.shortId;
317	            } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318	                Asset.startingShortId = b.prevShortId;
319	            } else {
320	                if (b.isMovingFwd) {
321	                    Asset.startingShortId = currentShort.nextId;
322	                } else {
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324	                }
325	            }
...
317	            } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318	                Asset.startingShortId = b.prevShortId;
319	            } else {
320	                if (b.isMovingFwd) {
321	                    Asset.startingShortId = currentShort.nextId;
322	                } else {
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324	                }
325	            }
...
392	        if (prevPrice >= b.oraclePrice && !b.isMovingFwd) {
393	            // @dev shortHintId should always be the first thing matched
394	            b.isMovingBack = true;
395	            b.shortId = b.prevShortId;
396	        } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) {
397	            b.firstShortIdBelowOracle = b.prevShortId;
398	            b.shortId = s.shorts[asset][b.shortHintId].nextId;
399	
400	            STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId];
401	            // @dev Only set to true if actually moving forward
402	            if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403	                b.isMovingFwd = true;
404	            }
405	        } else if (b.isMovingFwd) {
406	            b.shortId = lowestSell.nextId;
407	        }
...
396	        } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) {
397	            b.firstShortIdBelowOracle = b.prevShortId;
398	            b.shortId = s.shorts[asset][b.shortHintId].nextId;
399	
400	            STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId];
401	            // @dev Only set to true if actually moving forward
402	            if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403	                b.isMovingFwd = true;
404	            }
405	        } else if (b.isMovingFwd) {
406	            b.shortId = lowestSell.nextId;
407	        }
...
402	            if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403	                b.isMovingFwd = true;
404	            }
```

*GitHub* : [106..116](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L106-L116), [141..146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L141-L146), [315..325](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L315-L325), [317..325](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L317-L325), [392..407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L392-L407), [396..407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L396-L407), [402..404](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L402-L404)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
75	        if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76	            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77	        }
```

*GitHub* : [75..77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L75-L77)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
100	        if (
101	            // Checks for no eligible asks
102	            (lowestAskKey == C.TAIL || s.asks[m.asset][lowestAskKey].price > bufferPrice)
103	            // Checks for no eligible shorts
104	            && (
105	                startingShortId == C.HEAD // means no short >= oracleprice
106	                    || s.shorts[m.asset][startingShortId].price > bufferPrice
107	            )
108	        ) {
109	            revert Errors.NoSells();
110	        }
...
263	            if (m.loseCollateral && m.shorter != address(this)) {
264	                // Delete partially liquidated short
265	                LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);
266	                // Absorb leftovers into TAPP short
267	                LibShortRecord.fillShortRecord(
268	                    m.asset,
269	                    address(this),
270	                    C.SHORT_STARTING_ID,
271	                    SR.FullyFilled,
272	                    m.short.collateral,
273	                    m.short.ercDebt,
274	                    s.asset[m.asset].ercDebtRate,
275	                    m.short.dethYieldRate
276	                );
277	            }
```

*GitHub* : [100..110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L100-L110), [263..277](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L263-L277)


---

	 - contracts/facets/BridgeRouterFacet.sol


*GitHub* : [150..152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L150-L152)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [111..114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L111-L114), [243..245](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243-L245), [259..300](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L259-L300), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361), [371..378](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L371-L378)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [156..159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L156-L159), [161..193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L161-L193), [170..193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L170-L193)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [241..247](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L241-L247), [272..278](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L272-L278), [506..520](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L506-L520), [510..520](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L510-L520), [513..520](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L513-L520), [516..520](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L516-L520), [821..823](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L821-L823), [840..842](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L840-L842)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [97..99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L97-L99)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [65..67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65-L67)

### [N-06]<a name="n-06"></a> `Constants` in comparisons should appear on the left side

Doing so will prevent [typo bugs](https://www.moserware.com/2008/01/constants-on-left-are-better-but-this.html)

*There are 98 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
152	                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
...
281	        if (matchTotal.fillEth == 0) {
...
292	        if (b.dustAskId > 0) {
...
294	        } else if (b.dustShortId > 0) {
...
299	        if (matchTotal.shortFillEth > 0) {
```

*GitHub* : [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L152), [281](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L281), [292](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L292), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L294), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L299)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
56	        p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
```

*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
56	        if (shortHintArray.length > 10) revert Errors.TooManyHints();
```

*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
102	        if (dethAmount == 0) revert Errors.ParameterIsZero();
...
109	            if (dethAssessable > 0) {
...
111	                if (withdrawalFeePct > 0) {
```

*GitHub* : [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L109), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L111), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L188)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L73), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L181), [184](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L184), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L188), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L192), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L196), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235), [279](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L279), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L358), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L371), [388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L388), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L135), [129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L129)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14), [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14), [20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L20), [20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L20)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L25), [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L89), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L104), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L371), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L371), [501](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L501), [505](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L505), [576](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L576), [677](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L677), [794](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L794), [792](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L792), [805](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L805)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L35), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L113), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L131), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L41), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

### [N-07]<a name="n-07"></a> Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables

If the variable needs to be different based on which class it comes from, a `view`/`pure` _function_ should be used instead (e.g. like [this](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/76eee35971c2541585e05cbf258510dda7b2fbc6/contracts/token/ERC20/extensions/draft-IERC20Permit.sol#L59)).

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
165	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
211	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
241	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
```

*GitHub* : [165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241)


---

	 - contracts/libraries/LibBytes.sol

```solidity
24	            uint64 CR; // bytes8
```

*GitHub* : [24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24)

### [N-08]<a name="n-08"></a> Consider using `delete` rather than assigning zero/false to clear values

The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic

*There are 17 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
191	                            b.dustShortId = b.dustAskId = 0;
...
194	                    incomingBid.ercAmount = 0;
...
158	                    lowestSell.ercAmount = 0;
```

*GitHub* : [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L191), [194](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L194), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L158)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
86	            VaultUser.bridgeCreditSteth = 0;
...
99	                        VaultUser.bridgeCreditReth = 0;
...
56	            VaultUser.bridgeCreditReth = 0;
...
69	                        VaultUser.bridgeCreditSteth = 0;
...
188	                    VaultUserFrom.bridgeCreditReth = 0;
...
189	                    VaultUserFrom.bridgeCreditSteth = 0;
...
176	                    VaultUserFrom.bridgeCreditSteth = 0;
```

*GitHub* : [86](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L86), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L99), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L56), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L69), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L188), [189](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L189), [176](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L176), [167](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L167)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [578](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L578), [612](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L612), [585](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L585)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L138), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L148)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L56)

### [N-09]<a name="n-09"></a> Large numeric literals should use underscores for readability



*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
193	            m = uint256(0.417 ether).div(0.1 ether);
...
189	            m = uint256(0.75 ether).div(0.2 ether);
...
191	                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
...
290	                LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
...
401	        uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);
```

*GitHub* : [193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L193), [189](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L189), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [290](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L290), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)


---

	 - contracts/libraries/LibOrders.sol

```solidity
761	                bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
...
794	            orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
...
792	            orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
...
960	        bool isDiscounted = savedPrice > price.mul(1.01 ether);
...
965	            uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));
```

*GitHub* : [761](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L761), [794](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L794), [792](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L792), [960](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L960), [965](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L965), [965](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L965), [968](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L968)

### [N-10]<a name="n-10"></a> Unused contract variables

Note that there may be cases where a variable appears to be used, but this is only because there are multiple definitions of the varible in different files. In such cases, the variable definition should be moved into a separate file. The instances below are the unused variables.

*There are 13 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [384](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L384)

### [N-11]<a name="n-11"></a> `else`-block not required

One level of nesting can be removed by not having an `else` block when the `if`-block returns, and `if (foo) { return 1; } else { return 2; }` becomes `if (foo) { return 1; } return 2;`

*There are 38 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
106	        if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107	            // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108	            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109	            b.shortHintId = b.shortId = Asset.startingShortId;
110	            b.oraclePrice = LibOracle.getPrice(asset);
111	            return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112	        } else {
113	            // @dev no match, add to market if limit order
114	            LibOrders.addBid(asset, incomingBid, orderHintArray);
115	            return (0, ercAmount);
116	        }
...
150	            if (incomingBid.price >= lowestSell.price) {
151	                // Consider bid filled if only dust amount left
152	                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153	                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
154	                }
155	                matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156	                if (incomingBid.ercAmount > lowestSell.ercAmount) {
157	                    incomingBid.ercAmount -= lowestSell.ercAmount;
158	                    lowestSell.ercAmount = 0;
159	                    if (lowestSell.isShort()) {
160	                        b.matchedShortId = lowestSell.id;
161	                        b.prevShortId = lowestSell.prevId;
162	                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163	                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164	                    } else {
165	                        b.matchedAskId = lowestSell.id;
166	                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167	                        b.askId = lowestSell.nextId;
168	                    }
169	                } else {
170	                    if (incomingBid.ercAmount == lowestSell.ercAmount) {
171	                        if (lowestSell.isShort()) {
172	                            b.matchedShortId = lowestSell.id;
173	                            b.prevShortId = lowestSell.prevId;
174	                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175	                        } else {
176	                            b.matchedAskId = lowestSell.id;
177	                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178	                        }
179	                    } else {
180	                        lowestSell.ercAmount -= incomingBid.ercAmount;
181	                        if (lowestSell.isShort()) {
182	                            b.dustShortId = lowestSell.id;
183	                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184	                            lowestShort.ercAmount = lowestSell.ercAmount;
185	                        } else {
186	                            b.dustAskId = lowestSell.id;
187	                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188	                        }
189	                        // Check reduced dust threshold for existing limit orders
190	                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191	                            b.dustShortId = b.dustAskId = 0;
192	                        }
193	                    }
194	                    incomingBid.ercAmount = 0;
195	                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
196	                }
197	            } else {
198	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199	                    LibOrders.addBid(asset, incomingBid, orderHintArray);
200	                }
201	                return matchIncomingBid(asset, incomingBid, matchTotal, b);
202	            }
...
156	                if (incomingBid.ercAmount > lowestSell.ercAmount) {
157	                    incomingBid.ercAmount -= lowestSell.ercAmount;
158	                    lowestSell.ercAmount = 0;
159	                    if (lowestSell.isShort()) {
160	                        b.matchedShortId = lowestSell.id;
161	                        b.prevShortId = lowestSell.prevId;
162	                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163	                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164	                    } else {
165	                        b.matchedAskId = lowestSell.id;
166	                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167	                        b.askId = lowestSell.nextId;
168	                    }
169	                } else {
170	                    if (incomingBid.ercAmount == lowestSell.ercAmount) {
171	                        if (lowestSell.isShort()) {
172	                            b.matchedShortId = lowestSell.id;
173	                            b.prevShortId = lowestSell.prevId;
174	                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175	                        } else {
176	                            b.matchedAskId = lowestSell.id;
177	                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178	                        }
179	                    } else {
180	                        lowestSell.ercAmount -= incomingBid.ercAmount;
181	                        if (lowestSell.isShort()) {
182	                            b.dustShortId = lowestSell.id;
183	                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184	                            lowestShort.ercAmount = lowestSell.ercAmount;
185	                        } else {
186	                            b.dustAskId = lowestSell.id;
187	                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188	                        }
189	                        // Check reduced dust threshold for existing limit orders
190	                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191	                            b.dustShortId = b.dustAskId = 0;
192	                        }
193	                    }
194	                    incomingBid.ercAmount = 0;
195	                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
196	                }
...
341	        if (b.shortId != C.HEAD) {
342	            STypes.Order storage lowestShort = s.shorts[asset][b.shortId];
343	            STypes.Order storage lowestAsk = s.asks[asset][b.askId];
344	            // @dev Setting lowestSell after comparing short and ask prices
345	            bool noAsks = b.askId == C.TAIL;
346	            bool shortPriceLessThanAskPrice = lowestShort.price < lowestAsk.price;
347	            if (noAsks || shortPriceLessThanAskPrice) {
348	                return lowestShort;
349	            } else {
350	                return lowestAsk;
351	            }
352	        } else if (b.askId != C.TAIL) {
353	            // @dev Handles scenario when there are no shorts
354	            return s.asks[asset][b.askId];
355	        }
...
347	            if (noAsks || shortPriceLessThanAskPrice) {
348	                return lowestShort;
349	            } else {
350	                return lowestAsk;
351	            }
```

*GitHub* : [106..116](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L106-L116), [150..202](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L150-L202), [156..196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L156-L196), [341..355](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L341-L355), [347..351](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L347-L351)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
173	        if (dethTotalNew >= dethTotal) {
174	            // when yield is positive 1 deth = 1 eth
175	            return amount;
176	        } else {
177	            // negative yield means 1 deth < 1 eth
178	            // @dev don't use mulU88 in rare case of overflow
179	            return amount.mul(dethTotalNew).divU88(dethTotal);
180	        }
```

*GitHub* : [173..180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L173-L180)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
38	        if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
39	            return false;
40	        } else {
41	            return true;
42	        }
```

*GitHub* : [38..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L38-L42)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
48	        if (bridgePointer == VAULT.BRIDGE_RETH) {
49	            // Withdraw RETH
50	            creditReth = VaultUser.bridgeCreditReth;
51	            if (creditReth >= amount) {
52	                VaultUser.bridgeCreditReth -= amount;
53	                return 0;
54	            }
55	
56	            VaultUser.bridgeCreditReth = 0;
57	            amount -= creditReth;
58	            creditSteth = VaultUser.bridgeCreditSteth;
59	            if (creditSteth < C.ROUNDING_ZERO) {
60	                // Valid withdraw when no STETH credits
61	                return amount;
62	            } else {
63	                if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64	                    // Can withdraw RETH using STETH credit when STETH bridge is empty
65	                    if (creditSteth >= amount) {
66	                        VaultUser.bridgeCreditSteth -= amount;
67	                        return 0;
68	                    } else {
69	                        VaultUser.bridgeCreditSteth = 0;
70	                        return amount - creditSteth;
71	                    }
72	                } else {
73	                    // Must use available bridge credits on withdrawal
74	                    // @dev Prevents abusing bridge for arbitrage
75	                    revert Errors.MustUseExistingBridgeCredit();
76	                }
77	            }
78	        } else {
79	            // Withdraw STETH
80	            creditSteth = VaultUser.bridgeCreditSteth;
81	            if (creditSteth >= amount) {
82	                VaultUser.bridgeCreditSteth -= amount;
83	                return 0;
84	            }
85	
86	            VaultUser.bridgeCreditSteth = 0;
87	            amount -= creditSteth;
88	            creditReth = VaultUser.bridgeCreditReth;
89	            if (creditReth < C.ROUNDING_ZERO) {
90	                // Valid withdraw when no RETH credits
91	                return amount;
92	            } else {
93	                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94	                    // Can withdraw STETH using RETH credit when RETH bridge is empty
95	                    if (creditReth >= amount) {
96	                        VaultUser.bridgeCreditReth -= amount;
97	                        return 0;
98	                    } else {
99	                        VaultUser.bridgeCreditReth = 0;
100	                        return amount - creditReth;
101	                    }
102	                } else {
103	                    // Must use available bridge credits on withdrawal
104	                    // @dev Prevents abusing bridge for arbitrage
105	                    revert Errors.MustUseExistingBridgeCredit();
106	                }
107	            }
108	        }
...
89	            if (creditReth < C.ROUNDING_ZERO) {
90	                // Valid withdraw when no RETH credits
91	                return amount;
92	            } else {
93	                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94	                    // Can withdraw STETH using RETH credit when RETH bridge is empty
95	                    if (creditReth >= amount) {
96	                        VaultUser.bridgeCreditReth -= amount;
97	                        return 0;
98	                    } else {
99	                        VaultUser.bridgeCreditReth = 0;
100	                        return amount - creditReth;
101	                    }
102	                } else {
103	                    // Must use available bridge credits on withdrawal
104	                    // @dev Prevents abusing bridge for arbitrage
105	                    revert Errors.MustUseExistingBridgeCredit();
106	                }
107	            }
...
95	                    if (creditReth >= amount) {
96	                        VaultUser.bridgeCreditReth -= amount;
97	                        return 0;
98	                    } else {
99	                        VaultUser.bridgeCreditReth = 0;
100	                        return amount - creditReth;
101	                    }
```

*GitHub* : [48..108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L48-L108), [89..107](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L89-L107), [95..101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L95-L101), [59..77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L59-L77), [65..71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L65-L71), [125..140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L125-L140), [131..140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L131-L140)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [28..46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L28-L46), [48..65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L48-L65), [83..114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L83-L114), [85..114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L85-L114), [98..108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L98-L108), [169..173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169-L173)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [241..247](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L241-L247), [243..247](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L243-L247), [272..278](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L272-L278), [274..278](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L274-L278), [381..388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L381-L388), [383..388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L383-L388), [412..416](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L412-L416), [421..427](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L421-L427), [423..427](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L423-L427), [574..624](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L574-L624), [583..615](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L583-L615), [739..779](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L739-L779), [765..775](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L765-L775), [768..775](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L768-L775), [836..842](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L836-L842), [963..979](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L963-L979), [973..978](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L973-L978)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [59..68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L59-L68)

### [N-12]<a name="n-12"></a> Convert simple if-statements to ternary expressions

The code can be made more compact while also increasing readability by converting the following `if`-statements to ternaries (e.g. `foo += (x > y) ? a : b`)

*There are 28 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
170	                    if (incomingBid.ercAmount == lowestSell.ercAmount) {
171	                        if (lowestSell.isShort()) {
172	                            b.matchedShortId = lowestSell.id;
173	                            b.prevShortId = lowestSell.prevId;
174	                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175	                        } else {
176	                            b.matchedAskId = lowestSell.id;
177	                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178	                        }
179	                    } else {
180	                        lowestSell.ercAmount -= incomingBid.ercAmount;
181	                        if (lowestSell.isShort()) {
182	                            b.dustShortId = lowestSell.id;
183	                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184	                            lowestShort.ercAmount = lowestSell.ercAmount;
185	                        } else {
186	                            b.dustAskId = lowestSell.id;
187	                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188	                        }
189	                        // Check reduced dust threshold for existing limit orders
190	                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191	                            b.dustShortId = b.dustAskId = 0;
192	                        }
193	                    }
...
171	                        if (lowestSell.isShort()) {
172	                            b.matchedShortId = lowestSell.id;
173	                            b.prevShortId = lowestSell.prevId;
174	                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175	                        } else {
176	                            b.matchedAskId = lowestSell.id;
177	                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178	                        }
...
159	                    if (lowestSell.isShort()) {
160	                        b.matchedShortId = lowestSell.id;
161	                        b.prevShortId = lowestSell.prevId;
162	                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163	                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164	                    } else {
165	                        b.matchedAskId = lowestSell.id;
166	                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167	                        b.askId = lowestSell.nextId;
168	                    }
...
224	        if (lowestSell.orderType == O.LimitShort) {
225	            // Match short
226	            uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR));
227	            LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);
228	            uint88 shortFillEth = fillEth + colUsed;
229	            matchTotal.shortFillEth += shortFillEth;
230	            // Saves gas when multiple shorts are matched
231	            if (!matchTotal.ratesQueried) {
232	                STypes.Asset storage Asset = s.asset[asset];
233	                matchTotal.ratesQueried = true;
234	                matchTotal.ercDebtRate = Asset.ercDebtRate;
235	                matchTotal.dethYieldRate = s.vault[Asset.vault].dethYieldRate;
236	            }
237	            // Default enum is PartialFill
238	            SR status;
239	            if (incomingBid.ercAmount >= lowestSell.ercAmount) {
240	                status = SR.FullyFilled;
241	            }
242	
243	            LibShortRecord.fillShortRecord(
244	                asset,
245	                lowestSell.addr,
246	                lowestSell.shortRecordId,
247	                status,
248	                shortFillEth,
249	                fillErc,
250	                matchTotal.ercDebtRate,
251	                matchTotal.dethYieldRate
252	            );
253	        } else {
254	            // Match ask
255	            s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth;
256	            matchTotal.askFillErc += fillErc;
257	        }
...
315	            if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
316	                Asset.startingShortId = b.shortId;
317	            } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318	                Asset.startingShortId = b.prevShortId;
319	            } else {
320	                if (b.isMovingFwd) {
321	                    Asset.startingShortId = currentShort.nextId;
322	                } else {
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324	                }
325	            }
...
317	            } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318	                Asset.startingShortId = b.prevShortId;
319	            } else {
320	                if (b.isMovingFwd) {
321	                    Asset.startingShortId = currentShort.nextId;
322	                } else {
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324	                }
325	            }
...
320	                if (b.isMovingFwd) {
321	                    Asset.startingShortId = currentShort.nextId;
322	                } else {
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324	                }
...
392	        if (prevPrice >= b.oraclePrice && !b.isMovingFwd) {
393	            // @dev shortHintId should always be the first thing matched
394	            b.isMovingBack = true;
395	            b.shortId = b.prevShortId;
396	        } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) {
397	            b.firstShortIdBelowOracle = b.prevShortId;
398	            b.shortId = s.shorts[asset][b.shortHintId].nextId;
399	
400	            STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId];
401	            // @dev Only set to true if actually moving forward
402	            if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403	                b.isMovingFwd = true;
404	            }
405	        } else if (b.isMovingFwd) {
406	            b.shortId = lowestSell.nextId;
407	        }
...
396	        } else if (prevPrice < b.oraclePrice && !b.isMovingFwd) {
397	            b.firstShortIdBelowOracle = b.prevShortId;
398	            b.shortId = s.shorts[asset][b.shortHintId].nextId;
399	
400	            STypes.Order storage nextShort = s.shorts[asset][lowestSell.nextId];
401	            // @dev Only set to true if actually moving forward
402	            if (b.shortId != C.HEAD && nextShort.price <= incomingBid.price) {
403	                b.isMovingFwd = true;
404	            }
405	        } else if (b.isMovingFwd) {
406	            b.shortId = lowestSell.nextId;
407	        }
```

*GitHub* : [170..193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L170-L193), [171..178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L171-L178), [159..168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L159-L168), [224..257](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L224-L257), [315..325](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L315-L325), [317..325](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L317-L325), [320..324](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L320-L324), [392..407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L392-L407), [396..407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L396-L407)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
157	        if (bridge == rethBridge) {
158	            vault = VAULT.ONE;
159	        } else if (bridge == stethBridge) {
160	            vault = VAULT.ONE;
161	            bridgePointer = VAULT.BRIDGE_STETH;
162	        } else {
163	            vault = s.bridge[bridge].vault;
164	            if (vault == 0) revert Errors.InvalidBridge();
165	        }
```

*GitHub* : [157..165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L157-L165)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [96..102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L96-L102)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [27..31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L27-L31), [95..101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L95-L101), [65..71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L65-L71)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [90..94](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L90-L94), [111..115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L111-L115), [132..136](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L132-L136), [196..202](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L196-L202), [339..348](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L339-L348), [455..460](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L455-L460), [765..775](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L765-L775), [768..775](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L768-L775), [791..795](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L791-L795), [817..823](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L817-L823), [944..948](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L944-L948), [963..979](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L963-L979)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [41..45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L41-L45)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [36..44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L36-L44)

### [N-13]<a name="n-13"></a> Remaining eth may not be refunded to users

 When a contract function accepts Ethereum and executes a `.call()` or similar function that also forwards Ethereum value, it's important to check for and refund any remaining balance. This is because some of the supplied value may not be used during the call execution due to gas constraints, a revert in the called contract, or simply because not all the value was needed.

If you do not account for this remaining balance, it can become "locked" in the contract. It's crucial to either return the remaining balance to the sender or handle it in a way that ensures it is not permanently stuck. Neglecting to do so can lead to loss of funds and degradation of the contract's reliability. Furthermore, it's good practice to ensure fairness and trust with your users by returning unused funds. 

*There are 1 instance(s) of this issue:*


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
82	    function depositEth(address bridge) external payable nonReentrant {
```

*GitHub* : [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82)

### [N-14]<a name="n-14"></a> External calls in an un-bounded `for`-loop may result in a DOS

Consider limiting the number of iterations in `for`-loops that make external calls

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
79	            p.shorter = proposalInput[i].shorter;
80	            p.shortId = proposalInput[i].shortId;
81	            p.shortOrderId = proposalInput[i].shortOrderId;
82	            // @dev Setting this above _onlyValidShortRecord to allow skipping
83	            STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84	
85	            /// Evaluate proposed shortRecord
86	
87	            if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88	
89	            currentSR.updateErcDebt(p.asset);
90	            p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91	
92	            // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93	            if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94	
95	            // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96	            if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97	                p.amountProposed = currentSR.ercDebt;
98	            } else {
99	                p.amountProposed = redemptionAmount - p.totalAmountProposed;
100	                // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101	                if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102	            }
103	
104	            /// At this point, the shortRecord passes all checks and will be included in the slate
105	
106	            p.previousCR = p.currentCR;
107	
108	            // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109	            // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110	            STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111	            if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112	                if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113	                LibOrders.cancelShort(asset, p.shortOrderId);
114	            }
115	
116	            p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117	            if (p.colRedeemed > currentSR.collateral) {
118	                p.colRedeemed = currentSR.collateral;
119	            }
120	
121	            currentSR.collateral -= p.colRedeemed;
122	            currentSR.ercDebt -= p.amountProposed;
123	
124	            p.totalAmountProposed += p.amountProposed;
125	            p.totalColRedeemed += p.colRedeemed;
126	
127	            // @dev directly write the properties of MTypes.ProposalData into bytes
128	            // instead of usual abi.encode to save on extra zeros being written
129	            slate = bytes.concat(
130	                slate,
131	                bytes20(p.shorter),
132	                bytes1(p.shortId),
133	                bytes8(uint64(p.currentCR)),
134	                bytes11(p.amountProposed),
135	                bytes11(p.colRedeemed)
136	            );
137	
138	            LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139	            p.redemptionCounter++;
140	            if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141	        }
...
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
243	            if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244	                revert Errors.CannotDisputeWithRedeemerProposal();
245	            }
246	        }
...
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
322	            MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323	            totalColRedeemed += currentProposal.colRedeemed;
324	            _claimRemainingCollateral({
325	                asset: asset,
326	                vault: vault,
327	                shorter: currentProposal.shorter,
328	                shortId: currentProposal.shortId
329	            });
330	        }
```

*GitHub* : [78..141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78-L141), [242..246](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242-L246), [321..330](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321-L330)


---

	 - contracts/libraries/LibOrders.sol

```solidity
743	            for (uint256 i = 0; i < shortHintArray.length;) {
744	                shortHintId = shortHintArray[i];
745	                unchecked {
746	                    ++i;
747	                }
748	
749	                STypes.Order storage short = s.shorts[asset][shortHintId];
750	                {
751	                    O shortOrderType = short.orderType;
752	                    if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753	                        continue;
754	                    }
755	                }
756	
757	                uint80 shortPrice = short.price;
758	                uint16 prevId = short.prevId;
759	                uint80 prevShortPrice = s.shorts[asset][prevId].price;
760	                // @dev force hint to be within 0.5% of oraclePrice
761	                bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762	                bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763	                bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764	
765	                if (isExactStartingShort) {
766	                    Asset.startingShortId = shortHintId;
767	                    return;
768	                } else if (startingShortWithinOracleRange) {
769	                    // @dev prevShortPrice >= oraclePrice
770	                    Asset.startingShortId = prevId;
771	                    return;
772	                } else if (allShortUnderOraclePrice) {
773	                    Asset.startingShortId = C.HEAD;
774	                    return;
775	                }
776	            }
```

*GitHub* : [743..776](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743-L776)

### [N-15]<a name="n-15"></a> `constructor` missing zero address check

It is important to ensure that the constructor does not allow zero address to be set.
    This is a common mistake that can lead to loss of funds or redeployment of the contract.

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
30	    constructor(address _dusd) {
```

*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
29	    constructor(address _rethBridge, address _stethBridge) {
```

*GitHub* : [29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
28	    constructor(address _dusd) {
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28)

### [N-16]<a name="n-16"></a> Variable initialization with default value

It's not necessary to initialize a variable with its default value, and it's actually worse in gas terms as it adds an overhead.

*There are 6 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
...
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
...
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
```

*GitHub* : [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321)


---

	 - contracts/libraries/LibBytes.sol

```solidity
18	        for (uint256 i = 0; i < slateLength; i++) {
```

*GitHub* : [18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)


---

	 - contracts/libraries/LibOrders.sol

```solidity
71	        for (uint256 i = 0; i < size; i++) {
...
743	            for (uint256 i = 0; i < shortHintArray.length;) {
```

*GitHub* : [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [743](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743)

### [N-17]<a name="n-17"></a> Large multiples of ten should use scientific notation

Use a scientific notation rather than decimal literals (e.g. `1e6` instead of `1000000`), for better code readability. The same for exponentiation  (e.g. `1e18` instead of `10**18`): although the compiler is capable of optimizing it, it is considered good coding practice to utilize idioms that don't rely on compiler optimization, whenever possible.

*There are 24 instance(s) of this issue:*


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
56	        p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
...
56	        p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
```

*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
140	            m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
...
180	            m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)
```

*GitHub* : [140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L140), [180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
197	            m = uint256(C.ONE_THIRD.div(0.1 ether));
...
198	            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
...
193	            m = uint256(0.417 ether).div(0.1 ether);
...
195	                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
...
191	                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
...
187	                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
```

*GitHub* : [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L197), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L193), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L388), [396](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L396), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L118), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L135), [129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L129)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L104), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [965](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L965)

### [N-18]<a name="n-18"></a> Complex math should be split into multiple steps

Consider splitting long arithmetic calculations into multiple steps to improve the code readability.

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
195	                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
...
191	                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
...
187	                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
...
183	            redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
```

*GitHub* : [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183)

### [N-19]<a name="n-19"></a> Duplicated `require/if` statements should be refactored

These statements should be refactored to a separate function, as there are multiple parts of the codebase that use the same logic, to improve the code readability and reduce code duplication.



*There are 54 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
320	                if (b.isMovingFwd) {
...
405	        } else if (b.isMovingFwd) {
...
142	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
...
159	                    if (lowestSell.isShort()) {
...
171	                        if (lowestSell.isShort()) {
...
181	                        if (lowestSell.isShort()) {
...
198	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
```

*GitHub* : [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L320), [405](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L405), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L142), [159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L159), [171](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L171), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L181), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L198)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
102	        if (dethAmount == 0) revert Errors.ParameterIsZero();
...
134	        if (dethAmount == 0) revert Errors.ParameterIsZero();
```

*GitHub* : [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
235	        if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
```

*GitHub* : [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235), [251](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L251), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L87)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L27), [48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L48), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L51), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L63), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L65), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L81), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L93), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L95), [127](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L127), [150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L150), [25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L25)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L28), [48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L48), [83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L83), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L89), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L104), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L128), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [272](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L272), [274](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L274), [276](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L276), [425](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L425), [565](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L565), [593](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L593), [620](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L620), [635](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L635), [637](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L637), [859](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L859), [873](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L873), [887](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L887), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L155), [157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L157), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L241), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L243), [245](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L245)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L54), [57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L57), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L81), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84)

### [N-20]<a name="n-20"></a> Variable names don't follow the Solidity naming convention

Use `mixedCase` for local and state variables that are not constants, and add a trailing underscore for internal variables. [Documentation](https://docs.soliditylang.org/en/latest/style-guide.html#local-and-state-variable-names)

*There are 37 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
89	        STypes.Asset storage Asset = s.asset[asset];
...
232	                STypes.Asset storage Asset = s.asset[asset];
...
285	        STypes.Asset storage Asset = s.asset[asset];
...
300	            STypes.Vault storage Vault = s.vault[vault];
```

*GitHub* : [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L89), [232](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L232), [285](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L285), [300](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L300)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
44	        STypes.Asset storage Asset = s.asset[asset];
```

*GitHub* : [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L44)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
159	        uint80 _bidPrice = m.oraclePrice.mulU80(m.forcedBidPriceBuffer);
...
165	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
170	            STypes.Asset storage Asset = s.asset[m.asset];
...
210	        STypes.VaultUser storage VaultUser = s.vaultUser[m.vault][msg.sender];
...
211	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
```

*GitHub* : [159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L159), [165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [170](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L170), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L210), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L47), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L93), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L102), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L154), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L182)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L151), [207](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L207), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L255), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L363), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L386)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [23](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L23), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L44), [147](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L147), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L151), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L154)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [670](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L670), [672](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L672), [737](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L737), [812](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L812), [891](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L891), [909](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L909), [958](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L958)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L27), [29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L29), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L112)

### [N-21]<a name="n-21"></a> Contract functions should use an `interface`

All `external`/`public` functions should extend an `interface`. This is useful to make sure that the whole API is extracted.

*There are 17 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
40	    function createBid(
41	        address asset,
42	        uint80 price,
43	        uint88 ercAmount,
44	        bool isMarketOrder,
45	        MTypes.OrderHint[] calldata orderHintArray,
46	        uint16[] calldata shortHintArray
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66	        external
67	        onlyDiamond
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
69	    {
```

*GitHub* : [40..47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65..69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
35	    function createLimitShort(
36	        address asset,
37	        uint80 price,
38	        uint88 ercAmount,
39	        MTypes.OrderHint[] memory orderHintArray,
40	        uint16[] memory shortHintArray,
41	        uint16 shortOrderCR
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

*GitHub* : [35..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
47	    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48	        external
49	        isNotFrozen(asset)
50	        nonReentrant
51	        onlyValidShortRecord(asset, shorter, id)
52	        returns (uint88, uint88)
53	    {
```

*GitHub* : [47..53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
40	    function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
...
51	    function getBridges(uint256 vault) external view returns (address[] memory) {
...
63	    function deposit(address bridge, uint88 amount) external nonReentrant {
...
82	    function depositEth(address bridge) external payable nonReentrant {
...
101	    function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
...
133	    function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
```

*GitHub* : [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L51), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [41..46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87..92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [56..61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224..228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347..351](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351)

### [N-22]<a name="n-22"></a> State variables should include comments

Consider adding some comments on critical state variables to explain what they are supposed to do: this will help for future code reviews.

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
28	    address private immutable dusd;
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
26	    address private immutable rethBridge;
...
27	    address private immutable stethBridge;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
26	    address private immutable dusd;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

### [N-23]<a name="n-23"></a> Consider implementing two-step procedure for updating protocol addresses

A copy-paste error or a typo may end up bricking protocol functionality, or sending tokens to an address with no known private key. Consider implementing a two-step procedure for updating protocol addresses, where the recipient is set as pending, and must 'accept' the assignment by making an affirmative call. A straight forward way of doing this would be to have the target contracts implement [EIP-165](https://eips.ethereum.org/EIPS/eip-165), and to have the 'set' functions ensure that the recipient is of the right interface type.

*There are 6 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
77	    function _createBid(
78	        address sender,
79	        address asset,
80	        uint80 price,
81	        uint88 ercAmount,
82	        bool isMarketOrder,
83	        MTypes.OrderHint[] memory orderHintArray,
84	        uint16[] memory shortHintArray
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [77..85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
122	    function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123	        private
124	        returns (MTypes.PrimaryLiquidation memory)
125	    {
```

*GitHub* : [122..125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
142	    function exitShort(
143	        address asset,
144	        uint8 id,
145	        uint88 buybackAmount,
146	        uint80 price,
147	        uint16[] memory shortHintArray,
148	        uint16 shortOrderId
149	    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

*GitHub* : [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
56	    function proposeRedemption(
57	        address asset,
58	        MTypes.ProposalInput[] calldata proposalInput,
59	        uint88 redemptionAmount,
60	        uint88 maxRedemptionFee
61	    ) external isNotFrozen(asset) nonReentrant {
...
224	    function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225	        external
226	        isNotFrozen(asset)
227	        nonReentrant
228	    {
```

*GitHub* : [56..61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224..228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228)


---

	 - contracts/libraries/LibSRUtil.sol

```solidity
124	    function transferShortRecord(address from, address to, uint40 tokenId) internal {
```

*GitHub* : [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124)

### [N-24]<a name="n-24"></a> Constant redefined elsewhere

Consider defining in only one contract so that values cannot become out of sync when only one location is updated. A [cheap way](https://medium.com/coinmonks/gas-cost-of-solidity-library-functions-dbe0cedd4678) to store constants in a single location is to create an `internal constant` in a `library`. If the variable is a local cache of another contract's value, consider making the cache variable internal or private, which will require external users to query the contract with the source of truth, so that callers don't get out of sync.

*There are 2 instance(s) of this issue:*


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
// @audit Variable redefined in: file `contracts/facets/ExitShortFacet.sol`: `dusd`, file `contracts/facets/PrimaryLiquidationFacet.sol`: `dusd`
26	    address private immutable dusd;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
// @audit Variable redefined in: file `contracts/facets/ExitShortFacet.sol`: `dusd`, file `contracts/facets/PrimaryLiquidationFacet.sol`: `dusd`
28	    address private immutable dusd;
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

### [N-25]<a name="n-25"></a> Function names should use lowerCamelCase

According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#function-names) function names should be in `mixedCase` (lowerCamelCase)

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
31	    function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32	        internal
33	        view
34	        returns (bool)
35	    {
```

*GitHub* : [31..35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35)


---

	 - contracts/libraries/LibOrders.sol

```solidity
35	    function convertCR(uint16 cr) internal pure returns (uint256) {
```

*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35)


---

	 - contracts/libraries/UniswapOracleLibrary.sol

```solidity
47	    function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
48	        internal
49	        view
50	        returns (uint256 amountOut)
51	    {
```

*GitHub* : [47..51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

### [N-26]<a name="n-26"></a> Overflows in unchecked blocks

While integers with a large number of bits are unlikely to overflow on human time scales, it is not strictly correct to use an `unchecked` block around them, because _eventually_ they will overflow, and `unchecked` blocks are meant for cases where it's mathematically impossible for an operation to trigger an overflow (e.g. a prior `require()` statement prevents the overflow case)

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibOrders.sol

```solidity
745	                unchecked {
746	                    ++i;
747	                }
```

*GitHub* : [745..747](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L745-L747)

### [N-27]<a name="n-27"></a> Events may be emitted out of order due to reentrancy

Ensure that events follow the best practice of check-effects-interaction, and are emitted before external calls

*There are 10 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
275	    function matchIncomingBid(
276	        address asset,
277	        STypes.Order memory incomingBid,
278	        MTypes.Match memory matchTotal,
279	        MTypes.BidMatchAlgo memory b
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [275..280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
47	    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48	        external
49	        isNotFrozen(asset)
50	        nonReentrant
51	        onlyValidShortRecord(asset, shorter, id)
52	        returns (uint88, uint88)
53	    {
```

*GitHub* : [47..53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
63	    function deposit(address bridge, uint88 amount) external nonReentrant {
...
82	    function depositEth(address bridge) external payable nonReentrant {
...
101	    function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
...
133	    function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
```

*GitHub* : [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
41	    function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
42	        external
43	        isNotFrozen(asset)
44	        nonReentrant
45	        onlyValidShortRecord(asset, msg.sender, id)
46	    {
...
87	    function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
88	        external
89	        isNotFrozen(asset)
90	        nonReentrant
91	        onlyValidShortRecord(asset, msg.sender, id)
92	    {
...
142	    function exitShort(
143	        address asset,
144	        uint8 id,
145	        uint88 buybackAmount,
146	        uint80 price,
147	        uint16[] memory shortHintArray,
148	        uint16 shortOrderId
149	    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

*GitHub* : [41..46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87..92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
56	    function proposeRedemption(
57	        address asset,
58	        MTypes.ProposalInput[] calldata proposalInput,
59	        uint88 redemptionAmount,
60	        uint88 maxRedemptionFee
61	    ) external isNotFrozen(asset) nonReentrant {
```

*GitHub* : [56..61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61)

### [N-28]<a name="n-28"></a> Function can return unassigned variable

Make sure that functions with a return value always return a valid and assigned value. Even if the default value is as expected, it should be assigned with the default value for code clarity and to reduce confusion.

*There are 2 instance(s) of this issue:*


---

	 - contracts/libraries/LibOracle.sol

```solidity
//@audit Variable `priceInEth` defined here, but never assigned
43	                uint256 priceInEth = uint256(price).div(uint256(basePrice));
...
//@audit Variable `priceInEth` defined here, but never assigned
63	                uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv);
...
//@audit Variable returned here uninitialized
45	                return priceInEth;
...
//@audit Variable returned here uninitialized
64	                return priceInEth;
```

*GitHub* : [45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L45), [64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L64)

### [N-29]<a name="n-29"></a> Simplify complex require statements

Simplifying complex `require` statements with local variables and `if`(or `revert`) statements can improve readability, make debugging easier, and promote modularity and reusability in the code.

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibBytes.sol

```solidity
14	        require(slate.length % 51 == 0, "Invalid data length");
```

*GitHub* : [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14)

### [N-30]<a name="n-30"></a> Events should be emitted before external calls

Ensure that events follow the best practice of check-effects-interaction, and are emitted before external calls

*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
// @audit functions: `updateSellOrdersOnMatch`, `_cancelShort`, `_cancelAsk` called before this event
332	        emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
```

*GitHub* : [332](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L332)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
// @audit functions: `CannotLiquidateSelf`, `TooManyHints`, `checkCancelShortOrder`, `updateOracleAndStartingShortViaTimeBidOnly`, `liquidationCR`, `checkRecoveryModeViolation`, `SufficientCollateral` called before this event
87	        emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
```

*GitHub* : [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L87)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
// @audit functions: `UnderMinimumDeposit`, `deposit`, `addDeth` called before this event
72	        emit Events.Deposit(bridge, msg.sender, dethAmount);
...
// @audit functions: `UnderMinimumDeposit`, `addDeth` called before this event
90	        emit Events.DepositEth(bridge, msg.sender, dethAmount);
...
// @audit functions: `ParameterIsZero`, `assessDeth`, `withdrawalFeePct`, `mulU88`, `removeDeth`, `withdraw` called before this event
122	        emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
...
// @audit functions: `ParameterIsZero`, `withdraw` called before this event
143	        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
```

*GitHub* : [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L72), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L90), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L122), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L143)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
// @audit functions: `updateErcDebt`, `InvalidBuyback`, `burnMsgSenderDebt`, `disburseCollateral`, `deleteShortRecord`, `checkShortMinErc` called before this event
75	        emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);
...
// @audit functions: `updateErcDebt`, `InvalidBuyback`, `InsufficientERCEscrowed`, `disburseCollateral`, `deleteShortRecord`, `checkShortMinErc` called before this event
128	        emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);
...
// @audit functions: `updateOracleAndStartingShortViaTimeBidOnly`, `checkCancelShortOrder`, `updateErcDebt`, `InvalidBuyback`, `mul`, `InsufficientCollateral`, `createForcedBid`, `ExitShortPriceTooLow`, `minShortErc`, `CannotLeaveDustAmount`, `PostExitCRLtPreExitCR`, `disburseCollateral`, `disburseCollateral`, `deleteShortRecord` called before this event
210	        emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
```

*GitHub* : [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L75), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L128), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L210)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit functions: `TooManyProposals`, `minShortErc`, `RedemptionUnderMinShortErc`, `InsufficientERCEscrowed`, `ExistingProposedRedemptions`, `getPrice`, `updateErcDebt`, `getCollateralRatio`, `InvalidShortOrder`, `cancelShort`, `mulU88`, `concat`, `disburseCollateral`, `RedemptionUnderMinShortErc`, `write`, `getOffsetTime`, `div`, `mul`, `div`, `mul`, `div`, `mul`, `div`, `mul`, `div`, `mul`, `getOffsetTime`, `RedemptionFeeTooHigh`, `InsufficientETHEscrowed` called before this event
210	        emit Events.ProposeRedemption(p.asset, msg.sender);
```

*GitHub* : [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L210), [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L333)

### [N-31]<a name="n-31"></a> Contract name does not follow the Solidity Style Guide

According to the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#contract-and-library-names), contracts and libraries should be named using the CapWords style.

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibSRUtil.sol

```solidity
18	library LibSRUtil {
19	    using U88 for uint88;
```

*GitHub* : [18..19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18-L19)

### [N-32]<a name="n-32"></a> Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES

For `immutable` variable names, each word should use all capital letters, with underscores separating each word (UPPER_CASE_WITH_UNDERSCORES)

*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
28	    address private immutable dusd;
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
26	    address private immutable rethBridge;
...
27	    address private immutable stethBridge;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
26	    address private immutable dusd;
```

*GitHub* : [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

### [N-33]<a name="n-33"></a> Contracts should have full test coverage

A 100% test coverage is not foolproof, but it helps immensely in reducing the amount of bugs that may occur.

*There are 1 instance(s) of this issue:*

*GitHub* : [project\2024-03-dittoeth](https://github.com/code-423n4/2024-03-dittoeth//blob/main/#L0)

### [N-34]<a name="n-34"></a> Large or complicated code bases should implement invariant tests

This includes: large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts.

Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold.

Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers may help significantly.

*There are 1 instance(s) of this issue:*

*GitHub* : [project\2024-03-dittoeth](https://github.com/code-423n4/2024-03-dittoeth//blob/main/#L0)

### [N-35]<a name="n-35"></a> Codebase should implement formal verification testing

Formal verification is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification/property/invariant, using formal methods of mathematics.

Some tools that are currently available to perform these tests on smart contracts are [SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html) and [Certora Prover](https://www.certora.com/).

*There are 1 instance(s) of this issue:*

*GitHub* : [project\2024-03-dittoeth](https://github.com/code-423n4/2024-03-dittoeth//blob/main/#L0)

### [N-36]<a name="n-36"></a> Unsafe `uint` to `int` conversion

The `int` type in Solidity uses the [two's complement system](https://en.wikipedia.org/wiki/Two%27s_complement), so it is possible to accidentally overflow a very large `uint` to an `int`, even if they share the same number of bytes (e.g. a `uint256 number > type(uint128).max` will overflow a `int256` cast).

Consider using the [SafeCast](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeCast.sol) library to prevent any overflows.

*There are 2 instance(s) of this issue:*


---

	 - contracts/libraries/UniswapOracleLibrary.sol

```solidity
62	        int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
...
65	        if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
```

*GitHub* : [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

### [N-37]<a name="n-37"></a> State variables not capped at reasonable values

Consider adding minimum/maximum value checks to ensure that the state variables below can never be used to excessively harm users, including via griefing

*There are 7 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
// @audit: parameter `price` is not limited in function body
80	        uint80 price,
```

*GitHub* : [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L80)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
// @audit: parameter `price` is not limited in function body
37	        uint80 price,
```

*GitHub* : [37](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L37)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
// @audit: parameter `amount` is not limited in function body
148	    function maybeUpdateYield(uint256 vault, uint88 amount) private {
...
// @audit: parameter `amount` is not limited in function body
169	    function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```

*GitHub* : [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
// @audit: parameter `price` is not limited in function body
146	        uint80 price,
```

*GitHub* : [146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L146)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
// @audit: parameter `amount` is not limited in function body
39	    function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
```

*GitHub* : [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39)


---

	 - contracts/libraries/UniswapOracleLibrary.sol

```solidity
// @audit: parameter `amountIn` is not limited in function body
47	    function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
```

*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)

### [N-38]<a name="n-38"></a> Consider adding a block/deny-list

Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens

*There are 1 instance(s) of this issue:*


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
18	contract BridgeRouterFacet is Modifiers {
19	    using U256 for uint256;
```

*GitHub* : [18..19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L19)

### [N-39]<a name="n-39"></a> Typos



*There are 2 instance(s) of this issue:*

```bash
error: `forumula` should be `formula`
  --> project\2024-03-dittoeth\contracts\facets\RedemptionFacet.sol:393:34
    |
393 |         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
    |                                  ^^^^^^^^
    |

```

*GitHub* : [1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L1)

```bash
error: `mulitply` should be `multiply`
  --> project\2024-03-dittoeth\contracts\libraries\LibBytes.sol:19:44
   |
19 |             // 32 offset for array length, mulitply by each ProposalData
   |                                            ^^^^^^^^
   |

```

*GitHub* : [1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1)

### [N-40]<a name="n-40"></a> Alternative Solady library can be used instead of OpenZeppelin to save gas

The following OpenZeppelin imports have a [Solady](https://github.com/Vectorized/solady) equivalent, as such they can be used to save GAS as Solady modules have been specifically designed to be as GAS efficient as possible.    

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibOracle.sol

```solidity
 // @audit `IERC20` has Solady alternative
7	import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

*GitHub* : [7](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L7)

### [N-41]<a name="n-41"></a> Setting the `constructor` to `payable`

Saves ~13 gas per instance

*There are 3 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
30	    constructor(address _dusd) {
```

*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
29	    constructor(address _rethBridge, address _stethBridge) {
```

*GitHub* : [29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
28	    constructor(address _dusd) {
```

*GitHub* : [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28)

### [N-42]<a name="n-42"></a> `++i`/`i++` should be `unchecked{++i}`/`unchecked{i++}` when it is not possible for them to overflow, as is the case when used in `for`- and `while`-loops

The `unchecked` keyword is new in solidity version 0.8.0, so this only applies to that version or higher, which these instances are. This saves 30-40 gas [per loop](https://gist.github.com/hrkrshnn/ee8fabd532058307229d65dcd5836ddc#the-increment-in-for-loop-post-condition-can-be-made-unchecked)

*There are 8 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
79	            p.shorter = proposalInput[i].shorter;
80	            p.shortId = proposalInput[i].shortId;
81	            p.shortOrderId = proposalInput[i].shortOrderId;
82	            // @dev Setting this above _onlyValidShortRecord to allow skipping
83	            STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84	
85	            /// Evaluate proposed shortRecord
86	
87	            if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88	
89	            currentSR.updateErcDebt(p.asset);
90	            p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91	
92	            // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93	            if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94	
95	            // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96	            if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97	                p.amountProposed = currentSR.ercDebt;
98	            } else {
99	                p.amountProposed = redemptionAmount - p.totalAmountProposed;
100	                // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101	                if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102	            }
103	
104	            /// At this point, the shortRecord passes all checks and will be included in the slate
105	
106	            p.previousCR = p.currentCR;
107	
108	            // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109	            // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110	            STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111	            if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112	                if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113	                LibOrders.cancelShort(asset, p.shortOrderId);
114	            }
115	
116	            p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117	            if (p.colRedeemed > currentSR.collateral) {
118	                p.colRedeemed = currentSR.collateral;
119	            }
120	
121	            currentSR.collateral -= p.colRedeemed;
122	            currentSR.ercDebt -= p.amountProposed;
123	
124	            p.totalAmountProposed += p.amountProposed;
125	            p.totalColRedeemed += p.colRedeemed;
126	
127	            // @dev directly write the properties of MTypes.ProposalData into bytes
128	            // instead of usual abi.encode to save on extra zeros being written
129	            slate = bytes.concat(
130	                slate,
131	                bytes20(p.shorter),
132	                bytes1(p.shortId),
133	                bytes8(uint64(p.currentCR)),
134	                bytes11(p.amountProposed),
135	                bytes11(p.colRedeemed)
136	            );
137	
138	            LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139	            p.redemptionCounter++;
140	            if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141	        }
...
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
243	            if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244	                revert Errors.CannotDisputeWithRedeemerProposal();
245	            }
246	        }
...
263	            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264	                currentProposal = decodedProposalData[i];
265	
266	                STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267	                currentSR.collateral += currentProposal.colRedeemed;
268	                currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269	
270	                d.incorrectCollateral += currentProposal.colRedeemed;
271	                d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272	            }
...
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
322	            MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323	            totalColRedeemed += currentProposal.colRedeemed;
324	            _claimRemainingCollateral({
325	                asset: asset,
326	                vault: vault,
327	                shorter: currentProposal.shorter,
328	                shortId: currentProposal.shortId
329	            });
330	        }
```

*GitHub* : [78..141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78-L141), [242..246](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242-L246), [263..272](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263-L272), [321..330](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321-L330)


---

	 - contracts/libraries/LibBytes.sol

```solidity
18	        for (uint256 i = 0; i < slateLength; i++) {
19	            // 32 offset for array length, mulitply by each ProposalData
20	            uint256 offset = i * 51 + 32;
21	
22	            address shorter; // bytes20
23	            uint8 shortId; // bytes1
24	            uint64 CR; // bytes8
25	            uint88 ercDebtRedeemed; // bytes11
26	            uint88 colRedeemed; // bytes11
27	
28	            assembly {
29	                // mload works 32 bytes at a time
30	                let fullWord := mload(add(slate, offset))
31	                // read 20 bytes
32	                shorter := shr(96, fullWord) // 0x60 = 96 (256-160)
33	                // read 8 bytes
34	                shortId := and(0xff, shr(88, fullWord)) // 0x58 = 88 (96-8), mask of bytes1 = 0xff * 1
35	                // read 64 bytes
36	                CR := and(0xffffffffffffffff, shr(24, fullWord)) // 0x18 = 24 (88-64), mask of bytes8 = 0xff * 8
37	
38	                fullWord := mload(add(slate, add(offset, 29))) // (29 offset)
39	                // read 88 bytes
40	                ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
41	                // read 88 bytes
42	                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
43	            }
44	
45	            data[i] = MTypes.ProposalData({
46	                shorter: shorter,
47	                shortId: shortId,
48	                CR: CR,
49	                ercDebtRedeemed: ercDebtRedeemed,
50	                colRedeemed: colRedeemed
51	            });
52	        }
```

*GitHub* : [18..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18-L52)


---

	 - contracts/libraries/LibOrders.sol

```solidity
63	        while (currentId != C.TAIL) {
64	            size++;
65	            currentId = orders[asset][currentId].nextId;
66	        }
...
71	        for (uint256 i = 0; i < size; i++) {
72	            list[i] = orders[asset][currentId];
73	            currentId = orders[asset][currentId].nextId;
74	        }
...
832	        for (uint256 i; i < orderHintArray.length; i++) {
833	            MTypes.OrderHint memory orderHint = orderHintArray[i];
834	            STypes.Order storage order = orders[asset][orderHint.hintId];
835	            O hintOrderType = order.orderType;
836	            if (hintOrderType == O.Cancelled || hintOrderType == O.Matched) {
837	                continue;
838	            } else if (order.creationTime == orderHint.creationTime) {
839	                return orderHint.hintId;
840	            } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
841	                anyOrderHintPrevMatched = true;
842	            }
843	        }
```

*GitHub* : [63..66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L63-L66), [71..74](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71-L74), [832..843](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832-L843)

### [N-43]<a name="n-43"></a> `Internal` functions only called once can be inlined to save gas



*There are 14 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
382	    function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383	        internal
384	        returns (uint88 redemptionFee)
385	    {
```

*GitHub* : [382..385](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)


---

	 - contracts/libraries/LibOracle.sol

```solidity
19	    function getOraclePrice(address asset) internal view returns (uint256) {
...
156	    function getTime(address asset) internal view returns (uint256 creationTime) {
```

*GitHub* : [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156)


---

	 - contracts/libraries/LibOrders.sol

```solidity
40	    function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {
...
103	    function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
...
128	    function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
...
231	    function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
232	        internal
233	        view
234	        returns (int256 direction)
235	    {
...
362	    function findPrevOfIncomingId(
363	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364	        address asset,
365	        STypes.Order memory incomingOrder,
366	        uint16 hintId
367	    ) internal view returns (uint16) {
...
705	    function matchHighestBid(
706	        STypes.Order memory incomingSell,
707	        STypes.Order memory highestBid,
708	        address asset,
709	        MTypes.Match memory matchTotal
710	    ) internal {
...
810	    function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
```

*GitHub* : [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [231..235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [362..367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [705..710](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L705-L710), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [28..32](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28-L32)

### [N-44]<a name="n-44"></a> Usage of `uint`/`int` smaller than 32 bytes (256 bits) incurs overhead

When using elements that are smaller than 32 bytes, your contract’s gas usage may be higher. This is because the EVM operates on 32 bytes at a time. Therefore, if the element is smaller than that, the EVM must use more operations in order to reduce the size of the element from 32 bytes to the desired size.

Each operation involving a uint8 costs an extra 22-28 gas (depending on whether the other operand is also a variable of type uint8) as compared to ones involving uint256, due to the compiler having to clear the higher bits of the memory word before operating on the uint8, as well as the associated stack operations of doing so. Use a larger size then downcast where needed.

https://docs.soliditylang.org/en/v0.8.11/internals/layout_in_storage.html

Use a larger size then downcast where needed.

*There are 191 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
42	        uint80 price,
...
43	        uint88 ercAmount,
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
...
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
80	        uint80 price,
...
81	        uint88 ercAmount,
```

*GitHub* : [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L42), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L43), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L80), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L81), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [221](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L221), [222](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L222), [226](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L226), [228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L228), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [391](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L391)


---

	 - contracts/facets/ShortOrdersFacet.sol


*GitHub* : [37](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L37), [38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L38), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L41)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol


*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L52), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L52), [97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L97), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L98), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L156), [159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L159), [171](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L171), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L181), [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L213), [214](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L214), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L242)


---

	 - contracts/facets/BridgeRouterFacet.sol


*GitHub* : [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87), [106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L106), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L108), [119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L119), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L137), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L149), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [171](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L171), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L59), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L111), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L144), [145](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L145), [146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L146), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L148)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L154), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L204), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L59), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L60), [293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L293), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L320), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347), [373](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L373), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368), [387](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L387), [392](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L392), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382), [384](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L384)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L46), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L47), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L41), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L152), [153](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L153), [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L181), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [23](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L23), [24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24), [25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L25), [26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L26), [11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L36), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27), [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L53), [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L71), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L118), [119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L119), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L44), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L60), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L84), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L89), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L99), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L105), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L110), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L130), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L131), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L142), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L182), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L183), [186](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L186), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L187), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L177), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L263), [265](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L265), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L291), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [315](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L315), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [323](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L323), [324](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L324), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L368), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L386), [366](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L366), [367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L367), [405](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L405), [407](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L407), [449](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L449), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [444](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L444), [447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L447), [477](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L477), [517](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L517), [540](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L540), [535](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L535), [536](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L536), [563](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L563), [712](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L712), [713](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L713), [742](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L742), [757](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L757), [758](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L758), [759](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L759), [830](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L830), [862](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L862), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [889](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L889), [894](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L894), [903](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L903), [907](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L907), [911](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L911), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [34](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L34), [22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22), [22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L142), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L155), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L156)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [33](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L33), [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28), [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28), [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L61), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)

### [N-45]<a name="n-45"></a> `>=` costs less gas than `>`

The compiler uses opcodes `GT` and `ISZERO` for solidity code that uses `>`, but only requires LT for `>=`, which saves 3 gas. Similarly for `<=`.

*There are 26 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
292	        if (b.dustAskId > 0) {
...
294	        } else if (b.dustShortId > 0) {
...
299	        if (matchTotal.shortFillEth > 0) {
```

*GitHub* : [292](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L292), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L294), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L299)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
56	        p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
```

*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
56	        if (shortHintArray.length > 10) revert Errors.TooManyHints();
```

*GitHub* : [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
109	            if (dethAssessable > 0) {
...
111	                if (withdrawalFeePct > 0) {
```

*GitHub* : [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L109), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L111)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
181	        if (p.currentCR > 1.7 ether) {
...
184	        } else if (p.currentCR > 1.5 ether) {
...
188	        } else if (p.currentCR > 1.3 ether) {
```

*GitHub* : [181](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L181), [184](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L184), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L188), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L192), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L196), [279](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L279), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L104), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [794](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L794), [792](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L792)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L35), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L113), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

### [N-46]<a name="n-46"></a> Using `storage` instead of `memory` for structs/arrays saves gas

When fetching data from a storage location, assigning the data to a `memory` variable causes all fields of the struct/array to be read from storage, which incurs a Gcoldsload (**2100 gas**) for *each* field of the struct/array. If the fields are read from the new memory variable, they incur an additional `MLOAD` rather than a cheap stack read. Instead of declearing the variable with the `memory` keyword, declaring the variable with the `storage` keyword and caching any fields that need to be re-read in stack variables, will be much cheaper, only incuring the Gcoldsload for the fields actually read. The only time it makes sense to read the whole struct/array into a `memory` variable, is if the full struct/array is being returned by the function, is being passed to a function that requires `memory`, or if the array/struct is being read from another `memory` array/struct

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibOrders.sol

```solidity
573	            STypes.Order memory highestBid = s.bids[asset][startingId];
```

*GitHub* : [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573)

### [N-47]<a name="n-47"></a> Stack variable used as a cheaper cache for a state variable is only used once

If the variable is only accessed once, it's cheaper to use the state variable directly that one time, and save the 3 gas the extra stack assignment would spend

*There are 47 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
65	    function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66	        external
67	        onlyDiamond
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
69	    {
...
130	    function bidMatchAlgo(
131	        address asset,
132	        STypes.Order memory incomingBid,
133	        MTypes.OrderHint[] memory orderHintArray,
134	        MTypes.BidMatchAlgo memory b
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
340	    function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
...
358	    function _shortDirectionHandler(
359	        address asset,
360	        STypes.Order memory lowestSell,
361	        STypes.Order memory incomingBid,
362	        MTypes.BidMatchAlgo memory b
363	    ) private view {
```

*GitHub* : [65..69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69), [130..135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358..363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
154	    function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private {
```

*GitHub* : [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
63	    function deposit(address bridge, uint88 amount) external nonReentrant {
...
82	    function depositEth(address bridge) external payable nonReentrant {
...
101	    function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
...
133	    function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
```

*GitHub* : [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
41	    function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
42	        external
43	        isNotFrozen(asset)
44	        nonReentrant
45	        onlyValidShortRecord(asset, msg.sender, id)
46	    {
```

*GitHub* : [41..46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87..92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [224..228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347..351](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351), [382..385](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [39..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69..75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [117..124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117-L124), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [173..178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [362..367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [440..447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499), [668](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L668), [705..710](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L705-L710), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [22..24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [102..106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)

### [N-48]<a name="n-48"></a> Newer versions of solidity are more gas efficient

The solidity language continues to pursue more efficient gas optimization schemes. Adopting a [newer version of solidity](https://github.com/ethereum/solc-js/tags) can be more gas efficient.

solc-version = "0.8.21"

proof: 
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/foundry.toml#L2


*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L2)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L2)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L2)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L2)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L2)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L2)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L2)


---

	 - contracts/libraries/LibBytes.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L2)


---

	 - contracts/libraries/LibOracle.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L2)


---

	 - contracts/libraries/LibOrders.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L2)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L2)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L2)

### [N-49]<a name="n-49"></a> Consider activating `via-ir` for deploying

The IR-based code generator was developed to make code generation more performant by enabling optimization passes that can be applied across functions.

It is possible to activate the IR-based code generator through the command line by using the flag `--via-ir` or by including the option `{"viaIR": true}`.

Keep in mind that compiling with this option may take longer. However, you can simply test it before deploying your code. If you find that it provides better performance, you can add the `--via-ir` flag to your deploy command.

*There are 1 instance(s) of this issue:*

*GitHub* : [project\2024-03-dittoeth](https://github.com/code-423n4/2024-03-dittoeth//blob/main/#L0)

### [N-50]<a name="n-50"></a> Function calls should be cached instead of re-calling the function

Consider caching the result instead of re-calling the function when possible. Note: this also includes casts, which cost between 42-46 gas, depending on the type.

*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
77	    function _createBid(
78	        address sender,
79	        address asset,
80	        uint80 price,
81	        uint88 ercAmount,
82	        bool isMarketOrder,
83	        MTypes.OrderHint[] memory orderHintArray,
84	        uint16[] memory shortHintArray
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
130	    function bidMatchAlgo(
131	        address asset,
132	        STypes.Order memory incomingBid,
133	        MTypes.OrderHint[] memory orderHintArray,
134	        MTypes.BidMatchAlgo memory b
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [77..85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130..135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
35	    function createLimitShort(
36	        address asset,
37	        uint80 price,
38	        uint88 ercAmount,
39	        MTypes.OrderHint[] memory orderHintArray,
40	        uint16[] memory shortHintArray,
41	        uint16 shortOrderCR
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

*GitHub* : [35..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
240	    function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {
```

*GitHub* : [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
142	    function exitShort(
143	        address asset,
144	        uint8 id,
145	        uint88 buybackAmount,
146	        uint80 price,
147	        uint16[] memory shortHintArray,
148	        uint16 shortOrderId
149	    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

*GitHub* : [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
56	    function proposeRedemption(
57	        address asset,
58	        MTypes.ProposalInput[] calldata proposalInput,
59	        uint88 redemptionAmount,
60	        uint88 maxRedemptionFee
61	    ) external isNotFrozen(asset) nonReentrant {
```

*GitHub* : [56..61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
144	    function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
```

*GitHub* : [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144)


---

	 - contracts/libraries/LibOracle.sol

```solidity
19	    function getOraclePrice(address asset) internal view returns (uint256) {
```

*GitHub* : [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19)


---

	 - contracts/libraries/LibOrders.sol

```solidity
556	    function sellMatchAlgo(
557	        address asset,
558	        STypes.Order memory incomingAsk,
559	        MTypes.OrderHint[] memory orderHintArray,
560	        uint256 minAskEth
561	    ) internal {
...
783	    function updateOracleAndStartingShortViaThreshold(
784	        address asset,
785	        uint256 savedPrice,
786	        STypes.Order memory incomingOrder,
787	        uint16[] memory shortHintArray
788	    ) internal {
```

*GitHub* : [556..561](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [783..788](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783-L788), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [49..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52)

### [N-51]<a name="n-51"></a> Consider pre-calculating the address of `address(this)`

It can be more gas-efficient to use a hardcoded address instead of the `address(this)` expression, especially if you need to use the same address multiple times in your contract.

The reason for this, is that using `address(this)` requires an additional `EXTCODESIZE` operation to retrieve the contract’s address from its bytecode, which can increase the gas cost of your contract. By pre-calculating and using a hardcoded address, you can avoid this additional operation and reduce the overall gas cost of your contract.

Save 100 - 2600 Gas

*There are 18 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
295	            IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
...
293	            IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
```

*GitHub* : [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L295), [293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L293)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
165	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
188	            IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
...
188	            IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
...
193	        s.assetUser[m.asset][address(this)].ercEscrowed -= m.ercDebtMatched;
...
211	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
241	        STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
...
263	            if (m.loseCollateral && m.shorter != address(this)) {
...
269	                    address(this),
```

*GitHub* : [165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188), [193](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L193), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L263), [269](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L269), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L280)


---

	 - contracts/facets/BridgeRouterFacet.sol


*GitHub* : [114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L114), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L139)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L187)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [982](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L982)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L44)

### [N-52]<a name="n-52"></a> Optimize Zero Checks Using Assembly

The usage of inline assembly to check if variable is the zero can save gas compared to traditional `require` or `if` statement checks. 

The assembly check uses the `extcodesize` operation which is generally cheaper in terms of gas.

[More information can be found here.](https://medium.com/@kalexotsu/solidity-assembly-checking-if-an-address-is-0-efficiently-d2bfe071331)

*There are 51 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
152	                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
...
281	        if (matchTotal.fillEth == 0) {
...
292	        if (b.dustAskId > 0) {
...
294	        } else if (b.dustShortId > 0) {
...
299	        if (matchTotal.shortFillEth > 0) {
```

*GitHub* : [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L152), [281](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L281), [292](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L292), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L294), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L299)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
102	        if (dethAmount == 0) revert Errors.ParameterIsZero();
...
109	            if (dethAssessable > 0) {
...
111	                if (withdrawalFeePct > 0) {
...
134	        if (dethAmount == 0) revert Errors.ParameterIsZero();
...
164	            if (vault == 0) revert Errors.InvalidBridge();
```

*GitHub* : [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L109), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L111), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L188)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L73), [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235), [279](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L279), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L371), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L25), [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L89), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L371), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L371), [501](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L501), [505](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L505), [576](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L576), [677](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L677)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L35), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L113), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L131), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

### [N-53]<a name="n-53"></a> Consider Caching Multiple Accesses to Mappings/Arrays

Leveraging a local variable to cache these values when accessed more than once can yield a gas saving of approximately 42 units per access. This reduction is attributed to eliminating the need for recalculating the key's keccak256 hash (which costs Gkeccak256 - 30 gas) and the associated stack operations. For arrays, this also prevents the overhead of re-computing offsets in memory or calldata.

*There are 51 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
77	    function _createBid(
78	        address sender,
79	        address asset,
80	        uint80 price,
81	        uint88 ercAmount,
82	        bool isMarketOrder,
83	        MTypes.OrderHint[] memory orderHintArray,
84	        uint16[] memory shortHintArray
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
130	    function bidMatchAlgo(
131	        address asset,
132	        STypes.Order memory incomingBid,
133	        MTypes.OrderHint[] memory orderHintArray,
134	        MTypes.BidMatchAlgo memory b
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
215	    function matchlowestSell(
216	        address asset,
217	        STypes.Order memory lowestSell,
218	        STypes.Order memory incomingBid,
219	        MTypes.Match memory matchTotal
220	    ) private {
...
275	    function matchIncomingBid(
276	        address asset,
277	        STypes.Order memory incomingBid,
278	        MTypes.Match memory matchTotal,
279	        MTypes.BidMatchAlgo memory b
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
340	    function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
...
358	    function _shortDirectionHandler(
359	        address asset,
360	        STypes.Order memory lowestSell,
361	        STypes.Order memory incomingBid,
362	        MTypes.BidMatchAlgo memory b
363	    ) private view {
```

*GitHub* : [77..85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130..135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215..220](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275..280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358..363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
35	    function createLimitShort(
36	        address asset,
37	        uint80 price,
38	        uint88 ercAmount,
39	        MTypes.OrderHint[] memory orderHintArray,
40	        uint16[] memory shortHintArray,
41	        uint16 shortOrderCR
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

*GitHub* : [35..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35-L42)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
47	    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48	        external
49	        isNotFrozen(asset)
50	        nonReentrant
51	        onlyValidShortRecord(asset, shorter, id)
52	        returns (uint88, uint88)
53	    {
...
96	    function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {
...
122	    function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123	        private
124	        returns (MTypes.PrimaryLiquidation memory)
125	    {
```

*GitHub* : [47..53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53), [96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [122..125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154), [209](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L209), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [41..46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87..92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142..149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [56..61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224..228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347..351](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [55..59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [173..178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [231..235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [260..266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [320..326](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320-L326), [362..367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [440..447](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [474..479](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L474-L479), [499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499), [532..537](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L532-L537), [556..561](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [652](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L652), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [22..24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72..75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [47..51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

### [N-54]<a name="n-54"></a> Optimize Gas by Using Do-While Loops

Using `do-while` loops instead of `for` loops can be more gas-efficient. 
Even if you add an `if` condition to account for the case where the loop doesn't execute at all, a `do-while` loop can still be cheaper in terms of gas.

*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
139	        while (true) {
140	            // @dev Handles scenario when no sells left after partial fill
141	            if (b.askId == C.TAIL && b.shortId == C.TAIL) {
142	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143	                    LibOrders.addBid(asset, incomingBid, orderHintArray);
144	                }
145	                return matchIncomingBid(asset, incomingBid, matchTotal, b);
146	            }
147	
148	            STypes.Order memory lowestSell = _getLowestSell(asset, b);
149	
150	            if (incomingBid.price >= lowestSell.price) {
151	                // Consider bid filled if only dust amount left
152	                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153	                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
154	                }
155	                matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156	                if (incomingBid.ercAmount > lowestSell.ercAmount) {
157	                    incomingBid.ercAmount -= lowestSell.ercAmount;
158	                    lowestSell.ercAmount = 0;
159	                    if (lowestSell.isShort()) {
160	                        b.matchedShortId = lowestSell.id;
161	                        b.prevShortId = lowestSell.prevId;
162	                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163	                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164	                    } else {
165	                        b.matchedAskId = lowestSell.id;
166	                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167	                        b.askId = lowestSell.nextId;
168	                    }
169	                } else {
170	                    if (incomingBid.ercAmount == lowestSell.ercAmount) {
171	                        if (lowestSell.isShort()) {
172	                            b.matchedShortId = lowestSell.id;
173	                            b.prevShortId = lowestSell.prevId;
174	                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175	                        } else {
176	                            b.matchedAskId = lowestSell.id;
177	                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178	                        }
179	                    } else {
180	                        lowestSell.ercAmount -= incomingBid.ercAmount;
181	                        if (lowestSell.isShort()) {
182	                            b.dustShortId = lowestSell.id;
183	                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184	                            lowestShort.ercAmount = lowestSell.ercAmount;
185	                        } else {
186	                            b.dustAskId = lowestSell.id;
187	                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188	                        }
189	                        // Check reduced dust threshold for existing limit orders
190	                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191	                            b.dustShortId = b.dustAskId = 0;
192	                        }
193	                    }
194	                    incomingBid.ercAmount = 0;
195	                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
196	                }
197	            } else {
198	                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199	                    LibOrders.addBid(asset, incomingBid, orderHintArray);
200	                }
201	                return matchIncomingBid(asset, incomingBid, matchTotal, b);
202	            }
203	        }
```

*GitHub* : [139..203](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L139-L203)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
79	            p.shorter = proposalInput[i].shorter;
80	            p.shortId = proposalInput[i].shortId;
81	            p.shortOrderId = proposalInput[i].shortOrderId;
82	            // @dev Setting this above _onlyValidShortRecord to allow skipping
83	            STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84	
85	            /// Evaluate proposed shortRecord
86	
87	            if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88	
89	            currentSR.updateErcDebt(p.asset);
90	            p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91	
92	            // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93	            if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94	
95	            // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96	            if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97	                p.amountProposed = currentSR.ercDebt;
98	            } else {
99	                p.amountProposed = redemptionAmount - p.totalAmountProposed;
100	                // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101	                if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102	            }
103	
104	            /// At this point, the shortRecord passes all checks and will be included in the slate
105	
106	            p.previousCR = p.currentCR;
107	
108	            // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109	            // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110	            STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111	            if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112	                if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113	                LibOrders.cancelShort(asset, p.shortOrderId);
114	            }
115	
116	            p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117	            if (p.colRedeemed > currentSR.collateral) {
118	                p.colRedeemed = currentSR.collateral;
119	            }
120	
121	            currentSR.collateral -= p.colRedeemed;
122	            currentSR.ercDebt -= p.amountProposed;
123	
124	            p.totalAmountProposed += p.amountProposed;
125	            p.totalColRedeemed += p.colRedeemed;
126	
127	            // @dev directly write the properties of MTypes.ProposalData into bytes
128	            // instead of usual abi.encode to save on extra zeros being written
129	            slate = bytes.concat(
130	                slate,
131	                bytes20(p.shorter),
132	                bytes1(p.shortId),
133	                bytes8(uint64(p.currentCR)),
134	                bytes11(p.amountProposed),
135	                bytes11(p.colRedeemed)
136	            );
137	
138	            LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139	            p.redemptionCounter++;
140	            if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141	        }
...
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
243	            if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244	                revert Errors.CannotDisputeWithRedeemerProposal();
245	            }
246	        }
...
263	            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264	                currentProposal = decodedProposalData[i];
265	
266	                STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267	                currentSR.collateral += currentProposal.colRedeemed;
268	                currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269	
270	                d.incorrectCollateral += currentProposal.colRedeemed;
271	                d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272	            }
...
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
322	            MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323	            totalColRedeemed += currentProposal.colRedeemed;
324	            _claimRemainingCollateral({
325	                asset: asset,
326	                vault: vault,
327	                shorter: currentProposal.shorter,
328	                shortId: currentProposal.shortId
329	            });
330	        }
```

*GitHub* : [78..141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78-L141), [242..246](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242-L246), [263..272](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263-L272), [321..330](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321-L330)


---

	 - contracts/libraries/LibBytes.sol

```solidity
18	        for (uint256 i = 0; i < slateLength; i++) {
19	            // 32 offset for array length, mulitply by each ProposalData
20	            uint256 offset = i * 51 + 32;
21	
22	            address shorter; // bytes20
23	            uint8 shortId; // bytes1
24	            uint64 CR; // bytes8
25	            uint88 ercDebtRedeemed; // bytes11
26	            uint88 colRedeemed; // bytes11
27	
28	            assembly {
29	                // mload works 32 bytes at a time
30	                let fullWord := mload(add(slate, offset))
31	                // read 20 bytes
32	                shorter := shr(96, fullWord) // 0x60 = 96 (256-160)
33	                // read 8 bytes
34	                shortId := and(0xff, shr(88, fullWord)) // 0x58 = 88 (96-8), mask of bytes1 = 0xff * 1
35	                // read 64 bytes
36	                CR := and(0xffffffffffffffff, shr(24, fullWord)) // 0x18 = 24 (88-64), mask of bytes8 = 0xff * 8
37	
38	                fullWord := mload(add(slate, add(offset, 29))) // (29 offset)
39	                // read 88 bytes
40	                ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
41	                // read 88 bytes
42	                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
43	            }
44	
45	            data[i] = MTypes.ProposalData({
46	                shorter: shorter,
47	                shortId: shortId,
48	                CR: CR,
49	                ercDebtRedeemed: ercDebtRedeemed,
50	                colRedeemed: colRedeemed
51	            });
52	        }
```

*GitHub* : [18..52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18-L52)


---

	 - contracts/libraries/LibOrders.sol

```solidity
63	        while (currentId != C.TAIL) {
64	            size++;
65	            currentId = orders[asset][currentId].nextId;
66	        }
...
71	        for (uint256 i = 0; i < size; i++) {
72	            list[i] = orders[asset][currentId];
73	            currentId = orders[asset][currentId].nextId;
74	        }
...
448	        while (true) {
449	            uint16 nextId = orders[asset][hintId].nextId;
450	
451	            if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
452	                return hintId;
453	            }
454	
455	            if (direction == C.PREV) {
456	                uint16 prevId = orders[asset][hintId].prevId;
457	                hintId = prevId;
458	            } else {
459	                hintId = nextId;
460	            }
461	        }
...
572	        while (true) {
573	            STypes.Order memory highestBid = s.bids[asset][startingId];
574	            if (incomingAsk.price <= highestBid.price) {
575	                // Consider ask filled if only dust amount left
576	                if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577	                    updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578	                    incomingAsk.ercAmount = 0;
579	                    matchIncomingSell(asset, incomingAsk, matchTotal);
580	                    return;
581	                }
582	                matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
583	                if (incomingAsk.ercAmount > highestBid.ercAmount) {
584	                    incomingAsk.ercAmount -= highestBid.ercAmount;
585	                    highestBid.ercAmount = 0;
586	                    matchOrder(s.bids, asset, highestBid.id);
587	
588	                    // loop
589	                    startingId = highestBid.nextId;
590	                    if (startingId == C.TAIL) {
591	                        matchIncomingSell(asset, incomingAsk, matchTotal);
592	
593	                        if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594	                            addSellOrder(incomingAsk, asset, orderHintArray);
595	                        }
596	                        s.bids[asset][C.HEAD].nextId = C.TAIL;
597	                        return;
598	                    }
599	                } else {
600	                    if (incomingAsk.ercAmount == highestBid.ercAmount) {
601	                        matchOrder(s.bids, asset, highestBid.id);
602	                        updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603	                    } else {
604	                        highestBid.ercAmount -= incomingAsk.ercAmount;
605	                        s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606	                        updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607	                        // Check reduced dust threshold for existing limit orders
608	                        if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609	                            cancelBid(asset, highestBid.id);
610	                        }
611	                    }
612	                    incomingAsk.ercAmount = 0;
613	                    matchIncomingSell(asset, incomingAsk, matchTotal);
614	                    return;
615	                }
616	            } else {
617	                updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
618	                matchIncomingSell(asset, incomingAsk, matchTotal);
619	
620	                if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621	                    addSellOrder(incomingAsk, asset, orderHintArray);
622	                }
623	                return;
624	            }
625	        }
```

*GitHub* : [63..66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L63-L66), [71..74](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71-L74), [448..461](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L448-L461), [572..625](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L572-L625), [743..776](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743-L776), [832..843](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832-L843)

### [N-55]<a name="n-55"></a> Use Assembly for Efficient Event Emission

To efficiently emit events, consider utilizing assembly by making use of scratch space and the free memory pointer.
This approach can potentially avoid the costs associated with memory expansion.

However, it's crucial to cache and restore the free memory pointer for safe optimization.
Good examples of such practices can be found in well-optimized [Solady's codebases](https://github.com/Vectorized/solady/blob/main/src/tokens/ERC1155.sol#L167).
Please review your code and consider the potential gas savings of this approach.

*There are 15 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
332	        emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
```

*GitHub* : [332](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L332)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
87	        emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
```

*GitHub* : [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L87)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
72	        emit Events.Deposit(bridge, msg.sender, dethAmount);
...
90	        emit Events.DepositEth(bridge, msg.sender, dethAmount);
...
122	        emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
...
143	        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
```

*GitHub* : [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L72), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L90), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L122), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L143)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
75	        emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);
...
128	        emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);
...
210	        emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
```

*GitHub* : [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L75), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L128), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L210)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
210	        emit Events.ProposeRedemption(p.asset, msg.sender);
```

*GitHub* : [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L210), [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L333)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [218](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L218), [301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301), [631..633](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L631-L633)

### [N-56]<a name="n-56"></a> Optimize External Calls with Assembly for Memory Efficiency

Using interfaces to make external contract calls in Solidity is convenient but can be inefficient in terms of memory utilization.
Each such call involves creating a new memory location to store the data being passed, thus incurring memory expansion costs. 

Inline assembly allows for optimized memory usage by re-using already allocated memory spaces or using the scratch space for smaller datasets.
This can result in notable gas savings, especially for contracts that make frequent external calls.

Additionally, using inline assembly enables important safety checks like verifying if the target address has code deployed to it using `extcodesize(addr)` before making the call, mitigating risks associated with contract interactions.

*There are 22 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
295	            IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
...
293	            IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
```

*GitHub* : [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L295), [293](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L293)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
188	            IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
```

*GitHub* : [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
68	        uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast)
...
87	        uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
...
87	        uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
...
121	        IBridge(bridge).withdraw(msg.sender, ethAmount);
...
142	        IBridge(bridge).withdraw(msg.sender, ethAmount);
```

*GitHub* : [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87), [121](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L121), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L142)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
187	            IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
```

*GitHub* : [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L187)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
93	                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
```

*GitHub* : [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L93), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L63), [119](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L119), [123](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L123)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L42), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L59), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L103), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L87), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133), [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L138)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [982](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L982)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L59)

### [N-57]<a name="n-57"></a> Consider Using Solady's Gas Optimized Lib for Math

Utilizing gas-optimized math functions from libraries like [Solady](https://github.com/Vectorized/solady/blob/main/src/utils/FixedPointMathLib.sol) can lead to more efficient smart contracts.
This is particularly beneficial in contracts where these operations are frequently used.

*There are 25 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
199	        m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast)
```

*GitHub* : [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L199)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
198	            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
...
198	            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
...
195	                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
...
195	                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
...
191	                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
...
191	                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
...
187	                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
...
187	                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
...
183	            redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
```

*GitHub* : [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [388](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L388)


---

	 - contracts/libraries/LibBytes.sol


*GitHub* : [20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L20)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L30), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L63), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [37](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L37), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62)

### [N-58]<a name="n-58"></a> Trade-offs Between Modifiers and Internal Functions

In Solidity, both internal functions and modifiers are used to refactor and manage code, but they come with their own trade-offs, especially in terms of gas cost and flexibility.

#### Modifiers:
- Less runtime gas cost (saves around 24 gas per function call).
- Increases deployment gas cost due to repetitive code.
- Can only be executed at the start or end of a function.

#### Internal Functions:
- Lower deployment cost.
- Can be executed at any point in a function.
- Slightly higher runtime gas cost (24 gas) due to the need to jump to the function's location in bytecode.

#### Recommendations:
- Use modifiers for high-frequency functions where runtime gas cost matters the most.
- Use internal functions where the priority is reducing deployment gas cost or when you need more flexibility in the function's logic.

Example analysis shows that using modifiers can increase deployment costs by over 35k gas but save 24 gas per function call during runtime. Choose wisely based on your specific use case.

*There are 32 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
67	        onlyDiamond
```

*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L67)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
...
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
...
42	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

*GitHub* : [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L42), [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L42), [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L42)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
49	        isNotFrozen(asset)
...
50	        nonReentrant
...
51	        onlyValidShortRecord(asset, shorter, id)
```

*GitHub* : [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L49), [50](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L50), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L51)


---

	 - contracts/facets/BridgeRouterFacet.sol


*GitHub* : [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40), [63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L43), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L44), [45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L45), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L89), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L90), [91](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L91), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L149), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L149), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L149)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L61), [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L61), [226](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L226), [227](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L227), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [349](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L349), [350](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L350)

### [N-59]<a name="n-59"></a> Optimize Unsigned Integer Comparison With Zero

For unsigned integers, checking whether the integer is not equal to zero (`!= 0`) is less gas-intensive than checking whether it is greater than zero (`> 0`). 

This is because the Ethereum Virtual Machine (EVM) can perform a simple bitwise operation to check if any bit is set (which directly translates to `!= 0`), while checking for `> 0` requires additional logic.

As such, when dealing with unsigned integers in Solidity, it is recommended to use the `!= 0` comparison for gas optimization.

*There are 11 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
292	        if (b.dustAskId > 0) {
...
294	        } else if (b.dustShortId > 0) {
...
299	        if (matchTotal.shortFillEth > 0) {
```

*GitHub* : [292](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L292), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L294), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L299)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
109	            if (dethAssessable > 0) {
...
111	                if (withdrawalFeePct > 0) {
```

*GitHub* : [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L109), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L111)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
279	            if (incorrectIndex > 0) {
...
397	        assert(newBaseRate > 0); // Base rate is always non-zero after redemption
```

*GitHub* : [279](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L279), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397)


---

	 - contracts/libraries/LibOracle.sol

```solidity
80	        bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;
```

*GitHub* : [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80)


---

	 - contracts/libraries/LibSRUtil.sol

```solidity
35	        if (yield > 0) {
...
113	            if (Asset.ercDebt > 0) {
```

*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L35), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L113), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158)

### [N-60]<a name="n-60"></a> Delete Unused State Variables

State variables that aren't used in the contract not only clutter the codebase but also consume unnecessary gas during deployment.
Specifically, setting non-zero initial values for state variables costs significant gas.
By removing these unused state variables, you can save on both deployment gas and potential future storage gas costs.
This optimization not only reduces gas expenditures but also enhances code clarity and maintainability.
Always ensure a thorough review to confirm that these variables are indeed redundant before removal.

*There are 13 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
47	    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
68	        returns (uint88 ethFilled, uint88 ercAmountLeft)
...
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
85	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
135	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

*GitHub* : [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L47), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L68), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L85), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L135), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [280](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340)


---

	 - contracts/facets/ExitShortFacet.sol


*GitHub* : [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [384](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L384)

### [N-61]<a name="n-61"></a> Optimize Gas by Using Only Named Returns

The Solidity compiler can generate more efficient bytecode when using named returns.
It's recommended to replace anonymous returns with named returns for potential gas savings.

Example:
```solidity
/// 985 gas cost
function add(uint256 x, uint256 y) public pure returns (uint256) {
  return x + y;
}
/// 941 gas cost
function addNamed(uint256 x, uint256 y) public pure returns (uint256 res) {
  res = x + y;
}
```

*There are 17 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
47	    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48	        external
49	        isNotFrozen(asset)
50	        nonReentrant
51	        onlyValidShortRecord(asset, shorter, id)
52	        returns (uint88, uint88)
53	    {
...
122	    function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123	        private
124	        returns (MTypes.PrimaryLiquidation memory)
125	    {
...
229	    function min88(uint256 a, uint88 b) private pure returns (uint88) {
```

*GitHub* : [47..53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53), [122..125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
40	    function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
...
51	    function getBridges(uint256 vault) external view returns (address[] memory) {
...
169	    function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```

*GitHub* : [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L51), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
31	    function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32	        internal
33	        view
34	        returns (bool)
35	    {
```

*GitHub* : [31..35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
39	    function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40	        internal
41	        returns (uint88)
42	    {
```

*GitHub* : [39..42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42)


---

	 - contracts/libraries/LibBytes.sol

```solidity
11	    function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```

*GitHub* : [11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)


---

	 - contracts/libraries/LibOracle.sol

```solidity
19	    function getOraclePrice(address asset) internal view returns (uint256) {
```

*GitHub* : [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [55..59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [362..367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

### [N-62]<a name="n-62"></a> Optimize Address Storage Value Management with `assembly`



*There are 4 instance(s) of this issue:*


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
31	        dusd = _dusd;
```

*GitHub* : [31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L31)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
30	        rethBridge = _rethBridge;
...
31	        stethBridge = _stethBridge;
```

*GitHub* : [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L30), [31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L31)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
29	        dusd = _dusd;
```

*GitHub* : [29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L29)

### [N-63]<a name="n-63"></a> Gas savings can be achieved by changing the model for assigning value to the structure

Change this `structName a = structName({item1: val1,item2: val2}); ==> structName a; a.item1 = val1; a.item2 = val2;`

*There are 1 instance(s) of this issue:*


---

	 - contracts/libraries/LibBytes.sol

```solidity
45	            data[i] = MTypes.ProposalData({
46	                shorter: shorter,
47	                shortId: shortId,
48	                CR: CR,
49	                ercDebtRedeemed: ercDebtRedeemed,
50	                colRedeemed: colRedeemed
51	            });
```

*GitHub* : [45..51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L45-L51)

### [N-64]<a name="n-64"></a> Use `Array.unsafeAccess` to avoid repeated array length checks

When using storage arrays, solidity adds an internal lookup of the array's length (a **Gcoldsload 2100 gas**) to ensure it doesn't read past the array's end.

It's possible to avoid this lookup by using `Array.unsafeAccess` in cases where the length has already been checked.

*There are 125 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
215	    function matchlowestSell(
216	        address asset,
217	        STypes.Order memory lowestSell,
218	        STypes.Order memory incomingBid,
219	        MTypes.Match memory matchTotal
220	    ) private {
...
// @audit: array `asset[asset]` is accesed 2 times
232	                STypes.Asset storage Asset = s.asset[asset];
...
// @audit: array `asset[asset]` is accesed 2 times
255	            s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth;
...
275	    function matchIncomingBid(
276	        address asset,
277	        STypes.Order memory incomingBid,
278	        MTypes.Match memory matchTotal,
279	        MTypes.BidMatchAlgo memory b
280	    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
...
// @audit: array `shorts[asset]` is accesed 3 times
310	            STypes.Order storage currentShort = s.shorts[asset][b.shortId];
...
// @audit: array `shorts[asset]` is accesed 3 times
312	            STypes.Order storage prevShort = s.shorts[asset][b.prevShortId];
...
// @audit: array `shorts[asset]` is accesed 3 times
323	                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
...
340	    function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
...
// @audit: array `asks[asset]` is accesed 2 times
343	            STypes.Order storage lowestAsk = s.asks[asset][b.askId];
...
// @audit: array `asks[asset]` is accesed 2 times
354	            return s.asks[asset][b.askId];
```

*GitHub* : [232](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L232), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L255), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L310), [312](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L312), [323](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L323), [343](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L343), [354](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L354), [343](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L343), [354](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L354), [391](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L391), [398](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L398), [400](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L400)


---

	 - contracts/facets/ShortOrdersFacet.sol


*GitHub* : [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L72), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L73)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol


*GitHub* : [97](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L97), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L102), [170](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L170), [194](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L194), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L210), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241), [250](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L250)


---

	 - contracts/facets/RedemptionFacet.sol


*GitHub* : [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L79), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L80), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L81), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243), [264](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L264), [234](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L234), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L297), [248](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L248), [266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L266)


---

	 - contracts/libraries/LibBridgeRouter.sol


*GitHub* : [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L151), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L154)


---

	 - contracts/libraries/LibOracle.sol


*GitHub* : [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L151), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L152), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L151), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L152)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L60), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L65), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L69), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L72), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L73), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L60), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L69), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L65), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L72), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L73), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L89), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L90), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L110), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L111), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L131), [132](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L132), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L183), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L187), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L192), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L197), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L201), [212](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L212), [214](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L214), [217](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L217), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L187), [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L197), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L201), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L192), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L183), [217](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L217), [238](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L238), [239](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L239), [268](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L268), [270](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L270), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L291), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297), [298](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L298), [298](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L298), [298](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L298), [301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297), [298](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L298), [298](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L298), [301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L333), [334](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L334), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L340), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L347), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L333), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L340), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L347), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L368), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L386), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L368), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L386), [449](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L449), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [449](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L449), [456](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L456), [487](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L487), [488](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L488), [540](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L540), [542](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L542), [544](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L544), [563](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L563), [564](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L564), [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573), [596](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L596), [605](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L605), [563](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L563), [596](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L596), [564](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L564), [573](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L573), [738](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L738), [749](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L749), [759](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L759), [814](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L814), [815](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L815), [884](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L884), [943](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L943)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L42), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L44)

### [N-65]<a name="n-65"></a> Consider using OpenZeppelin's `EnumerateSet` instead of nested mappings

Nested mappings and multi-dimensional arrays in Solidity operate through a process of double hashing, wherein the original storage slot and the first key are concatenated and hashed, and then this hash is again concatenated with the second key and hashed. This process can be quite gas expensive due to the double-hashing operation and subsequent storage operation (sstore).

OpenZeppelin's `EnumerableSet` provides a potential solution to this problem. It creates a data structure that combines the benefits of set operations with the ability to enumerate stored elements, which is not natively available in Solidity. EnumerableSet handles the element uniqueness internally and can therefore provide a more gas-efficient and collision-resistant alternative to nested mappings or multi-dimensional arrays in certain scenarios.

*There are 12 instance(s) of this issue:*


---

	 - contracts/libraries/LibOrders.sol

```solidity
55	    function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
...
174	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
261	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
289	    function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
...
314	    function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
...
321	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
363	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
403	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
441	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
...
475	        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
```

*GitHub* : [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L174), [261](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L261), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L321), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L363), [403](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L403), [441](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L441), [475](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L475), [533](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L533), [827](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L827)

### [N-66]<a name="n-66"></a> Counting down in `for` statements is more gas efficient

Counting down is more gas efficient than counting up because neither we are making zero variable to non-zero variable and also we will get gas refund in the last transaction when making non-zero to zero variable. [More info](https://solodit.xyz/issues/g-02-counting-down-in-for-statements-is-more-gas-efficient-code4rena-pooltogether-pooltogether-git)

*There are 8 instance(s) of this issue:*


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
// @audit `i` is counter for the loop
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
...
 // @audit increment is used for counter
78	        for (uint8 i = 0; i < proposalInput.length; i++) {
...
// @audit `i` is counter for the loop
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
...
 // @audit increment is used for counter
242	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
...
// @audit `i` is counter for the loop
263	            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
...
 // @audit increment is used for counter
263	            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
...
// @audit `i` is counter for the loop
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
...
 // @audit increment is used for counter
321	        for (uint256 i = 0; i < decodedProposalData.length; i++) {
```

*GitHub* : [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L263), [321](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L321)


---

	 - contracts/libraries/LibBytes.sol

```solidity
// @audit `i` is counter for the loop
18	        for (uint256 i = 0; i < slateLength; i++) {
...
 // @audit increment is used for counter
18	        for (uint256 i = 0; i < slateLength; i++) {
```

*GitHub* : [18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L18)


---

	 - contracts/libraries/LibOrders.sol


*GitHub* : [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L71), [746](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L746), [832](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L832)


The rule itself is correct. But here are the cases in which SemVer allows you to use version up to `0.8.20`

*There are 12 instance(s) of this issue:*


---

	 - contracts/facets/BidOrdersFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L2)


---

	 - contracts/facets/ShortOrdersFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L2)


---

	 - contracts/facets/PrimaryLiquidationFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L2)


---

	 - contracts/facets/BridgeRouterFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L2)


---

	 - contracts/facets/ExitShortFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L2)


---

	 - contracts/facets/RedemptionFacet.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L2)


---

	 - contracts/libraries/LibBridgeRouter.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L2)


---

	 - contracts/libraries/LibBytes.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L2)


---

	 - contracts/libraries/LibOracle.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L2)


---

	 - contracts/libraries/LibOrders.sol

```solidity
2	pragma solidity 0.8.21;
```

*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L2)


---

	 - contracts/libraries/LibSRUtil.sol


*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L2)


---

	 - contracts/libraries/UniswapOracleLibrary.sol


*GitHub* : [2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L2)