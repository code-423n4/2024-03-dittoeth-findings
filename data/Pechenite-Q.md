**Note:** All instances from the 4naly3er report are removed.

---

### Low

|Number|Issue|Instances|
|-|:-|:-:|
| [L&#x2011;1](#L1-array-length-is-not-checked-before-access-its-index) | Array length is not checked before access its index | 11 |
| [L&#x2011;2](#L2-calling-bytesconcat-with-final-arguments-that-may-differ-in-length-may-cause-hash-collisions) | Calling `bytes.concat()` with final arguments that may differ in length, may cause hash collisions | 1 |
| [L&#x2011;3](#L3-consider-implementing-two-step-procedure-for-updating-protocol-addresses) | Consider implementing two-step procedure for updating protocol addresses | 2 |
| [L&#x2011;4](#L4-constructor/initialize-function-lacks-parameter-validation) | `constructor`/`initialize` function lacks parameter validation | 3 |
| [L&#x2011;5](#L5-incorrect-comparison-implementation) | Incorrect comparison implementation | 5 |
| [L&#x2011;6](#L6-missing-zero-address-check-in-functions-with-address-parameters) | Missing zero address check in functions with address parameters | 73 |
| [L&#x2011;7](#L7-multiplication-on-the-result-of-a-division) | Multiplication on the result of a division | 3 |
| [L&#x2011;8](#L8-payable-function-does-not-transfer-eth) | `payable` function does not transfer Eth | 1 |
| [L&#x2011;9](#L9-setters-should-prevent-re-setting-of-the-same-value) | Setters should prevent re-setting of the same value | 1 |
| [L&#x2011;10](#L10-unsafe-conversion-from-unsigned-to-signed-values) | Unsafe conversion from unsigned to signed values | 2 |
| [L&#x2011;11](#L11-unsafe-downcast) | Unsafe downcast | 18 |
| [L&#x2011;12](#L12-vulnerable-versions-of-packages-are-being-used) | Vulnerable versions of packages are being used | 1 |


### NonCritical

|Number|Issue|Instances|
|-|:-|:-:|
| [NC&#x2011;1](#NC1-avoid-mutating-function/modifier-parameters) | Avoid mutating `function`/`modifier` parameters | 74 |
| [NC&#x2011;2](#NC2-chainlink-oracle-roundid-and-answeredin-variables-no-longer-contain-useful-information) | Chainlink oracle `roundId` and `answeredIn` variables no longer contain useful information | 6 |
| [NC&#x2011;3](#NC3-codebase-should-implement-formal-verification-testing) | Codebase should implement formal verification testing | 1 |
| [NC&#x2011;4](#NC4-complicated-functions-should-have-explicit-comments) | Complicated functions should have explicit comments | 7 |
| [NC&#x2011;5](#NC5-consider-adding-a-block/deny-list) | Consider adding a block/deny-list | 6 |
| [NC&#x2011;6](#NC6-consider-disallowing-transfers-to-addressthis) | Consider disallowing transfers to `address(this)` | 2 |
| [NC&#x2011;7](#NC7-consider-making-contracts-upgradeable) | Consider making contracts `Upgradeable` | 6 |
| [NC&#x2011;8](#NC8-consider-using-delete-rather-than-assigning-zero-to-clear-values) | Consider using `delete` rather than assigning zero to clear values | 17 |
| [NC&#x2011;9](#NC9-consider-using-named-function-arguments) | Consider using named function arguments | 2 |
| [NC&#x2011;10](#NC10-constants-in-comparisons-should-appear-on-the-left-side) | Constants in comparisons should appear on the left side | 32 |
| [NC&#x2011;11](#NC11-constants/immutables-redefined-elsewhere) | `constant`s/`immutable`s redefined elsewhere | 4 |
| [NC&#x2011;12](#NC12-constructor-should-emit-an-event) | `constructor` should emit an event | 3 |
| [NC&#x2011;13](#NC13-contract-timekeeping-will-break-earlier-than-the-ethereum-network-itself-will-stop-working) | Contract timekeeping will break earlier than the Ethereum network itself will stop working | 1 |
| [NC&#x2011;14](#NC14-contract/library/interface-definitions-should-be-defined-in-separate-files) | `contract`/`library`/`interface` definitions should be defined in separate files | 1 |
| [NC&#x2011;15](#NC15-contracts-should-have-all-public/external-functions-exposed-by-interfaces) | Contracts should have all `public`/`external` functions exposed by `interface`s | 6 |
| [NC&#x2011;16](#NC16-contracts-should-have-full-test-coverage) | Contracts should have full test coverage | 1 |
| [NC&#x2011;17](#NC17-custom-errors-should-be-used-rather-than-revert/require) | Custom errors should be used rather than `revert()`/`require()` | 1 |
| [NC&#x2011;18](#NC18-dependence-on-external-protocols) | Dependence on external protocols | 60 |
| [NC&#x2011;19](#NC19-else-block-not-required) | `else`-block not required | 21 |
| [NC&#x2011;20](#NC20-events-should-be-emitted-before-external-calls) | Events should be emitted before external calls | 12 |
| [NC&#x2011;21](#NC21-extraneous-whitespace) | Extraneous whitespace | 2 |
| [NC&#x2011;22](#NC22-for-loops-in-public-or-external-functions-should-be-avoided-due-to-high-gas-costs-and-possible-dos) | For loops in `public` or `external` functions should be avoided due to high gas costs and possible DOS | 3 |
| [NC&#x2011;23](#NC23-function-can-be-declared-as-pure) | Function can be declared as `pure` | 1 |
| [NC&#x2011;24](#NC24-function-definition-modifier-order-does-not-follow-solidity-style-guide) | Function definition modifier order does not follow Solidity style guide | 18 |
| [NC&#x2011;25](#NC25-functions-should-be-named-in-mixedcase-style) | Functions should be named in mixedCase style | 3 |
| [NC&#x2011;26](#NC26-high-cyclomatic-complexity) | High cyclomatic complexity | 17 |
| [NC&#x2011;27](#NC27-if-statement-can-be-converted-to-a-ternary) | `if`-statement can be converted to a ternary | 13 |
| [NC&#x2011;28](#NC28-imports-could-be-organized-more-systematically) | Imports could be organized more systematically | 6 |
| [NC&#x2011;29](#NC29-inconsistent-spacing-in-comments) | Inconsistent spacing in comments | 25 |
| [NC&#x2011;30](#NC30-initialisms-should-be-capitalized) | Initialisms should be capitalized | 18 |
| [NC&#x2011;31](#NC31-invalid-natspec-comment-style) | Invalid NatSpec comment style | 112 |
| [NC&#x2011;32](#NC32-large-or-complicated-code-bases-should-implement-invariant-tests) | Large or complicated code bases should implement invariant tests | 1 |
| [NC&#x2011;33](#NC33-make-use-of-soliditys-using-keyword) | Make use of Solidity's `using` keyword | 198 |
| [NC&#x2011;34](#NC34-missing-checks-for-address0x0-in-the-constructor) | Missing checks for `address(0x0)` in the constructor | 4 |
| [NC&#x2011;35](#NC35-missing-checks-for-uint-state-variable-assignments) | Missing checks for uint state variable assignments | 26 |
| [NC&#x2011;36](#NC36-multiple-type-casts-create-complexity-within-the-code) | Multiple type casts create complexity within the code | 1 |
| [NC&#x2011;37](#NC37-natspec-contract-declarations-should-have-@author-tags) | NatSpec: Contract declarations should have `@author` tags | 13 |
| [NC&#x2011;38](#NC38-natspec-contract-declarations-should-have-@dev-tags) | NatSpec: Contract declarations should have `@dev` tags | 13 |
| [NC&#x2011;39](#NC39-natspec-contract-declarations-should-have-@notice-tags) | NatSpec: Contract declarations should have `@notice` tags | 12 |
| [NC&#x2011;40](#NC40-natspec-contract-declarations-should-have-@title-tags) | NatSpec: Contract declarations should have `@title` tags | 12 |
| [NC&#x2011;41](#NC41-natspec-contract-declarations-should-have-natspec-descriptions) | NatSpec: Contract declarations should have NatSpec descriptions | 12 |
| [NC&#x2011;42](#NC42-natspec-file-is-missing-natspec-documentation) | NatSpec: File is missing NatSpec Documentation | 11 |
| [NC&#x2011;43](#NC43-natspec-function-declarations-should-have-@notice-tags) | NatSpec: Function declarations should have `@notice` tags | 55 |
| [NC&#x2011;44](#NC44-natspec-function-declarations-should-have-natspec-descriptions) | NatSpec: Function declarations should have NatSpec descriptions | 55 |
| [NC&#x2011;45](#NC45-natspec-functions-missing-natspec-@dev-tag) | NatSpec: Functions missing NatSpec `@dev` tag | 76 |
| [NC&#x2011;46](#NC46-natspec-functions-missing-natspec-@param-tag) | NatSpec: Functions missing NatSpec `@param` tag | 88 |
| [NC&#x2011;47](#NC47-natspec-functions-missing-natspec-@return-tag) | NatSpec: Functions missing NatSpec `@return` tag | 39 |
| [NC&#x2011;48](#NC48-not-using-the-latest-versions-of-project-dependencies) | Not using the latest versions of project dependencies | 1 |
| [NC&#x2011;49](#NC49-not-using-the-named-return-variables-anywhere-in-the-function-is-confusing) | Not using the named return variables anywhere in the function is confusing | 22 |
| [NC&#x2011;50](#NC50-outdated-solidity-version) | Outdated Solidity version | 12 |
| [NC&#x2011;51](#NC51-overly-complicated-arithmetic) | Overly complicated arithmetic | 5 |
| [NC&#x2011;52](#NC52-place-interface-files-into-a-dedicated-folder) | Place `interface` files into a dedicated folder | 1 |
| [NC&#x2011;53](#NC53-prefer-skip-over-revert-model-in-iteration) | Prefer skip over revert model in iteration | 2 |
| [NC&#x2011;54](#NC54-state-variables-should-include-comments) | State variables should include comments | 4 |
| [NC&#x2011;55](#NC55-the-nonreentrant-modifier-should-occur-before-all-other-modifiers) | The `nonReentrant` `modifier` should occur before all other modifiers | 10 |
| [NC&#x2011;56](#NC56-top-level-declarations-should-be-separated-by-at-least-two-lines) | Top-level declarations should be separated by at least two lines | 40 |
| [NC&#x2011;57](#NC57-unnecessary-cast) | Unnecessary cast | 3 |
| [NC&#x2011;58](#NC58-unused-file) | Unused file | 6 |
| [NC&#x2011;59](#NC59-unused-import) | Unused import | 20 |
| [NC&#x2011;60](#NC60-use-a-struct-to-encapsulate-multiple-function-parameters) | Use a struct to encapsulate multiple function parameters | 11 |
| [NC&#x2011;61](#NC61-use-upper_case-for-immutable) | Use UPPER_CASE for `immutable` | 4 |
| [NC&#x2011;62](#NC62-variable-names-that-consist-of-all-capital-letters-should-be-reserved-for-constant/immutable-variables) | Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables | 4 |
| [NC&#x2011;63](#NC63-variable/struct/contract-names-should-be-descriptive-rather-than-cryptic) | `variable`/`struct`/`contract` names should be descriptive rather than cryptic | 44 |
| [NC&#x2011;64](#NC64-variables-should-be-named-in-mixedcase-style) | Variables should be named in mixedCase style | 67 |
| [NC&#x2011;65](#NC65-zero-as-a-function-argument-should-have-a-descriptive-meaning) | Zero as a function argument should have a descriptive meaning | 1 |


## Low


---
### [L&#x2011;1] Array length is not checked before access its index
Accessing the elements of the array without checking or ensuring the validity of the access index in advance. It may result in an unexpected out-of-bounds error, or may result in missing elements when trying to traverse the entire array.

<details>
<summary><i>There are 11 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) { 

253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex]; 

264:                 currentProposal = decodedProposalData[i]; 

322:             MTypes.ProposalData memory currentProposal = decodedProposalData[i]; 
```
[243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L243), [253](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L253), [264](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L264), [322](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L322)

```solidity
📁 File: contracts/libraries/LibOrders.sol

744:                 shortHintId = shortHintArray[i]; 

833:             MTypes.OrderHint memory orderHint = orderHintArray[i]; 
```
[744](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L744), [833](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L833)

</details>


---
### [L&#x2011;2] Calling `bytes.concat()` with final arguments that may differ in length, may cause hash collisions
`bytes3(bytes2(uint16(1)))` and `bytes3(bytes3(uint24(256)))` both are equal to `0x000100`, and if they each were passed to a function used them as the last argument to `bytes.concat()`, which is the case below, the resulting bytes would be equivalent. When this sort of function is a part of a general-purpose library, or is a part of a standard, and is used for e.g. indexing storage slots, it's possible for two byte values to map to the same location. There is no safe way to ensure the caller hasn't cast bytes from a smaller size. The suggested fix is to require that the input be the result of a call to `keccak256(abi.encode(<value>))`, and truncate the extra bytes of entropy if a specific size is absolutely needed.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

129:             slate = bytes.concat( 
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
```
[129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L129-L136)


---
### [L&#x2011;3] Consider implementing two-step procedure for updating protocol addresses
A copy-paste error or a typo may end up bricking protocol functionality, or sending tokens to an address with no known private key. Consider implementing a two-step procedure for updating protocol addresses, where the recipient is set as pending, and must 'accept' the assignment by making an affirmative call. A straight forward way of doing this would be to have the target contracts implement [EIP-165](https://eips.ethereum.org/EIPS/eip-165), and to have the 'set' functions ensure that the recipient is of the right interface type.


<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit line 129
/// @audit line 133
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {
126:         LibShortRecord.updateErcDebt(asset, shorter, id);
127:         {
128:             MTypes.PrimaryLiquidation memory m;
129:             m.asset = asset;
130:             m.short = s.shortRecords[asset][shorter][id];
131:             m.shortOrderId = shortOrderId;
132:             m.vault = s.asset[asset].vault;
133:             m.shorter = shorter;
134:             m.penaltyCR = LibAsset.penaltyCR(asset);
135:             m.oraclePrice = LibOracle.getPrice(asset);
136:             m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);
138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);
139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
141:             return m;
142:         }
143:     }
```
[122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L143)


---
### [L&#x2011;4] `constructor`/`initialize` function lacks parameter validation
Constructors and initialization functions play a critical role in contracts by setting important initial states when the contract is first deployed before the system starts. The parameters passed to the constructor and initialization functions directly affect the behavior of the contract / protocol. If incorrect parameters are provided, the system may fail to run, behave abnormally, be unstable, or lack security. Therefore, it's crucial to carefully check each parameter in the constructor and initialization functions. If an exception is found, the transaction should be rolled back.

<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit _rethBridge , _stethBridge 
29:     constructor(address _rethBridge, address _stethBridge) { 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit _dusd 
28:     constructor(address _dusd) { 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit _dusd 
30:     constructor(address _dusd) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

</details>


---
### [L&#x2011;5] Incorrect comparison implementation
Use `require` or `if` to compare values. Otherwise comparison will be ignored.


<i>There are 5 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOracle.sol

77:             || block.timestamp > 2 hours + timeStamp; 

126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0; 
```
[77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L77), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126)


---
### [L&#x2011;6] Missing zero address check in functions with address parameters
Adding a zero address check for each address type parameter can prevent errors.

<details>
<summary><i>There are 73 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit asset
40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit sender, asset
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {

/// @audit sender, asset
77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit asset
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit asset
215:     function matchlowestSell( 
216:         address asset,
217:         STypes.Order memory lowestSell,
218:         STypes.Order memory incomingBid,
219:         MTypes.Match memory matchTotal
220:     ) private {

/// @audit asset
275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit asset
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 

/// @audit asset
358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit bridge
63:     function deposit(address bridge, uint88 amount) external nonReentrant { 

/// @audit bridge
82:     function depositEth(address bridge) external payable nonReentrant { 

/// @audit bridge
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant { 

/// @audit bridge
133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO { 
```
[63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L63), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit asset
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {

/// @audit asset
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {

/// @audit asset
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

/// @audit asset, shorter
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {

/// @audit asset, shorter
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit proposer, shorter
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
32:         internal
33:         view
34:         returns (bool)
35:     {

/// @audit asset
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

/// @audit asset, disputeShorter
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {

/// @audit asset
310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant { 

/// @audit asset, redeemer
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {

/// @audit asset, shorter
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 

/// @audit asset
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
383:         internal
384:         returns (uint88 redemptionFee)
385:     {
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit asset
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

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit rethBridge, stethBridge
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {

/// @audit rethBridge, stethBridge
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 

/// @audit asset, from, to
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit SSTORE2Pointer
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit asset
19:     function getOraclePrice(address asset) internal view returns (uint256) { 

/// @audit asset
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal { 

/// @audit asset
156:     function getTime(address asset) internal view returns (uint256 creationTime) { 

/// @audit asset
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 

/// @audit asset
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit asset
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal { 

/// @audit asset
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 
56:         internal
57:         view
58:         returns (STypes.Order[] memory)
59:     {

/// @audit asset
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit asset
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit asset
128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit asset
153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private { 

/// @audit asset
173:     function addOrder( 
174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
175:         address asset,
176:         STypes.Order memory incomingOrder,
177:         uint16 hintId
178:     ) private {

/// @audit asset
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId) 
232:         internal
233:         view
234:         returns (int256 direction)
235:     {

/// @audit asset
260:     function verifySellId( 
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

/// @audit asset
289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

/// @audit asset
314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

/// @audit asset
320:     function _reuseOrderIds( 
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

/// @audit asset
362:     function findPrevOfIncomingId( 
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

/// @audit asset
402:     function verifyId( 
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {

/// @audit asset
440:     function getOrderId( 
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

/// @audit asset
474:     function updateBidOrdersOnMatch( 
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled
479:     ) internal {

/// @audit asset
499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal { 

/// @audit asset
532:     function _updateOrders( 
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {

/// @audit asset
556:     function sellMatchAlgo( 
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {

/// @audit asset
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private { 

/// @audit asset
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private { 

/// @audit asset
668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private { 

/// @audit asset
705:     function matchHighestBid( 
706:         STypes.Order memory incomingSell,
707:         STypes.Order memory highestBid,
708:         address asset,
709:         MTypes.Match memory matchTotal
710:     ) internal {

/// @audit asset
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 

/// @audit asset
783:     function updateOracleAndStartingShortViaThreshold( 
784:         address asset,
785:         uint256 savedPrice,
786:         STypes.Order memory incomingOrder,
787:         uint16[] memory shortHintArray
788:     ) internal {

/// @audit asset
803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal { 

/// @audit asset
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal { 

/// @audit asset
826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {

/// @audit asset
854:     function cancelBid(address asset, uint16 id) internal { 

/// @audit asset
868:     function cancelAsk(address asset, uint16 id) internal { 

/// @audit asset
882:     function cancelShort(address asset, uint16 id) internal { 

/// @audit asset
955:     function handlePriceDiscount(address asset, uint80 price) internal { 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [153](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L153), [173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320-L326), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L409), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [474](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L474-L479), [499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499), [532](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L532-L537), [556](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [628](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L628), [652](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L652), [668](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L668), [705](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L705-L710), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [783](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783-L788), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit asset, shorter
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 
23:         internal
24:     {

/// @audit asset, shorter
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {

/// @audit asset, shorter
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {

/// @audit asset
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 
103:         internal
104:         view
105:         returns (bool recoveryViolation)
106:     {

/// @audit from, to
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal { 

/// @audit asset
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal { 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit pool, baseToken, quoteToken
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

</details>


---
### [L&#x2011;7] Multiplication on the result of a division
Dividing an integer by another integer will often result in loss of precision.
When the result is multiplied by another number, the loss of precision is magni'fied, often to material magnitudes. `(X / Z) * Y` should be re-written as `(X * Y) / Z`

Example:
```solidity
contract A {
  function f(uint n) public {
       coins = (oldSupply / n) * interest;
   }
}
```

If `n` is greater than `oldSupply`, coins will be zero. For example, with `oldSupply = 5; n = 10, interest = 2`, coins will be zero.
If `(oldSupply * interest / n)` was used, coins would have been 1. In general, it's usually a good idea to re-arrange arithmetic to perform `multiplication before division`, unless the limit of a smaller type makes this dangerous.


<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/libraries/LibOracle.sol

93:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 

141:         uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC); 
```
[93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L93), [141](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141)

```solidity
📁 File: contracts/libraries/LibOrders.sol

47:             uint88 shares = eth * (timeTillMatch / 1 days); 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47)

</details>


---
### [L&#x2011;8] `payable` function does not transfer Eth
Funds sent along with the call to this function will be lost.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

82:     function depositEth(address bridge) external payable nonReentrant { 
83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();
84: 
85:         (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
86: 
87:         uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
88:         vault.addDeth(bridgePointer, dethAmount);
89:         maybeUpdateYield(vault, dethAmount);
90:         emit Events.DepositEth(bridge, msg.sender, dethAmount);
91:     }
```
[82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L82-L91)


---
### [L&#x2011;9] Setters should prevent re-setting of the same value
This especially problematic when the setter also emits the same value, which may be confusing to offline parsers


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {
126:         LibShortRecord.updateErcDebt(asset, shorter, id);
127:         {
128:             MTypes.PrimaryLiquidation memory m;
129:             m.asset = asset;
130:             m.short = s.shortRecords[asset][shorter][id];
131:             m.shortOrderId = shortOrderId;
132:             m.vault = s.asset[asset].vault;
133:             m.shorter = shorter;
134:             m.penaltyCR = LibAsset.penaltyCR(asset);
135:             m.oraclePrice = LibOracle.getPrice(asset);
136:             m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);
138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);
139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
141:             return m;
142:         }
143:     }
```
[122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L143)


---
### [L&#x2011;10] Unsafe conversion from unsigned to signed values
Solidity follows [two's complement](https://en.wikipedia.org/wiki/Two%27s_complement) rules for its integers, meaning that the most significant bit for signed integers is used to denote the sign, and converting between the two requires inverting all of the bits and adding one. Because of this, casting an unsigned integer to a signed one may result in a change of the sign and or magnitude of the value. For example, `int8(type(uint8).max)` is not equal to `type(int8).max`, but is equal to `-1`. `type(uint8).max` in binary is `11111111`, which if cast to a signed value, means the first binary `1` indicates a negative value, and the binary `1`s, invert to all zeroes, and when one is added, it becomes one, but negative, and therefore the decimal value of binary `11111111` is `-1`.


<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit uint32 -> int32
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo)); 

/// @audit uint32 -> int32
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) { 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)


---
### [L&#x2011;11] Unsafe downcast
When a type is downcast to a smaller type, the higher order bits are discarded, resulting in the application of a modulo operation to the original value.

If the downcasted value is large enough, this may result in an overflow that will not revert.

<details>
<summary><i>There are 18 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit uint256 -> uint88
68:         uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast) 

/// @audit uint256 -> uint88
87:         uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH 
```
[68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L87)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit uint256 -> uint88
180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast) 

/// @audit uint256 -> uint88
199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast) 

/// @audit uint256 -> uint88
231:         return a < b ? uint88(a) : b; 
```
[180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180), [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L199), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L231)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit uint256 -> uint64
133:                 bytes8(uint64(p.currentCR)), 

/// @audit uint256 -> uint32
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether); 

/// @audit uint256 -> uint32
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether); 

/// @audit uint256 -> uint32
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether); 

/// @audit uint256 -> uint32
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether); 

/// @audit uint256 -> uint32
198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether); 

/// @audit uint256 -> uint64
399:         Asset.baseRate = uint64(newBaseRate); 

/// @audit uint256 -> uint88
402:         return uint88(redemptionRate.mul(colRedeemed)); 
```
[133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L133), [183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198), [399](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L399), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L402)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit uint256 -> uint80
151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice); 

/// @audit uint88 -> uint80
164:         return uint80(s.bids[asset][C.HEAD].ercAmount); 
```
[151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L151), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L164)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit uint256 -> uint32
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast) 

/// @audit uint256 -> uint88
903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset)); 
```
[32](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L32), [903](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L903)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit int56 -> int24
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo)); 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62)

</details>


---
### [L&#x2011;12] Vulnerable versions of packages are being used
This project's specific package versions are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities.
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-m6w8-fq7v-ph4m) - GovernorCompatibilityBravo incorrect ABI encoding may lead to unexpected behavior

>### Impact
>
>The `GovernorCompatibilityBravo` module may lead to the creation of governance proposals that execute function calls with incorrect arguments due to bad ABI encoding. This happens if the proposal is created using explicit function signatures, e.g. a proposal to invoke the function `foo(uint256)` is created as `propose([target], [0], ["foo(uint256)"], ["0x00..01"])`. If the function selector is provided as part of the encoded proposal data the issue is not present, e.g. the same proposal is created as `propose([target], [0], ["0x2fbebd3800..01"])`, where `2fbebd38` is the function selector.
>
>We've assessed the instances of this contract found on chain, and did not find any occurrence of this bug in the past. Proposal creation through Tally or OpenZeppelin Defender is not affected. The core `Governor` contract on its own is not affected.
>
>### Patches
>
>A fix is included in version v4.4.2 of `@openzeppelin/contracts` and `@openzeppelin/contracts-upgradeable`.
>
>### Workarounds
>
>Do not create proposals using explicit function signatures. Instead, use the `propose` function without the `signatures` argument, and create the proposal using the fully ABI-encoded function call including the function selector in the `calldatas` argument as explained above.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/issues/3099
>
>### Credits
>
>This issue was identified and reported by @GeraldHost.
>
>### For more information
>
>If you have any questions, comments, or need assistance regarding this advisory, email us at security@openzeppelin.com.
>
>To submit security reports please use [our bug bounty on Immunefi](https://immunefi.com/bounty/openzeppelin/).
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-4g63-c64m-25w9) - OpenZeppelin Contracts's SignatureChecker may revert on invalid EIP-1271 signers

>### Impact
>
>`SignatureChecker.isValidSignatureNow` is not expected to revert. However, an incorrect assumption about Solidity 0.8's `abi.decode` allows some cases to revert, given a target contract that doesn't implement EIP-1271 as expected.
>
>The contracts that may be affected are those that use `SignatureChecker` to check the validity of a signature and handle invalid signatures in a way other than reverting. We believe this to be unlikely.
>
>### Patches
>
>The issue was patched in 4.7.1.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/3552
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance deploying the fix, email us at [security@openzeppelin.com](mailto:security@openzeppelin.com).
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-9c22-pwxw-p6hx) - OpenZeppelin Contracts initializer reentrancy may lead to double initialization

>### Impact
>
>Initializer functions that are invoked separate from contract creation (the most prominent example being minimal proxies) may be reentered if they make an untrusted non-view external call.
>
>Once an initializer has finished running it can never be re-executed. However, an exception put in place to support multiple inheritance made reentrancy possible in the scenario described above, breaking the expectation that there is a single execution.
>
>Note that upgradeable proxies are commonly initialized together with contract creation, where reentrancy is not feasible, so the impact of this issue is believed to be minor.
>
>### Patches
>
>A fix is included in the version v4.4.1 of `@openzeppelin/contracts` and `@openzeppelin/contracts-upgradeable`.
>
>### Workarounds
>
>Avoid untrusted external calls during initialization.
>
>### References
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/3006
>
>### Credits
>
>This issue was identified and reported by @chaitinblockchain through [our bug bounty on Immunefi](https://immunefi.com/bounty/openzeppelin/).
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance executing the mitigation, email us at security@openzeppelin.com.
>
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-xrc4-737v-9q75) - OpenZeppelin Contracts's GovernorVotesQuorumFraction updates to quorum may affect past defeated proposals

>### Impact
>
>This issue concerns instances of Governor that use the module `GovernorVotesQuorumFraction`, a mechanism that determines quorum requirements as a percentage of the voting token's total supply. In affected instances, when a proposal is passed to lower the quorum requirement, past proposals may become executable if they had been defeated only due to lack of quorum, and the number of votes it received meets the new quorum requirement.
>
>Analysis of instances on chain found only one proposal that met this condition, and we are actively monitoring for new occurrences of this particular issue.
>
>### Patches
>
>This issue has been patched in v4.7.2.
>
>### Workarounds
>
>Avoid lowering quorum requirements if a past proposal was defeated for lack of quorum.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/3561
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance deploying the fix, email us at [security@openzeppelin.com](mailto:security@openzeppelin.com).
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-qh9x-gcfh-pcrw) - OpenZeppelin Contracts's ERC165Checker may revert instead of returning false

>### Impact
>
>`ERC165Checker.supportsInterface` is designed to always successfully return a boolean, and under no circumstance revert. However, an incorrect assumption about Solidity 0.8's `abi.decode` allows some cases to revert, given a target contract that doesn't implement EIP-165 as expected, specifically if it returns a value other than 0 or 1.
>
>The contracts that may be affected are those that use `ERC165Checker` to check for support for an interface and then handle the lack of support in a way other than reverting.
>
>### Patches
>
>The issue was patched in 4.7.1.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/3552
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance deploying the fix, email us at [security@openzeppelin.com](mailto:security@openzeppelin.com).
>
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-4h98-2769-gh6h) - OpenZeppelin Contracts vulnerable to ECDSA signature malleability

>### Impact
>
>The functions `ECDSA.recover` and `ECDSA.tryRecover` are vulnerable to a kind of signature malleability due to accepting EIP-2098 compact signatures in addition to the traditional 65 byte signature format. This is only an issue for the functions that take a single `bytes` argument, and not the functions that take `r, v, s` or `r, vs` as separate arguments.
>
>The potentially affected contracts are those that implement signature reuse or replay protection by marking the signature itself as used rather than the signed message or a nonce included in it. A user may take a signature that has already been submitted, submit it again in a different form, and bypass this protection.
>
>### Patches
>
>The issue has been patched in 4.7.3.
>
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance deploying a fix, email us at [security@openzeppelin.com](mailto:security@openzeppelin.com).
>
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-9c22-pwxw-p6hx) - Improper Initialization in OpenZeppelin

>In OpenZeppelin <=v4.4.0, initializer functions that are invoked separate from contract creation (the most prominent example being minimal proxies) may be reentered if they make an untrusted non-view external call. Once an initializer has finished running it can never be re-executed. However, an exception put in place to support multiple inheritance made reentrancy possible, breaking the expectation that there is a single execution.
- `@openzeppelin/contracts` - <b>HIGH</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-93hq-5wgc-jc82) - GovernorCompatibilityBravo may trim proposal calldata

>### Impact
>
>The proposal creation entrypoint (`propose`) in `GovernorCompatibilityBravo` allows the creation of proposals with a `signatures` array shorter than the `calldatas` array. This causes the additional elements of the latter to be ignored, and if the proposal succeeds the corresponding actions would eventually execute without any calldata. The `ProposalCreated` event correctly represents what will eventually execute, but the proposal parameters as queried through `getActions` appear to respect the original intended calldata.
>
>### Patches
>
>This issue has been patched in v4.8.3.
>
>### Workarounds
>
>Ensure that all proposals that pass through governance have equal length `signatures` and `calldatas` parameters.
>
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-7grf-83vw-6f5x) - OpenZeppelin Contracts ERC165Checker unbounded gas consumption

>### Impact
>
>The target contract of an EIP-165 `supportsInterface` query can cause unbounded gas consumption by returning a lot of data, while it is generally assumed that this operation has a bounded cost.
>
>### Patches
>
>The issue has been fixed in v4.7.2.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/3587
>
>### For more information
>
>If you have any questions or comments about this advisory, or need assistance deploying a fix, email us at [security@openzeppelin.com](mailto:security@openzeppelin.com).
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-g4vp-m682-qqmp) - OpenZeppelin Contracts vulnerable to Improper Escaping of Output

>### Impact
>
>OpenZeppelin Contracts is a library for secure smart contract development. Starting in version 4.0.0 and prior to version 4.9.3, contracts using `ERC2771Context` along with a custom trusted forwarder may see `_msgSender` return `address(0)` in calls that originate from the forwarder with calldata shorter than 20 bytes. This combination of circumstances does not appear to be common, in particular it is not the case for `MinimalForwarder` from OpenZeppelin Contracts, or any deployed forwarder the team is aware of, given that the signer address is appended to all calls that originate from these forwarders.
>
>### Patches
>
>The problem has been patched in v4.9.3.
>
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-mx2q-35m2-x2rh) - OpenZeppelin Contracts TransparentUpgradeableProxy clashing selector calls may not be delegated

>### Impact
>
>A function in the implementation contract may be inaccessible if its selector clashes with one of the proxy's own selectors. Specifically, if the clashing function has a different signature with incompatible ABI encoding, the proxy could revert while attempting to decode the arguments from calldata.
>
>The probability of an accidental clash is negligible, but one could be caused deliberately.
>
>### Patches
>
>The issue has been fixed in v4.8.3.
>
>### Workarounds
>
>If a function appears to be inaccessible for this reason, it may be possible to craft the calldata such that ABI decoding does not fail at the proxy and the function is properly proxied through.
>
>### References
>
>https://github.com/OpenZeppelin/openzeppelin-contracts/pull/4154
>
- `@openzeppelin/contracts` - <b>MODERATE</b> - [Link](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-5h3x-9wvq-w4m2) - OpenZeppelin Contracts's governor proposal creation may be blocked by frontrunning

>### Impact
>
>By frontrunning the creation of a proposal, an attacker can become the proposer and gain the ability to cancel it. The attacker can do this repeatedly to try to prevent a proposal from being proposed at all.
>
>This impacts the `Governor` contract in v4.9.0 only, and the `GovernorCompatibilityBravo` contract since v4.3.0.
>
>### Patches
>
>The problem has been patched in 4.9.1 by introducing opt-in frontrunning protection.
>
>### Workarounds
>
>Submit the proposal creation transaction to an endpoint with frontrunning protection.
>
>### Credit
>
>Reported by Lior Abadi and Joaquin Pereyra from Coinspect.
>
>### References
>
>https://www.coinspect.com/openzeppelin-governor-dos/


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1)


## NonCritical


---
### [NC&#x2011;1] Avoid mutating `function`/`modifier` parameters
Use a local variable instead

<details>
<summary><i>There are 74 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit incomingBid
157:                     incomingBid.ercAmount -= lowestSell.ercAmount; 

/// @audit b
160:                         b.matchedShortId = lowestSell.id; 
/// @audit b
161:                         b.prevShortId = lowestSell.prevId;

/// @audit b
165:                         b.matchedAskId = lowestSell.id; 

/// @audit b
167:                         b.askId = lowestSell.nextId; 

/// @audit b
172:                             b.matchedShortId = lowestSell.id; 
/// @audit b
173:                             b.prevShortId = lowestSell.prevId;

/// @audit b
176:                             b.matchedAskId = lowestSell.id; 

/// @audit b
182:                             b.dustShortId = lowestSell.id; 

/// @audit b
186:                             b.dustAskId = lowestSell.id; 

/// @audit b
/// @audit b
191:                             b.dustShortId = b.dustAskId = 0; 

/// @audit incomingBid
194:                     incomingBid.ercAmount = 0; 

/// @audit matchTotal
229:             matchTotal.shortFillEth += shortFillEth; 

/// @audit matchTotal
233:                 matchTotal.ratesQueried = true; 
/// @audit matchTotal
234:                 matchTotal.ercDebtRate = Asset.ercDebtRate;
/// @audit matchTotal
235:                 matchTotal.dethYieldRate = s.vault[Asset.vault].dethYieldRate;

/// @audit matchTotal
256:             matchTotal.askFillErc += fillErc; 

/// @audit matchTotal
259:         matchTotal.fillErc += fillErc; 
/// @audit matchTotal
260:         matchTotal.fillEth += fillEth;
/// @audit matchTotal
261:         matchTotal.lastMatchPrice = lowestSell.price;

/// @audit b
394:             b.isMovingBack = true; 
/// @audit b
395:             b.shortId = b.prevShortId;

/// @audit b
397:             b.firstShortIdBelowOracle = b.prevShortId; 
/// @audit b
398:             b.shortId = s.shorts[asset][b.shortHintId].nextId;

/// @audit b
403:                 b.isMovingFwd = true; 

/// @audit b
406:             b.shortId = lowestSell.nextId; 
```
[157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L157), [160](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L160-L161), [165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L165), [167](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L167), [172](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L172-L173), [176](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L176), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L182), [186](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L186), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L191), [194](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L194), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L229), [233](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L233-L235), [256](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L256), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L259-L261), [394](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L394-L395), [397](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L397-L398), [403](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L403), [406](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L406)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit dethAmount
113:                     dethAmount -= fee; 
```
[113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L113)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit m
162:         m.loseCollateral = m.cRatio <= m.penaltyCR; 

/// @audit m
176:             m.loseCollateral = true; 

/// @audit m
178:             m.ethDebt = TAPP.ethEscrowed; 

/// @audit m
180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast) 

/// @audit m
190:         m.ercDebtMatched = m.short.ercDebt - ercAmountLeft; 

/// @audit m
199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast) 

/// @audit m
216:         m.totalFee += tappFee + callerFee; 

/// @audit m
224:             m.totalFee -= m.gasFee; 

/// @audit m
249:                 m.short.collateral -= decreaseCol; 

/// @audit m
255:             m.short.ercDebt -= m.ercDebtMatched; 
/// @audit m
256:             m.short.collateral -= decreaseCol;
```
[162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L162), [176](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L176), [178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L178), [180](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180), [190](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L190), [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L199), [216](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L216), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L224), [249](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L249), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L255-L256)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit amount
57:             amount -= creditReth; 

/// @audit amount
87:             amount -= creditSteth; 
```
[57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L57), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L87)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit matchTotal
48:             matchTotal.dittoMatchedShares += shares; 

/// @audit incomingOrder
184:         incomingOrder.prevId = prevId; 
/// @audit incomingOrder
185:         incomingOrder.nextId = nextId;

/// @audit incomingOrder
192:             incomingOrder.prevOrderType = orders[asset][canceledID].orderType; 

/// @audit orders
197:                 orders[asset][C.HEAD].prevId = prevCanceledID; 

/// @audit orders
201:                 orders[asset][C.HEAD].prevId = C.HEAD; 

/// @audit incomingOrder
204:             id = incomingOrder.id = canceledID; 

/// @audit orders
212:         orders[asset][id] = incomingOrder; 

/// @audit orders
214:             orders[asset][nextId].prevId = incomingOrder.id; 

/// @audit orders
217:         orders[asset][prevId].nextId = incomingOrder.id; 

/// @audit orders
297:         orders[asset][orders[asset][id].nextId].prevId = orders[asset][id].prevId; 
/// @audit orders
298:         orders[asset][orders[asset][id].prevId].nextId = orders[asset][id].nextId;

/// @audit orders
333:         orders[asset][id].orderType = cancelledOrMatched; 
/// @audit orders
334:         orders[asset][C.HEAD].prevId = id;

/// @audit orders
340:             orders[asset][id].prevId = prevHEAD; 

/// @audit orders
347:             orders[asset][id].prevId = C.HEAD; 

/// @audit orderType
410:         orderType = normalizeOrderType(orderType); 

/// @audit hintId
457:                 hintId = prevId; 

/// @audit hintId
459:                 hintId = nextId; 

/// @audit orders
487:             orders[asset][id].prevId = C.HEAD; 
/// @audit orders
488:             orders[asset][C.HEAD].nextId = id;

/// @audit orders
542:             orders[asset][nextAskId].prevId = headId; 

/// @audit orders
544:         orders[asset][headId].nextId = nextAskId; 

/// @audit incomingAsk
578:                     incomingAsk.ercAmount = 0; 

/// @audit incomingAsk
584:                     incomingAsk.ercAmount -= highestBid.ercAmount; 

/// @audit incomingAsk
612:                     incomingAsk.ercAmount = 0; 

/// @audit matchTotal
675:         matchTotal.fillEth += matchTotal.colUsed; 

/// @audit matchTotal
718:             matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR)); 

/// @audit matchTotal
720:         matchTotal.fillErc += fillErc; 
/// @audit matchTotal
721:         matchTotal.fillEth += fillEth;
/// @audit matchTotal
722:         matchTotal.lastMatchPrice = highestBid.price;
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L48), [184](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L184-L185), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L192), [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L197), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L201), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L204), [212](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L212), [214](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L214), [217](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L217), [297](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L297-L298), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L333-L334), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L340), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L347), [410](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L410), [457](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L457), [459](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L459), [487](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L487-L488), [542](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L542), [544](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L544), [578](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L578), [584](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L584), [612](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L612), [675](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L675), [718](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L718), [720](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L720-L722)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit short
159:             short.ercDebt += ercDebt; 
/// @audit short
160:             short.ercDebtRate = ercDebtRate;
```
[159](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L159-L160)

</details>


---
### [NC&#x2011;2] Chainlink oracle `roundId` and `answeredIn` variables no longer contain useful information
The new Chainlink [OCR](https://docs.chain.link/architecture-overview/off-chain-reporting) methodology no longer relies on rounds, so adding checks related to the `roundId`/`answeredIn` return values is unnecessary, and may cause issues down the line.


<i>There are 6 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOracle.sol

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


---
### [NC&#x2011;3] Codebase should implement formal verification testing
Formal verification is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification/property/invariant, using formal methods of mathematics.

Some tools that are currently available to perform these tests on smart contracts are [SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html) and [Certora Prover](https://www.certora.com/).


---
### [NC&#x2011;4] Complicated functions should have explicit comments
Large and/or complex functions should have more comments to better explain the purpose of each logic step.

<details>
<summary><i>There are 7 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit function is 74 lines long
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit function is 69 lines long
142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit function is 155 lines long
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

/// @audit function is 77 lines long
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit function is 70 lines long
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit function is 70 lines long
556:     function sellMatchAlgo( 
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {

/// @audit function is 70 lines long
882:     function cancelShort(address asset, uint16 id) internal { 
```
[556](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882)

</details>


---
### [NC&#x2011;5] Consider adding a block/deny-list
Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens

<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers { 
21:     using U256 for uint256;
22:     using U88 for uint88;
23:     using U80 for uint80;
24:     using {LibOrders.isShort} for STypes.Order;
25: 
26:     /**
27:      * @notice Creates bid order in market
28:      * @dev IncomingBid created here instead of BidMatchAlgo to prevent stack too deep
29:      *
30:      * @param asset The market that will be impacted
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20-L30)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using LibBridge for uint256;
22:     using LibBridge for address;
23:     using LibBridgeRouter for uint256;
24:     using LibVault for uint256;
25: 
26:     address private immutable rethBridge;
27:     address private immutable stethBridge;
28: 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L28)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers { 
20:     using U256 for uint256;
21:     using U80 for uint80;
22:     using U88 for uint88;
23:     using LibSRUtil for STypes.ShortRecord;
24:     using {LibAsset.burnMsgSenderDebt} for address;
25: 
26:     address private immutable dusd;
27: 
28:     constructor(address _dusd) {
29:         dusd = _dusd;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19-L29)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers { 
22:     using LibShortRecord for STypes.ShortRecord;
23:     using U256 for uint256;
24:     using U96 for uint96;
25:     using U88 for uint88;
26:     using U80 for uint80;
27: 
28:     address private immutable dusd;
29: 
30:     constructor(address _dusd) {
31:         dusd = _dusd;
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21-L31)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers { 
22:     using LibSRUtil for STypes.ShortRecord;
23:     using LibShortRecord for STypes.ShortRecord;
24:     using U256 for uint256;
25:     using U104 for uint104;
26:     using U88 for uint88;
27:     using U80 for uint80;
28:     using U64 for uint64;
29:     using U32 for uint32;
30: 
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21-L31)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using U80 for uint80;
22: 
23:     /**
24:      * @notice Creates limit short in market system
25:      * @dev incomingShort created here instead of AskMatchAlgo to prevent stack too deep
26:      * @dev Shorts can only be limits
27:      *
28:      * @param asset The market that will be impacted
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18-L28)

</details>


---
### [NC&#x2011;6] Consider disallowing transfers to `address(this)`

<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant { 

133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO { 
```
[101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133)


---
### [NC&#x2011;7] Consider making contracts `Upgradeable`
This allows for bugs to be fixed in production, at the expense of *significantly* increasing centralization.

<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit contract BidOrdersFacet is not upgradeable
20: contract BidOrdersFacet is Modifiers { 
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit contract BridgeRouterFacet is not upgradeable
18: contract BridgeRouterFacet is Modifiers { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit contract ExitShortFacet is not upgradeable
19: contract ExitShortFacet is Modifiers { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit contract PrimaryLiquidationFacet is not upgradeable
21: contract PrimaryLiquidationFacet is Modifiers { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit contract RedemptionFacet is not upgradeable
21: contract RedemptionFacet is Modifiers { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit contract ShortOrdersFacet is not upgradeable
18: contract ShortOrdersFacet is Modifiers { 
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18)

</details>


---
### [NC&#x2011;8] Consider using `delete` rather than assigning zero to clear values
The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic.

<details>
<summary><i>There are 17 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

158:                     lowestSell.ercAmount = 0; 

191:                             b.dustShortId = b.dustAskId = 0; 

194:                     incomingBid.ercAmount = 0; 
```
[158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L158), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L191), [194](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L194)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

56:             VaultUser.bridgeCreditReth = 0; 

69:                         VaultUser.bridgeCreditSteth = 0; 

86:             VaultUser.bridgeCreditSteth = 0; 

99:                         VaultUser.bridgeCreditReth = 0; 

167:                     VaultUserFrom.bridgeCreditReth = 0; 

176:                     VaultUserFrom.bridgeCreditSteth = 0; 

188:                     VaultUserFrom.bridgeCreditReth = 0; 
189:                     VaultUserFrom.bridgeCreditSteth = 0;
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L56), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L69), [86](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L86), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L99), [167](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L167), [176](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L176), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L188-L189)

```solidity
📁 File: contracts/libraries/LibOrders.sol

578:                     incomingAsk.ercAmount = 0; 

585:                     highestBid.ercAmount = 0; 

612:                     incomingAsk.ercAmount = 0; 
```
[578](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L578), [585](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L585), [612](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L612)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

138:         short.tokenId = 0; 

148:         nft.shortOrderId = 0; 
```
[138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L138), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L148)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

56:         secondsAgos[1] = 0; 
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L56)

</details>


---
### [NC&#x2011;9] Consider using named function arguments
When calling functions in external contracts with multiple arguments, consider using [named](https://docs.soliditylang.org/en/latest/control-structures.html#function-calls-with-named-parameters) function parameters, rather than positional ones.

<details>
<summary><i>There are 2 instances of this issue:</i></summary>

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

</details>


---
### [NC&#x2011;10] Constants in comparisons should appear on the left side
Putting constants on the left side of comparison statements is a best practice known as [Yoda conditions](https://en.wikipedia.org/wiki/Yoda_conditions). Although solidity's static typing system prevents accidental assignments within conditionals, adopting this practice can improve code readability and consistency, especially when working across multiple languages.

<details>
<summary><i>There are 32 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit move 0 to the left
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) { 

/// @audit move 0 to the left
281:         if (matchTotal.fillEth == 0) { 
```
[152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L152), [281](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L281)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit move 0 to the left
102:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

/// @audit move 0 to the left
134:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

/// @audit move 0 to the left
164:             if (vault == 0) revert Errors.InvalidBridge(); 
```
[102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit move 0 to the left
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback(); 

/// @audit move 0 to the left
99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback(); 

/// @audit move 0 to the left
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback(); 

/// @audit move 0 to the left
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow(); 
```
[53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L188)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit move msg.sender to the left
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself(); 

/// @audit move msg.sender to the left
361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort(); 

/// @audit move 0 to the left
371:         if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) { 
```
[229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L229), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361), [371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L371)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit move 0 to the left
14:         require(slate.length % 51 == 0, "Invalid data length"); 
```
[14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit move 0 to the left
/// @audit move 0 to the left
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice(); 

/// @audit move 0 to the left
/// @audit move 0 to the left
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 

/// @audit move 0 to the left
89:                 if (twapPrice == 0) { 

/// @audit move 0 to the left
/// @audit move 0 to the left
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 
/// @audit move 0 to the left
/// @audit move 0 to the left
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

/// @audit move 0 to the left
134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice(); 
```
[60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L89), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125-L126), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit move 0 to the left
/// @audit move 0 to the left
371:         if (hintId == 0 || nextId == 0) { 

/// @audit move 0 to the left
501:         if (b.matchedAskId != 0) { 

/// @audit move 0 to the left
505:         if (b.matchedShortId != 0) { 

/// @audit move 0 to the left
576:                 if (incomingAsk.ercAmount.mul(highestBid.price) == 0) { 

/// @audit move 0 to the left
677:         SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill; 
```
[371](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L371), [501](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L501), [505](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L505), [576](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L576), [677](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L677)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit move msg.sender to the left
59:             if (shorter == msg.sender) { 

/// @audit move 0 to the left
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed(); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L59), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L131)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit move 0 to the left
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) { 
```
[65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

</details>


---
### [NC&#x2011;11] `constant`s/`immutable`s redefined elsewhere
Consider defining each of these in only one contract so that values cannot become out of sync when only one location is updated (i.e. having `ContA.X`,`ContB.Y` is fine since they're different constant names in different files, but `ContA.X`, `ContB.X` is not since it's the same constant defined in multiple files with the same value). Even things like `decimals` and `VERSION` can employ file-level constants such as `PREFERRED_DECIMALS = 18` and `INITIAL_VERSION = "1.0.0"`

<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge; 
27:     address private immutable stethBridge;
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26-L27)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

26:     address private immutable dusd; 
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

28:     address private immutable dusd; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

</details>


---
### [NC&#x2011;12] `constructor` should emit an event
Use events to signal significant changes to off-chain monitoring tools.

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
### [NC&#x2011;13] Contract timekeeping will break earlier than the Ethereum network itself will stop working
When a timestamp is downcast from `uint256` to `uint32`, the value will wrap in the year 2106, and the contracts will break. Other downcasts will have different endpoints. Consider whether your contract is intended to live past the size of the type being used.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOrders.sol

32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast) 
```
[32](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L32)


---
### [NC&#x2011;14] `contract`/`library`/`interface` definitions should be defined in separate files
This helps to make tracking changes across commits easier, among other reasons. They can be combined into a single file later by importing multiple contracts, and using that file as the common import.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit IUniswapV3Pool, OracleLibrary
21: library OracleLibrary { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21)


---
### [NC&#x2011;15] Contracts should have all `public`/`external` functions exposed by `interface`s
The `contract`s should expose an `interface` so that other projects can more easily integrate with it, without having to develop their own non-standard variants.

<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit createBid, createForcedBid
20: contract BidOrdersFacet is Modifiers { 
21:     using U256 for uint256;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20-L21)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit getDethTotal, getBridges, deposit, depositEth, withdraw, withdrawTapp
18: contract BridgeRouterFacet is Modifiers { 
19:     using U256 for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L19)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit exitShortWallet, exitShortErcEscrowed, exitShort
19: contract ExitShortFacet is Modifiers { 
20:     using U256 for uint256;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19-L20)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit liquidate
21: contract PrimaryLiquidationFacet is Modifiers { 
22:     using LibShortRecord for STypes.ShortRecord;
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21-L22)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit proposeRedemption, disputeRedemption, claimRedemption, claimRemainingCollateral
21: contract RedemptionFacet is Modifiers { 
22:     using LibSRUtil for STypes.ShortRecord;
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21-L22)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit createLimitShort
18: contract ShortOrdersFacet is Modifiers { 
19:     using U256 for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18-L19)

</details>


---
### [NC&#x2011;16] Contracts should have full test coverage
A 100% test coverage is not foolproof, but it helps immensely in reducing the amount of bugs that may occur.


---
### [NC&#x2011;17] Custom errors should be used rather than `revert()`/`require()`
Custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/LibBytes.sol

14:         require(slate.length % 51 == 0, "Invalid data length"); 
```
[14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14)


---
### [NC&#x2011;18] Dependence on external protocols
External protocols should be monitored as such dependencies may introduce vulnerabilities if a vulnerability is found /introduced in the external protocol

<details>
<summary><i>There are 60 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

13: import {LibOracle} from "contracts/libraries/LibOracle.sol"; 

108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray); 

110:             b.oraclePrice = LibOracle.getPrice(asset); 
```
[13](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L13), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L108), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L110)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

14: import {LibOracle} from "contracts/libraries/LibOracle.sol"; 

135:             m.oraclePrice = LibOracle.getPrice(asset); 
```
[14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L14), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L135)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

13: import {LibOracle} from "contracts/libraries/LibOracle.sol"; 

75:         p.oraclePrice = LibOracle.getPrice(p.asset); 
```
[13](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L13), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L75)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

11: import {LibOracle} from "contracts/libraries/LibOracle.sol"; 

76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray); 

79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset); 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L11), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L76), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L79)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

8: import {OracleLibrary} from "contracts/libraries/UniswapOracleLibrary.sol"; 

118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH); 

120:         uint256 factorReth = unitRethTWAP.div(unitRethOracle); 

122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH); 

124:         uint256 factorSteth = unitWstethTWAP.div(unitWstethOracle); 
```
[8](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L8), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L118), [120](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L120), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L124)

```solidity
📁 File: contracts/libraries/LibOracle.sol

25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset(); 

27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) { 
28:             if (oracle == baseOracle) {

31:                 basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth); 

42:                 ) = oracle.latestRoundData(); 

44:                 oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp); 

48:             if (oracle == baseOracle) { 

59:                 ) = oracle.latestRoundData(); 

76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 

79:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth; 
80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

90:                     return chainlinkPriceInEth; 

98:                 if (chainlinkDiff <= twapDiff) { 
99:                     return chainlinkPriceInEth;

105:                         return chainlinkPriceInEth; 

110:                 return chainlinkPriceInEth; 

113:             return chainlinkPriceInEth; 

125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0 
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice); 
152:         s.bids[asset][C.HEAD].creationTime = oracleTime;

172:             return getOraclePrice(asset); 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L25), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27-L28), [31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L31), [42](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L42), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L44), [48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L48), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L59), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L79-L80), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L90), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L98-L99), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L105), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L110), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L113), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L125-L126), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L151-L152), [172](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L172)

```solidity
📁 File: contracts/libraries/LibOrders.sol

13: import {LibOracle} from "contracts/libraries/LibOracle.sol"; 

730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset); 

732:         asset.setPriceAndTime(oraclePrice, getOffsetTime()); 
733:         if (oraclePrice == savedPrice) {

761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice; 
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;

768:                 } else if (startingShortWithinOracleRange) { 

772:                 } else if (allShortUnderOraclePrice) { 

798:             _updateOracleAndStartingShort(asset, shortHintArray); 

804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset); 

806:             _updateOracleAndStartingShort(asset, shortHintArray); 

813:         uint256 savedPrice = LibOracle.getPrice(asset); 

942:             uint256 savedPrice = LibOracle.getPrice(asset); 

959:         uint256 savedPrice = LibOracle.getPrice(asset); 
```
[13](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L13), [730](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L730), [732](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L732-L733), [761](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L761-L763), [768](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L768), [772](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L772), [798](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L798), [804](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L804), [806](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L806), [813](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L813), [942](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L942), [959](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L959)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

115:                 uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt)); 
```
[115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L115)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos); 
```
[59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L59)

</details>


---
### [NC&#x2011;19] `else`-block not required
One level of nesting can be removed by not having an `else` block when the `if`-block returns, and `if (foo) { return 1; } else { return 2; }` becomes `if (foo) { return 1; } return 2;`

<details>
<summary><i>There are 21 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

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

347:             if (noAsks || shortPriceLessThanAskPrice) { 
348:                 return lowestShort;
349:             } else {
350:                 return lowestAsk;
351:             }
```
[106](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L106-L116), [150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L150-L202), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L347-L351)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

173:         if (dethTotalNew >= dethTotal) { 
174:             // when yield is positive 1 deth = 1 eth
175:             return amount;
176:         } else {
177:             // negative yield means 1 deth < 1 eth
178:             // @dev don't use mulU88 in rare case of overflow
179:             return amount.mul(dethTotalNew).divU88(dethTotal);
180:         }
```
[173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L173-L180)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) { 
39:             return false;
40:         } else {
41:             return true;
42:         }
```
[38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L38-L42)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

48:         if (bridgePointer == VAULT.BRIDGE_RETH) { 
49:             // Withdraw RETH
50:             creditReth = VaultUser.bridgeCreditReth;
51:             if (creditReth >= amount) {
52:                 VaultUser.bridgeCreditReth -= amount;
53:                 return 0;
54:             }
55: 
56:             VaultUser.bridgeCreditReth = 0;
57:             amount -= creditReth;
58:             creditSteth = VaultUser.bridgeCreditSteth;
59:             if (creditSteth < C.ROUNDING_ZERO) {
60:                 // Valid withdraw when no STETH credits
61:                 return amount;
62:             } else {
63:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64:                     // Can withdraw RETH using STETH credit when STETH bridge is empty
65:                     if (creditSteth >= amount) {
66:                         VaultUser.bridgeCreditSteth -= amount;
67:                         return 0;
68:                     } else {
69:                         VaultUser.bridgeCreditSteth = 0;
70:                         return amount - creditSteth;
71:                     }
72:                 } else {
73:                     // Must use available bridge credits on withdrawal
74:                     // @dev Prevents abusing bridge for arbitrage
75:                     revert Errors.MustUseExistingBridgeCredit();
76:                 }
77:             }
78:         } else {
79:             // Withdraw STETH
80:             creditSteth = VaultUser.bridgeCreditSteth;
81:             if (creditSteth >= amount) {
82:                 VaultUser.bridgeCreditSteth -= amount;
83:                 return 0;
84:             }
85: 
86:             VaultUser.bridgeCreditSteth = 0;
87:             amount -= creditSteth;
88:             creditReth = VaultUser.bridgeCreditReth;
89:             if (creditReth < C.ROUNDING_ZERO) {
90:                 // Valid withdraw when no RETH credits
91:                 return amount;
92:             } else {
93:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94:                     // Can withdraw STETH using RETH credit when RETH bridge is empty
95:                     if (creditReth >= amount) {
96:                         VaultUser.bridgeCreditReth -= amount;
97:                         return 0;
98:                     } else {
99:                         VaultUser.bridgeCreditReth = 0;
100:                         return amount - creditReth;
101:                     }
102:                 } else {
103:                     // Must use available bridge credits on withdrawal
104:                     // @dev Prevents abusing bridge for arbitrage
105:                     revert Errors.MustUseExistingBridgeCredit();
106:                 }
107:             }
108:         }

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
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L48-L108), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L131-L140)

```solidity
📁 File: contracts/libraries/LibOracle.sol

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

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) { 
170:             return getPrice(asset);
171:         } else {
172:             return getOraclePrice(asset);
173:         }
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L28-L46), [48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L48-L65), [85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L85-L114), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169-L173)

```solidity
📁 File: contracts/libraries/LibOrders.sol

383:         } else if (direction == C.NEXT) { 
384:             return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
385:         } else {
386:             uint16 prevId = orders[asset][hintId].prevId;
387:             return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);
388:         }

574:             if (incomingAsk.price <= highestBid.price) { 
575:                 // Consider ask filled if only dust amount left
576:                 if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577:                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578:                     incomingAsk.ercAmount = 0;
579:                     matchIncomingSell(asset, incomingAsk, matchTotal);
580:                     return;
581:                 }
582:                 matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
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
620:                 if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621:                     addSellOrder(incomingAsk, asset, orderHintArray);
622:                 }
623:                 return;
624:             }
```
[383](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L383-L388), [574](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L574-L624)

</details>


---
### [NC&#x2011;20] Events should be emitted before external calls
Ensure that events follow the best practice of check-effects-interaction, and are emitted before external calls.

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit _cancelShort() on line 295
332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc); 
```
[332](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L332)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit addDeth() on line 70
72:         emit Events.Deposit(bridge, msg.sender, dethAmount); 

/// @audit addDeth() on line 88
90:         emit Events.DepositEth(bridge, msg.sender, dethAmount); 

/// @audit withdraw() on line 121
122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee); 

/// @audit withdraw() on line 142
143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount); 
```
[72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L72), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L90), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L122), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L143)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit checkShortMinErc() on line 67
75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount); 

/// @audit checkShortMinErc() on line 120
128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount); 

/// @audit disburseCollateral() on line 208
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled); 
```
[75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L75), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L128), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L210)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit checkRecoveryModeViolation() on line 75
87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched); 
```
[87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L87)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit InsufficientETHEscrowed() on line 208
210:         emit Events.ProposeRedemption(p.asset, msg.sender); 

/// @audit InvalidRedemption() on line 251
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer); 

/// @audit readProposalData() on line 318
333:         emit Events.ClaimRedemption(asset, msg.sender); 
```
[210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L210), [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L333)

</details>


---
### [NC&#x2011;21] Extraneous whitespace
See the [whitespace](https://docs.soliditylang.org/en/v0.8.16/style-guide.html#whitespace-in-expressions) section of the Solidity Style Guide


<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOracle.sol

35:                 ( 
36:                     uint80 roundID,
37:                     int256 price,
38:                     /*uint256 startedAt*/
39:                     ,
40:                     uint256 timeStamp,
41:                     /*uint80 answeredInRound*/
42:                 ) = oracle.latestRoundData();

52:                 ( 
53:                     uint80 roundID,
54:                     int256 price,
55:                     /*uint256 startedAt*/
56:                     ,
57:                     uint256 timeStamp,
58:                     /*uint80 answeredInRound*/
59:                 ) = oracle.latestRoundData();
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L35-L42), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L52-L59)


---
### [NC&#x2011;22] For loops in `public` or `external` functions should be avoided due to high gas costs and possible DOS
In Solidity, for loops can potentially cause Denial of Service (DoS) attacks if not handled carefully. DoS attacks can occur when an attacker intentionally exploits the gas cost of a function, causing it to run out of gas or making it too expensive for other users to call. Below are some scenarios where for loops can lead to DoS attacks: Nested for loops can become exceptionally gas expensive and should be used sparingly.


<i>There are 3 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit line 78
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

/// @audit line 242
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

/// @audit line 321
310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant { 
311:         uint256 vault = s.asset[asset].vault;
312:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
313:         STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
316: 
317:         MTypes.ProposalData[] memory decodedProposalData =
318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
319: 
320:         uint88 totalColRedeemed;
321:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
322:             MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323:             totalColRedeemed += currentProposal.colRedeemed;
324:             _claimRemainingCollateral({
325:                 asset: asset,
326:                 vault: vault,
327:                 shorter: currentProposal.shorter,
328:                 shortId: currentProposal.shortId
329:             });
330:         }
331:         redeemerVaultUser.ethEscrowed += totalColRedeemed;
332:         delete redeemerAssetUser.SSTORE2Pointer;
333:         emit Events.ClaimRedemption(asset, msg.sender);
334:     }
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L211), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L301), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310-L334)


---
### [NC&#x2011;23] Function can be declared as `pure`
Functions below do not interact with the state of the contract and can be declared as `pure`. It will save gas and make the code more readable.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) { 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40)


---
### [NC&#x2011;24] Function definition modifier order does not follow Solidity style guide
See [this](https://docs.soliditylang.org/en/v0.8.19/style-guide.html#function-declaration) link for an explanation of the correct ordering.


<i>There are 18 instaces of this issue:</i>

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit internal should be before modifier
/// @audit view should be before modifier
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 
56:         internal
57:         view
58:         returns (STypes.Order[] memory)
59:     {

/// @audit private should be before modifier
173:     function addOrder( 
174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
175:         address asset,
176:         STypes.Order memory incomingOrder,
177:         uint16 hintId
178:     ) private {

/// @audit private should be before modifier
/// @audit view should be before modifier
260:     function verifySellId( 
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

/// @audit internal should be before modifier
289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

/// @audit internal should be before modifier
314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal { 

/// @audit private should be before modifier
320:     function _reuseOrderIds( 
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

/// @audit internal should be before modifier
/// @audit view should be before modifier
362:     function findPrevOfIncomingId( 
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

/// @audit internal should be before modifier
/// @audit view should be before modifier
402:     function verifyId( 
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {

/// @audit internal should be before modifier
/// @audit view should be before modifier
440:     function getOrderId( 
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

/// @audit internal should be before modifier
474:     function updateBidOrdersOnMatch( 
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled
479:     ) internal {

/// @audit private should be before modifier
532:     function _updateOrders( 
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {

/// @audit internal should be before modifier
/// @audit view should be before modifier
826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {
```
[55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L289), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L314), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320-L326), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L409), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [474](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L474-L479), [532](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L532-L537), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830)


---
### [NC&#x2011;25] Functions should be named in mixedCase style
According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#function-names) function names should be in `mixedCase` (lowerCamelCase)Rule exceptions
- Allow `_` at the beginning of the mixedCase match for `private`/`internal` functions.

<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit validRedemptionSR
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit convertCR
35:     function convertCR(uint16 cr) internal pure returns (uint256) { 
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit estimateTWAP
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)

</details>


---
### [NC&#x2011;26] High cyclomatic complexity
Functions with high cyclomatic complexity are harder to understand, test, and maintain. Consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns.

[Learn More About Cyclomatic Complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity)

<details>
<summary><i>There are 17 instances of this issue:</i></summary>

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

275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private { 
```
[240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61)

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

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144)

```solidity
📁 File: contracts/libraries/LibOracle.sol

69:     function baseOracleCircuitBreaker( 
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {
```
[69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75)

```solidity
📁 File: contracts/libraries/LibOrders.sol

499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal { 

556:     function sellMatchAlgo( 
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 

826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {

882:     function cancelShort(address asset, uint16 id) internal { 
```
[499](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L499), [556](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {
```
[72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75)

</details>


---
### [NC&#x2011;27] `if`-statement can be converted to a ternary
The code can be made more compact while also increasing readability by converting the following `if`-statements to ternaries (e.g. `foo += (x > y) ? a : b`)

<details>
<summary><i>There are 13 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

320:                 if (b.isMovingFwd) { 
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }

347:             if (noAsks || shortPriceLessThanAskPrice) { 
348:                 return lowestShort;
349:             } else {
350:                 return lowestAsk;
351:             }
```
[320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L320-L324), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L347-L351)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

173:         if (dethTotalNew >= dethTotal) { 
174:             // when yield is positive 1 deth = 1 eth
175:             return amount;
176:         } else {
177:             // negative yield means 1 deth < 1 eth
178:             // @dev don't use mulU88 in rare case of overflow
179:             return amount.mul(dethTotalNew).divU88(dethTotal);
180:         }
```
[173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L173-L180)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) { 
39:             return false;
40:         } else {
41:             return true;
42:         }
```
[38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L38-L42)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

85:         if (incomingShort.price < p.oraclePrice) { 
86:             LibOrders.addShort(asset, incomingShort, orderHintArray);
87:         } else {
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89:         }
```
[85](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L85-L89)

```solidity
📁 File: contracts/libraries/LibOracle.sol

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) { 
170:             return getPrice(asset);
171:         } else {
172:             return getOraclePrice(asset);
173:         }
```
[169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169-L173)

```solidity
📁 File: contracts/libraries/LibOrders.sol

90:         if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) { 
91:             hintId = C.HEAD;
92:         } else {
93:             hintId = findOrderHintId(s.bids, asset, orderHintArray);
94:         }

111:         if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) { 
112:             hintId = C.HEAD;
113:         } else {
114:             hintId = findOrderHintId(s.asks, asset, orderHintArray);
115:         }

132:         if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) { 
133:             hintId = C.HEAD;
134:         } else {
135:             hintId = findOrderHintId(s.shorts, asset, orderHintArray);
136:         }

196:             if (prevCanceledID != C.HEAD) { 
197:                 orders[asset][C.HEAD].prevId = prevCanceledID;
198:             } else {
199:                 // BEFORE: HEAD <- (ID) <- HEAD <-> .. <-> PREV <----------> NEXT
200:                 // AFTER1: HEAD <--------- HEAD <-> .. <-> PREV <-> [ID] <-> NEXT
201:                 orders[asset][C.HEAD].prevId = C.HEAD;
202:             }

339:         if (prevHEAD != C.HEAD) { 
340:             orders[asset][id].prevId = prevHEAD;
341:         } else {
342:             // if this is the first ID cancelled
343:             // HEAD.prevId needs to be HEAD
344:             // and one of the cancelled id.prevID should point to HEAD
345:             // BEFORE: HEAD <--------- HEAD <-> ... [ID]
346:             // AFTER1: HEAD <- [ID] <- HEAD <-> ...
347:             orders[asset][id].prevId = C.HEAD;
348:         }

791:         if (incomingOrder.price >= savedPrice) { 
792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
793:         } else {
794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
795:         }

944:             if (prevPrice >= savedPrice) { 
945:                 Asset.startingShortId = shortOrder.prevId;
946:             } else {
947:                 Asset.startingShortId = shortOrder.nextId;
948:             }
```
[90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L90-L94), [111](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L111-L115), [132](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L132-L136), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L196-L202), [339](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L339-L348), [791](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L791-L795), [944](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L944-L948)

</details>


---
### [NC&#x2011;28] Imports could be organized more systematically
The contract's interface should be imported first, followed by each of the interfaces it uses, followed by all other files. The examples below do not follow this layout.

<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
7: 
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
9: import {Errors} from "contracts/libraries/Errors.sol";
10: import {Events} from "contracts/libraries/Events.sol";
11: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";
12: import {LibAsset} from "contracts/libraries/LibAsset.sol";
13: import {LibOracle} from "contracts/libraries/LibOracle.sol";
14: import {LibOrders} from "contracts/libraries/LibOrders.sol";
15: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
16: import {C} from "contracts/libraries/Constants.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L2-L16)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IBridge} from "contracts/interfaces/IBridge.sol";
7: 
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
9: import {Errors} from "contracts/libraries/Errors.sol";
10: import {Events} from "contracts/libraries/Events.sol";
11: import {LibBridge} from "contracts/libraries/LibBridge.sol";
12: import {LibBridgeRouter} from "contracts/libraries/LibBridgeRouter.sol";
13: import {LibVault} from "contracts/libraries/LibVault.sol";
14: import {C, VAULT} from "contracts/libraries/Constants.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L2-L14)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
7: 
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
9: import {Errors} from "contracts/libraries/Errors.sol";
10: import {Events} from "contracts/libraries/Events.sol";
11: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";
12: import {LibAsset} from "contracts/libraries/LibAsset.sol";
13: import {LibOrders} from "contracts/libraries/LibOrders.sol";
14: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
15: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L2-L15)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
7: 
8: import {Errors} from "contracts/libraries/Errors.sol";
9: import {Events} from "contracts/libraries/Events.sol";
10: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";
11: import {Modifiers} from "contracts/libraries/AppStorage.sol";
12: import {LibAsset} from "contracts/libraries/LibAsset.sol";
13: import {LibOrders} from "contracts/libraries/LibOrders.sol";
14: import {LibOracle} from "contracts/libraries/LibOracle.sol";
15: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
16: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";
17: import {C} from "contracts/libraries/Constants.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L2-L17)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {Errors} from "contracts/libraries/Errors.sol";
7: import {Events} from "contracts/libraries/Events.sol";
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
9: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";
10: import {LibAsset} from "contracts/libraries/LibAsset.sol";
11: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
12: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";
13: import {LibOracle} from "contracts/libraries/LibOracle.sol";
14: import {LibOrders} from "contracts/libraries/LibOrders.sol";
15: import {LibBytes} from "contracts/libraries/LibBytes.sol";
16: import {C} from "contracts/libraries/Constants.sol";
17: 
18: import {SSTORE2} from "solmate/utils/SSTORE2.sol";
19: import {console} from "contracts/libraries/console.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L2-L19)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21; 
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {Errors} from "contracts/libraries/Errors.sol";
7: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
9: import {LibOrders} from "contracts/libraries/LibOrders.sol";
10: import {LibAsset} from "contracts/libraries/LibAsset.sol";
11: import {LibOracle} from "contracts/libraries/LibOracle.sol";
12: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
13: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";
14: import {C} from "contracts/libraries/Constants.sol";
```
[2](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L2-L14)

</details>


---
### [NC&#x2011;29] Inconsistent spacing in comments
Some lines use `// x` and some use `//x`. The instances below point out the usages that don't follow the majority, within each file

<details>
<summary><i>There are 25 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Space: `1`
/// @audit No space: `25`
1: // SPDX-License-Identifier: GPL-3.0-only 

18: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1), [18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L18)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Space: `1`
/// @audit No space: `8`
1: // SPDX-License-Identifier: GPL-3.0-only 

16: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L1), [16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L16)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Space: `1`
/// @audit No space: `10`
1: // SPDX-License-Identifier: GPL-3.0-only 

17: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L1), [17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L17)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Space: `1`
/// @audit No space: `32`
1: // SPDX-License-Identifier: GPL-3.0-only 

19: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L1), [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L19)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit Space: `1`
/// @audit No space: `5`
1: // SPDX-License-Identifier: GPL-3.0-only 

16: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L1), [16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L16)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Space: `1`
/// @audit No space: `28`
1: // SPDX-License-Identifier: GPL-3.0-only 

14: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L1), [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L14)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit Space: `1`
/// @audit No space: `9`
1: // SPDX-License-Identifier: GPL-3.0-only 

7: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1), [7](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L7)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Space: `1`
/// @audit No space: `12`
1: // SPDX-License-Identifier: GPL-3.0-only 

14: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L1), [14](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L14)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit Space: `1`
/// @audit No space: `88`
1: // SPDX-License-Identifier: GPL-3.0-only 

18: // import {console} from "contracts/libraries/console.sol"; 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L1), [18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L18)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Space: `2`
/// @audit No space: `12`
1: // SPDX-License-Identifier: GPL-3.0-only 

15: // import {console} from "contracts/libraries/console.sol"; 

17: // extra ShortRecord helpers, similar to LibShortRecord 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L1), [15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L15), [17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L17)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Space: `3`
/// @audit No space: `10`
1: // SPDX-License-Identifier: GPL-2.0-or-later 

4: // https://github.com/Uniswap/v3-periphery/blob/b325bb0905d922ae61fcc7df85ee802e8df5e96c/contracts/libraries/OracleLibrary.sol 

19: /// @title Oracle library 
20: /// @notice Provides functions to integrate with V3 pool oracle
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L1), [4](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L4), [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L19-L20)

</details>


---
### [NC&#x2011;30] Initialisms should be capitalized
According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#naming-styles) initialisms such as "NFT", "ERC", etc should be capitalized.

<details>
<summary><i>There are 18 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

31:      * @param price Unit price in eth for erc 
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L31)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge; 
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

52:         uint256 ercDebt = short.ercDebt; 

60:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral; 
```
[52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L52), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L60)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

36:      * @dev Primary liquidation method 

58:         // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L36), [58](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L58)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

36:         // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition 

138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt); 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L36), [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L138)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

29:      * @param price Unit price in eth for erc sold 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L29)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21)

```solidity
📁 File: contracts/libraries/LibBytes.sol

25:             uint88 ercDebtRedeemed; // bytes11 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L25)

```solidity
📁 File: contracts/libraries/LibOracle.sol

80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether; 

151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice); 
```
[80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L80), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L151)

```solidity
📁 File: contracts/libraries/LibOrders.sol

36:         return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES; 

99:         uint88 eth = order.ercAmount.mulU88(order.price); 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L36), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L99)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 

64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) { 

127:         STypes.NFT storage nft = s.nftMapping[tokenId]; 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22), [64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L64), [127](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L127)

</details>


---
### [NC&#x2011;31] Invalid NatSpec comment style
NatSpec [must](https://docs.soliditylang.org/en/latest/natspec-format.html#documentation-example) begin with `///`, or use the `/* ... */` syntax.

<details>
<summary><i>There are 112 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

70:         // @dev leave empty, don't need hint for market buys 

73:         // @dev update oracle in callers 

102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below) 

107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId 

113:             // @dev no match, add to market if limit order 

140:             // @dev Handles scenario when no sells left after partial fill 

291:         // @dev needs to happen after updateSellOrdersOnMatch() 

309:             // @dev Approximates the startingShortId after bid is fully executed 

334:         // @dev match price is based on the order that was already on orderbook 

339:     // @dev If neither conditions are true, it returns an empty Order struct 

344:             // @dev Setting lowestSell after comparing short and ask prices 

353:             // @dev Handles scenario when there are no shorts 

393:             // @dev shortHintId should always be the first thing matched 

401:             // @dev Only set to true if actually moving forward 
```
[70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L70), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L73), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L102), [107](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L107), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L113), [140](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L140), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L291), [309](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L309), [334](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L334), [339](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L339), [344](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L344), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L353), [393](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L393), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L401)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

67:         // @dev amount after deposit might be less, if bridge takes a fee 

147:     // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions 

178:             // @dev don't use mulU88 in rare case of overflow 
```
[67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L67), [147](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L147), [178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L178)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder 

168:         // @dev if short order was cancelled, fully exit 

203:             // @dev Only allow partial exit if the CR is same or better than before 

206:             // @dev collateral already subtracted in exitShort() 
```
[157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L157), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L168), [203](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L203), [206](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L206)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

55:         // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost 

58:         // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile 

67:         // @dev liquidate requires more up-to-date oraclePrice 

72:         // @dev Can liquidate as long as CR is low enough 

95:     // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call 

158:         // @dev Provide higher price to better ensure it can fully fill the liquidation 

164:         // @dev Increase ethEscrowed by shorter's full collateral for forced bid 

177:             // @dev Max ethDebt can only be the ethEscrowed in the TAPP 

186:         // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP 

192:         // @dev virtually burning the repurchased debt 

197:         // @dev manually setting basefee to 1,000,000 in foundry.toml; 
198:         // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP

217:         // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out. 
```
[55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L55), [58](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L58), [67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L67), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L72), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L95), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L158), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L164), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L177), [186](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L186), [192](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L192), [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L197-L198), [217](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L217)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

36:         // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition 
37:         // @dev Proposer can't redeem on self

72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption 

82:             // @dev Setting this above _onlyValidShortRecord to allow skipping 

92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold 

95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount 

100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate 

108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR 
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()

127:             // @dev directly write the properties of MTypes.ProposalData into bytes 

145:         // @dev SSTORE2 the entire proposalData after validating proposalInput 

156:         // @dev Calculate the dispute period 
157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x

261:             // @dev All proposals from the incorrectIndex onward will be removed 
262:             // @dev Thus the proposer can only redeem a portion of their original slate

278:             // @dev Update the redeemer's SSTORE2Pointer 

282:                 // @dev this implies everything in the redeemer's proposal was incorrect 

287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted) 
288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees

295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied) 

356:         // @dev Only need to read up to the position of the SR to be claimed 

372:             // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already 

375:             // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS 

381:     // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated 

391:         // @dev Calculate Asset.ercDebt prior to proposal 

393:         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD) 
```
[36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L36-L37), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L72), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L82), [92](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L92), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L95), [100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L100), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L108-L109), [127](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L127), [145](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L145), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L156-L157), [261](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L261-L262), [278](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L278), [282](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L282), [287](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L287-L288), [295](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L295), [356](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L356), [372](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L372), [375](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L375), [381](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L381), [391](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L391), [393](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L393)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

47:         // @dev create "empty" SR. Fail early. 

55:         // @dev minShortErc needs to be modified (bigger) when cr < 1 

74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId 

84:         // @dev reading spot oracle price 
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L47), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L55), [74](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L74), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L84)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

74:                     // @dev Prevents abusing bridge for arbitrage 

104:                     // @dev Prevents abusing bridge for arbitrage 

112:     // @dev Only applicable to VAULT.ONE which has mixed LST 

143:     // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system 
```
[74](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L74), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L104), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L112), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L143)

```solidity
📁 File: contracts/libraries/LibOracle.sol

29:                 // @dev multiply base oracle by 10**10 to give it 18 decimals of precision 

82:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink 

155:     // @dev Intentionally using creationTime for oracleTime. 

161:     // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos. 

167:     // @dev Allows caller to save gas since reading spot price costs ~16K 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L29), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L82), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L155), [161](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L161), [167](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L167)

```solidity
📁 File: contracts/libraries/LibOrders.sol

29:     // @dev in seconds 

43:         // @dev use the diff to get more time (2159), to prevent overflow at year 2106 

138:         // @dev: Only need to set this when placing incomingShort onto market 

172:     // @dev partial addOrder 

188:         // @dev (ID) is exiting, [ID] is inserted 

237:         // @dev: TAIL can't be prevId because it will always be last item in list 

267:         // @dev: TAIL can't be prevId because it will always be last item in list 

294:         // @dev (ID) is exiting, [ID] is inserted 

332:         // @dev mark as cancelled instead of deleting the order itself 

419:     // @dev not used to change state, just which methods to call 

507:                 // @dev Handles only matching one thing 
508:                 // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block

511:                 // @dev Handles moving forward only 

514:                 //@handles moving backwards only. 

518:                 // @dev Handle going backward and forward 

641:         // @dev match price is based on the order that was already on orderbook 

724:         // @dev this happens at the end so fillErc isn't affected in previous calculations 

760:                 // @dev force hint to be within 0.5% of oraclePrice 

769:                     // @dev prevShortPrice >= oraclePrice 

782:     // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%) 

790:         // @dev handle .5% deviations in either directions 

802:     // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough 

846:             // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD 

899:             // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId 
900:             // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId

905:                 // @dev prevents leaving behind a partially filled SR is under minShortErc 
906:                 // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc

928:                     // @dev update the eth refund amount 

931:                 // @dev virtually mint the increased debt 

962:         // @dev tithe is increased only if discount is greater than 1% 

964:             // @dev bound the new tithe amount between 25% and 100% 

967:             // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount 

970:             // @dev dethTitheMod is only set when setTithe is called. 

974:                 // @dev change back to original tithe percent 

981:         // @dev exists because of ShortOrderFacet contract size 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L29), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L43), [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L138), [172](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L172), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L188), [237](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L237), [267](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L267), [294](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L294), [332](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L332), [419](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L419), [507](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L507-L508), [511](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L511), [514](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L514), [518](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L518), [641](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L641), [724](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L724), [760](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L760), [769](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L769), [782](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L782), [790](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L790), [802](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L802), [846](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L846), [899](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L899-L900), [905](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L905-L906), [928](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L928), [931](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L931), [962](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L962), [964](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L964), [967](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L967), [970](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L970), [974](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L974), [981](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L981)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

89:                     // @dev The resulting SR will not have PartialFill status after cancel 

133:         // @dev shortOrderId is already validated in mintNFT 
```
[89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L89), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L133)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp 

69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick 
```
[58](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L58), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L69)

</details>


---
### [NC&#x2011;32] Large or complicated code bases should implement invariant tests
Large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts, should implement [invariant fuzzing tests](https://medium.com/coinmonks/smart-contract-fuzzing-d9b88e0b0a05). Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold. Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers, with properly and extensively-written invariants, can close this testing gap significantly.


---
### [NC&#x2011;33] Make use of Solidity's `using` keyword
The `using`-`for` [syntax](https://docs.soliditylang.org/en/latest/contracts.html#using-for) is the more common way of calling library functions.

<details>
<summary><i>There are 198 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit LibOrders
48:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray); 

/// @audit LibAsset
/// @audit Errors
87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize(); 

/// @audit Errors
90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed(); 

/// @audit LibOrders
98:         incomingBid.creationTime = LibOrders.getOffsetTime(); 

/// @audit LibOrders
/// @audit LibOracle
108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray); 

/// @audit LibOracle
110:             b.oraclePrice = LibOracle.getPrice(asset); 

/// @audit LibOrders
114:             LibOrders.addBid(asset, incomingBid, orderHintArray); 

/// @audit LibAsset
136:         uint256 minBidEth = LibAsset.minBidEth(asset); 

/// @audit LibOrders
143:                     LibOrders.addBid(asset, incomingBid, orderHintArray); 

/// @audit LibOrders
162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id); 

/// @audit LibOrders
166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id); 

/// @audit LibOrders
174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id); 

/// @audit LibOrders
177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id); 

/// @audit LibAsset
190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) { 

/// @audit LibOrders
199:                     LibOrders.addBid(asset, incomingBid, orderHintArray); 

/// @audit LibOrders
226:             uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR)); 
/// @audit LibOrders
227:             LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);

/// @audit LibShortRecord
243:             LibShortRecord.fillShortRecord( 
244:                 asset,
245:                 lowestSell.addr,
246:                 lowestSell.shortRecordId,
247:                 status,
248:                 shortFillEth,
249:                 fillErc,
250:                 matchTotal.ercDebtRate,
251:                 matchTotal.dethYieldRate
252:             );

/// @audit LibOrders
288:         LibOrders.updateSellOrdersOnMatch(asset, b); 

/// @audit Events
332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc); 

/// @audit LibOrders
335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice); 
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L48), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L87), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L90), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L98), [108](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L108), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L110), [114](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L114), [136](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L136), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L143), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L162), [166](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L166), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L174), [177](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L177), [190](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L190), [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L199), [226](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L226-L227), [243](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L243-L252), [288](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L288), [332](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L332), [335](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L335)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Errors
64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

/// @audit Events
72:         emit Events.Deposit(bridge, msg.sender, dethAmount); 

/// @audit Errors
83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit(); 

/// @audit Events
90:         emit Events.DepositEth(bridge, msg.sender, dethAmount); 

/// @audit Errors
102:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

/// @audit LibBridgeRouter
110:                 uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge); 

/// @audit Events
122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee); 

/// @audit Errors
134:         if (dethAmount == 0) revert Errors.ParameterIsZero(); 

/// @audit Events
143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount); 

/// @audit Errors
164:             if (vault == 0) revert Errors.InvalidBridge(); 
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L64), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L72), [83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L83), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L90), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L102), [110](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L110), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L122), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L134), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L143), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Errors
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback(); 

/// @audit LibSRUtil
61:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt); 
/// @audit LibShortRecord
62:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);

