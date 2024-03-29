## QA Summary<a name="QA Summary">

### Low Risk Issues
| |Issue|Contexts|
|-|:-|:-:|
| [LOW&#x2011;1](#LOW&#x2011;1) | Governance functions should be controlled by time locks | 1 |
| [LOW&#x2011;2](#LOW&#x2011;2) | Consider implementing two-step procedure for updating protocol addresses | 1 |
| [LOW&#x2011;3](#LOW&#x2011;3) | External calls in an un-bounded `for-`loop may result in a DOS | 2 |
| [LOW&#x2011;4](#LOW&#x2011;4) | Constructor is missing zero address check | 3 |
| [LOW&#x2011;5](#LOW&#x2011;5) | Cap state variables at reasonable values | 1 |
| [LOW&#x2011;6](#LOW&#x2011;6) | Missing Checks for Address(0x0) | 4 |
| [LOW&#x2011;7](#LOW&#x2011;7) | `mulDiv` may result in the result being zero when called by large numbers | 3 |

Total: 15 contexts over 7 issues

### Non-critical Issues
| |Issue|Contexts|
|-|:-|:-:|
| [NC&#x2011;1](#NC&#x2011;1) | Array lengths not checked | 2 |
| [NC&#x2011;2](#NC&#x2011;2) | Assembly block creates dirty bits | 1 |
| [NC&#x2011;3](#NC&#x2011;3) | Consider adding formal verification proofs | 6 |
| [NC&#x2011;4](#NC&#x2011;4) | Consider emitting an event at the end of the constructor | 3 |
| [NC&#x2011;5](#NC&#x2011;5) | Consider making contracts `Upgradeable` | 6 |
| [NC&#x2011;6](#NC&#x2011;6) | Constants in comparisons should appear on the left side | 18 |
| [NC&#x2011;7](#NC&#x2011;7) | Constructor declarations should have NatSpec descriptions | 3 |
| [NC&#x2011;8](#NC&#x2011;8) | Contract declarations should have NatSpec `@author` annotations | 12 |
| [NC&#x2011;9](#NC&#x2011;9) | Contracts should have NatSpec `@dev` tags | 6 |
| [NC&#x2011;10](#NC&#x2011;10) | Contract declarations should have NatSpec `@title` annotations | 11 |
| [NC&#x2011;11](#NC&#x2011;11) | Contracts with only unimplemented functions can be labeled as abstract | 6 |
| [NC&#x2011;12](#NC&#x2011;12) | Critical Changes Should Use Two-step Procedure | 1 |
| [NC&#x2011;13](#NC&#x2011;13) | Cyclomatic complexity in functions  | 5 |
| [NC&#x2011;14](#NC&#x2011;14) | Dependence on external protocols | 2 |
| [NC&#x2011;15](#NC&#x2011;15) | `else`-block not required | 3 |
| [NC&#x2011;16](#NC&#x2011;16) | Enable IR-based code generation | 1 |
| [NC&#x2011;17](#NC&#x2011;17) | Event Is Missing Indexed Fields | 1 |
| [NC&#x2011;18](#NC&#x2011;18) | Functions that alter state should emit events containing both the old and the new value | 1 |
| [NC&#x2011;19](#NC&#x2011;19) | Functions should have `@notice` tags | 32 |
| [NC&#x2011;20](#NC&#x2011;20) | Large or complicated code bases should implement fuzzing tests | 1 |
| [NC&#x2011;21](#NC&#x2011;21) | Use `delete` to Clear Variables | 12 |
| [NC&#x2011;22](#NC&#x2011;22) | `if`-statement can be converted to a ternary | 16 |
| [NC&#x2011;23](#NC&#x2011;23) | Imports can be grouped together | 95 |
| [NC&#x2011;24](#NC&#x2011;24) | Inconsistent Spacing In Comments | 1 |
| [NC&#x2011;25](#NC&#x2011;25) | Incorrect withdraw declaration | 3 |
| [NC&#x2011;26](#NC&#x2011;26) | Contracts should have full test coverage | 1 |
| [NC&#x2011;27](#NC&#x2011;27) | Interface imports should be declared first | 8 |
| [NC&#x2011;28](#NC&#x2011;28) | Invalid NatSpec comment style | 115 |
| [NC&#x2011;29](#NC&#x2011;29) | Assembly blocks should have extensive comments | 1 |
| [NC&#x2011;30](#NC&#x2011;30) | Large or complicated code bases should implement invariant tests | 1 |
| [NC&#x2011;31](#NC&#x2011;31) | Missing Contract-existence Checks Before Low-level Calls | 5 |
| [NC&#x2011;32](#NC&#x2011;32) | Missing event for critical parameter change | 1 |
| [NC&#x2011;33](#NC&#x2011;33) | NatSpec `@return` argument is missing | 2 |
| [NC&#x2011;34](#NC&#x2011;34) | No equate comparison checks between `to` and `from` address parameters | 2 |
| [NC&#x2011;35](#NC&#x2011;35) | The `nonReentrant` modifier should occur before all other modifiers | 10 |
| [NC&#x2011;36](#NC&#x2011;36) | Overly complicated arithmetic | 5 |
| [NC&#x2011;37](#NC&#x2011;37) | `private` and `internal` variables should have a preceding `_` in their name | 4 |
| [NC&#x2011;38](#NC&#x2011;38) | Project should include an `EmergencyStop` pattern | 6 |
| [NC&#x2011;39](#NC&#x2011;39) | Top-level declarations should be separated by at least two lines | 18 |
| [NC&#x2011;40](#NC&#x2011;40) | Unused event may be unused code or indicative of missed emit/logic | 1 |
| [NC&#x2011;41](#NC&#x2011;41) | Upgrade OpenZeppelin Contract Dependency | 1 |
| [NC&#x2011;42](#NC&#x2011;42) | Use a struct to encapsulate multiple function parameters | 1 |
| [NC&#x2011;43](#NC&#x2011;43) | Use SafeCast to safely downcast variables | 19 |
| [NC&#x2011;44](#NC&#x2011;44) | Use SMTChecker | 1 |
| [NC&#x2011;45](#NC&#x2011;45) | Variable names for `immutable`s should use CONSTANT_CASE | 4 |
| [NC&#x2011;46](#NC&#x2011;46) | Zero as a function argument should have a descriptive meaning | 1 |

Total: 455 contexts over 46 issues

## Low Risk Issues

### <a href="#qa-summary">[LOW&#x2011;1]</a><a name="LOW&#x2011;1"> Governance functions should be controlled by time locks 

Governance functions (such as upgrading contracts, setting critical parameters) should be controlled using time locks to introduce a delay between a proposal and its execution. This gives users time to exit before a potentially dangerous or malicious operation is applied.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149







### <a href="#qa-summary">[LOW&#x2011;2]</a><a name="LOW&#x2011;2"> Consider implementing two-step procedure for updating protocol addresses 

A copy-paste error or a typo may end up bricking protocol functionality, or sending tokens to an address with no known private key. Consider implementing a two-step procedure for updating protocol addresses, where the recipient is set as pending, and must 'accept' the assignment by making an affirmative call. A straight forward way of doing this would be to have the target contracts implement [EIP-165](https://eips.ethereum.org/EIPS/eip-165), and to have the 'set' functions ensure that the recipient is of the right interface type.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149





### <a href="#qa-summary">[LOW&#x2011;3]</a><a name="LOW&#x2011;3"> External calls in an un-bounded `for-`loop may result in a DOS 

Consider limiting the number of iterations in `for-`loops that make external calls

#### <ins>Proof Of Concept</ins>

```solidity
File: RedemptionFacet.sol

242: for (uint256 i = 0; i < decodedProposalData.length; i++) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L242

```solidity
File: RedemptionFacet.sol

321: for (uint256 i = 0; i < decodedProposalData.length; i++) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L321





### <a href="#qa-summary">[LOW&#x2011;4]</a><a name="LOW&#x2011;4"> Constructor is missing zero address check 

In Solidity, constructors often take address parameters to initialize important components of a contract, such as owner or linked contracts. However, without a check, there's a risk that an address parameter could be mistakenly set to the zero address (0x0). This could occur due to a mistake or oversight during contract deployment. A zero address in a crucial role can cause serious issues, as it cannot perform actions like a normal address, and any funds sent to it are irretrievable. Therefore, it's crucial to include a zero address check in constructors to prevent such potential problems. If a zero address is detected, the constructor should revert the transaction.

#### <ins>Proof Of Concept</ins>

```solidity
File: BridgeRouterFacet.sol

29: constructor: address _rethBridge
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L29

```solidity
File: ExitShortFacet.sol

28: constructor: address _dusd
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L28

```solidity
File: PrimaryLiquidationFacet.sol

30: constructor: address _dusd
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L30






### <a href="#qa-summary">[LOW&#x2011;5]</a><a name="LOW&#x2011;5"> Cap state variables at reasonable values 

Consider adding maximum value checks to ensure that state variables cannot be set to values that may excessively harm users.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibOracle.sol


function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
        AppStorage storage s = appStorage();
        s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
        s.bids[asset][C.HEAD].creationTime = oracleTime;
    }

```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149







### <a href="#qa-summary">[LOW&#x2011;6]</a><a name="LOW&#x2011;6"> Missing Checks for Address(0x0) 

Lack of zero-address validation on address parameters may lead to transaction reverts, waste gas, require resubmission of transactions and may even force contract redeployments in certain cases within the protocol.

#### <ins>Proof Of Concept</ins>


```solidity
File: ExitShortFacet.sol

143: function exitShort: address asset
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L143

```solidity
File: RedemptionFacet.sol

57: function proposeRedemption: address asset
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L57

```solidity
File: RedemptionFacet.sol

224: function disputeRedemption: address asset
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L224

```solidity
File: LibSRUtil.sol

124: function transferShortRecord: address to
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L124



#### <ins>Recommended Mitigation Steps</ins>

Consider adding explicit zero-address validation on input parameters of address type.



### <a href="#qa-summary">[LOW&#x2011;7]</a><a name="LOW&#x2011;7"> `mulDiv` may result in the result being zero when called by large numbers 

Division by large numbers may result in the result being zero, due to solidity not supporting fractions. Consider requiring a minimum amount for the numerator to ensure that it is always larger than the denominator.

#### <ins>Proof Of Concept</ins>


```solidity
File: UniswapOracleLibrary.sol

39: baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

41: uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);

43: baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L39

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L41

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L43




## Non Critical Issues

### <a href="#qa-summary">[NC&#x2011;1]</a><a name="NC&#x2011;1"> Array lengths not checked 

If the length of the arrays are not required to be of the same length, user operations may not be fully executed

#### <ins>Proof Of Concept</ins>


```solidity
File: BidOrdersFacet.sol


function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L77-L78

```solidity
File: ShortOrdersFacet.sol


function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {

```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L35-L36






### <a href="#qa-summary">[NC&#x2011;2]</a><a name="NC&#x2011;2"> Assembly block creates dirty bits 

Manipulating data directly at the free memory pointer location without subsequently adjusting the pointer can lead to unwanted data remnants, or "dirty bits", in that memory spot. This can cause challenges for the Solidity optimizer, making it difficult to determine if memory cleaning is required before reuse, potentially resulting in less efficient optimization. To mitigate this issue, it's advised to always update the free memory pointer following any data write operation. Furthermore, using the `assembly ("memory-safe") { ... }` annotation will clearly indicate to the optimizer the sections of your code that are memory-safe, improving code efficiency and reducing the potential for errors.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibBytes.sol

11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {

		...

		assembly {
                
                let fullWord := mload(add(slate, offset))
                
                shorter := shr(96, fullWord) 
                
                shortId := and(0xff, shr(88, fullWord)) 
                
                CR := and(0xffffffffffffffff, shr(24, fullWord)) 

                fullWord := mload(add(slate, add(offset, 29))) 
                
                ercDebtRedeemed := shr(168, fullWord) 
                
                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) 
            }

		...


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L11






### <a href="#qa-summary">[NC&#x2011;3]</a><a name="NC&#x2011;3"> Consider adding formal verification proofs 

Formal verification is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification/property/invariant, using formal methods of mathematics.

Some tools that are currently available to perform these tests on smart contracts are [SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html) and [Certora Prover](https://www.certora.com/).

There are 6 instances:

- [*DestinationBridge.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/bridge/DestinationBridge.sol)

- [*SourceBridge.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/bridge/SourceBridge.sol)

- [*IRWADynamicOracle.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/rwaOracles/IRWADynamicOracle.sol)

- [*RWADynamicOracle.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/rwaOracles/RWADynamicOracle.sol)

- [*rUSDY.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/usdy/rUSDY.sol)

- [*rUSDYFactory.sol*](https://github.com/code-423n4/2023-09-ondo/tree/623dd3c0ff3c4d8ce4ed563b96da50d08cd803c5/contracts/usdy/rUSDYFactory.sol)



### <a href="#qa-summary">[NC&#x2011;4]</a><a name="NC&#x2011;4"> Consider emitting an event at the end of the constructor 

This will allow users to easily exactly pinpoint when and by whom a contract was constructed

#### <ins>Proof Of Concept</ins>


```solidity
File: BridgeRouterFacet.sol

29: constructor(address _rethBridge, address _stethBridge) {
        rethBridge = _rethBridge;
        stethBridge = _stethBridge;
    }
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L29

```solidity
File: ExitShortFacet.sol

28: constructor(address _dusd) {
        dusd = _dusd;
    }
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L28

```solidity
File: PrimaryLiquidationFacet.sol

30: constructor(address _dusd) {
        dusd = _dusd;
    }
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L30






### <a href="#qa-summary">[NC&#x2011;5]</a><a name="NC&#x2011;5"> Consider making contracts `Upgradeable` 

This allows for bugs to be fixed in production, at the expense of significantly increasing centralization.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L20

```solidity
File: BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L18

```solidity
File: ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L19

```solidity
File: PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L21


```solidity
File: RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L21

```solidity
File: ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L18


</details>



### <a href="#qa-summary">[NC&#x2011;6]</a><a name="NC&#x2011;6"> Constants in comparisons should appear on the left side 

Putting constants on the left side of a comparison operator like `==` or `<` is a best practice known as "Yoda conditions", which can help prevent accidental assignment instead of comparison. In some programming languages, if a variable is mistakenly put on the left with a single `=` instead of `==`, it assigns the constant's value to the variable without any compiler error. However, doing this with the constant on the left would generate an error, as constants cannot be assigned values. Although Solidity's static typing system prevents accidental assignments within conditionals, adopting this practice enhances code readability and consistency, especially when developers are working across multiple languages that support this convention.

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: BidOrdersFacet.sol

281: if (matchTotal.fillEth == 0) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L281

```solidity
File: BridgeRouterFacet.sol

102: if (dethAmount == 0) revert Errors.ParameterIsZero();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L102

```solidity
File: BridgeRouterFacet.sol

134: if (dethAmount == 0) revert Errors.ParameterIsZero();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L134

```solidity
File: BridgeRouterFacet.sol

164: if (vault == 0) revert Errors.InvalidBridge();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L164

```solidity
File: ExitShortFacet.sol

53: if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L53

```solidity
File: ExitShortFacet.sol

99: if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L99

```solidity
File: ExitShortFacet.sol

174: if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L174

```solidity
File: ExitShortFacet.sol

188: if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L188

```solidity
File: RedemptionFacet.sol

371: if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L371

```solidity
File: LibOracle.sol

60: if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L60

```solidity
File: LibOracle.sol

76: bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L76

```solidity
File: LibOracle.sol

89: if (twapPrice == 0) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L89

```solidity
File: LibOracle.sol

125: bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L125

```solidity
File: LibOracle.sol

126: || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L126

```solidity
File: LibOracle.sol

134: if (twapPrice == 0) revert Errors.InvalidTwapPrice();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L134

```solidity
File: LibOrders.sol

371: if (hintId == 0 || nextId == 0) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L371

```solidity
File: LibOrders.sol

677: SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L677

```solidity
File: LibSRUtil.sol

131: if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L131



</details>




### <a href="#qa-summary">[NC&#x2011;7]</a><a name="NC&#x2011;7"> Constructor declarations should have NatSpec descriptions 

#### <ins>Proof Of Concept</ins>

```solidity
File: BridgeRouterFacet.sol

29: constructor(address _rethBridge, address _stethBridge) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L29

```solidity
File: ExitShortFacet.sol

28: constructor(address _dusd) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L28

```solidity
File: PrimaryLiquidationFacet.sol

30: constructor(address _dusd) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L30





### <a href="#qa-summary">[NC&#x2011;8]</a><a name="NC&#x2011;8"> Contract declarations should have NatSpec `@author` annotations 

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: 

BidOrdersFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol
```



```solidity
File: 

BridgeRouterFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol
```



```solidity
File: 

ExitShortFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol
```



```solidity
File: 

PrimaryLiquidationFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol
```



```solidity
File: 

RedemptionFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol
```



```solidity
File: 

ShortOrdersFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol
```



```solidity
File: 

LibBridgeRouter.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol
```



```solidity
File: 

LibBytes.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol
```



```solidity
File: 

LibOracle.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol
```



```solidity
File: 

LibOrders.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol
```



```solidity
File: 

LibSRUtil.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol
```



```solidity
File: 

UniswapOracleLibrary.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol
```





</details>



### <a href="#qa-summary">[NC&#x2011;9]</a><a name="NC&#x2011;9"> Contracts should have NatSpec `@dev` tags 

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L20

```solidity
File: BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L18

```solidity
File: ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L19

```solidity
File: PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L21

```solidity
File: RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L21

```solidity
File: ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L18



</details>



### <a href="#qa-summary">[NC&#x2011;10]</a><a name="NC&#x2011;10"> Contract declarations should have NatSpec `@title` annotations 

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: 

BidOrdersFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol
```



```solidity
File: 

BridgeRouterFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol
```



```solidity
File: 

ExitShortFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol
```



```solidity
File: 

PrimaryLiquidationFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol
```



```solidity
File: 

RedemptionFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol
```



```solidity
File: 

ShortOrdersFacet.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol
```



```solidity
File: 

LibBridgeRouter.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol
```



```solidity
File: 

LibBytes.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol
```



```solidity
File: 

LibOracle.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol
```



```solidity
File: 

LibOrders.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol
```



```solidity
File: 

LibSRUtil.sol

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol
```





</details>



### <a href="#qa-summary">[NC&#x2011;11]</a><a name="NC&#x2011;11"> Contracts with only unimplemented functions can be labeled as abstract 

In Solidity, a contract that's not meant to be deployed on its own but is intended to be inherited by other contracts should be marked `abstract`. This ensures that developers recognize the contract's incomplete or intended-to-be-extended nature. If a contract has unimplemented functions or is designed with the intention that another contract should extend its functionality, it should be explicitly labeled as `abstract`. 
This helps prevent inadvertent deployments and clearly communicates the contract's purpose to other developers. Resolution: Review the contract, and if it's not supposed to function standalone, mark it as `abstract` to make the intention clear.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L20

```solidity
File: BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L18

```solidity
File: ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L19

```solidity
File: PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L21

```solidity
File: RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L21

```solidity
File: ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L18



</details>




### <a href="#qa-summary">[NC&#x2011;12]</a><a name="NC&#x2011;12"> Critical Changes Should Use Two-step Procedure 

The critical procedures should be two step process.

#### <ins>Proof Of Concept</ins>

```solidity
File: LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149



#### <ins>Recommended Mitigation Steps</ins>

Lack of two-step procedure for critical operations leaves them error-prone. Consider adding two step procedure on the critical functions.




### <a href="#qa-summary">[NC&#x2011;13]</a><a name="NC&#x2011;13"> Cyclomatic complexity in functions  

Cyclomatic complexity is a software metric used to measure the complexity of a program. It quantifies the number of linearly independent paths through a program's source code, giving an idea of how complex the control flow is. High cyclomatic complexity may indicate a higher risk of defects and can make the code harder to understand, test, and maintain. It often suggests that a function or method is trying to do too much, and a refactor might be needed. By breaking down complex functions into smaller, more focused pieces, you can improve readability, ease of testing, and overall maintainability.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
        uint256 minBidEth = LibAsset.minBidEth(asset);
        MTypes.Match memory matchTotal;

        while (true) {
            
            if (b.askId == C.TAIL && b.shortId == C.TAIL) {
                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
                    LibOrders.addBid(asset, incomingBid, orderHintArray);
                }
                return matchIncomingBid(asset, incomingBid, matchTotal, b);
            }

            STypes.Order memory lowestSell = _getLowestSell(asset, b);

            if (incomingBid.price >= lowestSell.price) {
                
                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
                }
                matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
                if (incomingBid.ercAmount > lowestSell.ercAmount) {
                    incomingBid.ercAmount -= lowestSell.ercAmount;
                    lowestSell.ercAmount = 0;
                    if (lowestSell.isShort()) {
                        b.matchedShortId = lowestSell.id;
                        b.prevShortId = lowestSell.prevId;
                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
                    } else {
                        b.matchedAskId = lowestSell.id;
                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
                        b.askId = lowestSell.nextId;
                    }
                } else {
                    if (incomingBid.ercAmount == lowestSell.ercAmount) {
                        if (lowestSell.isShort()) {
                            b.matchedShortId = lowestSell.id;
                            b.prevShortId = lowestSell.prevId;
                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
                        } else {
                            b.matchedAskId = lowestSell.id;
                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
                        }
                    } else {
                        lowestSell.ercAmount -= incomingBid.ercAmount;
                        if (lowestSell.isShort()) {
                            b.dustShortId = lowestSell.id;
                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
                            lowestShort.ercAmount = lowestSell.ercAmount;
                        } else {
                            b.dustAskId = lowestSell.id;
                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
                        }
                        
                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
                            b.dustShortId = b.dustAskId = 0;
                        }
                    }
                    incomingBid.ercAmount = 0;
                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
                }
            } else {
                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
                    LibOrders.addBid(asset, incomingBid, orderHintArray);
                }
                return matchIncomingBid(asset, incomingBid, matchTotal, b);
            }
        }
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L131

```solidity
File: BidOrdersFacet.sol

275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
        if (matchTotal.fillEth == 0) {
            return (0, incomingBid.ercAmount);
        }

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;

        LibOrders.updateSellOrdersOnMatch(asset, b);

        
        
        if (b.dustAskId > 0) {
            IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
        } else if (b.dustShortId > 0) {
            IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
        }

        
        if (matchTotal.shortFillEth > 0) {
            STypes.Vault storage Vault = s.vault[vault];

            
            Vault.dittoMatchedShares += matchTotal.dittoMatchedShares;
            
            Vault.dethCollateral += matchTotal.shortFillEth;
            Asset.dethCollateral += matchTotal.shortFillEth;
            Asset.ercDebt += matchTotal.fillErc - matchTotal.askFillErc;

            
            STypes.Order storage currentShort = s.shorts[asset][b.shortId];
            O shortOrderType = currentShort.orderType;
            STypes.Order storage prevShort = s.shorts[asset][b.prevShortId];
            O prevShortOrderType = prevShort.orderType;

            if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
                Asset.startingShortId = b.shortId;
            } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
                Asset.startingShortId = b.prevShortId;
            } else {
                if (b.isMovingFwd) {
                    Asset.startingShortId = currentShort.nextId;
                } else {
                    Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
                }
            }
        }

        
        address bidder = incomingBid.addr; 
        s.vaultUser[vault][bidder].ethEscrowed -= matchTotal.fillEth;
        s.assetUser[asset][bidder].ercEscrowed += matchTotal.fillErc;
        emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);

        
        LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);
        return (matchTotal.fillEth, incomingBid.ercAmount);
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L276

```solidity
File: RedemptionFacet.sol

56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
        if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
        MTypes.ProposeRedemption memory p;
        p.asset = asset;
        STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
        uint256 minShortErc = LibAsset.minShortErc(p.asset);

        if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();

        if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();

        
        if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();

        p.oraclePrice = LibOracle.getPrice(p.asset);

        bytes memory slate;
        for (uint8 i = 0; i < proposalInput.length; i++) {
            p.shorter = proposalInput[i].shorter;
            p.shortId = proposalInput[i].shortId;
            p.shortOrderId = proposalInput[i].shortOrderId;
            
            STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];

            

            if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;

            currentSR.updateErcDebt(p.asset);
            p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);

            
            if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;

            
            if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
                p.amountProposed = currentSR.ercDebt;
            } else {
                p.amountProposed = redemptionAmount - p.totalAmountProposed;
                
                if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
            }

            

            p.previousCR = p.currentCR;

            
            
            STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
            if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
                if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
                LibOrders.cancelShort(asset, p.shortOrderId);
            }

            p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
            if (p.colRedeemed > currentSR.collateral) {
                p.colRedeemed = currentSR.collateral;
            }

            currentSR.collateral -= p.colRedeemed;
            currentSR.ercDebt -= p.amountProposed;

            p.totalAmountProposed += p.amountProposed;
            p.totalColRedeemed += p.colRedeemed;

            
            
            slate = bytes.concat(
                slate,
                bytes20(p.shorter),
                bytes1(p.shortId),
                bytes8(uint64(p.currentCR)),
                bytes11(p.amountProposed),
                bytes11(p.colRedeemed)
            );

            LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
            p.redemptionCounter++;
            if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
        }

        if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();

        
        redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
        redeemerAssetUser.slateLength = p.redemptionCounter;
        redeemerAssetUser.oraclePrice = p.oraclePrice;
        redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;

        STypes.Asset storage Asset = s.asset[p.asset];
        Asset.ercDebt -= p.totalAmountProposed;

        uint32 protocolTime = LibOrders.getOffsetTime();
        redeemerAssetUser.timeProposed = protocolTime;
        
        

        

        uint256 m;

        if (p.currentCR > 1.7 ether) {
            m = uint256(3 ether).div(0.3 ether);
            redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.5 ether) {
            m = uint256(1.5 ether).div(0.2 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.3 ether) {
            m = uint256(0.75 ether).div(0.2 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.2 ether) {
            m = uint256(0.417 ether).div(0.1 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.1 ether) {
            m = uint256(C.ONE_THIRD.div(0.1 ether));
            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
        }

        redeemerAssetUser.oraclePrice = p.oraclePrice;
        redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();

        uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
        if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();

        STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
        if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
        VaultUser.ethEscrowed -= redemptionFee;
        emit Events.ProposeRedemption(p.asset, msg.sender);
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L57

```solidity
File: LibBridgeRouter.sol

39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
        AppStorage storage s = appStorage();
        STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];

        uint88 creditReth;
        uint88 creditSteth;
        if (bridgePointer == VAULT.BRIDGE_RETH) {
            
            creditReth = VaultUser.bridgeCreditReth;
            if (creditReth >= amount) {
                VaultUser.bridgeCreditReth -= amount;
                return 0;
            }

            VaultUser.bridgeCreditReth = 0;
            amount -= creditReth;
            creditSteth = VaultUser.bridgeCreditSteth;
            if (creditSteth < C.ROUNDING_ZERO) {
                
                return amount;
            } else {
                if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    
                    if (creditSteth >= amount) {
                        VaultUser.bridgeCreditSteth -= amount;
                        return 0;
                    } else {
                        VaultUser.bridgeCreditSteth = 0;
                        return amount - creditSteth;
                    }
                } else {
                    
                    
                    revert Errors.MustUseExistingBridgeCredit();
                }
            }
        } else {
            
            creditSteth = VaultUser.bridgeCreditSteth;
            if (creditSteth >= amount) {
                VaultUser.bridgeCreditSteth -= amount;
                return 0;
            }

            VaultUser.bridgeCreditSteth = 0;
            amount -= creditSteth;
            creditReth = VaultUser.bridgeCreditReth;
            if (creditReth < C.ROUNDING_ZERO) {
                
                return amount;
            } else {
                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    
                    if (creditReth >= amount) {
                        VaultUser.bridgeCreditReth -= amount;
                        return 0;
                    } else {
                        VaultUser.bridgeCreditReth = 0;
                        return amount - creditReth;
                    }
                } else {
                    
                    
                    revert Errors.MustUseExistingBridgeCredit();
                }
            }
        }
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L39

```solidity
File: LibBridgeRouter.sol

144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
        AppStorage storage s = appStorage();

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;

        if (vault == VAULT.ONE) {
            STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
            uint88 creditReth = VaultUserFrom.bridgeCreditReth;
            uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
            STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];

            if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                
                return;
            }

            if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                
                if (creditReth > collateral) {
                    VaultUserFrom.bridgeCreditReth -= collateral;
                    VaultUserTo.bridgeCreditReth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserTo.bridgeCreditReth += creditReth;
                }
            } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
                
                if (creditSteth > collateral) {
                    VaultUserFrom.bridgeCreditSteth -= collateral;
                    VaultUserTo.bridgeCreditSteth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditSteth = 0;
                    VaultUserTo.bridgeCreditSteth += creditSteth;
                }
            } else {
                
                uint88 creditTotal = creditReth + creditSteth;
                if (creditTotal > collateral) {
                    creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
                    creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
                    VaultUserFrom.bridgeCreditReth -= creditReth;
                    VaultUserFrom.bridgeCreditSteth -= creditSteth;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserFrom.bridgeCreditSteth = 0;
                }
                VaultUserTo.bridgeCreditReth += creditReth;
                VaultUserTo.bridgeCreditSteth += creditSteth;
            }
        }
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L144



</details>




### <a href="#qa-summary">[NC&#x2011;14]</a><a name="NC&#x2011;14"> Dependence on external protocols 

External protocols should be monitored as such dependencies may introduce vulnerabilities if a vulnerability is found /introduced in the external protocol

#### <ins>Proof Of Concept</ins>

```solidity
File: LibBridgeRouter.sol

8: import {OracleLibrary} from "contracts/libraries/UniswapOracleLibrary.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L8

```solidity
File: UniswapOracleLibrary.sol

7: import {TickMath} from "contracts/libraries/UniswapTickMath.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L7






### <a href="#qa-summary">[NC&#x2011;15]</a><a name="NC&#x2011;15"> `else`-block not required 

One level of nesting can be removed by not having an `else` block when the `if`-block returns, and `if (foo) { return 1; } else { return 2; }` becomes `if (foo) { return 1; } return 2;`

#### <ins>Proof Of Concept</ins>


```solidity
File: RedemptionFacet.sol

38: if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
            return false;
        } else {
            return true;
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L38

```solidity
File: LibOracle.sol

169: if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
            return getPrice(asset);
        } else {
            return getOraclePrice(asset);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L169

```solidity
File: LibOrders.sol

383: } else if (direction == C.NEXT) {
            return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
        } else {
            uint16 prevId = orders[asset][hintId].prevId;
            return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L383






### <a href="#qa-summary">[NC&#x2011;16]</a><a name="NC&#x2011;16"> Enable IR-based code generation 

The IR-based code generator was introduced with an aim to not only allow code generation to be more transparent and auditable but also to enable more powerful optimization passes that span across functions.
You can enable it on the command line using `--via-ir` or with the option `{"viaIR": true}`.
This will take longer to compile, but you can just simple test it before deploying and if you got a better benchmark then you can add --via-ir to your deploy command
More on: https://docs.soliditylang.org/en/v0.8.17/ir-breaking-changes.html




### <a href="#qa-summary">[NC&#x2011;17]</a><a name="NC&#x2011;17"> Event Is Missing Indexed Fields 

Index event fields make the field more quickly accessible [to off-chain tools](https://ethereum.stackexchange.com/questions/40396/can-somebody-please-explain-the-concept-of-event-indexing) that parse events. This is especially useful when it comes to filtering based on an address. However, note that each index field costs extra gas during emission, so it's not necessarily best to index the maximum allowed per event (three fields). Where applicable, each `event` should use three `indexed` fields if there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three applicable fields, all of the applicable fields should be indexed.

#### <ins>Proof Of Concept</ins>


```solidity
File: ExitShortFacet.sol

event forcedBid from exitShort() matching with original shortOrder
        e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L157






### <a href="#qa-summary">[NC&#x2011;18]</a><a name="NC&#x2011;18"> Functions that alter state should emit events containing both the old and the new value 

#### <ins>Proof Of Concept</ins>


```solidity
File: LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
        AppStorage storage s = appStorage();
        s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
        s.bids[asset][C.HEAD].creationTime = oracleTime;
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149






### <a href="#qa-summary">[NC&#x2011;19]</a><a name="NC&#x2011;19"> Functions should have `@notice` tags 

The `@notice` is used to explain to users what the function does. The compiler interprets `///` or `/**` comments [as this tag](https://docs.soliditylang.org/en/latest/natspec-format.html#tags) if one wasn't explicitly provided.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

77: function _createBid(

358: function _shortDirectionHandler(


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L77

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L358



```solidity
File: ExitShortFacet.sol

213: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L213

```solidity
File: PrimaryLiquidationFacet.sol

229: function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L229

```solidity
File: RedemptionFacet.sol

31: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L31

```solidity
File: LibOracle.sol

19: function getOraclePrice(address asset) internal view returns (uint256) {

69: function baseOracleCircuitBreaker(

117: function oracleCircuitBreaker(

131: function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L19

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L69

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L117

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L131



```solidity
File: LibOrders.sol

35: function convertCR(uint16 cr) internal pure returns (uint256) {

55: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

78: function isShort(STypes.Order memory order) internal pure returns (bool) {

82: function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103: function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

319: // shared function for both canceling and order and matching an order

628: function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

728: function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

802: // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough

810: function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

826: function findOrderHintId(

868: function cancelAsk(address asset, uint16 id) internal {

882: function cancelShort(address asset, uint16 id) internal {

985: function min(uint256 a, uint256 b) internal pure returns (uint256) {

989: function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L35

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L55

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L78

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L82

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L103

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L319

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L628

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L728

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L802

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L810

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L826

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L868

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L882

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L985

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L989



```solidity
File: LibSRUtil.sol

22: function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

49: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

102: function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

124: function transferShortRecord(address from, address to, uint40 tokenId) internal {

151: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L22

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L49

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L72

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L102

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L124

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L151



```solidity
File: UniswapOracleLibrary.sol

11: function observe(uint32[] calldata secondsAgos)

47: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L47





</details>





### <a href="#qa-summary">[NC&#x2011;20]</a><a name="NC&#x2011;20"> Large or complicated code bases should implement fuzzing tests 

Large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts, should implement <a href="https://medium.com/coinmonks/smart-contract-fuzzing-d9b88e0b0a05">fuzzing tests</a>. Fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold. Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and fuzzers, with properly and extensively-written invariants, can close this testing gap significantly.

#### <ins>Proof Of Concept</ins>

Various in-scope contract files.




### <a href="#qa-summary">[NC&#x2011;21]</a><a name="NC&#x2011;21"> Use `delete` to Clear Variables 

`delete a` assigns the initial value for the type to `a`. i.e. for integers it is equivalent to `a = 0`, but it can also be used on arrays, where it assigns a dynamic array of length zero or a static array of the same length with all elements reset. For structs, it assigns a struct with all members reset. Similarly, it can also be used to set an address to zero address. It has no effect on whole mappings though (as the keys of mappings may be arbitrary and are generally unknown). However, individual keys and what they map to can be deleted: If `a` is a mapping, then `delete a[x]` will delete the value stored at `x`.

The `delete` key better conveys the intention and is also more idiomatic. Consider replacing assignments of zero with `delete` statements.

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: BidOrdersFacet.sol

158: lowestSell.ercAmount = 0;

191: b.dustShortId = b.dustAskId = 0;

194: incomingBid.ercAmount = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L158

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L191

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L194



```solidity
File: LibBridgeRouter.sol

56: VaultUser.bridgeCreditReth = 0;

69: VaultUser.bridgeCreditSteth = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L56

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L69



```solidity
File: LibBridgeRouter.sol

167: VaultUserFrom.bridgeCreditReth = 0;

176: VaultUserFrom.bridgeCreditSteth = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L167

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L176



```solidity
File: LibOrders.sol

578: incomingAsk.ercAmount = 0;

585: highestBid.ercAmount = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L578

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L585



```solidity
File: LibSRUtil.sol

138: short.tokenId = 0;

148: nft.shortOrderId = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L138

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L148



```solidity
File: UniswapOracleLibrary.sol

56: secondsAgos[1] = 0;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L56



</details>



### <a href="#qa-summary">[NC&#x2011;22]</a><a name="NC&#x2011;22"> `if`-statement can be converted to a ternary 

The code can be made more compact while also increasing readability by converting the following `if`-statements to ternaries (e.g. `foo += (x > y) ? a : b`)

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

170: if (incomingBid.ercAmount == lowestSell.ercAmount) {
                        if (lowestSell.isShort()) {
                            b.matchedShortId = lowestSell.id;
                            b.prevShortId = lowestSell.prevId;
                            LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
                        } else {
                            b.matchedAskId = lowestSell.id;
                            LibOrders.matchOrder(s.asks, asset, lowestSell.id);
                        }

181: if (lowestSell.isShort()) {
                            b.dustShortId = lowestSell.id;
                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
                            lowestShort.ercAmount = lowestSell.ercAmount;
                        } else {
                            b.dustAskId = lowestSell.id;
                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
                        }

190: if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
                            b.dustShortId = b.dustAskId = 0;
                        }
                    }
                    incomingBid.ercAmount = 0;
                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
                }
            } else {
                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
                    LibOrders.addBid(asset, incomingBid, orderHintArray);
                }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L170

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L181

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L190



```solidity
File: ExitShortFacet.sol

58: if (buybackAmount == ercDebt) {
            uint88 collateral = short.collateral;
            s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;
            LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);
            LibShortRecord.deleteShortRecord(asset, msg.sender, id);
        } else {
            short.ercDebt -= buybackAmount;
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L58

```solidity
File: ExitShortFacet.sol

110: if (ercDebt == buybackAmount) {
            uint88 collateral = short.collateral;
            s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;
            LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

            LibShortRecord.deleteShortRecord(asset, msg.sender, id);
        } else {
            short.ercDebt -= buybackAmount;
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L110

```solidity
File: RedemptionFacet.sol

38: if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
            return false;
        } else {
            return true;
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L38

```solidity
File: LibBridgeRouter.sol

182: if (creditTotal > collateral) {
                    creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
                    creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
                    VaultUserFrom.bridgeCreditReth -= creditReth;
                    VaultUserFrom.bridgeCreditSteth -= creditSteth;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserFrom.bridgeCreditSteth = 0;
                }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L182

```solidity
File: LibOracle.sol

169: if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
            return getPrice(asset);
        } else {
            return getOraclePrice(asset);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L169

```solidity
File: LibOrders.sol

86: if (order.orderType == O.MarketBid) {
            return;
        }
        uint16 nextId = s.bids[asset][C.HEAD].nextId;
        if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.bids, asset, orderHintArray);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L86

```solidity
File: LibOrders.sol

107: if (order.orderType == O.MarketAsk) {
            return;
        }
        uint16 nextId = s.asks[asset][C.HEAD].nextId;
        if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.asks, asset, orderHintArray);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L107

```solidity
File: LibOrders.sol

132: if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.shorts, asset, orderHintArray);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L132

```solidity
File: LibOrders.sol

451: if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
                return hintId;
            }

            if (direction == C.PREV) {
                uint16 prevId = orders[asset][hintId].prevId;
                hintId = prevId;
            } else {
                hintId = nextId;
            }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L451

```solidity
File: LibOrders.sol

608: if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
                            cancelBid(asset, highestBid.id);
                        }
                    }
                    incomingAsk.ercAmount = 0;
                    matchIncomingSell(asset, incomingAsk, matchTotal);
                    return;
                }
            } else {
                updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
                matchIncomingSell(asset, incomingAsk, matchTotal);

                if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
                    addSellOrder(incomingAsk, asset, orderHintArray);
                }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L608

```solidity
File: LibOrders.sol

791: if (incomingOrder.price >= savedPrice) {
            orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
        } else {
            orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L791

```solidity
File: LibOrders.sol

941: if (id == Asset.startingShortId) {
            uint256 savedPrice = LibOracle.getPrice(asset);
            uint256 prevPrice = s.shorts[asset][shortOrder.prevId].price;
            if (prevPrice >= savedPrice) {
                Asset.startingShortId = shortOrder.prevId;
            } else {
                Asset.startingShortId = shortOrder.nextId;
            }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L941

```solidity
File: UniswapOracleLibrary.sol

36: if (sqrtRatioX96 <= type(uint128).max) {
            uint256 ratioX192 = uint256(sqrtRatioX96) * sqrtRatioX96;
            quoteAmount =
                baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
        } else {
            uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);
            quoteAmount =
                baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
        }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L36



</details>




### <a href="#qa-summary">[NC&#x2011;23]</a><a name="NC&#x2011;23"> Imports can be grouped together 

Consider importing OZ first, then all interfaces, then all utils.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

6: import {IDiamond} from "interfaces/IDiamond.sol";

8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

9: import {Errors} from "contracts/libraries/Errors.sol";

10: import {Events} from "contracts/libraries/Events.sol";

11: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";

12: import {LibAsset} from "contracts/libraries/LibAsset.sol";

13: import {LibOracle} from "contracts/libraries/LibOracle.sol";

14: import {LibOrders} from "contracts/libraries/LibOrders.sol";

15: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";

16: import {C} from "contracts/libraries/Constants.sol";

18: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L15

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L16

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L18



```solidity
File: BridgeRouterFacet.sol

4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";

6: import {IBridge} from "contracts/interfaces/IBridge.sol";

8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

9: import {Errors} from "contracts/libraries/Errors.sol";

10: import {Events} from "contracts/libraries/Events.sol";

11: import {LibBridge} from "contracts/libraries/LibBridge.sol";

12: import {LibBridgeRouter} from "contracts/libraries/LibBridgeRouter.sol";

13: import {LibVault} from "contracts/libraries/LibVault.sol";

14: import {C, VAULT} from "contracts/libraries/Constants.sol";

16: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L16



```solidity
File: ExitShortFacet.sol

4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";

6: import {IDiamond} from "interfaces/IDiamond.sol";

8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

9: import {Errors} from "contracts/libraries/Errors.sol";

10: import {Events} from "contracts/libraries/Events.sol";

11: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";

12: import {LibAsset} from "contracts/libraries/LibAsset.sol";

13: import {LibOrders} from "contracts/libraries/LibOrders.sol";

14: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";

15: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";

17: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L15

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L17



```solidity
File: PrimaryLiquidationFacet.sol

4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

6: import {IDiamond} from "interfaces/IDiamond.sol";

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

19: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L15

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L16

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L17

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L19



```solidity
File: RedemptionFacet.sol

4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";

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

18: import {SSTORE2} from "solmate/utils/SSTORE2.sol";

19: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L7

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L15

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L16

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L18

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L19



```solidity
File: ShortOrdersFacet.sol

4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

6: import {Errors} from "contracts/libraries/Errors.sol";

7: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";

8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

9: import {LibOrders} from "contracts/libraries/LibOrders.sol";

10: import {LibAsset} from "contracts/libraries/LibAsset.sol";

11: import {LibOracle} from "contracts/libraries/LibOracle.sol";

12: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";

13: import {LibSRUtil} from "contracts/libraries/LibSRUtil.sol";

14: import {C} from "contracts/libraries/Constants.sol";

16: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L7

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L16



```solidity
File: LibBytes.sol

4: import {MTypes} from "contracts/libraries/DataTypes.sol";

5: import {SSTORE2} from "solmate/utils/SSTORE2.sol";

7: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L5

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L7



```solidity
File: LibOracle.sol

4: import {U256} from "contracts/libraries/PRBMathHelper.sol";

6: import {AggregatorV3Interface} from "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

7: import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";

8: import {IDiamond} from "interfaces/IDiamond.sol";

9: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";

10: import {C} from "contracts/libraries/Constants.sol";

11: import {LibOrders} from "contracts/libraries/LibOrders.sol";

12: import {Errors} from "contracts/libraries/Errors.sol";

14: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L7

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L14



```solidity
File: LibOrders.sol

4: import {U256, U104, U80, U88, U16} from "contracts/libraries/PRBMathHelper.sol";

6: import {IDiamond} from "interfaces/IDiamond.sol";

8: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";

9: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";

10: import {Errors} from "contracts/libraries/Errors.sol";

11: import {Events} from "contracts/libraries/Events.sol";

12: import {LibAsset} from "contracts/libraries/LibAsset.sol";

13: import {LibOracle} from "contracts/libraries/LibOracle.sol";

14: import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";

15: import {LibVault} from "contracts/libraries/LibVault.sol";

16: import {C} from "contracts/libraries/Constants.sol";

18: import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L4

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L6

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L8

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L9

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L10

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L11

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L12

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L13

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L14

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L15

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L16

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L18





</details>





### <a href="#qa-summary">[NC&#x2011;24]</a><a name="NC&#x2011;24"> Inconsistent Spacing In Comments 

Some lines use // x and some use //x. The instances below point out the usages that don’t follow the majority, within each file

#### <ins>Proof Of Concept</ins>


```solidity
File: PrimaryLiquidationFacet.sol

92: //PRIVATE FUNCTIONS
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L92





### <a href="#qa-summary">[NC&#x2011;25]</a><a name="NC&#x2011;25"> Incorrect withdraw declaration 

In Solidity, it's essential for clarity and interoperability to correctly specify return types in function declarations. If the `withdraw` function is expected to return a `bool` to indicate success or failure, its omission could lead to ambiguity or unexpected behavior when interacting with or calling this function from other contracts or off-chain systems. Missing return values can mislead developers and potentially lead to contract integrations built on incorrect assumptions. To resolve this, the function declaration for `withdraw` should be modified to explicitly include the `bool` return type, ensuring clarity and correctness in contract interactions.

#### <ins>Proof Of Concept</ins>


```solidity
File: BridgeRouterFacet.sol

101: function withdraw(address bridge, uint88 dethAmount) external nonReentrant {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L101

```solidity
File: BridgeRouterFacet.sol

133: function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L133

```solidity
File: LibBridgeRouter.sol

113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L113





### <a href="#qa-summary">[NC&#x2011;26]</a><a name="NC&#x2011;26"> Contracts should have full test coverage 

While 96% code coverage does not guarantee that there are no bugs, it often will catch easy-to-find bugs, and will ensure that there are fewer regressions when the code invariably has to be modified. Furthermore, in order to get full coverage, code authors will often have to re-organize their code so that it is more modular, so that each component can be tested separately, which reduces interdependencies between modules and layers, and makes for code that is easier to reason about and audit.



### <a href="#qa-summary">[NC&#x2011;27]</a><a name="NC&#x2011;27"> Interface imports should be declared first 

Amend the ordering of imports to import interfaces first followed by other imports

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

6: import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L6

```solidity
File: BridgeRouterFacet.sol

6: import {IBridge} from "contracts/interfaces/IBridge.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L6

```solidity
File: ExitShortFacet.sol

6: import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L6

```solidity
File: PrimaryLiquidationFacet.sol

6: import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L6

```solidity
File: LibOracle.sol

6: import {AggregatorV3Interface} from "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";

7: import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";

8: import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L6-L8

```solidity
File: LibOrders.sol

6: import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L6



</details>





### <a href="#qa-summary">[NC&#x2011;28]</a><a name="NC&#x2011;28"> Invalid NatSpec comment style 

NatSpec must begin with `///`, or use `/* ... */` syntax

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: BidOrdersFacet.sol

70: // @dev leave empty, don't need hint for market buys
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L70

```solidity
File: BidOrdersFacet.sol

73: // @dev update oracle in callers
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L73

```solidity
File: BidOrdersFacet.sol

102: // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L102

```solidity
File: BidOrdersFacet.sol

107: // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L107

```solidity
File: BidOrdersFacet.sol

113: // @dev no match, add to market if limit order
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L113

```solidity
File: BidOrdersFacet.sol

140: // @dev Handles scenario when no sells left after partial fill
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L140

```solidity
File: BidOrdersFacet.sol

291: // @dev needs to happen after updateSellOrdersOnMatch()
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L291

```solidity
File: BidOrdersFacet.sol

309: // @dev Approximates the startingShortId after bid is fully executed
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L309

```solidity
File: BidOrdersFacet.sol

334: // @dev match price is based on the order that was already on orderbook
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L334

```solidity
File: BidOrdersFacet.sol

339: // @dev If neither conditions are true, it returns an empty Order struct
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L339

```solidity
File: BidOrdersFacet.sol

344: // @dev Setting lowestSell after comparing short and ask prices
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L344

```solidity
File: BidOrdersFacet.sol

353: // @dev Handles scenario when there are no shorts
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L353

```solidity
File: BidOrdersFacet.sol

393: // @dev shortHintId should always be the first thing matched
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L393

```solidity
File: BidOrdersFacet.sol

401: // @dev Only set to true if actually moving forward
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L401

```solidity
File: BridgeRouterFacet.sol

67: // @dev amount after deposit might be less, if bridge takes a fee
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L67

```solidity
File: BridgeRouterFacet.sol

68: // @dev(safe-cast)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L68

```solidity
File: BridgeRouterFacet.sol

147: // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L147

```solidity
File: BridgeRouterFacet.sol

178: // @dev don't use mulU88 in rare case of overflow
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L178

```solidity
File: ExitShortFacet.sol

157: // @dev Must prevent forcedBid from exitShort() matching with original shortOrder
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L157

```solidity
File: ExitShortFacet.sol

168: // @dev if short order was cancelled, fully exit
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L168

```solidity
File: ExitShortFacet.sol

203: // @dev Only allow partial exit if the CR is same or better than before
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L203

```solidity
File: ExitShortFacet.sol

206: // @dev collateral already subtracted in exitShort()
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L206

```solidity
File: PrimaryLiquidationFacet.sol

55: // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L55

```solidity
File: PrimaryLiquidationFacet.sol

58: // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L58

```solidity
File: PrimaryLiquidationFacet.sol

67: // @dev liquidate requires more up-to-date oraclePrice
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L67

```solidity
File: PrimaryLiquidationFacet.sol

72: // @dev Can liquidate as long as CR is low enough
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L72

```solidity
File: PrimaryLiquidationFacet.sol

95: // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L95

```solidity
File: PrimaryLiquidationFacet.sol

158: // @dev Provide higher price to better ensure it can fully fill the liquidation
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L158

```solidity
File: PrimaryLiquidationFacet.sol

164: // @dev Increase ethEscrowed by shorter's full collateral for forced bid
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L164

```solidity
File: PrimaryLiquidationFacet.sol

177: // @dev Max ethDebt can only be the ethEscrowed in the TAPP
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L177

```solidity
File: PrimaryLiquidationFacet.sol

180: // @dev(safe-cast)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L180

```solidity
File: PrimaryLiquidationFacet.sol

199: // @dev(safe-cast)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L199

```solidity
File: PrimaryLiquidationFacet.sol

186: // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L186

```solidity
File: PrimaryLiquidationFacet.sol

192: // @dev virtually burning the repurchased debt
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L192

```solidity
File: PrimaryLiquidationFacet.sol

197: // @dev manually setting basefee to 1,000,000 in foundry.toml;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L197

```solidity
File: PrimaryLiquidationFacet.sol

198: // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L198

```solidity
File: PrimaryLiquidationFacet.sol

217: // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out.
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L217

```solidity
File: RedemptionFacet.sol

36: // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L36

```solidity
File: RedemptionFacet.sol

37: // @dev Proposer can't redeem on self
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L37

```solidity
File: RedemptionFacet.sol

72: // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L72

```solidity
File: RedemptionFacet.sol

82: // @dev Setting this above _onlyValidShortRecord to allow skipping
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L82

```solidity
File: RedemptionFacet.sol

92: // @dev Skip if proposal is not sorted correctly or if above redemption threshold
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L92

```solidity
File: RedemptionFacet.sol

95: // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L95

```solidity
File: RedemptionFacet.sol

100: // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L100

```solidity
File: RedemptionFacet.sol

108: // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L108

```solidity
File: RedemptionFacet.sol

109: // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L109

```solidity
File: RedemptionFacet.sol

127: // @dev directly write the properties of MTypes.ProposalData into bytes
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L127

```solidity
File: RedemptionFacet.sol

145: // @dev SSTORE2 the entire proposalData after validating proposalInput
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L145

```solidity
File: RedemptionFacet.sol

156: // @dev Calculate the dispute period
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L156

```solidity
File: RedemptionFacet.sol

157: // @dev timeToDispute is immediate for shorts with CR <= 1.1x
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L157

```solidity
File: RedemptionFacet.sol

261: // @dev All proposals from the incorrectIndex onward will be removed
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L261

```solidity
File: RedemptionFacet.sol

262: // @dev Thus the proposer can only redeem a portion of their original slate
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L262

```solidity
File: RedemptionFacet.sol

278: // @dev Update the redeemer's SSTORE2Pointer
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L278

```solidity
File: RedemptionFacet.sol

282: // @dev this implies everything in the redeemer's proposal was incorrect
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L282

```solidity
File: RedemptionFacet.sol

287: // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L287

```solidity
File: RedemptionFacet.sol

288: // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L288

```solidity
File: RedemptionFacet.sol

295: // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L295

```solidity
File: RedemptionFacet.sol

356: // @dev Only need to read up to the position of the SR to be claimed
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L356

```solidity
File: RedemptionFacet.sol

372: // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L372

```solidity
File: RedemptionFacet.sol

375: // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L375

```solidity
File: RedemptionFacet.sol

381: // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L381

```solidity
File: RedemptionFacet.sol

391: // @dev Calculate Asset.ercDebt prior to proposal
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L391

```solidity
File: RedemptionFacet.sol

393: // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L393

```solidity
File: ShortOrdersFacet.sol

47: // @dev create "empty" SR. Fail early.
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L47

```solidity
File: ShortOrdersFacet.sol

55: // @dev minShortErc needs to be modified (bigger) when cr < 1
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L55

```solidity
File: ShortOrdersFacet.sol

74: // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L74

```solidity
File: ShortOrdersFacet.sol

84: // @dev reading spot oracle price
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L84

```solidity
File: LibBridgeRouter.sol

74: // @dev Prevents abusing bridge for arbitrage
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L74

```solidity
File: LibBridgeRouter.sol

104: // @dev Prevents abusing bridge for arbitrage
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L104

```solidity
File: LibBridgeRouter.sol

112: // @dev Only applicable to VAULT.ONE which has mixed LST
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L112

```solidity
File: LibBridgeRouter.sol

143: // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L143

```solidity
File: LibOracle.sol

29: // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L29

```solidity
File: LibOracle.sol

82: // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L82

```solidity
File: LibOracle.sol

155: // @dev Intentionally using creationTime for oracleTime.
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L155

```solidity
File: LibOracle.sol

161: // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L161

```solidity
File: LibOracle.sol

167: // @dev Allows caller to save gas since reading spot price costs ~16K
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L167

```solidity
File: LibOrders.sol

29: // @dev in seconds
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L29

```solidity
File: LibOrders.sol

32: // @dev(safe-cast)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L32

```solidity
File: LibOrders.sol

43: // @dev use the diff to get more time (2159), to prevent overflow at year 2106
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L43

```solidity
File: LibOrders.sol

138: // @dev: Only need to set this when placing incomingShort onto market
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L138

```solidity
File: LibOrders.sol

172: // @dev partial addOrder
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L172

```solidity
File: LibOrders.sol

188: // @dev (ID) is exiting, [ID] is inserted
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L188

```solidity
File: LibOrders.sol

294: // @dev (ID) is exiting, [ID] is inserted
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L294

```solidity
File: LibOrders.sol

237: // @dev: TAIL can't be prevId because it will always be last item in list
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L237

```solidity
File: LibOrders.sol

267: // @dev: TAIL can't be prevId because it will always be last item in list
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L267

```solidity
File: LibOrders.sol

332: // @dev mark as cancelled instead of deleting the order itself
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L332

```solidity
File: LibOrders.sol

419: // @dev not used to change state, just which methods to call
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L419

```solidity
File: LibOrders.sol

507: // @dev Handles only matching one thing
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L507

```solidity
File: LibOrders.sol

508: // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L508

```solidity
File: LibOrders.sol

511: // @dev Handles moving forward only
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L511

```solidity
File: LibOrders.sol

518: // @dev Handle going backward and forward
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L518

```solidity
File: LibOrders.sol

641: // @dev match price is based on the order that was already on orderbook
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L641

```solidity
File: LibOrders.sol

724: // @dev this happens at the end so fillErc isn't affected in previous calculations
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L724

```solidity
File: LibOrders.sol

760: // @dev force hint to be within 0.5% of oraclePrice
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L760

```solidity
File: LibOrders.sol

769: // @dev prevShortPrice >= oraclePrice
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L769

```solidity
File: LibOrders.sol

782: // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L782

```solidity
File: LibOrders.sol

790: // @dev handle .5% deviations in either directions
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L790

```solidity
File: LibOrders.sol

802: // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L802

```solidity
File: LibOrders.sol

846: // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L846

```solidity
File: LibOrders.sol

899: // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L899

```solidity
File: LibOrders.sol

900: // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L900

```solidity
File: LibOrders.sol

905: // @dev prevents leaving behind a partially filled SR is under minShortErc
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L905

```solidity
File: LibOrders.sol

906: // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L906

```solidity
File: LibOrders.sol

928: // @dev update the eth refund amount
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L928

```solidity
File: LibOrders.sol

931: // @dev virtually mint the increased debt
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L931

```solidity
File: LibOrders.sol

962: // @dev tithe is increased only if discount is greater than 1%
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L962

```solidity
File: LibOrders.sol

964: // @dev bound the new tithe amount between 25% and 100%
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L964

```solidity
File: LibOrders.sol

967: // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L967

```solidity
File: LibOrders.sol

970: // @dev dethTitheMod is only set when setTithe is called.
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L970

```solidity
File: LibOrders.sol

974: // @dev change back to original tithe percent
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L974

```solidity
File: LibOrders.sol

981: // @dev exists because of ShortOrderFacet contract size
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L981

```solidity
File: LibSRUtil.sol

89: // @dev The resulting SR will not have PartialFill status after cancel
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L89

```solidity
File: LibSRUtil.sol

133: // @dev shortOrderId is already validated in mintNFT
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L133

```solidity
File: UniswapOracleLibrary.sol

58: // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L58

```solidity
File: UniswapOracleLibrary.sol

69: // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L69



</details>





### <a href="#qa-summary">[NC&#x2011;29]</a><a name="NC&#x2011;29"> Assembly blocks should have extensive comments 

Assembly blocks are take a lot more time to audit than normal Solidity code, and often have gotchas and side-effects that the Solidity versions of the same code do not. Consider adding more comments explaining what is being done in every step of the assembly code

#### <ins>Proof Of Concept</ins>


```solidity
File: LibBytes.sol

11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
        bytes memory slate = SSTORE2.read(SSTORE2Pointer);
        
        require(slate.length % 51 == 0, "Invalid data length");

        MTypes.ProposalData[] memory data = new MTypes.ProposalData[](slateLength);

        for (uint256 i = 0; i < slateLength; i++) {
            
            uint256 offset = i * 51 + 32;

            address shorter; 
            uint8 shortId; 
            uint64 CR; 
            uint88 ercDebtRedeemed; 
            uint88 colRedeemed; 

            assembly {
                
                let fullWord := mload(add(slate, offset))
                
                shorter := shr(96, fullWord) 
                
                shortId := and(0xff, shr(88, fullWord)) 
                
                CR := and(0xffffffffffffffff, shr(24, fullWord)) 

                fullWord := mload(add(slate, add(offset, 29))) 
                
                ercDebtRedeemed := shr(168, fullWord) 
                
                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) 
            }

            data[i] = MTypes.ProposalData({
                shorter: shorter,
                shortId: shortId,
                CR: CR,
                ercDebtRedeemed: ercDebtRedeemed,
                colRedeemed: colRedeemed
            });
        }

        return data;
    }
}


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L11






### <a href="#qa-summary">[NC&#x2011;30]</a><a name="NC&#x2011;30"> Large or complicated code bases should implement invariant tests 

This includes: large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts. Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold. Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers may help significantly.




### <a href="#qa-summary">[NC&#x2011;31]</a><a name="NC&#x2011;31"> Missing Contract-existence Checks Before Low-level Calls 

Low-level calls return success if there is no code present at the specified address. 

#### <ins>Proof Of Concept</ins>


```solidity
File: PrimaryLiquidationFacet.sol

138: m.callerFeePct = LibAsset.callerFeePct(m.asset);
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L138

```solidity
File: PrimaryLiquidationFacet.sol

140: m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct);
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L140

```solidity
File: PrimaryLiquidationFacet.sol

180: m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct)));
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L180

```solidity
File: PrimaryLiquidationFacet.sol

214: uint88 callerFee = m.ethFilled.mulU88(m.callerFeePct) + m.gasFee;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L214

```solidity
File: RedemptionFacet.sol

290: LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L290




#### <ins>Recommended Mitigation Steps</ins>

In addition to the zero-address checks, add a check to verify that `<address>.code.length > 0`



### <a href="#qa-summary">[NC&#x2011;32]</a><a name="NC&#x2011;32"> Missing event for critical parameter change 

When changing state variables events are not emitted. Emitting events allows monitoring activities with off-chain monitoring tools.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L149




### <a href="#qa-summary">[NC&#x2011;33]</a><a name="NC&#x2011;33"> NatSpec `@return` argument is missing 

#### <ins>Proof Of Concept</ins>

```solidity
File: BridgeRouterFacet.sol

34: /**
     * @notice Returns the present value of all bridges within a given vault
     *
     * @param vault The vault being queried
     *
     */
    function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L34

```solidity
File: BridgeRouterFacet.sol

44: /**
     * @notice Returns an array of the bridge addresses of the vault
     * @dev does not need read only reentrancy
     *
     * @param vault The vault being queried
     *
     */
    function getBridges(uint256 vault) external view returns (address[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L44





### <a href="#qa-summary">[NC&#x2011;34]</a><a name="NC&#x2011;34"> No equate comparison checks between `to` and `from` address parameters 

The function lacks a standard check: it does not validate if the 'to' and 'from' addresses are identical. This omission can lead to unintended outcomes if the same address is used in both parameters. To rectify this, we recommend implementing a comparison check at the beginning of the function. In the context of Solidity, the command `require(to != from, "To and From addresses can't be the same");` could be utilized. This addition will generate an error if the 'to' and 'from' addresses are the same, thereby fortifying the function's robustness and security.

#### <ins>Proof Of Concept</ins>


```solidity
File: LibBridgeRouter.sol

144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
        AppStorage storage s = appStorage();

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;

        if (vault == VAULT.ONE) {
            STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
            uint88 creditReth = VaultUserFrom.bridgeCreditReth;
            uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
            STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];

            if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                
                return;
            }

            if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                
                if (creditReth > collateral) {
                    VaultUserFrom.bridgeCreditReth -= collateral;
                    VaultUserTo.bridgeCreditReth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserTo.bridgeCreditReth += creditReth;
                }
            } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
                
                if (creditSteth > collateral) {
                    VaultUserFrom.bridgeCreditSteth -= collateral;
                    VaultUserTo.bridgeCreditSteth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditSteth = 0;
                    VaultUserTo.bridgeCreditSteth += creditSteth;
                }
            } else {
                
                uint88 creditTotal = creditReth + creditSteth;
                if (creditTotal > collateral) {
                    creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
                    creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
                    VaultUserFrom.bridgeCreditReth -= creditReth;
                    VaultUserFrom.bridgeCreditSteth -= creditSteth;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserFrom.bridgeCreditSteth = 0;
                }
                VaultUserTo.bridgeCreditReth += creditReth;
                VaultUserTo.bridgeCreditSteth += creditSteth;
            }
        }
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L144

```solidity
File: LibSRUtil.sol

124: function transferShortRecord(address from, address to, uint40 tokenId) internal {
        AppStorage storage s = appStorage();

        STypes.NFT storage nft = s.nftMapping[tokenId];
        address asset = s.assetMapping[nft.assetId];
        STypes.ShortRecord storage short = s.shortRecords[asset][from][nft.shortRecordId];
        if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled();
        if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

        
        if (short.status == SR.PartialFill) {
            LibOrders.cancelShort(asset, nft.shortOrderId);
        }

        short.tokenId = 0;
        LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId);
        LibBridgeRouter.transferBridgeCredit(asset, from, to, short.collateral);

        uint8 id = LibShortRecord.createShortRecord(
            asset, to, SR.FullyFilled, short.collateral, short.ercDebt, short.ercDebtRate, short.dethYieldRate, tokenId
        );

        nft.owner = to;
        nft.shortRecordId = id;
        nft.shortOrderId = 0;
    }


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L124




### <a href="#qa-summary">[NC&#x2011;35]</a><a name="NC&#x2011;35"> The `nonReentrant` modifier should occur before all other modifiers 

Currently the `nonReentrant` modifier is not the first to occur, it should occur before all other modifiers.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

41: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L41


```solidity
File: ExitShortFacet.sol

41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L41

```solidity
File: ExitShortFacet.sol

87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L87

```solidity
File: ExitShortFacet.sol

143: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L143

```solidity
File: PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
    {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L47

```solidity
File: RedemptionFacet.sol

57: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L57

```solidity
File: RedemptionFacet.sol

224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L224

```solidity
File: RedemptionFacet.sol

310: function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L310

```solidity
File: RedemptionFacet.sol

347: function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L347

```solidity
File: ShortOrdersFacet.sol

36: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L36



</details>

#### <ins>Recommended Mitigation Steps</ins>

Re-sort modifiers so that the `nonReentrant` modifier occurs first.



### <a href="#qa-summary">[NC&#x2011;36]</a><a name="NC&#x2011;36"> Overly complicated arithmetic 

To maintain readability in code, particularly in Solidity which can involve complex mathematical operations, it is often recommended to limit the number of arithmetic operations to a maximum of 2-3 per line. Too many operations in a single line can make the code difficult to read and understand, increase the likelihood of mistakes, and complicate the process of debugging and reviewing the code. Consider splitting such operations over more than one line, take special care when dealing with division however. Try to limit the number of arithmetic operations to a maximum of 3 per line.

#### <ins>Proof Of Concept</ins>


```solidity
File: RedemptionFacet.sol

183: redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

187: protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);

191: protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);

195: protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);

198: redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L183

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L187

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L191

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L195

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L198








### <a href="#qa-summary">[NC&#x2011;37]</a><a name="NC&#x2011;37"> `private` and `internal` variables should have a preceding `_` in their name 

Add a preceding underscore `_` to the variable name, take care to refactor where there variables are read/write

#### <ins>Proof Of Concept</ins>


```solidity
File: BridgeRouterFacet.sol

26: address private immutable rethBridge;

27: address private immutable stethBridge;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L26-L27

```solidity
File: ExitShortFacet.sol

26: address private immutable dusd;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L26

```solidity
File: PrimaryLiquidationFacet.sol

28: address private immutable dusd;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L28






### <a href="#qa-summary">[NC&#x2011;38]</a><a name="NC&#x2011;38"> Project should include an `EmergencyStop` pattern 

Adding a way to quickly halt protocol functionality in an emergency, rather than having to pause individual contracts one-by-one, will make in-progress hack mitigation faster and much less stressful.

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L20

```solidity
File: BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L18

```solidity
File: ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L19

```solidity
File: PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L21

```solidity
File: RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L21

```solidity
File: ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L18



</details>




### <a href="#qa-summary">[NC&#x2011;39]</a><a name="NC&#x2011;39"> Top-level declarations should be separated by at least two lines 

#### <ins>Proof Of Concept</ins>


<details>

```solidity
File: BidOrdersFacet.sol

2: pragma solidity 0.8.21;

import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L2

```solidity
File: BidOrdersFacet.sol

18: // import {console} from "contracts/libraries/console.sol";

contract BidOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L18

```solidity
File: BridgeRouterFacet.sol

2: pragma solidity 0.8.21;

import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L2

```solidity
File: BridgeRouterFacet.sol

16: // import {console} from "contracts/libraries/console.sol";

contract BridgeRouterFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L16

```solidity
File: ExitShortFacet.sol

2: pragma solidity 0.8.21;

import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L2

```solidity
File: ExitShortFacet.sol

17: // import {console} from "contracts/libraries/console.sol";

contract ExitShortFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L17

```solidity
File: PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21;

import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L2

```solidity
File: PrimaryLiquidationFacet.sol

19: // import {console} from "contracts/libraries/console.sol";

contract PrimaryLiquidationFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L19

```solidity
File: RedemptionFacet.sol

2: pragma solidity 0.8.21;

import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L2

```solidity
File: RedemptionFacet.sol

19: import {console} from "contracts/libraries/console.sol";

contract RedemptionFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L19

```solidity
File: ShortOrdersFacet.sol

2: pragma solidity 0.8.21;

import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L2

```solidity
File: ShortOrdersFacet.sol

16: // import {console} from "contracts/libraries/console.sol";

contract ShortOrdersFacet is Modifiers {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L16

```solidity
File: LibBridgeRouter.sol

2: pragma solidity 0.8.21;

import {IBridge} from "contracts/interfaces/IBridge.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBridgeRouter.sol#L2

```solidity
File: LibBytes.sol

2: pragma solidity 0.8.21;

import {MTypes} from "contracts/libraries/DataTypes.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibBytes.sol#L2

```solidity
File: LibOracle.sol

2: pragma solidity 0.8.21;

import {U256} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L2

```solidity
File: LibOrders.sol

2: pragma solidity 0.8.21;

import {U256, U104, U80, U88, U16} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L2

```solidity
File: LibSRUtil.sol

2: pragma solidity 0.8.21;

import {U88, U256} from "contracts/libraries/PRBMathHelper.sol";
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibSRUtil.sol#L2

```solidity
File: UniswapOracleLibrary.sol

8: import {U256} from "contracts/libraries/PRBMathHelper.sol";

interface IUniswapV3Pool {
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L8



</details>





### <a href="#qa-summary">[NC&#x2011;40]</a><a name="NC&#x2011;40"> Unused event may be unused code or indicative of missed emit/logic 

Events that are declared but not used may be indicative of unused declarations where it makes sense to remove them for better readability/maintainability/auditability, or worse indicative of a missing emit which is bad for monitoring or missing logic that would have emitted that event.

#### <ins>Proof Of Concept</ins>


```solidity
File: ExitShortFacet.sol

157: event forcedBid from exitShort
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L157



#### <ins>Recommended Mitigation Steps</ins>
Add emit or remove event declaration.




### <a href="#qa-summary">[NC&#x2011;41]</a><a name="NC&#x2011;41"> Upgrade OpenZeppelin Contract Dependency 

An outdated OZ version is used (which has known vulnerabilities, see: https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories).
Release: https://github.com/OpenZeppelin/openzeppelin-contracts/releases/tag/v5.0.0

#### <ins>Proof Of Concept</ins>

Require dependencies to be at least version of 5.0.0 to include critical vulnerability patches.

```solidity
File: package.json

    "@openzeppelin/contracts": "^4.9.0"
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/package.json#L56



#### <ins>Recommended Mitigation Steps</ins>

Update OpenZeppelin Contracts Usage in package.json and require at least version of 5.0.0



### <a href="#qa-summary">[NC&#x2011;42]</a><a name="NC&#x2011;42"> Use a struct to encapsulate multiple function parameters 

If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.

#### <ins>Proof Of Concept</ins>

```solidity
File: BidOrdersFacet.sol

77: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BidOrdersFacet.sol#L77







### <a href="#qa-summary">[NC&#x2011;43]</a><a name="NC&#x2011;43"> Use SafeCast to safely downcast variables 

Downcasting `int`/`uint`s in Solidity can be unsafe due to the potential for data loss and unintended behavior. When downcasting a larger integer type to a smaller one (e.g., `uint256` to `uint128`), the value may exceed the range of the target type, leading to truncation and loss of significant digits. This data loss can result in unexpected state changes, incorrect calculations, or other contract vulnerabilities, ultimately compromising the contracts functionality and reliability. To prevent these risks, developers should carefully consider the range of values their variables may hold and ensure that proper checks are in place to prevent out-of-range values before performing downcasting. Also consider using OZ SafeCast functionality.

#### <ins>Proof Of Concept</ins>

<details>

```solidity
File: BridgeRouterFacet.sol

68: uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount));


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L68

```solidity
File: BridgeRouterFacet.sol

87: uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}());


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L87

```solidity
File: PrimaryLiquidationFacet.sol

180: m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct)));

199: m.gasFee = uint88(gasUsed * block.basefee);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L180

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L199



```solidity
File: PrimaryLiquidationFacet.sol

231: return a < b ? uint88(a) : b;


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L231

```solidity
File: RedemptionFacet.sol

133: bytes8(uint64(p.currentCR)),

183: redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

187: protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);

191: protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);

195: protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);

198: redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L133

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L183

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L187

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L191

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L195

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L198



```solidity
File: RedemptionFacet.sol

399: Asset.baseRate = uint64(newBaseRate);

402: return uint88(redemptionRate.mul(colRedeemed));


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L399

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/RedemptionFacet.sol#L402



```solidity
File: LibOracle.sol

151: s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L151

```solidity
File: LibOracle.sol

164: return uint80(s.bids[asset][C.HEAD].ercAmount);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOracle.sol#L164

```solidity
File: LibOrders.sol

32: return uint32(block.timestamp - C.STARTING_TIME);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L32

```solidity
File: LibOrders.sol

903: uint88 minShortErc = uint88(LibAsset.minShortErc(asset));


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/LibOrders.sol#L903

```solidity
File: UniswapOracleLibrary.sol

62: int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));

65: if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L62

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/libraries/UniswapOracleLibrary.sol#L65





</details>



### <a href="#qa-summary">[NC&#x2011;44]</a><a name="NC&#x2011;44"> Use SMTChecker 

The highest tier of smart contract behavior assurance is formal mathematical verification. All assertions that are made are guaranteed to be true across all inputs → The quality of your asserts is the quality of your verification

https://twitter.com/0xOwenThurm/status/1614359896350425088?t=dbG9gHFigBX85Rv29lOjIQ&s=19






### <a href="#qa-summary">[NC&#x2011;45]</a><a name="NC&#x2011;45"> Variable names for `immutable`s should use CONSTANT_CASE 

For `immutable` variable names, each word should use all capital letters, with underscores separating each word (CONSTANT_CASE)

#### <ins>Proof Of Concept</ins>


```solidity
File: BridgeRouterFacet.sol

26: address private immutable rethBridge;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L26

```solidity
File: BridgeRouterFacet.sol

27: address private immutable stethBridge;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/BridgeRouterFacet.sol#L27

```solidity
File: ExitShortFacet.sol

26: address private immutable dusd;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ExitShortFacet.sol#L26

```solidity
File: PrimaryLiquidationFacet.sol

28: address private immutable dusd;
```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/PrimaryLiquidationFacet.sol#L28






### <a href="#qa-summary">[NC&#x2011;46]</a><a name="NC&#x2011;46"> Zero as a function argument should have a descriptive meaning 

Consider using descriptive constants or an enum instead of passing zero directly on function calls, as that might be error-prone, to fully describe the caller's intention.

#### <ins>Proof Of Concept</ins>


```solidity
File: ShortOrdersFacet.sol

48: incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);


```

https://github.com/code-423n4/2024-03-dittoeth/tree/main/contracts/facets/ShortOrdersFacet.sol#L48