/// @audit LibSRUtil
67:         LibSRUtil.checkShortMinErc({ 
68:             asset: asset,
69:             initialStatus: initialStatus,
70:             shortOrderId: shortOrderId,
71:             shortRecordId: id,
72:             shorter: msg.sender
73:         });

/// @audit Events
75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount); 

/// @audit Errors
99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback(); 

/// @audit Errors
103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed(); 

/// @audit LibSRUtil
113:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt); 

/// @audit LibShortRecord
115:             LibShortRecord.deleteShortRecord(asset, msg.sender, id); 

/// @audit LibSRUtil
120:         LibSRUtil.checkShortMinErc({ 
121:             asset: asset,
122:             initialStatus: initialStatus,
123:             shortOrderId: shortOrderId,
124:             shortRecordId: id,
125:             shorter: msg.sender
126:         });

/// @audit Events
128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount); 

/// @audit LibOrders
152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray); 

/// @audit LibSRUtil
158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({ 
159:             asset: asset,
160:             initialStatus: short.status,
161:             shortOrderId: shortOrderId,
162:             shortRecordId: id,
163:             shorter: msg.sender
164:         });

/// @audit Errors
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback(); 

/// @audit Errors
178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral(); 

/// @audit Errors
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow(); 

/// @audit LibSRUtil
196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt); 
/// @audit LibShortRecord
197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy

/// @audit LibAsset
/// @audit Errors
201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount(); 

/// @audit Errors
204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR(); 

/// @audit LibSRUtil
208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt); 

/// @audit Events
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled); 
```
[53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L53), [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L61-L62), [67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L67-L73), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L75), [99](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L99), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L103), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L113), [115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L115), [120](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L120-L126), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L128), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L152), [158](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L158-L164), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L174), [178](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L178), [188](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L188), [196](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L196-L197), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L201), [204](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L204), [208](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L208), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L210)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Errors
54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf(); 

/// @audit Errors
56:         if (shortHintArray.length > 10) revert Errors.TooManyHints(); 

/// @audit LibSRUtil
59:         LibSRUtil.checkCancelShortOrder({ 
60:             asset: asset,
61:             initialStatus: s.shortRecords[asset][shorter][id].status,
62:             shortOrderId: shortOrderId,
63:             shortRecordId: id,
64:             shorter: shorter
65:         });

/// @audit LibOrders
68:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray); 

/// @audit LibAsset
73:         if (m.cRatio >= LibAsset.liquidationCR(m.asset)) { 

/// @audit LibSRUtil
/// @audit Errors
75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral(); 

/// @audit Events
87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched); 

/// @audit Errors
109:             revert Errors.NoSells(); 

/// @audit LibShortRecord
126:         LibShortRecord.updateErcDebt(asset, shorter, id); 

/// @audit LibAsset
134:             m.penaltyCR = LibAsset.penaltyCR(asset); 
/// @audit LibOracle
135:             m.oraclePrice = LibOracle.getPrice(asset);

/// @audit LibAsset
137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset); 
/// @audit LibAsset
138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);
/// @audit LibAsset
139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);

/// @audit Errors
174:                 revert Errors.CannotSocializeDebt(); 

/// @audit Errors
230:         if (a > type(uint88).max) revert Errors.InvalidAmount(); 

/// @audit LibSRUtil
246:             LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt); 
/// @audit LibShortRecord
247:             LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);

/// @audit LibSRUtil
260:             LibSRUtil.disburseCollateral(m.asset, m.shorter, decreaseCol, m.short.dethYieldRate, m.short.updatedAt); 

/// @audit LibShortRecord
265:                 LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id); 

/// @audit LibShortRecord
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

/// @audit LibSRUtil
282:             LibSRUtil.checkShortMinErc({ 
283:                 asset: m.asset,
284:                 initialStatus: m.short.status,
285:                 shortOrderId: m.shortOrderId,
286:                 shortRecordId: m.short.id,
287:                 shorter: m.shorter
288:             });
```
[54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56), [59](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L59-L65), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L68), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L73), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L75), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L87), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L109), [126](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L126), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L134-L135), [137](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L137-L139), [174](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L174), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L230), [246](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L246-L247), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L260), [265](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L265), [267](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L267-L276), [282](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L282-L288)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Errors
62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals(); 

/// @audit LibAsset
66:         uint256 minShortErc = LibAsset.minShortErc(p.asset); 

/// @audit Errors
68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

/// @audit Errors
70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed(); 

/// @audit Errors
73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions(); 

/// @audit LibOracle
75:         p.oraclePrice = LibOracle.getPrice(p.asset); 

/// @audit Errors
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder(); 
/// @audit LibOrders
113:                 LibOrders.cancelShort(asset, p.shortOrderId);

/// @audit LibSRUtil
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt); 

/// @audit Errors
143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc(); 

/// @audit SSTORE2
146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate); 

/// @audit LibOrders
154:         uint32 protocolTime = LibOrders.getOffsetTime(); 

/// @audit LibOrders
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime(); 

/// @audit Errors
205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh(); 

/// @audit Errors
208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed(); 

/// @audit Events
210:         emit Events.ProposeRedemption(p.asset, msg.sender); 

/// @audit Errors
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself(); 

/// @audit Errors
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 

/// @audit LibOrders
/// @audit Errors
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed(); 

/// @audit LibBytes
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength); 

/// @audit Errors
244:                 revert Errors.CannotDisputeWithRedeemerProposal(); 

/// @audit LibAsset
250:         uint256 minShortErc = LibAsset.minShortErc(d.asset); 
/// @audit Errors
251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();

/// @audit Events
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer); 

/// @audit LibOrders
289:             uint256 penaltyPct = LibOrders.min( 
/// @audit LibOrders
/// @audit LibAsset
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );

/// @audit Errors
299:             revert Errors.InvalidRedemptionDispute(); 

/// @audit Errors
314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
/// @audit LibOrders
/// @audit Errors
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

/// @audit LibBytes
318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength); 

/// @audit Events
333:         emit Events.ClaimRedemption(asset, msg.sender); 

/// @audit Errors
353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption(); 
/// @audit LibOrders
/// @audit Errors
354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

/// @audit LibBytes
358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1); 

/// @audit Errors
361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort(); 

/// @audit LibSRUtil
376:             LibSRUtil.disburseCollateral(asset, shorter, collateral, shortRecord.dethYieldRate, shortRecord.updatedAt); 
/// @audit LibShortRecord
377:             LibShortRecord.deleteShortRecord(asset, shorter, shortId);

/// @audit LibOrders
387:         uint32 protocolTime = LibOrders.getOffsetTime(); 

/// @audit LibOrders
396:         newBaseRate = LibOrders.min(newBaseRate, 1 ether); // cap baseRate at a maximum of 100% 

/// @audit LibOrders
401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether); 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L62), [66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L66), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L68), [70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L70), [73](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L73), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L75), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L112-L113), [138](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L138), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L143), [146](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L146), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L154), [202](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L202), [205](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L205), [208](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L208), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L210), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L229), [235](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L235), [237](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L237), [240](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L240), [244](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L244), [250](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L250-L251), [284](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284), [289](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L289-L291), [299](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L299), [314](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L314-L315), [318](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L318), [333](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L333), [353](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L353-L354), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L358), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L361), [376](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L376-L377), [387](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L387), [396](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L396), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit LibShortRecord
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0); 

/// @audit LibOrders
50:         uint256 cr = LibOrders.convertCR(shortOrderCR); 

/// @audit Errors
52:             revert Errors.InvalidCR(); 

/// @audit LibAsset
/// @audit LibAsset
56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset); 

/// @audit LibAsset
58:         p.minAskEth = LibAsset.minAskEth(asset); 
/// @audit Errors
59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();

/// @audit Errors
62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed(); 

/// @audit LibOrders
69:         incomingShort.creationTime = LibOrders.getOffsetTime(); 

/// @audit LibOrders
/// @audit LibOracle
76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray); 

/// @audit LibOracle
79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset); 
/// @audit LibSRUtil
80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
/// @audit Errors
81:             revert Errors.BelowRecoveryModeCR();

/// @audit LibOrders
86:             LibOrders.addShort(asset, incomingShort, orderHintArray); 

/// @audit LibOrders
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth); 
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L48), [50](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L50), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L52), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56), [58](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L58-L59), [62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L62), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L69), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L76), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L79-L81), [86](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L86), [88](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L88)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Errors
75:                     revert Errors.MustUseExistingBridgeCredit(); 

/// @audit Errors
105:                     revert Errors.MustUseExistingBridgeCredit(); 

/// @audit OracleLibrary
118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH); 

/// @audit OracleLibrary
122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH); 
```
[75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L75), [105](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L105), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L118), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit SSTORE2
12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer); 

/// @audit MTypes
45:             data[i] = MTypes.ProposalData({ 
46:                 shorter: shorter,
47:                 shortId: shortId,
48:                 CR: CR,
49:                 ercDebtRedeemed: ercDebtRedeemed,
50:                 colRedeemed: colRedeemed
51:             });
```
[12](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L12), [45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L45-L51)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Errors
25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset(); 

/// @audit Errors
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice(); 

/// @audit Errors
128:         if (invalidFetchData) revert Errors.InvalidPrice(); 

/// @audit Errors
134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice(); 

/// @audit Errors
139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool(); 

/// @audit LibOrders
169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) { 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L25), [60](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L60), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L128), [134](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L134), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L139), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit LibOrders
142:         uint88 eth = order.ercAmount.mulU88(order.price).mulU88(LibOrders.convertCR(order.shortOrderCR)); 

/// @audit Events
218:         emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount); 

/// @audit Events
301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType); 

/// @audit LibAsset
608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) { 

/// @audit Events
631:         emit Events.MatchOrder( 
632:             asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, matchTotal.fillEth, matchTotal.fillErc
633:         );

/// @audit LibOrders
642:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice); 

/// @audit LibShortRecord
679:         LibShortRecord.fillShortRecord( 
680:             asset,
681:             incomingShort.addr,
682:             incomingShort.shortRecordId,
683:             status,
684:             matchTotal.fillEth,
685:             matchTotal.fillErc,
686:             Asset.ercDebtRate,
687:             Vault.dethYieldRate
688:         );

/// @audit LibOrders
718:             matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR)); 

/// @audit LibOracle
730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset); 

/// @audit Errors
778:             revert Errors.BadShortHint(); 

/// @audit LibOracle
804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset); 

/// @audit LibOracle
813:         uint256 savedPrice = LibOracle.getPrice(asset); 

/// @audit Errors
850:         revert Errors.BadHintIdArray(); 

/// @audit Errors
859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 

/// @audit Errors
874:             revert Errors.NotActiveOrder(); 

/// @audit Errors
887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder(); 

/// @audit LibOrders
889:         uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR)); 

/// @audit LibShortRecord
901:             LibShortRecord.deleteShortRecord(asset, shorter, shortRecordId); 

/// @audit LibAsset
903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset)); 

/// @audit LibOrders
911:                     uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR)); 

/// @audit LibShortRecord
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

/// @audit LibOracle
942:             uint256 savedPrice = LibOracle.getPrice(asset); 

/// @audit LibOracle
959:         uint256 savedPrice = LibOracle.getPrice(asset); 
```
[142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L142), [218](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L218), [301](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L301), [608](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L608), [631](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L631-L633), [642](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L642), [679](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L679-L688), [718](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L718), [730](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L730), [778](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L778), [804](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L804), [813](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L813), [850](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L850), [859](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L859), [874](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L874), [887](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L887), [889](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L889), [901](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L901), [903](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L903), [911](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L911), [913](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L913-L922), [942](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L942), [959](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L959)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit LibOrders
40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS; 

/// @audit Errors
57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

/// @audit LibOrders
61:                 LibOrders.cancelShort(asset, shortOrderId); 

/// @audit LibAsset
64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) { 

/// @audit LibOrders
66:                 LibOrders.cancelShort(asset, shortOrderId); 

/// @audit LibAsset
79:         uint256 minShortErc = LibAsset.minShortErc(asset); 

/// @audit Errors
84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder(); 

/// @audit LibOrders
90:                     LibOrders.cancelShort(asset, shortOrderId); 

/// @audit Errors
95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount(); 

/// @audit Errors
98:             revert Errors.CannotLeaveDustAmount(); 

/// @audit LibAsset
109:         uint256 recoveryCR = LibAsset.recoveryCR(asset); 

/// @audit Errors
130:         if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled(); 
/// @audit Errors
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

/// @audit LibOrders
135:             LibOrders.cancelShort(asset, nft.shortOrderId); 

/// @audit LibShortRecord
139:         LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId); 
/// @audit LibBridgeRouter
140:         LibBridgeRouter.transferBridgeCredit(asset, from, to, short.collateral);

/// @audit LibShortRecord
142:         uint8 id = LibShortRecord.createShortRecord( 
143:             asset, to, SR.FullyFilled, short.collateral, short.ercDebt, short.ercDebtRate, short.dethYieldRate, tokenId
144:         );
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L40), [57](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L57), [61](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L61), [64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L64), [66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L66), [79](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L79), [84](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84), [90](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L90), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L95), [98](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L98), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L109), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L130-L131), [135](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L135), [139](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L139-L140), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L142-L144)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit TickMath
33:         uint160 sqrtRatioX96 = TickMath.getSqrtRatioAtTick(tick); 

/// @audit U256
/// @audit U256
39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192); 

/// @audit U256
41:             uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64); 

/// @audit U256
/// @audit U256
43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128); 

/// @audit Errors
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo(); 
```
[33](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L33), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L41), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52)

</details>


---
### [NC&#x2011;34] Missing checks for `address(0x0)` in the constructor
<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit _rethBridge missing zero address validation
/// @audit _stethBridge missing zero address validation
29:     constructor(address _rethBridge, address _stethBridge) { 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit _dusd missing zero address validation
28:     constructor(address _dusd) { 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit _dusd missing zero address validation
30:     constructor(address _dusd) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

</details>


---
### [NC&#x2011;35] Missing checks for uint state variable assignments
<details>
<summary><i>There are 26 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

94:         incomingBid.price = price; 
95:         incomingBid.ercAmount = ercAmount;
```
[94](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L94-L95)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

131:             m.shortOrderId = shortOrderId; 
```
[131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L131)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

65:         incomingShort.price = price; 
66:         incomingShort.ercAmount = ercAmount;

70:         incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x 
```
[65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L65-L66), [70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L70)

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

173:                     VaultUserFrom.bridgeCreditSteth -= collateral; 
174:                     VaultUserTo.bridgeCreditSteth += collateral;

201:         s.vault[vault].dethTotal -= amount; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L28), [30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L30), [34](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L34-L35), [52](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L52), [66](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L66), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L82), [96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L96), [164](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L164-L165), [173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L173-L174), [201](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L201)

```solidity
📁 File: contracts/libraries/LibOracle.sol

152:         s.bids[asset][C.HEAD].creationTime = oracleTime; 
```
[152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L152)

```solidity
📁 File: contracts/libraries/LibOrders.sol

334:         orders[asset][C.HEAD].prevId = id; 

340:             orders[asset][id].prevId = prevHEAD; 

488:             orders[asset][C.HEAD].nextId = id; 

542:             orders[asset][nextAskId].prevId = headId; 
```
[334](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L334), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L340), [488](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L488), [542](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L542)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

31:         Vault.dethCollateral -= collateral; 
32:         Asset.dethCollateral -= collateral;
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L31-L32)

</details>


---
### [NC&#x2011;36] Multiple type casts create complexity within the code
To ensure reliable and precise data handling in Solidity contracts, developers should avoid double type casting. Multiple type casts can lead to unintended consequences, such as truncation, rounding errors, or loss of precision. This compromises the contract's functionality and readability, making debugging more challenging. Instead, its crucial to use appropriate data types and minimize unnecessary type casting for a more dependable and robust contract execution.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit bytes8(uint64)
133:                 bytes8(uint64(p.currentCR)), 
```
[133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L133)


---
### [NC&#x2011;37] NatSpec: Contract declarations should have `@author` tags
<details>
<summary><i>There are 13 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

19:  
20: contract BidOrdersFacet is Modifiers {
21:     using U256 for uint256;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L19-L21)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

17:  
18: contract BridgeRouterFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L17-L19)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

18:  
19: contract ExitShortFacet is Modifiers {
20:     using U256 for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L18-L20)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

20:  
21: contract PrimaryLiquidationFacet is Modifiers {
22:     using LibShortRecord for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

20:  
21: contract RedemptionFacet is Modifiers {
22:     using LibSRUtil for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

17:  
18: contract ShortOrdersFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L17-L19)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

15:  
16: library LibBridgeRouter {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibBytes.sol

8:  
9: library LibBytes {
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
```
[8](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L8-L10)

```solidity
📁 File: contracts/libraries/LibOracle.sol

15:  
16: library LibOracle {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibOrders.sol

19:  
20: library LibOrders {
21:     using LibOracle for address;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L19-L21)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

17: // extra ShortRecord helpers, similar to LibShortRecord 
18: library LibSRUtil {
19:     using U88 for uint88;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L17-L19)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

9:  
10: interface IUniswapV3Pool {
11:     function observe(uint32[] calldata secondsAgos)

20: /// @notice Provides functions to integrate with V3 pool oracle 
21: library OracleLibrary {
22:     /// @notice Given a tick and a token amount, calculates the amount of token received in exchange
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L9-L11), [20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L20-L22)

</details>


---
### [NC&#x2011;38] NatSpec: Contract declarations should have `@dev` tags
<details>
<summary><i>There are 13 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

19:  
20: contract BidOrdersFacet is Modifiers {
21:     using U256 for uint256;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L19-L21)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

17:  
18: contract BridgeRouterFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L17-L19)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

18:  
19: contract ExitShortFacet is Modifiers {
20:     using U256 for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L18-L20)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

20:  
21: contract PrimaryLiquidationFacet is Modifiers {
22:     using LibShortRecord for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

20:  
21: contract RedemptionFacet is Modifiers {
22:     using LibSRUtil for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

17:  
18: contract ShortOrdersFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L17-L19)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

15:  
16: library LibBridgeRouter {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibBytes.sol

8:  
9: library LibBytes {
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
```
[8](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L8-L10)

```solidity
📁 File: contracts/libraries/LibOracle.sol

15:  
16: library LibOracle {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibOrders.sol

19:  
20: library LibOrders {
21:     using LibOracle for address;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L19-L21)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

17: // extra ShortRecord helpers, similar to LibShortRecord 
18: library LibSRUtil {
19:     using U88 for uint88;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L17-L19)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

9:  
10: interface IUniswapV3Pool {
11:     function observe(uint32[] calldata secondsAgos)

20: /// @notice Provides functions to integrate with V3 pool oracle 
21: library OracleLibrary {
22:     /// @notice Given a tick and a token amount, calculates the amount of token received in exchange
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L9-L11), [20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L20-L22)

</details>


---
### [NC&#x2011;39] NatSpec: Contract declarations should have `@notice` tags
`@notice` is used to explain to end users what the contract does, and the compiler interprets `///` or `/**` comments as this tag if one was't explicitly provided

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers { 
21:     using U256 for uint256;
22:     using U88 for uint88;
23:     using U80 for uint80;
24:     using {LibOrders.isShort} for STypes.Order;
25: 
26:     /**
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20-L26)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using LibBridge for uint256;
22:     using LibBridge for address;
23:     using LibBridgeRouter for uint256;
24:     using LibVault for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L24)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers { 
20:     using U256 for uint256;
21:     using U80 for uint80;
22:     using U88 for uint88;
23:     using LibSRUtil for STypes.ShortRecord;
24:     using {LibAsset.burnMsgSenderDebt} for address;
25: 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19-L25)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers { 
22:     using LibShortRecord for STypes.ShortRecord;
23:     using U256 for uint256;
24:     using U96 for uint96;
25:     using U88 for uint88;
26:     using U80 for uint80;
27: 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21-L27)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers { 
22:     using LibSRUtil for STypes.ShortRecord;
23:     using LibShortRecord for STypes.ShortRecord;
24:     using U256 for uint256;
25:     using U104 for uint104;
26:     using U88 for uint88;
27:     using U80 for uint80;
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21-L27)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using U80 for uint80;
22: 
23:     /**
24:      * @notice Creates limit short in market system
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18-L24)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter { 
17:     using U256 for uint256;
18:     using U88 for uint88;
19: 
20:     // Credit user account with dETH and bridge credit if applicable
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
22:         AppStorage storage s = appStorage();
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16-L22)

```solidity
📁 File: contracts/libraries/LibBytes.sol

9: library LibBytes { 
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer);
13:         // ProposalData is 51 bytes
14:         require(slate.length % 51 == 0, "Invalid data length");
15: 
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9-L15)

```solidity
📁 File: contracts/libraries/LibOracle.sol

16: library LibOracle { 
17:     using U256 for uint256;
18: 
19:     function getOraclePrice(address asset) internal view returns (uint256) {
20:         AppStorage storage s = appStorage();
21:         AggregatorV3Interface baseOracle = AggregatorV3Interface(s.baseOracle);
22:         uint256 protocolPrice = getPrice(asset);
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16-L22)

```solidity
📁 File: contracts/libraries/LibOrders.sol

20: library LibOrders { 
21:     using LibOracle for address;
22:     using LibVault for uint256;
23:     using U256 for uint256;
24:     using U104 for uint104;
25:     using U16 for uint16;
26:     using U80 for uint80;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20-L26)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil { 
19:     using U88 for uint88;
20:     using U256 for uint256;
21: 
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23:         internal
24:     {
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18-L24)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool { 
11:     function observe(uint32[] calldata secondsAgos)
12:         external
13:         view
14:         returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
15: }
16: 
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10-L16)

</details>


---
### [NC&#x2011;40] NatSpec: Contract declarations should have `@title` tags
<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

19:  
20: contract BidOrdersFacet is Modifiers {
21:     using U256 for uint256;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L19-L21)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

17:  
18: contract BridgeRouterFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L17-L19)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

18:  
19: contract ExitShortFacet is Modifiers {
20:     using U256 for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L18-L20)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

20:  
21: contract PrimaryLiquidationFacet is Modifiers {
22:     using LibShortRecord for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

20:  
21: contract RedemptionFacet is Modifiers {
22:     using LibSRUtil for STypes.ShortRecord;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L20-L22)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

17:  
18: contract ShortOrdersFacet is Modifiers {
19:     using U256 for uint256;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L17-L19)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

15:  
16: library LibBridgeRouter {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibBytes.sol

8:  
9: library LibBytes {
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
```
[8](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L8-L10)

```solidity
📁 File: contracts/libraries/LibOracle.sol

15:  
16: library LibOracle {
17:     using U256 for uint256;
```
[15](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L15-L17)

```solidity
📁 File: contracts/libraries/LibOrders.sol

19:  
20: library LibOrders {
21:     using LibOracle for address;
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L19-L21)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

17: // extra ShortRecord helpers, similar to LibShortRecord 
18: library LibSRUtil {
19:     using U88 for uint88;
```
[17](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L17-L19)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

9:  
10: interface IUniswapV3Pool {
11:     function observe(uint32[] calldata secondsAgos)
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L9-L11)

</details>


---
### [NC&#x2011;41] NatSpec: Contract declarations should have NatSpec descriptions
It is recommended that Solidity libraries and contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as DeFi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.

<details>
<summary><i>There are 12 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers { 
21:     using U256 for uint256;
22:     using U88 for uint88;
23:     using U80 for uint80;
24:     using {LibOrders.isShort} for STypes.Order;
25: 
26:     /**
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20-L26)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using LibBridge for uint256;
22:     using LibBridge for address;
23:     using LibBridgeRouter for uint256;
24:     using LibVault for uint256;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L24)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers { 
20:     using U256 for uint256;
21:     using U80 for uint80;
22:     using U88 for uint88;
23:     using LibSRUtil for STypes.ShortRecord;
24:     using {LibAsset.burnMsgSenderDebt} for address;
25: 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19-L25)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers { 
22:     using LibShortRecord for STypes.ShortRecord;
23:     using U256 for uint256;
24:     using U96 for uint96;
25:     using U88 for uint88;
26:     using U80 for uint80;
27: 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21-L27)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers { 
22:     using LibSRUtil for STypes.ShortRecord;
23:     using LibShortRecord for STypes.ShortRecord;
24:     using U256 for uint256;
25:     using U104 for uint104;
26:     using U88 for uint88;
27:     using U80 for uint80;
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21-L27)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using U80 for uint80;
22: 
23:     /**
24:      * @notice Creates limit short in market system
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18-L24)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter { 
17:     using U256 for uint256;
18:     using U88 for uint88;
19: 
20:     // Credit user account with dETH and bridge credit if applicable
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
22:         AppStorage storage s = appStorage();
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16-L22)

```solidity
📁 File: contracts/libraries/LibBytes.sol

9: library LibBytes { 
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer);
13:         // ProposalData is 51 bytes
14:         require(slate.length % 51 == 0, "Invalid data length");
15: 
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9-L15)

```solidity
📁 File: contracts/libraries/LibOracle.sol

16: library LibOracle { 
17:     using U256 for uint256;
18: 
19:     function getOraclePrice(address asset) internal view returns (uint256) {
20:         AppStorage storage s = appStorage();
21:         AggregatorV3Interface baseOracle = AggregatorV3Interface(s.baseOracle);
22:         uint256 protocolPrice = getPrice(asset);
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16-L22)

```solidity
📁 File: contracts/libraries/LibOrders.sol

20: library LibOrders { 
21:     using LibOracle for address;
22:     using LibVault for uint256;
23:     using U256 for uint256;
24:     using U104 for uint104;
25:     using U16 for uint16;
26:     using U80 for uint80;
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20-L26)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil { 
19:     using U88 for uint88;
20:     using U256 for uint256;
21: 
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23:         internal
24:     {
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18-L24)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool { 
11:     function observe(uint32[] calldata secondsAgos)
12:         external
13:         view
14:         returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
15: }
16: 
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10-L16)

</details>


---
### [NC&#x2011;42] NatSpec: File is missing NatSpec Documentation
<details>
<summary><i>There are 11 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L1)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L1)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L1)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L1)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L1)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L1)

```solidity
📁 File: contracts/libraries/LibBytes.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1)

```solidity
📁 File: contracts/libraries/LibOracle.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L1)

```solidity
📁 File: contracts/libraries/LibOrders.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L1)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L1)

</details>


---
### [NC&#x2011;43] NatSpec: Function declarations should have `@notice` tags
`@notice` is used to explain to end users what the function does, and the compiler interprets `///` or `/**` comments as this tag if one was't explicitly provided

<details>
<summary><i>There are 55 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 

358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private { 

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) { 

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L156), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
```
[213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
```
[96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
32:         internal
33:         view
34:         returns (bool)
35:     {

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
383:         internal
384:         returns (uint88 redemptionFee)
385:     {
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal { 

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
📁 File: contracts/libraries/LibBytes.sol

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

19:     function getOraclePrice(address asset) internal view returns (uint256) { 

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

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) { 

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal { 

156:     function getTime(address asset) internal view returns (uint256 creationTime) { 

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117-L124), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) { 

35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal { 

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 
56:         internal
57:         view
58:         returns (STypes.Order[] memory)
59:     {

78:     function isShort(STypes.Order memory order) internal pure returns (bool) { 

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

320:     function _reuseOrderIds( 
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

420:     function normalizeOrderType(O o) private pure returns (O newO) { 

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private { 

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 

783:     function updateOracleAndStartingShortViaThreshold( 
784:         address asset,
785:         uint256 savedPrice,
786:         STypes.Order memory incomingOrder,
787:         uint16[] memory shortHintArray
788:     ) internal {

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal { 

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal { 

826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {

854:     function cancelBid(address asset, uint16 id) internal { 

868:     function cancelAsk(address asset, uint16 id) internal { 

882:     function cancelShort(address asset, uint16 id) internal { 

955:     function handlePriceDiscount(address asset, uint80 price) internal { 

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320-L326), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [628](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L628), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [783](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783-L788), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 
23:         internal
24:     {

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 
103:         internal
104:         view
105:         returns (bool recoveryViolation)
106:     {

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal { 

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal { 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

11:     function observe(uint32[] calldata secondsAgos) 

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

</details>


---
### [NC&#x2011;44] NatSpec: Function declarations should have NatSpec descriptions
It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as DeFi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.

<details>
<summary><i>There are 55 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

77:     function _createBid( 

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 

358:     function _shortDirectionHandler( 
```
[77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private { 

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) { 

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L156), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
```
[213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
```
[96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal { 

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
📁 File: contracts/libraries/LibBytes.sol

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

19:     function getOraclePrice(address asset) internal view returns (uint256) { 

69:     function baseOracleCircuitBreaker( 

117:     function oracleCircuitBreaker( 

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) { 

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal { 

156:     function getTime(address asset) internal view returns (uint256 creationTime) { 

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) { 

35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal { 

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 

78:     function isShort(STypes.Order memory order) internal pure returns (bool) { 

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

320:     function _reuseOrderIds( 

420:     function normalizeOrderType(O o) private pure returns (O newO) { 

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private { 

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 

783:     function updateOracleAndStartingShortViaThreshold( 

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal { 

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal { 

826:     function findOrderHintId( 

854:     function cancelBid(address asset, uint16 id) internal { 

868:     function cancelAsk(address asset, uint16 id) internal { 

882:     function cancelShort(address asset, uint16 id) internal { 

955:     function handlePriceDiscount(address asset, uint80 price) internal { 

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [628](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L628), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [783](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal { 

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal { 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

11:     function observe(uint32[] calldata secondsAgos) 

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)

</details>


---
### [NC&#x2011;45] NatSpec: Functions missing NatSpec `@dev` tag
<details>
<summary><i>There are 76 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

64:      */ 
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66:         external

76:  
77:     function _createBid(
78:         address sender,

129:      */ 
130:     function bidMatchAlgo(
131:         address asset,

274:      */ 
275:     function matchIncomingBid(
276:         address asset,

339:     // @dev If neither conditions are true, it returns an empty Order struct 
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
341:         if (b.shortId != C.HEAD) {

357:  
358:     function _shortDirectionHandler(
359:         address asset,
```
[64](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L64-L66), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L76-L78), [129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L129-L131), [274](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L274-L276), [339](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L339-L341), [357](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L357-L359)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

28:  
29:     constructor(address _rethBridge, address _stethBridge) {
30:         rethBridge = _rethBridge;

39:      */ 
40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
41:         return vault.getDethTotal();

147:     // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions 
148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {
149:         uint88 dethTotal = s.vault[vault].dethTotal;

155:     // Checks for invalid bridge input 
156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
157:         if (bridge == rethBridge) {

168:     // Accounting for situations when the vault (via bridges) experiences loss in value 
169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
170:         uint256 dethTotalNew = vault.getDethTotal();
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L28-L30), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L39-L41), [147](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L147-L149), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L155-L157), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L168-L170)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

27:  
28:     constructor(address _dusd) {
29:         dusd = _dusd;

212:  
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
214:         return short.collateral.div(short.ercDebt);
```
[27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L27-L29), [212](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L212-L214)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

29:  
30:     constructor(address _dusd) {
31:         dusd = _dusd;

95:     // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call 
96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {
97:         uint16 lowestAskKey = s.asks[m.asset][C.HEAD].nextId;

121:      */ 
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123:         private

228:  
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {
230:         if (a > type(uint88).max) revert Errors.InvalidAmount();

239:      */ 
240:     function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {
241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L29-L31), [95](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L95-L97), [121](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L121-L123), [228](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L228-L230), [239](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L239-L241)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

30:  
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32:         internal

367:     // Send leftover collateral back to shorter and close SR 
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {
369:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortId];

381:     // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated 
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383:         internal
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L30-L32), [367](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L367-L369), [381](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L381-L383)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

20:     // Credit user account with dETH and bridge credit if applicable 
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
22:         AppStorage storage s = appStorage();

38:     // Determine how much dETH is NOT covered by bridge credits during withdrawal 
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40:         internal

112:     // @dev Only applicable to VAULT.ONE which has mixed LST 
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
114:         IBridge bridgeReth = IBridge(rethBridge);

143:     // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system 
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
145:         AppStorage storage s = appStorage();

197:     // Update user account upon dETH withdrawal 
198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
199:         AppStorage storage s = appStorage();
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L20-L22), [38](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L38-L40), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L112-L114), [143](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L143-L145), [197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L197-L199)

```solidity
📁 File: contracts/libraries/LibBytes.sol

10:     // Custom decode since SSTORE.write was written directly in proposeRedemption 
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer);
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L10-L12)

```solidity
📁 File: contracts/libraries/LibOracle.sol

18:  
19:     function getOraclePrice(address asset) internal view returns (uint256) {
20:         AppStorage storage s = appStorage();

68:  
69:     function baseOracleCircuitBreaker(
70:         uint256 protocolPrice,

116:  
117:     function oracleCircuitBreaker(
118:         uint80 roundId,

130:  
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
132:         // Check valid price

148:     */ 
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
150:         AppStorage storage s = appStorage();

155:     // @dev Intentionally using creationTime for oracleTime. 
156:     function getTime(address asset) internal view returns (uint256 creationTime) {
157:         AppStorage storage s = appStorage();

161:     // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos. 
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {
163:         AppStorage storage s = appStorage();

167:     // @dev Allows caller to save gas since reading spot price costs ~16K 
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L18-L20), [68](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L68-L70), [116](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L116-L118), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L130-L132), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L148-L150), [155](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L155-L157), [161](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L161-L163), [167](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L167-L169)

```solidity
📁 File: contracts/libraries/LibOrders.sol

29:     // @dev in seconds 
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {
31:         // shouldn't overflow in 136 years

34:  
35:     function convertCR(uint16 cr) internal pure returns (uint256) {
36:         return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;

39:     // For matched token reward 
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {
41:         AppStorage storage s = appStorage();

54:  
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
56:         internal

77:  
78:     function isShort(STypes.Order memory order) internal pure returns (bool) {
79:         return order.orderType == O.LimitShort;

81:  
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
83:         AppStorage storage s = appStorage();

102:  
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
104:         AppStorage storage s = appStorage();

127:      */ 
128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
129:         AppStorage storage s = appStorage();

152:      */ 
153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {
154:         O o = normalizeOrderType(incomingOrder.orderType);

230:      */ 
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
232:         internal

259:      */ 
260:     function verifySellId(
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

319:     // shared function for both canceling and order and matching an order 
320:     function _reuseOrderIds(
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

361:      */ 
362:     function findPrevOfIncomingId(
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

401:      */ 
402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

419:     // @dev not used to change state, just which methods to call 
420:     function normalizeOrderType(O o) private pure returns (O newO) {
421:         if (o == O.LimitBid || o == O.MarketBid) {

439:      */ 
440:     function getOrderId(
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

531:      */ 
532:     function _updateOrders(
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

555:      */ 
556:     function sellMatchAlgo(
557:         address asset,

627:  
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {
629:         O o = normalizeOrderType(incomingOrder.orderType);

651:      */ 
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {
653:         AppStorage storage s = appStorage();

667:      */ 
668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {
669:         AppStorage storage s = appStorage();

727:  
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
729:         AppStorage storage s = appStorage();

782:     // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%) 
783:     function updateOracleAndStartingShortViaThreshold(
784:         address asset,

802:     // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough 
803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {
804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset);

809:  
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
811:         AppStorage storage s = appStorage();

825:  
826:     function findOrderHintId(
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,

853:     // Helper Functions for cancelling orders 
854:     function cancelBid(address asset, uint16 id) internal {
855:         AppStorage storage s = appStorage();

867:  
868:     function cancelAsk(address asset, uint16 id) internal {
869:         AppStorage storage s = appStorage();

881:  
882:     function cancelShort(address asset, uint16 id) internal {
883:         AppStorage storage s = appStorage();

954:     // Approximates the match price compared to the oracle price and accounts for any discount by increasing dethTithePercent 
955:     function handlePriceDiscount(address asset, uint80 price) internal {
956:         AppStorage storage s = appStorage();

984:  
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {
986:         return a < b ? a : b;

988:  
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {
990:         return a > b ? a : b;
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L29-L31), [34](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L34-L36), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L39-L41), [54](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L54-L56), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L77-L79), [81](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L81-L83), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L102-L104), [127](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L127-L129), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L152-L154), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L230-L232), [259](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L259-L261), [319](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L319-L321), [361](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L361-L363), [401](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L401-L403), [419](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L419-L421), [439](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L439-L441), [531](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L531-L533), [555](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L555-L557), [627](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L627-L629), [651](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L651-L653), [667](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L667-L669), [727](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L727-L729), [782](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L782-L784), [802](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L802-L804), [809](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L809-L811), [825](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L825-L827), [853](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L853-L855), [867](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L867-L869), [881](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L881-L883), [954](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L954-L956), [984](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L984-L986), [988](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L988-L990)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

21:  
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23:         internal

48:  
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
50:         internal

71:  
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
73:         internal

101:  
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
103:         internal

123:  
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {
125:         AppStorage storage s = appStorage();

150:  
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
152:         AppStorage storage s = appStorage();
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L21-L23), [48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L48-L50), [71](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L71-L73), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L101-L103), [123](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L123-L125), [150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L150-L152)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool { 
11:     function observe(uint32[] calldata secondsAgos)
12:         external

27:     /// @return quoteAmount Amount of quoteToken received for baseAmount of baseToken 
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)
29:         internal

46:  
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
48:         internal
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10-L12), [27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L27-L29), [46](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L46-L48)

</details>


---
### [NC&#x2011;46] NatSpec: Functions missing NatSpec `@param` tag
It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as DeFi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.

<details>
<summary><i>There are 88 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Missing @param for `ercAmount`, `isMarketOrder`, `orderHintArray`, `shortHintArray`
40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @param for `ercAmount`, `shortHintArray`
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {

/// @audit Missing @param for all function parameters
77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @param for `incomingBid`, `orderHintArray`
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @param for `lowestSell`, `incomingBid`, `matchTotal`
215:     function matchlowestSell( 
216:         address asset,
217:         STypes.Order memory lowestSell,
218:         STypes.Order memory incomingBid,
219:         MTypes.Match memory matchTotal
220:     ) private {

/// @audit Missing @param for `incomingBid`, `matchTotal`
275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @param for all function parameters
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 

/// @audit Missing @param for all function parameters
358:     function _shortDirectionHandler( 
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [215](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L215-L220), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340), [358](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L358-L363)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Missing @param for all function parameters
29:     constructor(address _rethBridge, address _stethBridge) { 

/// @audit Missing @param for `dethAmount`
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant { 

/// @audit Missing @param for `dethAmount`
133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO { 

/// @audit Missing @param for all function parameters
148:     function maybeUpdateYield(uint256 vault, uint88 amount) private { 

/// @audit Missing @param for all function parameters
156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) { 

/// @audit Missing @param for all function parameters
169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101), [133](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133), [148](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L148), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L156), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Missing @param for all function parameters
28:     constructor(address _dusd) { 

/// @audit Missing @param for `buybackAmount`, `shortOrderId`
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant
45:         onlyValidShortRecord(asset, msg.sender, id)
46:     {

/// @audit Missing @param for `buybackAmount`, `shortOrderId`
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId) 
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant
91:         onlyValidShortRecord(asset, msg.sender, id)
92:     {

/// @audit Missing @param for `buybackAmount`, `shortHintArray`, `shortOrderId`
142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {

/// @audit Missing @param for all function parameters
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28), [41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L41-L46), [87](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L87-L92), [142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149), [213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Missing @param for all function parameters
30:     constructor(address _dusd) { 

/// @audit Missing @param for `shortHintArray`, `shortOrderId`
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId) 
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {

/// @audit Missing @param for all function parameters
96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view { 

/// @audit Missing @param for `shortOrderId`
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId) 
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
125:     {

/// @audit Missing @param for `shortHintArray`
154:     function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private { 

/// @audit Missing @param for all function parameters
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47-L53), [96](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122-L125), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154), [229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Missing @param for all function parameters
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
32:         internal
33:         view
34:         returns (bool)
35:     {

/// @audit Missing @param for `proposalInput`, `redemptionAmount`, `maxRedemptionFee`
56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

/// @audit Missing @param for `incorrectIndex`, `disputeShorter`, `disputeShortId`
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {

/// @audit Missing @param for `claimIndex`
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {

/// @audit Missing @param for all function parameters
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private { 

/// @audit Missing @param for all function parameters
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
383:         internal
384:         returns (uint88 redemptionFee)
385:     {
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35), [56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351), [368](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit Missing @param for `ercAmount`, `orderHintArray`, `shortHintArray`, `shortOrderCR`
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

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Missing @param for all function parameters
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal { 

/// @audit Missing @param for all function parameters
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {

/// @audit Missing @param for all function parameters
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 

/// @audit Missing @param for all function parameters
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal { 

/// @audit Missing @param for all function parameters
198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal { 
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L21), [39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113), [144](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit Missing @param for all function parameters
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Missing @param for all function parameters
19:     function getOraclePrice(address asset) internal view returns (uint256) { 

/// @audit Missing @param for all function parameters
69:     function baseOracleCircuitBreaker( 
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {

/// @audit Missing @param for all function parameters
117:     function oracleCircuitBreaker( 
118:         uint80 roundId,
119:         uint80 baseRoundId,
120:         int256 chainlinkPrice,
121:         int256 baseChainlinkPrice,
122:         uint256 timeStamp,
123:         uint256 baseTimeStamp
124:     ) private view {

/// @audit Missing @param for all function parameters
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal { 

/// @audit Missing @param for all function parameters
156:     function getTime(address asset) internal view returns (uint256 creationTime) { 

/// @audit Missing @param for all function parameters
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 

/// @audit Missing @param for all function parameters
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [117](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117-L124), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit Missing @param for all function parameters
35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

/// @audit Missing @param for all function parameters
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal { 

/// @audit Missing @param for all function parameters
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 
56:         internal
57:         view
58:         returns (STypes.Order[] memory)
59:     {

/// @audit Missing @param for all function parameters
78:     function isShort(STypes.Order memory order) internal pure returns (bool) { 

/// @audit Missing @param for all function parameters
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit Missing @param for all function parameters
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit Missing @param for `orderHintArray`
128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal { 

/// @audit Missing @param for `incomingOrder`, `orderHintArray`
153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private { 

/// @audit Missing @param for `incomingOrder`, `hintId`
173:     function addOrder( 
174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
175:         address asset,
176:         STypes.Order memory incomingOrder,
177:         uint16 hintId
178:     ) private {

/// @audit Missing @param for `_prevId`, `_newPrice`, `_nextId`
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId) 
232:         internal
233:         view
234:         returns (int256 direction)
235:     {

/// @audit Missing @param for `orders`, `_prevId`, `_newPrice`, `_nextId`
260:     function verifySellId( 
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

/// @audit Missing @param for all function parameters
320:     function _reuseOrderIds( 
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

/// @audit Missing @param for `incomingOrder`, `hintId`
362:     function findPrevOfIncomingId( 
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

/// @audit Missing @param for `orders`, `prevId`, `newPrice`, `nextId`, `orderType`
402:     function verifyId( 
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {

/// @audit Missing @param for all function parameters
420:     function normalizeOrderType(O o) private pure returns (O newO) { 

/// @audit Missing @param for `hintId`, `_newPrice`, `orderType`
440:     function getOrderId( 
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

/// @audit Missing @param for `isOrderFullyFilled`
474:     function updateBidOrdersOnMatch( 
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled
479:     ) internal {

/// @audit Missing @param for `headId`, `lastMatchedId`
532:     function _updateOrders( 
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {

/// @audit Missing @param for `incomingAsk`, `orderHintArray`, `minAskEth`
556:     function sellMatchAlgo( 
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {

/// @audit Missing @param for all function parameters
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private { 

/// @audit Missing @param for `incomingAsk`, `matchTotal`
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private { 

/// @audit Missing @param for `incomingShort`, `matchTotal`
668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private { 

/// @audit Missing @param for `incomingSell`, `highestBid`, `matchTotal`
705:     function matchHighestBid( 
706:         STypes.Order memory incomingSell,
707:         STypes.Order memory highestBid,
708:         address asset,
709:         MTypes.Match memory matchTotal
710:     ) internal {

/// @audit Missing @param for all function parameters
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private { 

/// @audit Missing @param for all function parameters
783:     function updateOracleAndStartingShortViaThreshold( 
784:         address asset,
785:         uint256 savedPrice,
786:         STypes.Order memory incomingOrder,
787:         uint16[] memory shortHintArray
788:     ) internal {

/// @audit Missing @param for all function parameters
803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal { 

/// @audit Missing @param for all function parameters
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal { 

/// @audit Missing @param for all function parameters
826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {

/// @audit Missing @param for all function parameters
854:     function cancelBid(address asset, uint16 id) internal { 

/// @audit Missing @param for all function parameters
868:     function cancelAsk(address asset, uint16 id) internal { 

/// @audit Missing @param for all function parameters
882:     function cancelShort(address asset, uint16 id) internal { 

/// @audit Missing @param for all function parameters
955:     function handlePriceDiscount(address asset, uint80 price) internal { 

/// @audit Missing @param for all function parameters
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 

/// @audit Missing @param for all function parameters
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
```
[35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L40), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [82](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L82), [103](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L103), [128](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L128), [153](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L153), [173](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L173-L178), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L235), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L266), [320](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L320-L326), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L409), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [474](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L474-L479), [532](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L532-L537), [556](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L556-L561), [628](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L628), [652](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L652), [668](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L668), [705](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L705-L710), [728](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728), [783](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L783-L788), [803](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L803), [810](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L810), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [854](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L854), [868](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L868), [882](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L882), [955](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L955), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Missing @param for all function parameters
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 
23:         internal
24:     {

/// @audit Missing @param for all function parameters
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {

/// @audit Missing @param for all function parameters
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {

/// @audit Missing @param for all function parameters
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 
103:         internal
104:         view
105:         returns (bool recoveryViolation)
106:     {

/// @audit Missing @param for all function parameters
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal { 

/// @audit Missing @param for all function parameters
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal { 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106), [124](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L124), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Missing @param for all function parameters
11:     function observe(uint32[] calldata secondsAgos) 

/// @audit Missing @param for `baseAmount`, `baseToken`, `quoteToken`
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken) 
29:         internal
30:         pure
31:         returns (uint256 quoteAmount)
32:     {

/// @audit Missing @param for all function parameters
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11), [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28-L32), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

</details>


---
### [NC&#x2011;47] NatSpec: Functions missing NatSpec `@return` tag
It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as DeFi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.

<details>
<summary><i>There are 39 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Missing @return for all function parameters
40:     function createBid( 
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @return for all function parameters
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {

/// @audit Missing @return for all function parameters
77:     function _createBid( 
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @return for all function parameters
130:     function bidMatchAlgo( 
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @return for all function parameters
275:     function matchIncomingBid( 
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit Missing @return for all function parameters
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) { 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69), [77](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L77-L85), [130](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L130-L135), [275](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L275-L280), [340](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L340)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit Missing @return for all function parameters
40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) { 

/// @audit Missing @return for all function parameters
51:     function getBridges(uint256 vault) external view returns (address[] memory) { 

/// @audit Missing @return for all function parameters
156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) { 

/// @audit Missing @return for all function parameters
169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) { 
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L40), [51](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L51), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L156), [169](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit Missing @return for all function parameters
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
```
[213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Missing @return for all function parameters
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) { 
```
[229](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit Missing @return for all function parameters
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc) 
32:         internal
33:         view
34:         returns (bool)
35:     {

/// @audit Missing @return for all function parameters
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed) 
383:         internal
384:         returns (uint88 redemptionFee)
385:     {
```
[31](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31-L35), [382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L385)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit Missing @return for all function parameters
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {

/// @audit Missing @return for all function parameters
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) { 
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42), [113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit Missing @return for all function parameters
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit Missing @return for all function parameters
19:     function getOraclePrice(address asset) internal view returns (uint256) { 

/// @audit Missing @return for all function parameters
69:     function baseOracleCircuitBreaker( 
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {

/// @audit Missing @return for all function parameters
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) { 

/// @audit Missing @return for all function parameters
156:     function getTime(address asset) internal view returns (uint256 creationTime) { 

/// @audit Missing @return for all function parameters
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 

/// @audit Missing @return for all function parameters
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) { 
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L19), [69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L75), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162), [168](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit Missing @return for all function parameters
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) { 

/// @audit Missing @return for all function parameters
35:     function convertCR(uint16 cr) internal pure returns (uint256) { 

/// @audit Missing @return for all function parameters
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset) 
56:         internal
57:         view
58:         returns (STypes.Order[] memory)
59:     {

/// @audit Missing @return for all function parameters
78:     function isShort(STypes.Order memory order) internal pure returns (bool) { 

/// @audit Missing @return for all function parameters
362:     function findPrevOfIncomingId( 
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

/// @audit Missing @return for all function parameters
420:     function normalizeOrderType(O o) private pure returns (O newO) { 

/// @audit Missing @return for all function parameters
440:     function getOrderId( 
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

/// @audit Missing @return for all function parameters
826:     function findOrderHintId( 
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {

/// @audit Missing @return for all function parameters
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) { 

/// @audit Missing @return for all function parameters
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) { 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30), [35](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35), [55](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L55-L59), [78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L78), [362](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L362-L367), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L447), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L830), [985](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L985), [989](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Missing @return for all function parameters
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {

/// @audit Missing @return for all function parameters
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {

/// @audit Missing @return for all function parameters
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 
103:         internal
104:         view
105:         returns (bool recoveryViolation)
106:     {
```
[49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L106)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Missing @return for all function parameters
11:     function observe(uint32[] calldata secondsAgos) 

/// @audit Missing @return for all function parameters
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken) 
29:         internal
30:         pure
31:         returns (uint256 quoteAmount)
32:     {

/// @audit Missing @return for all function parameters
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11), [28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28-L32), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

</details>


---
### [NC&#x2011;48] Not using the latest versions of project dependencies
Update the project dependencies to their latest versions wherever possible.

Use tools such as `retire.js`, `npm audit`, and `yarn audit` to confirm that no vulnerable dependencies remain.

|Dependency|Current Version|Latest Version|
|:-:|:-:|:-:|
|`openzeppelin-contracts`|4.9.0|5.0.2|
|`forge-std`|github:foundry-rs/forge-std#v1.7.4|1.8.1|
|`solmate`|6.2.0|6|



<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1)


---
### [NC&#x2011;49] Not using the named return variables anywhere in the function is confusing
Declaring named returns, but not using them, is confusing to the reader. Consider either completely removing them (by declaring just the type without a name), or remove the return statement and do a variable assignment.

This would improve the readability of the code, and it may also help reduce regressions during future code refactors.

If the optimizer is not turned on, leaving the code as it is will also waste gas for the stack variable.

<details>
<summary><i>There are 22 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit ethFilled is unused
/// @audit ercAmountLeft is unused
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

/// @audit ethFilled is unused
/// @audit ercAmountLeft is unused
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

/// @audit ethFilled is unused
/// @audit ercAmountLeft is unused
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

/// @audit ethFilled is unused
/// @audit ercAmountLeft is unused
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

/// @audit ethFilled is unused
/// @audit ercAmountLeft is unused
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

/// @audit lowestSell is unused
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
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit cRatio is unused
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) { 
214:         return short.collateral.div(short.ercDebt);
215:     }
```
[213](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L213-L215)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit redemptionFee is unused
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
[382](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382-L403)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit fee is unused
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
[113](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113-L141)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit _protocolPrice is unused
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

/// @audit twapPriceInEth is unused
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

/// @audit creationTime is unused
156:     function getTime(address asset) internal view returns (uint256 creationTime) { 
157:         AppStorage storage s = appStorage();
158:         return s.bids[asset][C.HEAD].creationTime;
159:     }

/// @audit oraclePrice is unused
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) { 
163:         AppStorage storage s = appStorage();
164:         return uint80(s.bids[asset][C.HEAD].ercAmount);
165:     }
```
[69](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69-L115), [131](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L131-L143), [156](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L156-L159), [162](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162-L165)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit timeInSeconds is unused
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) { 
31:         // shouldn't overflow in 136 years
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)
33:     }

/// @audit direction is unused
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

/// @audit direction is unused
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

/// @audit direction is unused
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

/// @audit newO is unused
420:     function normalizeOrderType(O o) private pure returns (O newO) { 
421:         if (o == O.LimitBid || o == O.MarketBid) {
422:             return O.LimitBid;
423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {
424:             return O.LimitAsk;
425:         } else if (o == O.LimitShort) {
426:             return O.LimitShort;
427:         }
428:     }

/// @audit _hintId is unused
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

/// @audit hintId is unused
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
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L30-L33), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231-L248), [260](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L260-L279), [402](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L402-L417), [420](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L420-L428), [440](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440-L462), [826](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L826-L851)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit isCancelled is unused
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

/// @audit recoveryViolation is unused
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
[49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L70), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102-L122)

</details>


---
### [NC&#x2011;50] Outdated Solidity version
Upgrade to the latest solidity version.

<a href="https://blog.soliditylang.org/2021/04/21/solidity-0.8.4-release-announcement/">0.8.4</a>: bytes.concat() instead of abi.encodePacked(<bytes>,<bytes>) 
<a href="https://blog.soliditylang.org/2022/02/16/solidity-0.8.12-release-announcement/">0.8.12</a>: string.concat() instead of abi.encodePacked(<str>,<str>) 
<a href="https://blog.soliditylang.org/2022/03/16/solidity-0.8.13-release-announcement/">0.8.13</a>:
- Ability to use using for with a list of free functions

<a href="https://blog.soliditylang.org/2022/05/18/solidity-0.8.14-release-announcement/">0.8.14</a>:
- ABI Encoder: When ABI-encoding values from calldata that contain nested arrays, correctly validate the nested array length against calldatasize() in all cases.
- Override Checker: Allow changing data location for parameters only when overriding external functions.

<a href="https://blog.soliditylang.org/2022/06/15/solidity-0.8.15-release-announcement/">0.8.15</a>:
- Code Generation: Avoid writing dirty bytes to storage when copying bytes arrays.
- Yul Optimizer: Keep all memory side-effects of inline assembly blocks.

<a href="https://blog.soliditylang.org/2022/08/08/solidity-0.8.16-release-announcement/">0.8.16</a>:
 - Code Generation: Fix data corruption that affected ABI-encoding of calldata values represented by tuples: structs at any nesting level; argument lists of external functions, events and errors; return value lists of external functions. The 32 leading bytes of the first dynamically-encoded value in the tuple would get zeroed when the last component contained a statically-encoded array.

<a href="https://blog.soliditylang.org/2022/09/08/solidity-0.8.17-release-announcement/">0.8.17</a>:
 - Yul Optimizer: Prevent the incorrect removal of storage writes before calls to Yul functions that conditionally terminate the external EVM call.

<a href="https://blog.soliditylang.org/2023/02/22/solidity-0.8.19-release-announcement/">0.8.19</a>:
- SMTChecker: New trusted mode that assumes that any compile-time available code is the actual used code, even in external calls.

Bug Fixes:
- Assembler: Avoid duplicating subassembly bytecode where possible.
- Code Generator: Avoid including references to the deployed label of referenced functions if they are called right away.
- ContractLevelChecker: Properly distinguish the case of missing base constructor arguments from having an unimplemented base function.
- SMTChecker: Fix internal error caused by unhandled z3 expressions that come from the solver when bitwise operators are used.
- SMTChecker: Fix internal error when using the custom NatSpec annotation to abstract free functions.
- TypeChecker: Also allow external library functions in using for.

<a href="https://blog.soliditylang.org/2023/05/10/solidity-0.8.20-release-announcement/">0.8.20</a>:
- Assembler: Use push0 for placing 0 on the stack for EVM versions starting from “Shanghai”. This decreases the deployment and runtime costs.
- Optimizer: Re-implement simplified version of UnusedAssignEliminator and UnusedStoreEliminator. It can correctly remove some unused assignments in deeply nested loops that were ignored by the old version.
- Parser: Unary plus is no longer recognized as a unary operator in the AST and triggers an error at the parsing stage (rather than later during the analysis).
- SMTChecker: Group all messages about unsupported language features in a single warning. The CLI option --model-checker-show-unsupported and the JSON option settings.modelChecker.showUnsupported can be enabled to show the full list.
- SMTChecker: Properties that are proved safe are now reported explicitly at the end of analysis. By default, only the number of safe properties is shown. The CLI option --model-checker-show-proved-safe and the JSON option settings.modelChecker.showProvedSafe can be enabled to show the full list of safe properties.
- Standard JSON Interface: Add experimental support for importing ASTs via Standard JSON.
- Yul EVM Code Transform: If available, use push0 instead of codesize to produce an arbitrary value on stack in order to create equal stack heights between branches.

<a href="https://soliditylang.org/blog/2023/07/19/solidity-0.8.21-release-announcement">0.8.21</a>:
- Code Generator: Always generate code for the expression in `<expression>.selector` in the legacy code generation pipeline.
- Yul Optimizer: Fix FullInliner step (i) not preserving the evaluation order of arguments passed into inlined functions in code that is not in expression-split form.
- Allow qualified access to events from other contracts.
- Relax restrictions on initialization of immutable variables. Reads and writes may now happen at any point at construction time outside of functions and modifiers. Explicit initialization is no longer mandatory.


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
### [NC&#x2011;51] Overly complicated arithmetic
To maintain readability in code, particularly in Solidity which can involve complex mathematical operations, it is often recommended to limit the number of arithmetic operations to a maximum of 2-3 per line. Too many operations in a single line can make the code difficult to read and understand, increase the likelihood of mistakes, and complicate the process of debugging and reviewing the code.


<i>There are 5 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether); 

187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether); 

191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether); 

195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether); 

198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether); 
```
[183](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L183), [187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L187), [191](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L191), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L195), [198](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L198)


---
### [NC&#x2011;52] Place `interface` files into a dedicated folder
Using a separate folder for interfaces keeps the codebase organised and helps to facilitate security audits as well as future development.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool { 
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10)


---
### [NC&#x2011;53] Prefer skip over revert model in iteration
It is preferable to skip operations on an array index when a condition is not met rather than reverting the whole transaction as reverting can introduce the possiblity of malicous actors purposefully introducing array objects which fail conditional checks within for/while loops so group operations fail. As such it is recommended to simply skip such array indices over reverting unless there is a valid security or logic reason behind not doing so.


<i>There are 2 instaces of this issue:</i>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit reverts on line: 112
78:         for (uint8 i = 0; i < proposalInput.length; i++) { 

/// @audit reverts on line: 244
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) { 
```
[78](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78), [242](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242)


---
### [NC&#x2011;54] State variables should include comments
Consider adding some comments on critical state variables to explain what they are supposed to do: this will help for future code reviews.

<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge; 
27:     address private immutable stethBridge;
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26-L27)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

26:     address private immutable dusd; 
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

28:     address private immutable dusd; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

</details>


---
### [NC&#x2011;55] The `nonReentrant` `modifier` should occur before all other modifiers
This is a best-practice to protect against reentrancy in other modifiers

<details>
<summary><i>There are 10 instances of this issue:</i></summary>

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
```
[40](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40-L47)

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
📁 File: contracts/facets/RedemptionFacet.sol

56:     function proposeRedemption( 
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {

310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant { 

347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id) 
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
351:     {
```
[56](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56-L61), [224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228), [310](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310), [347](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347-L351)

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
### [NC&#x2011;56] Top-level declarations should be separated by at least two lines
<details>
<summary><i>There are 40 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers { 
21:     using U256 for uint256;
22:     using U88 for uint88;
23:     using U80 for uint80;
24:     using {LibOrders.isShort} for STypes.Order;
25: 
26:     /**
27:      * @notice Creates bid order in market
28:      * @dev IncomingBid created here instead of BidMatchAlgo to prevent stack too deep
29:      *
30:      * @param asset The market that will be impacted
31:      * @param price Unit price in eth for erc
32:      * @param ercAmount Amount of erc to buy
33:      * @param isMarketOrder Boolean for whether the bid is limit or market
34:      * @param orderHintArray Array of hint ID for gas-optimized sorted placement on market
35:      * @param shortHintArray Array of hint ID for gas-optimized short matching above oracle price
36:      *
37:      * @return ethFilled Amount of eth filled
38:      * @return ercAmountLeft Amount of erc not matched
39:      */
40:     function createBid(

75:     } 
76: 
77:     function _createBid(

356:     } 
357: 
358:     function _shortDirectionHandler(
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L20-L40), [75](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L75-L77), [356](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L356-L358)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using LibBridge for uint256;
22:     using LibBridge for address;
23:     using LibBridgeRouter for uint256;
24:     using LibVault for uint256;
25: 
26:     address private immutable rethBridge;
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18-L26)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers { 
20:     using U256 for uint256;
21:     using U80 for uint80;
22:     using U88 for uint88;
23:     using LibSRUtil for STypes.ShortRecord;
24:     using {LibAsset.burnMsgSenderDebt} for address;
25: 
26:     address private immutable dusd;
27: 
28:     constructor(address _dusd) {

211:     } 
212: 
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L19-L28), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L211-L213)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers { 
22:     using LibShortRecord for STypes.ShortRecord;
23:     using U256 for uint256;
24:     using U96 for uint96;
25:     using U88 for uint88;
26:     using U80 for uint80;
27: 
28:     address private immutable dusd;
29: 
30:     constructor(address _dusd) {

227:     } 
228: 
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21-L30), [227](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L227-L229)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers { 
22:     using LibSRUtil for STypes.ShortRecord;
23:     using LibShortRecord for STypes.ShortRecord;
24:     using U256 for uint256;
25:     using U104 for uint104;
26:     using U88 for uint88;
27:     using U80 for uint80;
28:     using U64 for uint64;
29:     using U32 for uint32;
30: 
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
```
[21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21-L31)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers { 
19:     using U256 for uint256;
20:     using U88 for uint88;
21:     using U80 for uint80;
22: 
23:     /**
24:      * @notice Creates limit short in market system
25:      * @dev incomingShort created here instead of AskMatchAlgo to prevent stack too deep
26:      * @dev Shorts can only be limits
27:      *
28:      * @param asset The market that will be impacted
29:      * @param price Unit price in eth for erc sold
30:      * @param ercAmount Amount of erc minted and sold
31:      * @param orderHintArray Array of hint ID for gas-optimized sorted placement on market
32:      * @param shortHintArray Array of hint ID for gas-optimized short matching above oracle price
33:      * @param shortOrderCR Initial Collateral Ratio for a short order, between min/max, converted to uint8
34:      */
35:     function createLimitShort(
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18-L35)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter { 
17:     using U256 for uint256;
18:     using U88 for uint88;
19: 
20:     // Credit user account with dETH and bridge credit if applicable
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16-L21)

```solidity
📁 File: contracts/libraries/LibBytes.sol

9: library LibBytes { 
10:     // Custom decode since SSTORE.write was written directly in proposeRedemption
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9-L11)

```solidity
📁 File: contracts/libraries/LibOracle.sol

16: library LibOracle { 
17:     using U256 for uint256;
18: 
19:     function getOraclePrice(address asset) internal view returns (uint256) {

67:     } 
68: 
69:     function baseOracleCircuitBreaker(

115:     } 
116: 
117:     function oracleCircuitBreaker(
```
[16](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16-L19), [67](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L67-L69), [115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L115-L117)

```solidity
📁 File: contracts/libraries/LibOrders.sol

20: library LibOrders { 
21:     using LibOracle for address;
22:     using LibVault for uint256;
23:     using U256 for uint256;
24:     using U104 for uint104;
25:     using U16 for uint16;
26:     using U80 for uint80;
27:     using U88 for uint88;
28: 
29:     // @dev in seconds
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

53:     } 
54: 
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

76:     } 
77: 
78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

80:     } 
81: 
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

101:     } 
102: 
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

626:     } 
627: 
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

726:     } 
727: 
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

808:     } 
809: 
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

824:     } 
825: 
826:     function findOrderHintId(

866:     } 
867: 
868:     function cancelAsk(address asset, uint16 id) internal {

880:     } 
881: 
882:     function cancelShort(address asset, uint16 id) internal {

983:     } 
984: 
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

987:     } 
988: 
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {

991:     } 
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20-L30), [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L53-L55), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L76-L78), [80](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L80-L82), [101](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L101-L103), [626](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L626-L628), [726](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L726-L728), [808](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L808-L810), [824](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L824-L826), [866](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L866-L868), [880](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L880-L882), [983](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L983-L985), [987](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L987-L989), [991](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L991-L55)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil { 
19:     using U88 for uint88;
20:     using U256 for uint256;
21: 
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

47:     } 
48: 
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

70:     } 
71: 
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

100:     } 
101: 
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

122:     } 
123: 
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

149:     } 
150: 
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```
[18](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18-L22), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L47-L49), [70](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L70-L72), [100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L100-L102), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L122-L124), [149](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L149-L151)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool { 
11:     function observe(uint32[] calldata secondsAgos)

21: library OracleLibrary { 
22:     /// @notice Given a tick and a token amount, calculates the amount of token received in exchange
23:     /// @param tick Tick value used to calculate the quote
24:     /// @param baseAmount Amount of token to be converted
25:     /// @param baseToken Address of an ERC20 token contract used as the baseAmount denomination
26:     /// @param quoteToken Address of an ERC20 token contract used as the quoteAmount denomination
27:     /// @return quoteAmount Amount of quoteToken received for baseAmount of baseToken
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)

45:     } 
46: 
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10-L11), [21](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21-L28), [45](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L45-L47)

</details>


---
### [NC&#x2011;57] Unnecessary cast
The variable is being cast to its own type

<details>
<summary><i>There are 3 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit div
197:             m = uint256(C.ONE_THIRD.div(0.1 ether)); 
```
[197](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L197)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit secondsAgo
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo)); 

/// @audit secondsAgo
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) { 
```
[62](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62), [65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)

</details>


---
### [NC&#x2011;58] Unused file
The file is never imported by any other source file. If the file is needed for tests, it should be moved to a test directory

<details>
<summary><i>There are 6 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L1-L6)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IBridge} from "contracts/interfaces/IBridge.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L1-L6)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L1-L6)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {IDiamond} from "interfaces/IDiamond.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L1-L6)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {Errors} from "contracts/libraries/Errors.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L1-L6)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

1: // SPDX-License-Identifier: GPL-3.0-only 
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
5: 
6: import {Errors} from "contracts/libraries/Errors.sol";
```
[1](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L1-L6)

</details>


---
### [NC&#x2011;59] Unused import
The identifier is imported but never used within the file

<details>
<summary><i>There are 20 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit STypes is unused
/// @audit MTypes is unused
11: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol"; 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L11)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit STypes is unused
/// @audit MTypes is unused
/// @audit SR is unused
11: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol"; 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L11)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit STypes is unused
/// @audit MTypes is unused
10: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol"; 
```
[10](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L10)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit STypes is unused
/// @audit MTypes is unused
9: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol"; 

/// @audit console is unused
19: import {console} from "contracts/libraries/console.sol"; 
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L9), [19](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L19)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit STypes is unused
/// @audit MTypes is unused
7: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol"; 
```
[7](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L7)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit STypes is unused
6: import {STypes} from "contracts/libraries/DataTypes.sol"; 
/// @audit AppStorage is unused
7: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
```
[6](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L6-L7)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit AppStorage is unused
9: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol"; 
```
[9](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L9)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit AppStorage is unused
8: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol"; 
/// @audit STypes is unused
/// @audit MTypes is unused
9: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";
```
[8](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L8-L9)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit STypes is unused
6: import {STypes, SR} from "contracts/libraries/DataTypes.sol"; 
/// @audit AppStorage is unused
7: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
```
[6](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L6-L7)

</details>


---
### [NC&#x2011;60] Use a struct to encapsulate multiple function parameters
If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.

<details>
<summary><i>There are 11 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray) 
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {
```
[65](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L65-L69)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

142:     function exitShort( 
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[142](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L142-L149)

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
📁 File: contracts/facets/RedemptionFacet.sol

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) 
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
```
[224](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224-L228)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge) 
40:         internal
41:         returns (uint88)
42:     {
```
[39](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39-L42)

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
📁 File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt) 
23:         internal
24:     {

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
50:         internal
51:         returns (bool isCancelled)
52:     {

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter) 
73:         internal
74:         returns (bool isCancelled)
75:     {
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L22-L24), [49](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L49-L52), [72](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72-L75)

```solidity
📁 File: contracts/libraries/UniswapOracleLibrary.sol

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken) 
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
```
[47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47-L51)

</details>


---
### [NC&#x2011;61] Use UPPER_CASE for `immutable`
Immutables should be in uppercase as stated [Solidity style guide](https://docs.soliditylang.org/en/latest/style-guide.html#constants).

<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge; 
27:     address private immutable stethBridge;
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L26-L27)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

26:     address private immutable dusd; 
```
[26](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L26)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

28:     address private immutable dusd; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

</details>


---
### [NC&#x2011;62] Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables
Variable names with all capital letters should be restricted to be used only with `constant` or `immutable` variables. 
If the variable needs to be different based on which class it comes from, a `view`/`pure` function should be used instead (e.g. like <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/76eee35971c2541585e05cbf258510dda7b2fbc6/contracts/token/ERC20/extensions/draft-IERC20Permit.sol#L59">this</a>).

<details>
<summary><i>There are 4 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

165:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

211:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 
```
[165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [211](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241)

```solidity
📁 File: contracts/libraries/LibBytes.sol

24:             uint64 CR; // bytes8 
```
[24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24)

</details>


---
### [NC&#x2011;63] `variable`/`struct`/`contract` names should be descriptive rather than cryptic
<details>
<summary><i>There are 44 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

100:         MTypes.BidMatchAlgo memory b; 
```
[100](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L100)

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

179:         uint256 m; 

230:         MTypes.DisputeRedemption memory d; 
```
[63](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L63), [179](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L179), [230](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L230)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

43:         MTypes.CreateLimitShortParam memory p; 

50:         uint256 cr = LibOrders.convertCR(shortOrderCR); 
```
[43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L43), [50](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L50)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

22:         AppStorage storage s = appStorage(); 

43:         AppStorage storage s = appStorage(); 

145:         AppStorage storage s = appStorage(); 

199:         AppStorage storage s = appStorage(); 
```
[22](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L22), [43](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L43), [145](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L145), [199](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L199)

```solidity
📁 File: contracts/libraries/LibBytes.sol

24:             uint64 CR; // bytes8 
```
[24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24)

```solidity
📁 File: contracts/libraries/LibOracle.sol

20:         AppStorage storage s = appStorage(); 

150:         AppStorage storage s = appStorage(); 

157:         AppStorage storage s = appStorage(); 

163:         AppStorage storage s = appStorage(); 
```
[20](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L20), [150](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L150), [157](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L157), [163](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L163)

```solidity
📁 File: contracts/libraries/LibOrders.sol

41:         AppStorage storage s = appStorage(); 

83:         AppStorage storage s = appStorage(); 

104:         AppStorage storage s = appStorage(); 

129:         AppStorage storage s = appStorage(); 

154:         O o = normalizeOrderType(incomingOrder.orderType); 

179:         AppStorage storage s = appStorage(); 

236:         AppStorage storage s = appStorage(); 

500:         AppStorage storage s = appStorage(); 

562:         AppStorage storage s = appStorage(); 

629:         O o = normalizeOrderType(incomingOrder.orderType); 

653:         AppStorage storage s = appStorage(); 

669:         AppStorage storage s = appStorage(); 

711:         AppStorage storage s = appStorage(); 

729:         AppStorage storage s = appStorage(); 

811:         AppStorage storage s = appStorage(); 

855:         AppStorage storage s = appStorage(); 

869:         AppStorage storage s = appStorage(); 
870:         STypes.Order storage ask = s.asks[asset][id];

883:         AppStorage storage s = appStorage(); 

956:         AppStorage storage s = appStorage(); 
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L41), [83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L83), [104](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L104), [129](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L129), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L154), [179](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L179), [236](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L236), [500](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L500), [562](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L562), [629](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L629), [653](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L653), [669](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L669), [711](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L711), [729](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L729), [811](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L811), [855](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L855), [869](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L869-L870), [883](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L883), [956](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L956)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

25:         AppStorage storage s = appStorage(); 

53:         AppStorage storage s = appStorage(); 

76:         AppStorage storage s = appStorage(); 

107:         AppStorage storage s = appStorage(); 

125:         AppStorage storage s = appStorage(); 

152:         AppStorage storage s = appStorage(); 
```
[25](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L25), [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L53), [76](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L76), [107](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L107), [125](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L125), [152](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L152)

</details>


---
### [NC&#x2011;64] Variables should be named in mixedCase style
As the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#naming-styles) suggests: arguments, local variables and mutable state variables should be named in mixedCase style.

Rule exceptions
- Allow constant variable name/symbol/decimals to be lowercase (ERC20).
- Allow `_` at the beginning of the mixedCase match for `private variables` and `unused parameters`.

<details>
<summary><i>There are 67 instances of this issue:</i></summary>

```solidity
📁 File: contracts/facets/BidOrdersFacet.sol

/// @audit Asset
89:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
232:                 STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
285:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Vault
300:             STypes.Vault storage Vault = s.vault[vault]; 
```
[89](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L89), [232](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L232), [285](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L285), [300](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L300)

```solidity
📁 File: contracts/facets/BridgeRouterFacet.sol

/// @audit _rethBridge
/// @audit _stethBridge
29:     constructor(address _rethBridge, address _stethBridge) { 
```
[29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
📁 File: contracts/facets/ExitShortFacet.sol

/// @audit _dusd
28:     constructor(address _dusd) { 

/// @audit Asset
47:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
93:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit AssetUser
102:             STypes.AssetUser storage AssetUser = s.assetUser[asset][msg.sender]; 

/// @audit Asset
154:         STypes.Asset storage Asset = s.asset[e.asset]; 

/// @audit VaultUser
182:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender]; 
```
[28](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L28), [47](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L47), [93](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L93), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L102), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L154), [182](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ExitShortFacet.sol#L182)

```solidity
📁 File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit _dusd
30:     constructor(address _dusd) { 

/// @audit TAPP
165:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 

/// @audit Asset
170:             STypes.Asset storage Asset = s.asset[m.asset]; 

/// @audit VaultUser
210:         STypes.VaultUser storage VaultUser = s.vaultUser[m.vault][msg.sender]; 
/// @audit TAPP
211:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];

/// @audit TAPP
241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)]; 
```
[30](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30), [165](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165), [170](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L170), [210](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L210-L211), [241](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241)

```solidity
📁 File: contracts/facets/RedemptionFacet.sol

/// @audit currentSR
83:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId]; 

/// @audit Asset
151:         STypes.Asset storage Asset = s.asset[p.asset]; 

/// @audit VaultUser
207:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender]; 

/// @audit disputeSR
248:         STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId]; 

/// @audit Asset
255:         STypes.Asset storage Asset = s.asset[d.asset]; 

/// @audit disputeCR
257:         uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice); 

/// @audit currentSR
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId]; 

/// @audit Asset
363:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
386:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit redeemedDUSDFraction
394:         uint256 redeemedDUSDFraction = ercDebtRedeemed.div(totalAssetErcDebt); 
```
[83](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L83), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L151), [207](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L207), [248](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L248), [255](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L255), [257](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L257), [266](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L266), [363](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L363), [386](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L386), [394](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L394)

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

/// @audit shortOrderCR
41:         uint16 shortOrderCR 

/// @audit Asset
44:         STypes.Asset storage Asset = s.asset[asset]; 
```
[41](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L41), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L44)

```solidity
📁 File: contracts/libraries/LibBridgeRouter.sol

/// @audit VaultUser
23:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender]; 

/// @audit VaultUser
44:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender]; 

/// @audit unitRethTWAP
118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH); 

/// @audit unitWstethTWAP
122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH); 

/// @audit Asset
147:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit VaultUserFrom
151:             STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from]; 

/// @audit VaultUserTo
154:             STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to]; 
```
[23](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L23), [44](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L44), [118](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L118), [122](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122), [147](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L147), [151](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L151), [154](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L154)

```solidity
📁 File: contracts/libraries/LibBytes.sol

/// @audit SSTORE2Pointer
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) { 

/// @audit CR
24:             uint64 CR; // bytes8 
```
[11](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11), [24](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24)

```solidity
📁 File: contracts/libraries/LibOracle.sol

/// @audit baseRoundID
27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) { 

/// @audit roundID
36:                     uint80 roundID, 

/// @audit roundID
53:                     uint80 roundID, 
```
[27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L27), [36](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L36), [53](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L53)

```solidity
📁 File: contracts/libraries/LibOrders.sol

/// @audit canceledID
187:         uint16 canceledID = orders[asset][C.HEAD].prevId; 

/// @audit prevCanceledID
195:             uint16 prevCanceledID = orders[asset][canceledID].prevId; 

/// @audit _prevId
/// @audit _newPrice
/// @audit _nextId
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId) 

/// @audit _prevId
263:         uint16 _prevId, 
/// @audit _newPrice
264:         uint256 _newPrice,
/// @audit _nextId
265:         uint16 _nextId

/// @audit prevHEAD
291:         uint16 prevHEAD = orders[asset][C.HEAD].prevId; 

/// @audit prevHEAD
315:         uint16 prevHEAD = orders[asset][C.HEAD].prevId; 

/// @audit prevHEAD
324:         uint16 prevHEAD, 

/// @audit _newPrice
445:         uint256 _newPrice, 

/// @audit Asset
670:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Vault
672:         STypes.Vault storage Vault = s.vault[vault]; 

/// @audit Asset
737:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
812:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Asset
891:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Vault
909:                     STypes.Vault storage Vault = s.vault[vault]; 

/// @audit Vault
958:         STypes.Vault storage Vault = s.vault[vault]; 
```
[187](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L187), [195](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L195), [231](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L231), [263](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L263-L265), [291](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L291), [315](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L315), [324](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L324), [445](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L445), [670](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L670), [672](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L672), [737](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L737), [812](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L812), [891](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L891), [909](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L909), [958](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L958)

```solidity
📁 File: contracts/libraries/LibSRUtil.sol

/// @audit Asset
27:         STypes.Asset storage Asset = s.asset[asset]; 

/// @audit Vault
29:         STypes.Vault storage Vault = s.vault[vault]; 

/// @audit shortRecordCR
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice) 

/// @audit recoveryCR
109:         uint256 recoveryCR = LibAsset.recoveryCR(asset); 

/// @audit Asset
112:             STypes.Asset storage Asset = s.asset[asset]; 

/// @audit assetCR
115:                 uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt)); 
```
[27](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L27), [29](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L29), [102](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102), [109](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L109), [112](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L112), [115](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L115)

</details>


---
### [NC&#x2011;65] Zero as a function argument should have a descriptive meaning
Consider using descriptive constants or an enum instead of passing zero directly on function calls, as that might be error-prone, to fully describe the caller's intention.


<i>There is one instance of this issue:</i>

```solidity
📁 File: contracts/facets/ShortOrdersFacet.sol

48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0); 
```
[48](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L48)
