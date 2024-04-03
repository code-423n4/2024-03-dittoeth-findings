## Medium Findings

|    | Issue | Instances |
|----|-------|:---------:|
| [M-01] | Missing price checks for Chainlink oracle | 3 |
| [M-02] | Chainlink oracle will return the wrong price if the aggregator hits `minAnswer` | 3 |

## Low Findings

|    | Issue | Instances |
|----|-------|:---------:|
| [L-01] | Centralization issue caused by admin privileges | 8 |
| [L-02] | `assert()` should only be used for tests | 2 |
| [L-03] | Prefer skip over `revert` model in loops | 2 |
| [L-04] | Unbounded loop may run out of gas | 6 |
| [L-05] | Lack of index element validation in external/public function | 25 |
| [L-06] | Consider using OpenZeppelin's SafeCast for any casting | 32 |
| [L-07] | Missing checks for state variable assignments | 3 |
| [L-08] | External calls in an unbounded loop can result in a DoS | 3 |
| [L-09] | For loops in public or external functions should be avoided due to high gas costs and possible `revert` | 4 |
| [L-10] | Input Arrays Lengths Not Checked | 2 |
| [L-11] | Critical functions should be a two step procedure | 7 |
| [L-12] | Loss of precision on division | 10 |
| [L-13] | Unsafe `uint` to `int` conversion | 2 |
| [L-14] | Unsafe downcast from larger to smaller integer types | 4 |
| [L-15] | Missing checks for `address(0)` in constructor | 3 |
| [L-16] | Casting `block.timestamp` to Smaller Integer Types Limit Contract Lifespan | 1 |

## NonCritical Findings

|    | Issue | Instances |
|----|-------|:---------:|
| [N-01] | `internal/private` Function calls within for loops | 23 |
| [N-02] | Array indices should be referenced via `enum`s rather than via numeric literals | 4 |
| [N-03] | Consider splitting long calculations | 5 |
| [N-04] | Use custom errors instead of `require()/assert()` | 3 |
| [N-05] | Variables need not be initialized to zero | 6 |
| [N-06] | Consider using a `struct` rather than having many function input parameters | 18 |
| [N-07] | Consider using descriptive `constant`s when passing zero as a function argument | 1 |
| [N-08] | File with Library declaration Shoulde contain only Library | 2 |
| [N-09] | Unused `private` functions can be removed | 1 |
| [N-10] | Consider using `delete` rather than assigning `zero` to clear values | 17 |
| [N-11] | Consider emitting an event at the end of the constructor | 3 |
| [N-12] | Consider using named returns | 17 |
| [N-13] | Style guide: Initialisms should be capitalized | 104 |
| [N-14] | Consider using named function arguments | 89 |
| [N-15] | Function Parameters in Public Accessible Functions Need `address(0)` Check | 15 |
| [N-16] | Contract/Library Names Not in `CapWords` Style (CamelCase) | 1 |
| [N-17] | Events are missing sender information | 1 |
| [N-18] | Non-constant/non-immutable variables using all capital letters | 4 |
| [N-19] | Leverage Recent Solidity Features with `0.8.23` | 12 |
| [N-20] | NatSpec: Function `@param` tag is missing | 69 |
| [N-21] | High cyclomatic complexity | 15 |
| [N-22] | Contract should expose an `interface` | 36 |
| [N-23] | NatSpec: Function declarations should have descriptions | 4 |
| [N-24] | Inconsistent spacing in comments | 4 |
| [N-25] | Critical system parameter changes should be behind a timelock | 7 |
| [N-26] | Library Should be in a Separate File | 1 |
| [N-27] | Assembly blocks should have extensive comments | 1 |
| [N-28] | Function/Constructor Argument Names Not in mixedCase | 4 |
| [N-29] | NatSpec: Function `@return` tag is missing | 33 |
| [N-30] | Duplicated `require()`/`revert()` checks should be refactored to a modifier or function | 9 |
| [N-31] | Consider Adding Emergency-Stop Functionality | 6 |
| [N-32] | Non-uppercase/Constant-case Naming for `immutable` Variables | 4 |
| [N-33] | Not using the named return variables anywhere in the function is confusing | 22 |
| [N-34] | Function Names Not in mixedCase | 3 |
| [N-35] | Insufficient Comments in Complex Functions | 15 |
| [N-36] | NatSpec: Non-public state variable declarations should use `@dev` tags | 4 |
| [N-37] | `constant`s should be defined rather than using magic numbers | 15 |
| [N-38] | Consider moving `msg.sender` checks to a common authorization `modifier` | 6 |
| [N-39] | NatSpec: Contract declarations should have descriptions | 12 |
| [N-40] | NatSpec: Contract declarations should have `@author` tag | 13 |
| [N-41] | Style guide: Non-`external`/`public` function names should begin with an underscore | 65 |
| [N-42] | Invalid NatSpec comment style | 110 |
| [N-43] | Consider making contracts `Upgradeable` | 6 |
| [N-44] | Style guide: Non-`external`/`public` variable names should begin with an underscore | 4 |
| [N-45] | Style guide: Control structures do not follow the Solidity Style Guide | 52 |
| [N-46] | Consider bounding input array length | 1 |
| [N-47] | NatSpec: Function declarations should have `@notice` tag | 4 |
| [N-48] | Constants in comparisons should appear on the left side | 41 |
| [N-49] | NatSpec: Contract declarations should have `@notice` tag | 12 |
| [N-50] | Long functions should be refactored into multiple, smaller, functions | 15 |
| [N-51] | NatSpec: Contract declarations should have `@dev` tags | 13 |
| [N-52] | The nonReentrant modifier should occur before all other modifiers | 10 |
| [N-53] | Complex casting | 1 |
| [N-54] | Equal `block.timestamp` Cases Not Handled | 5 |
| [N-55] | `else`-block not required | 17 |
| [N-56] | Style guide: Function ordering does not follow the Solidity style guide | 4 |
| [N-57] | Style guide: Lines are too long | 63 |
| [N-58] | Style guide: Extraneous whitespace | 13 |
| [N-59] | Contract/Libraries Names Do Not Match Their Filenames | 1 |
| [N-60] | `if`-statement can be converted to a ternary | 8 |
| [N-61] | Consider using named mappings | 12 |
| [N-62] | Setters should prevent re-setting of the same value | 10 |
| [N-63] | NatSpec: Contract declarations should have `@title` tags | 12 |
| [N-64] | Contracts should have full test coverage | 1 |
| [N-65] | Large or complicated code bases should implement invariant tests | 1 |
| [N-66] | Implement Formal Verification Proofs to Improve Security | 1 |


## Medium Findings Details

### [M-01] Missing price checks for Chainlink oracle

`latestRoundData` may return invalid data, and there aren't any checks to ensure that this doesn't happen.

This can be caused by any issues with Chainlink, such as oracle consensus problems or chain congestion, which may result in this contract relying on outdated data.

<details>
<summary><i>3 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOracle.sol

27: try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
42: ) = oracle.latestRoundData();
59: ) = oracle.latestRoundData();
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L27) | [42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L42) | [59](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L59)
</details>

### [M-02] Chainlink oracle will return the wrong price if the aggregator hits `minAnswer`

Chainlink aggregators have a built-in circuit breaker if the price of an asset goes outside of a predetermined price band.

The result is that if an asset experiences a huge drop in value (i.e. LUNA crash) the price of the oracle will continue to return the minPrice instead of the actual price of the asset.

This would allow users to continue borrowing with the asset but at the wrong price. This is exactly what happened to Venus on BSC when LUNA [crashed](https://rekt.news/venus-blizz-rekt/).

<details>
<summary><i>3 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOracle.sol

27: try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
42: ) = oracle.latestRoundData();
59: ) = oracle.latestRoundData();
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L27) | [42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L42) | [59](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L59)
</details>


## Low Findings Details

### [L-01] Centralization issue caused by admin privileges

There are priviliged roles that are a single point of failure, who can use critical functions, posing a centralization issue.

<details>
<summary><i>8 issue instances in 5 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft)
65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
```
[40](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40) | [65](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant
```
[35](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
```
[47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

133: function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO
```
[133](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L133)

```solidity
File: contracts/facets/ExitShortFacet.sol

41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id)
```
[41](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41) | [87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [142](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)
</details>

### [L-02] `assert()` should only be used for tests

From (documentation)[https://docs.soliditylang.org/en/v0.8.20/control-structures.html#panic-via-assert-and-error-via-require]:
```text
The assert function creates an error of type Panic(uint256). The same error is created by the compiler in certain situations as listed below.
Assert should only be used to test for internal errors, and to check invariants. Properly functioning code should never create a Panic, not even on invalid external input. If this happens, then there is a bug in your contract which you should fix. Language analysis tools can evaluate your contract to identify the conditions and function calls which will cause a Panic.
```

<details>
<summary><i>2 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

397: assert(newBaseRate > 0)
```
[397](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L397)

```solidity
File: contracts/libraries/LibSRUtil.sol

62: assert(shortRecord.status != SR.PartialFill)
```
[62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L62)
</details>

### [L-03] Prefer skip over `revert` model in loops

When dealing with array operations in Solidity, it's often wiser to opt for skipping over reverting.
Instead of halting the entire transaction when a condition isn't met, suggests simply moving on to the next array index.
The reason behind this choice is to reduce the risk of malicious actors intentionally introducing array objects that fail conditional checks within loops, causing group operations to fail.
Unless there's a compelling security or logical justification for reverting, it's recommended to embrace the skip-over approach for a more robust codebase.

<details>
<summary><i>2 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

112: revert Errors.InvalidShortOrder()
244: revert Errors.CannotDisputeWithRedeemerProposal()
```
[112](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L112) | [244](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L244)
</details>

### [L-04] Unbounded loop may run out of gas

Unbounded loops in smart contracts pose a risk because they iterate over an unknown number of elements, potentially consuming all available gas for a transaction.
This can result in unintended transaction failures. Gas consumption increases linearly with the number of iterations, and if it surpasses the gas limit, the transaction reverts, wasting the gas spent.
To mitigate this, developers should either set a maximum limit on loop iterations.

<details>
<summary><i>6 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

78: for (uint8 i = 0; i < proposalInput.length; i++)
242: for (uint256 i = 0; i < decodedProposalData.length; i++)
263: for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++)
321: for (uint256 i = 0; i < decodedProposalData.length; i++)
```
[78](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L78) | [242](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L242) | [263](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L263) | [321](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L321)

```solidity
File: contracts/libraries/LibOrders.sol

743: for (uint256 i = 0; i < shortHintArray.length;)
832: for (uint256 i; i < orderHintArray.length; i++)
```
[743](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L743) | [832](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L832)
</details>

### [L-05] Lack of index element validation in external/public function

There's no validation to check whether the index element provided as an argument actually exists in the call. This omission could lead to unintended behavior if an element that does not exist in the call is passed to the function.

The function should validate that the provided index element exists in the call before proceeding.

Without this validation, the function could cause unintended behaviour as it will call an non-existing index element. This could lead to inconsistencies in data and potentially affect the integrity of the call structure.

<details>
<summary><i>25 issue instances in 5 files:</i></summary>

```solidity
File: contracts/facets/ShortOrdersFacet.sol

44: s.asset[asset]
72: s.bids[asset]
73: s.bids[asset]
```
[44](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L44) | [72](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L72) | [73](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L73)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

61: s.shortRecords[asset][shorter][id]
61: s.shortRecords[asset][shorter]
61: s.shortRecords[asset]
```
[61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L61) | [61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L61) | [61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L61)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

52: s.vaultBridges[vault]
```
[52](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L52)

```solidity
File: contracts/facets/ExitShortFacet.sol

47: s.asset[asset]
48: s.shortRecords[asset][msg.sender][id]
48: s.shortRecords[asset]
93: s.asset[asset]
94: s.shortRecords[asset][msg.sender][id]
94: s.shortRecords[asset]
102: s.assetUser[asset]
155: s.shortRecords[e.asset][msg.sender][id]
```
[47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L47) | [48](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L48) | [48](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L48) | [93](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L93) | [94](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L94) | [94](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L94) | [102](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L102) | [155](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L155)

```solidity
File: contracts/facets/RedemptionFacet.sol

110: s.shorts[asset]
248: s.shortRecords[d.asset][disputeShorter][disputeShortId]
248: s.shortRecords[d.asset][disputeShorter]
253: decodedProposalData[incorrectIndex]
311: s.asset[asset]
312: s.assetUser[asset]
352: s.assetUser[asset][redeemer]
352: s.assetUser[asset]
359: decodedProposalData[claimIndex]
363: s.asset[asset]
```
[110](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L110) | [248](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L248) | [248](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L248) | [253](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L253) | [311](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L311) | [312](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L312) | [352](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L352) | [352](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L352) | [359](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L359) | [363](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L363)
</details>

### [L-06] Consider using OpenZeppelin's SafeCast for any casting

OpenZeppelin's has `SafeCast` library that provides functions to safely cast. Recommended to use it instead of casting directly in any case.

<details>
<summary><i>32 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

180: uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct)))
199: uint88(gasUsed * block.basefee)
231: uint88(a)
```
[180](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180) | [199](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L199) | [231](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L231)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

68: uint88(IBridge(bridge).deposit(msg.sender, amount))
87: uint88(IBridge(bridge).depositEth{value: msg.value}())
```
[68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L68) | [87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L87)

```solidity
File: contracts/facets/RedemptionFacet.sol

133: uint64(p.currentCR)
182: uint256(3 ether)
183: uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether)
185: uint256(1.5 ether)
187: uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether)
189: uint256(0.75 ether)
191: uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether)
193: uint256(0.417 ether)
195: uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether)
197: uint256(C.ONE_THIRD.div(0.1 ether))
198: uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether)
388: uint256((protocolTime - Asset.lastRedemptionTime))
399: uint64(newBaseRate)
402: uint88(redemptionRate.mul(colRedeemed))
```
[133](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L133) | [182](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L182) | [183](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L183) | [185](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L185) | [187](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L187) | [189](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L189) | [191](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L191) | [193](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L193) | [195](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L195) | [197](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L197) | [198](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L198) | [388](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L388) | [399](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L399) | [402](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L402)

```solidity
File: contracts/libraries/LibOracle.sol

30: uint256(basePrice * C.BASE_ORACLE_DECIMALS)
43: uint256(price)
43: uint256(basePrice)
63: uint256(price * C.BASE_ORACLE_DECIMALS)
151: uint80(oraclePrice)
164: uint80(s.bids[asset][C.HEAD].ercAmount)
```
[30](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L30) | [43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L43) | [43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L43) | [63](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L63) | [151](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L151) | [164](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L164)

```solidity
File: contracts/libraries/LibOrders.sol

32: uint32(block.timestamp - C.STARTING_TIME)
36: uint256(cr)
903: uint88(LibAsset.minShortErc(asset))
```
[32](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L32) | [36](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L36) | [903](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L903)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

37: uint256(sqrtRatioX96)
62: int24(tickCumulativesDelta / int32(secondsAgo))
62: int32(secondsAgo)
65: int32(secondsAgo)
```
[37](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L37) | [62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62) | [62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62) | [65](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)
</details>

### [L-07] Missing checks for state variable assignments

There are some missing checks in these functions, and this could lead to unexpected scenarios. Consider always adding a sanity check for state variables.

<details>
<summary><i>3 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOrders.sol

744: shortHintId = shortHintArray[i];
798: _updateOracleAndStartingShort(asset, shortHintArray);
806: _updateOracleAndStartingShort(asset, shortHintArray);
```
[744](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L744) | [798](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L798) | [806](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L806)
</details>

### [L-08] External calls in an unbounded loop can result in a DoS

Consider limiting the number of iterations in loops that make external calls, as just a single one of them failing will result in a revert.

<details>
<summary><i>3 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit 7 external calls in unbounded for-loop -> 78: for (uint8 i = 0; i < proposalInput.length; i++) {
89: currentSR.updateErcDebt(p.asset);
90: p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
138: LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
```
[89](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L89) | [90](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L90) | [138](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L138)
</details>

### [L-09] For loops in public or external functions should be avoided due to high gas costs and possible `revert`

Loops in public or external functions can lead to high gas costs, as their unpredictable gas consumption and externally-influenced logic might make these functions costly.

<details>
<summary><i>4 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

78: for (uint8 i = 0; i < proposalInput.length; i++) {
242: for (uint256 i = 0; i < decodedProposalData.length; i++) {
263: for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
321: for (uint256 i = 0; i < decodedProposalData.length; i++) {
```
[78](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L78) | [242](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L242) | [263](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L263) | [321](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L321)
</details>

### [L-10] Input Arrays Lengths Not Checked

When a function takes two or more arrays as arguments, it is important to ensure that their lengths are equal to prevent unexpected behavior.
Add a check to compare the lengths of the arrays in the function body.

<details>
<summary><i>2 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)
</details>

### [L-11] Critical functions should be a two step procedure

Critical functions in Solidity contracts should follow a two-step procedure to enhance security, minimize human error, and ensure proper access control. By dividing sensitive operations into distinct phases, such as initiation and confirmation, developers can introduce a safeguard against unintended actions or unauthorized access.

<details>
<summary><i>7 issue instances in 3 files:</i></summary>

```solidity
File: contracts/libraries/LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
```
[149](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L149)

```solidity
File: contracts/libraries/LibOrders.sol

474: function updateBidOrdersOnMatch(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        bool isOrderFullyFilled
    ) internal {
499: function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
783: function updateOracleAndStartingShortViaThreshold(
        address asset,
        uint256 savedPrice,
        STypes.Order memory incomingOrder,
        uint16[] memory shortHintArray
    ) internal {
803: function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {
809: function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
```
[474](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L474) | [499](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L499) | [783](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L783) | [803](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L803) | [809](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L809)

```solidity
File: contracts/libraries/LibSRUtil.sol

150: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```
[150](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L150)
</details>

### [L-12] Loss of precision on division

Solidity doesn't support fractions, so divisions by large numbers could result in the quotient being zero.

To avoid this, it's recommended to require a minimum numerator amount to ensure that it is always greater than the denominator.

<details>
<summary><i>10 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

183: redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
187: protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
191: protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
195: protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
198: redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
```
[183](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L183) | [187](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L187) | [191](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L191) | [195](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L195) | [198](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L198)

```solidity
File: contracts/libraries/LibOracle.sol

93: uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
141: uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
```
[93](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L93) | [141](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L141)

```solidity
File: contracts/libraries/LibOrders.sol

36: return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;
47: uint88 shares = eth * (timeTillMatch / 1 days);
```
[36](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L36) | [47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L47)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

62: int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
```
[62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62)
</details>

### [L-13] Unsafe `uint` to `int` conversion

The `int` type in Solidity uses the [two's complement system](https://en.wikipedia.org/wiki/Two%27s_complement), so it is possible to accidentally overflow a very large `uint` to an `int`, even if they share the same number of bytes (e.g. a `uint256 number > type(uint128).max` will overflow a `int256` cast).

Consider using the [SafeCast](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeCast.sol) library to prevent any overflows.

<details>
<summary><i>2 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit cast from `uint32` to `int32`
62: int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
/// @audit cast from `uint32` to `int32`
65: if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
```
[62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62) | [65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)
</details>

### [L-14] Unsafe downcast from larger to smaller integer types

When a type is downcast to a smaller type, the higher order bits are discarded, resulting in the application of a modulo operation to the original value.

If the downcasted value is large enough, this may result in an overflow that will not revert.

<details>
<summary><i>4 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit cast from `uint256` to `uint88`
231: return a < b ? uint88(a) : b;
```
[231](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L231)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit cast from `uint256` to `uint64`
399: Asset.baseRate = uint64(newBaseRate);
```
[399](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L399)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit cast from `uint256` to `uint80`
151: s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
```
[151](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L151)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit casted from `int32` to `int24`
62: int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
```
[62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62)
</details>

### [L-15] Missing checks for `address(0)` in constructor

Check for zero-address to avoid the risk of setting `address(0)` for state variables when deploying.

<details>
<summary><i>3 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit `_dusd` has lack of `address(0)` check before use
29: constructor(address _dusd) {
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L29)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit `_rethBridge` has lack of `address(0)` check before use
/// @audit `_stethBridge` has lack of `address(0)` check before use
28: constructor(address _rethBridge, address _stethBridge) {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L28)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit `_dusd` has lack of `address(0)` check before use
27: constructor(address _dusd) {
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L27)
</details>

### [L-16] Casting `block.timestamp` to Smaller Integer Types Limit Contract Lifespan

Casting `block.timestamp` to a smaller integer type like uint32 can potentially reduce the lifespan of a contract.
While the current Unix timestamp fits within the uint32 range as of now, it will eventually exceed this range by the year 2106.

At this point, casting the Unix timestamp to a uint32 will lead to overflow errors, resulting in unpredictable contract behavior.
To future-proof your contract, it's advisable to use larger integer types such as uint40 or uint (up to uint256) when dealing with timestamps.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOrders.sol

32: return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)
```
[32](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L32)
</details>


## NonCritical Findings Details

### [N-01] `internal/private` Function calls within for loops

Making function calls or external calls within loops in Solidity can lead to inefficient gas usage, potential bottlenecks, and increased vulnerability to attacks.
Each function call or external call consumes gas, and when executed within a loop, the gas cost multiplies, potentially causing the transaction to run out of gas or exceed block gas limits.
This can result in transaction failure or unpredictable behavior.

<details>
<summary><i>23 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

145: matchIncomingBid(asset, incomingBid, matchTotal, b)
148: _getLowestSell(asset, b)
153: matchIncomingBid(asset, incomingBid, matchTotal, b)
155: matchlowestSell(asset, lowestSell, incomingBid, matchTotal)
163: _shortDirectionHandler(asset, lowestSell, incomingBid, b)
195: matchIncomingBid(asset, incomingBid, matchTotal, b)
201: matchIncomingBid(asset, incomingBid, matchTotal, b)
```
[145](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L145) | [148](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L148) | [153](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L153) | [155](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L155) | [163](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L163) | [195](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L195) | [201](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L201)

```solidity
File: contracts/facets/RedemptionFacet.sol

87: validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)
```
[87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L87)

```solidity
File: contracts/libraries/LibOrders.sol

451: verifyId(orders, asset, hintId, _newPrice, nextId, orderType)
577: updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false)
579: matchIncomingSell(asset, incomingAsk, matchTotal)
582: matchHighestBid(incomingAsk, highestBid, asset, matchTotal)
586: matchOrder(s.bids, asset, highestBid.id)
591: matchIncomingSell(asset, incomingAsk, matchTotal)
594: addSellOrder(incomingAsk, asset, orderHintArray)
601: matchOrder(s.bids, asset, highestBid.id)
602: updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true)
606: updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false)
609: cancelBid(asset, highestBid.id)
613: matchIncomingSell(asset, incomingAsk, matchTotal)
617: updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false)
618: matchIncomingSell(asset, incomingAsk, matchTotal)
621: addSellOrder(incomingAsk, asset, orderHintArray)
```
[451](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L451) | [577](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L577) | [579](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L579) | [582](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L582) | [586](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L586) | [591](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L591) | [594](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L594) | [601](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L601) | [602](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L602) | [606](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L606) | [609](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L609) | [613](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L613) | [617](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L617) | [618](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L618) | [621](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L621)
</details>

### [N-02] Array indices should be referenced via `enum`s rather than via numeric literals

Using constant array indexes can make your Solidity code harder to read and maintain.
To improve clarity, consider using commented enum values in place of constant array indexes.

Enums provide a way to define a type that has a few pre-defined values, making your code more self-explanatory and easy to understand.
This can be particularly helpful in large codebases or when working with a team.

<details>
<summary><i>4 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

55: secondsAgos[0]
56: secondsAgos[1]
61: tickCumulatives[1]
61: tickCumulatives[0]
```
[55](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L55) | [56](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L56) | [61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L61) | [61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L61)
</details>

### [N-03] Consider splitting long calculations

For improved readability and maintainability, it's suggested to limit arithmetic operations to 3 per expression.
Excessive operations can convolute the code, making it more prone to errors and more difficult to debug or review.
Splitting operations across multiple lines is often a good approach.
Special care should be taken with division operations. The number of arithmetic operations per line ideally shouldn't exceed three.

<details>
<summary><i>5 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

183: protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether)
187: protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether)
191: protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether)
195: protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether)
198: protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether)
```
[183](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L183) | [187](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L187) | [191](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L191) | [195](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L195) | [198](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L198)
</details>

### [N-04] Use custom errors instead of `require()/assert()`

Starting from Solidity 0.8.4, custom errors have been introduced to improve readability and clarity in your code. Instead of using `require()/assert()` with strings, custom errors can provide more expressive and understandable error conditions.

This change not only reduces unnecessary clutter in your codebase but also promotes a more streamlined contract structure, ultimately improving the quality of your Solidity code.

<details>
<summary><i>3 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

397: assert(newBaseRate > 0)
```
[397](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L397)

```solidity
File: contracts/libraries/LibBytes.sol

14: require(slate.length % 51 == 0, "Invalid data length")
```
[14](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L14)

```solidity
File: contracts/libraries/LibSRUtil.sol

62: assert(shortRecord.status != SR.PartialFill)
```
[62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L62)
</details>

### [N-05] Variables need not be initialized to zero

By default, `int/uint` variables in Solidity are initialized to `zero`.
Explicitly setting variables to zero during their declaration is redundant and might cause confusion.
Removing the explicit zero initialization can improve code readability and understanding.

<details>
<summary><i>6 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

78: for (uint8 i = 0; i < proposalInput.length; i++) {
242: for (uint256 i = 0; i < decodedProposalData.length; i++) {
321: for (uint256 i = 0; i < decodedProposalData.length; i++) {
```
[78](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L78) | [242](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L242) | [321](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L321)

```solidity
File: contracts/libraries/LibBytes.sol

18: for (uint256 i = 0; i < slateLength; i++) {
```
[18](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L18)

```solidity
File: contracts/libraries/LibOrders.sol

71: for (uint256 i = 0; i < size; i++) {
743: for (uint256 i = 0; i < shortHintArray.length;) {
```
[71](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L71) | [743](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L743)
</details>

### [N-06] Consider using a `struct` rather than having many function input parameters

Functions with many parameters can become difficult to read and maintain. 
Using a struct to encapsulate these parameters can improve code readability, increase reusability, and reduce the likelihood of errors.
Consider refactoring functions that take more than three parameters to use a struct instead.

<details>
<summary><i>18 issue instances in 10 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft)
65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
77: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft)
```
[40](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40) | [65](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65) | [77](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L77)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant
```
[35](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
```
[47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47)

```solidity
File: contracts/facets/ExitShortFacet.sol

142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id)
```
[142](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)

```solidity
File: contracts/facets/RedemptionFacet.sol

224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
```
[224](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
```
[39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39)

```solidity
File: contracts/libraries/LibOracle.sol

69: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice)
117: function oracleCircuitBreaker(
        uint80 roundId,
        uint80 baseRoundId,
        int256 chainlinkPrice,
        int256 baseChainlinkPrice,
        uint256 timeStamp,
        uint256 baseTimeStamp
    ) private view
```
[69](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L69) | [117](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L117)

```solidity
File: contracts/libraries/LibOrders.sol

260: function verifySellId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 _prevId,
        uint256 _newPrice,
        uint16 _nextId
    ) private view returns (int256 direction)
320: function _reuseOrderIds(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        uint16 prevHEAD,
        O cancelledOrMatched
    ) private
402: function verifyId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 prevId,
        uint256 newPrice,
        uint16 nextId,
        O orderType
    ) internal view returns (int256 direction)
440: function getOrderId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        int256 direction,
        uint16 hintId,
        uint256 _newPrice,
        O orderType
    ) internal view returns (uint16 _hintId)
```
[260](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L260) | [320](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L320) | [402](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L402) | [440](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L440)

```solidity
File: contracts/libraries/LibSRUtil.sol

22: function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
        internal
49: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
```
[22](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L22) | [49](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L49) | [72](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L72)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

47: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
        internal
        view
        returns (uint256 amountOut)
```
[47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)
</details>

### [N-07] Consider using descriptive `constant`s when passing zero as a function argument

In instances where utilizing a zero parameter is essential, it is recommended to employ descriptive constants or an enum instead of directly integrating zero within function calls.
This strategy aids in clearly articulating the caller's intention and minimizes the risk of errors.
Emitting zero also not recomended, as it is not clear what the intention is.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/ShortOrdersFacet.sol

48: LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0)
```
[48](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L48)
</details>

### [N-08] File with Library declaration Shoulde contain only Library

Libraries should be declared in a separate file and not in the same file where other contract/interfases declared.
This helps in maintaining a clean and organized codebase.

<details>
<summary><i>2 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

21: library OracleLibrary
10: interface IUniswapV3Pool
```
[21](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21) | [10](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10)
</details>

### [N-09] Unused `private` functions can be removed

All unused code should be removed.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

368: function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private
```
[368](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L368)
</details>

### [N-10] Consider using `delete` rather than assigning `zero` to clear values

Rather than merely setting a variable to zero, you can use the `delete` keyword to reset it to its default value.
This action is especially relevant for complex data types like arrays or mappings where the default is not necessarily zero.
Using `delete` not only provides explicit clarity that you intend to reset a variable, but it can also result in more concise and intuitive code.

<details>
<summary><i>17 issue instances in 5 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

158: lowestSell.ercAmount = 0
191: b.dustAskId = 0
194: incomingBid.ercAmount = 0
```
[158](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L158) | [191](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L191) | [194](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L194)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

56: VaultUser.bridgeCreditReth = 0
69: VaultUser.bridgeCreditSteth = 0
86: VaultUser.bridgeCreditSteth = 0
99: VaultUser.bridgeCreditReth = 0
167: VaultUserFrom.bridgeCreditReth = 0
176: VaultUserFrom.bridgeCreditSteth = 0
188: VaultUserFrom.bridgeCreditReth = 0
189: VaultUserFrom.bridgeCreditSteth = 0
```
[56](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L56) | [69](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L69) | [86](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L86) | [99](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L99) | [167](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L167) | [176](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L176) | [188](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L188) | [189](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L189)

```solidity
File: contracts/libraries/LibOrders.sol

578: incomingAsk.ercAmount = 0
585: highestBid.ercAmount = 0
612: incomingAsk.ercAmount = 0
```
[578](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L578) | [585](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L585) | [612](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L612)

```solidity
File: contracts/libraries/LibSRUtil.sol

138: short.tokenId = 0
148: nft.shortOrderId = 0
```
[138](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L138) | [148](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L148)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

56: secondsAgos[1] = 0
```
[56](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L56)
</details>

### [N-11] Consider emitting an event at the end of the constructor

This will allow users to easily exactly pinpoint when and by whom a contract was constructed.

<details>
<summary><i>3 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

30: constructor(address _dusd)
```
[30](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

29: constructor(address _rethBridge, address _stethBridge)
```
[29](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
File: contracts/facets/ExitShortFacet.sol

28: constructor(address _dusd)
```
[28](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L28)
</details>

### [N-12] Consider using named returns

Using named returns makes the code more self-documenting, makes it easier to fill out NatSpec, and in some cases can save gas.
The cases below are where there currently is at most one return statement, which is ideal for named returns.

<details>
<summary><i>17 issue instances in 7 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
122: function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
        private
        returns (MTypes.PrimaryLiquidation memory)
229: function min88(uint256 a, uint88 b) private pure returns (uint88)
```
[47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47) | [122](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122) | [229](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

40: function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256)
51: function getBridges(uint256 vault) external view returns (address[] memory)
169: function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88)
```
[40](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L40) | [51](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L51) | [169](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
File: contracts/facets/RedemptionFacet.sol

31: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
```
[31](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L31)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
```
[39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39)

```solidity
File: contracts/libraries/LibBytes.sol

11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory)
```
[11](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
File: contracts/libraries/LibOracle.sol

19: function getOraclePrice(address asset) internal view returns (uint256)
168: function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256)
```
[19](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L19) | [168](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
File: contracts/libraries/LibOrders.sol

35: function convertCR(uint16 cr) internal pure returns (uint256)
55: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
        internal
        view
        returns (STypes.Order[] memory)
78: function isShort(STypes.Order memory order) internal pure returns (bool)
362: function findPrevOfIncomingId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) internal view returns (uint16)
985: function min(uint256 a, uint256 b) internal pure returns (uint256)
989: function max(uint256 a, uint256 b) internal pure returns (uint256)
```
[35](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L35) | [55](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L55) | [78](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L78) | [362](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L362) | [985](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L985) | [989](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L989)
</details>

### [N-13] Style guide: Initialisms should be capitalized

According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#naming-styles) initialisms such as "NFT", "ERC", etc should be capitalized.

<details>
<summary><i>104 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

43: uint88 ercAmount
47: uint88 ethFilled
47: uint88 ercAmountLeft
65: uint88 ercAmount
68: uint88 ethFilled
68: uint88 ercAmountLeft
81: uint88 ercAmount
85: uint88 ethFilled
85: uint88 ercAmountLeft
135: uint88 ethFilled
135: uint88 ercAmountLeft
280: uint88 ethFilled
280: uint88 ercAmountLeft
86: uint256 eth = ercAmount.mul(price)
136: uint256 minBidEth = LibAsset.minBidEth(asset)
221: uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount
222: uint88 fillEth = lowestSell.price.mulU88(fillErc)
228: uint88 shortFillEth = fillEth + colUsed
```
[43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L43) | [47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L47) | [47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L47) | [65](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65) | [68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L68) | [68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L68) | [81](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L81) | [85](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L85) | [85](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L85) | [135](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L135) | [135](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L135) | [280](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L280) | [280](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L280) | [86](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L86) | [136](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L136) | [221](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L221) | [222](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L222) | [228](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L228)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

38: uint88 ercAmount
41: uint16 shortOrderCR
```
[38](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L38) | [41](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L41)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

155: uint256 startGas = gasleft()
156: uint88 ercAmountLeft
171: uint96 ercDebtPrev = m.short.ercDebt
181: uint96 ercDebtSocialized = ercDebtPrev - m.short.ercDebt
196: uint256 gasUsed = startGas - gasleft()
```
[155](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L155) | [156](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L156) | [171](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L171) | [181](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L181) | [196](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L196)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

26: address private immutable rethBridge
27: address private immutable stethBridge
29: address _rethBridge
29: address _stethBridge
40: function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256)
82: function depositEth(address bridge) external payable nonReentrant
101: uint88 dethAmount
133: uint88 dethAmount
169: function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88)
68: uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount))
87: uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}())
108: uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge)
119: uint88 ethAmount = _ethConversion(vault, dethAmount)
137: uint88 ethAmount = _ethConversion(vault, dethAmount)
149: uint88 dethTotal = s.vault[vault].dethTotal
170: uint256 dethTotalNew = vault.getDethTotal()
171: uint88 dethTotal = s.vault[vault].dethTotal
```
[26](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L26) | [27](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L27) | [29](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29) | [29](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29) | [40](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L40) | [82](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L82) | [101](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L101) | [133](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L133) | [169](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L169) | [68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L68) | [87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L87) | [108](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L108) | [119](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L119) | [137](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L137) | [149](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L149) | [170](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L170) | [171](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L171)

```solidity
File: contracts/facets/ExitShortFacet.sol

87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
52: uint256 ercDebt = short.ercDebt
98: uint256 ercDebt = short.ercDebt
177: uint256 ethAmount = price.mul(e.buybackAmount)
```
[87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [52](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L52) | [98](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L98) | [177](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L177)

```solidity
File: contracts/facets/RedemptionFacet.sol

31: uint256 minShortErc
224: uint8 incorrectIndex
347: uint8 claimIndex
382: uint88 ercDebtRedeemed
66: uint256 minShortErc = LibAsset.minShortErc(p.asset)
250: uint256 minShortErc = LibAsset.minShortErc(d.asset)
392: uint104 totalAssetErcDebt = (ercDebtRedeemed + Asset.ercDebt).mulU104(C.BETA)
```
[31](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L31) | [224](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224) | [347](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L347) | [382](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382) | [66](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L66) | [250](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L250) | [392](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L392)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

21: function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
39: address rethBridge
39: address stethBridge
113: address rethBridge
113: address stethBridge
198: function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal
46: uint88 creditReth
47: uint88 creditSteth
114: IBridge bridgeReth = IBridge(rethBridge)
115: IBridge bridgeSteth = IBridge(stethBridge)
118: uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH)
119: uint256 unitRethOracle = bridgeReth.getUnitDethValue()
120: uint256 factorReth = unitRethTWAP.div(unitRethOracle)
122: uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH)
123: uint256 unitWstethOracle = bridgeSteth.getUnitDethValue()
124: uint256 factorSteth = unitWstethTWAP.div(unitWstethOracle)
152: uint88 creditReth = VaultUserFrom.bridgeCreditReth
153: uint88 creditSteth = VaultUserFrom.bridgeCreditSteth
```
[21](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L21) | [39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [113](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113) | [113](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113) | [198](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L198) | [46](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L46) | [47](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L47) | [114](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L114) | [115](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L115) | [118](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L118) | [119](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L119) | [120](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L120) | [122](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L122) | [123](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L123) | [124](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L124) | [152](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L152) | [153](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L153)

```solidity
File: contracts/libraries/LibBytes.sol

25: uint88 ercDebtRedeemed
```
[25](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L25)

```solidity
File: contracts/libraries/LibOracle.sol

74: uint256 chainlinkPriceInEth
131: uint256 twapPriceInEth
30: uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0
43: uint256 priceInEth = uint256(price).div(uint256(basePrice))
62: uint256 twapInv = twapCircuitBreaker()
63: uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv)
94: uint256 twapPriceInEth = twapPriceNormalized.inv()
102: IERC20 weth = IERC20(C.WETH)
103: uint256 wethBal = weth.balanceOf(C.USDC_WETH)
137: IERC20 weth = IERC20(C.WETH)
138: uint256 wethBal = weth.balanceOf(C.USDC_WETH)
```
[74](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L74) | [131](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L131) | [30](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L30) | [43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L43) | [62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L62) | [63](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L63) | [94](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L94) | [102](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L102) | [103](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L103) | [137](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L137) | [138](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L138)

```solidity
File: contracts/libraries/LibOrders.sol

40: uint88 eth
558: STypes.Order memory incomingAsk
560: uint256 minAskEth
652: function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private
652: STypes.Order memory incomingAsk
99: uint88 eth = order.ercAmount.mulU88(order.price)
142: uint88 eth = order.ercAmount.mulU88(order.price).mulU88(LibOrders.convertCR(order.shortOrderCR))
712: uint88 fillErc = incomingSell.ercAmount > highestBid.ercAmount ? highestBid.ercAmount : incomingSell.ercAmount
713: uint88 fillEth = highestBid.price.mulU88(fillErc)
831: bool anyOrderHintPrevMatched
862: uint88 eth = bid.ercAmount.mulU88(bid.price)
889: uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR))
903: uint88 minShortErc = uint88(LibAsset.minShortErc(asset))
```
[40](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L40) | [558](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L558) | [560](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L560) | [652](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L652) | [652](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L652) | [99](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L99) | [142](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L142) | [712](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L712) | [713](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L713) | [831](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L831) | [862](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L862) | [889](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L889) | [903](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L903)

```solidity
File: contracts/libraries/LibSRUtil.sol

22: uint256 dethYieldRate
72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
151: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal
79: uint256 minShortErc = LibAsset.minShortErc(asset)
127: STypes.NFT storage nft = s.nftMapping[tokenId]
155: uint64 ercDebtRate = s.asset[asset].ercDebtRate
156: uint88 ercDebt = short.ercDebt.mulU88(ercDebtRate - short.ercDebtRate)
```
[22](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L22) | [72](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L72) | [151](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L151) | [79](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L79) | [127](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L127) | [155](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L155) | [156](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L156)
</details>

### [N-14] Consider using named function arguments

When calling functions in external contracts with multiple arguments, consider using named function parameters, rather than positional ones.

<details>
<summary><i>89 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

48: LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray)
108: LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray)
114: LibOrders.addBid(asset, incomingBid, orderHintArray)
143: LibOrders.addBid(asset, incomingBid, orderHintArray)
162: LibOrders.matchOrder(s.shorts, asset, lowestSell.id)
166: LibOrders.matchOrder(s.asks, asset, lowestSell.id)
174: LibOrders.matchOrder(s.shorts, asset, lowestSell.id)
177: LibOrders.matchOrder(s.asks, asset, lowestSell.id)
199: LibOrders.addBid(asset, incomingBid, orderHintArray)
227: LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed)
243: LibShortRecord.fillShortRecord(
                asset,
                lowestSell.addr,
                lowestSell.shortRecordId,
                status,
                shortFillEth,
                fillErc,
                matchTotal.ercDebtRate,
                matchTotal.dethYieldRate
            )
288: LibOrders.updateSellOrdersOnMatch(asset, b)
293: IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId)
295: IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId)
332: Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc)
335: LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice)
```
[48](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L48) | [108](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L108) | [114](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L114) | [143](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L143) | [162](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L162) | [166](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L166) | [174](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L174) | [177](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L177) | [199](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L199) | [227](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L227) | [243](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L243) | [288](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L288) | [293](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L293) | [295](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L295) | [332](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L332) | [335](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L335)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

48: LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0)
76: LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray)
80: LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)
86: LibOrders.addShort(asset, incomingShort, orderHintArray)
88: LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth)
```
[48](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L48) | [76](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L76) | [80](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L80) | [86](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L86) | [88](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L88)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

68: LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray)
75: LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)
87: Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched)
126: LibShortRecord.updateErcDebt(asset, shorter, id)
188: IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray)
246: LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt)
247: LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id)
260: LibSRUtil.disburseCollateral(m.asset, m.shorter, decreaseCol, m.short.dethYieldRate, m.short.updatedAt)
265: LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id)
267: LibShortRecord.fillShortRecord(
                    m.asset,
                    address(this),
                    C.SHORT_STARTING_ID,
                    SR.FullyFilled,
                    m.short.collateral,
                    m.short.ercDebt,
                    s.asset[m.asset].ercDebtRate,
                    m.short.dethYieldRate
                )
```
[68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L68) | [75](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L75) | [87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L87) | [126](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L126) | [188](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188) | [246](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L246) | [247](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L247) | [260](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L260) | [265](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L265) | [267](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L267)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

68: IBridge(bridge).deposit(msg.sender, amount)
70: vault.addDeth(bridgePointer, dethAmount)
72: Events.Deposit(bridge, msg.sender, dethAmount)
88: vault.addDeth(bridgePointer, dethAmount)
90: Events.DepositEth(bridge, msg.sender, dethAmount)
108: vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge)
110: LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge)
120: vault.removeDeth(dethAmount, fee)
121: IBridge(bridge).withdraw(msg.sender, ethAmount)
122: Events.Withdraw(bridge, msg.sender, dethAmount, fee)
142: IBridge(bridge).withdraw(msg.sender, ethAmount)
143: Events.WithdrawTapp(bridge, msg.sender, dethAmount)
```
[68](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L68) | [70](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L70) | [72](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L72) | [88](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L88) | [90](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L90) | [108](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L108) | [110](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L110) | [120](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L120) | [121](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L121) | [122](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L122) | [142](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L142) | [143](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L143)

```solidity
File: contracts/facets/ExitShortFacet.sol

61: LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt)
62: LibShortRecord.deleteShortRecord(asset, msg.sender, id)
75: Events.ExitShortWallet(asset, msg.sender, id, buybackAmount)
113: LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt)
115: LibShortRecord.deleteShortRecord(asset, msg.sender, id)
128: Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount)
152: LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray)
187: IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray)
196: LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt)
197: LibShortRecord.deleteShortRecord(e.asset, msg.sender, id)
208: LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt)
210: Events.ExitShort(asset, msg.sender, id, e.ercFilled)
```
[61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L61) | [62](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L62) | [75](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L75) | [113](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L113) | [115](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L115) | [128](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L128) | [152](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L152) | [187](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L187) | [196](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L196) | [197](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L197) | [208](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L208) | [210](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L210)

```solidity
File: contracts/facets/RedemptionFacet.sol

113: LibOrders.cancelShort(asset, p.shortOrderId)
129: bytes.concat(
                slate,
                bytes20(p.shorter),
                bytes1(p.shortId),
                bytes8(uint64(p.currentCR)),
                bytes11(p.amountProposed),
                bytes11(p.colRedeemed)
            )
138: LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt)
210: Events.ProposeRedemption(p.asset, msg.sender)
240: LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength)
284: Events.DisputeRedemptionAll(d.asset, redeemer)
318: LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength)
333: Events.ClaimRedemption(asset, msg.sender)
358: LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1)
376: LibSRUtil.disburseCollateral(asset, shorter, collateral, shortRecord.dethYieldRate, shortRecord.updatedAt)
377: LibShortRecord.deleteShortRecord(asset, shorter, shortId)
```
[113](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L113) | [129](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L129) | [138](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L138) | [210](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L210) | [240](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L240) | [284](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L284) | [318](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L318) | [333](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L333) | [358](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L358) | [376](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L376) | [377](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L377)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

118: OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH)
122: OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH)
```
[118](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L118) | [122](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L122)

```solidity
File: contracts/libraries/LibOracle.sol

87: IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes)
133: IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes)
```
[87](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L87) | [133](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L133)

```solidity
File: contracts/libraries/LibOrders.sol

218: Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount)
301: Events.CancelOrder(asset, id, orders[asset][id].orderType)
631: Events.MatchOrder(
            asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, matchTotal.fillEth, matchTotal.fillErc
        )
642: LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice)
679: LibShortRecord.fillShortRecord(
            asset,
            incomingShort.addr,
            incomingShort.shortRecordId,
            status,
            matchTotal.fillEth,
            matchTotal.fillErc,
            Asset.ercDebtRate,
            Vault.dethYieldRate
        )
732: asset.setPriceAndTime(oraclePrice, getOffsetTime())
901: LibShortRecord.deleteShortRecord(asset, shorter, shortRecordId)
913: LibShortRecord.fillShortRecord(
                        asset,
                        shorter,
                        shortRecordId,
                        SR.FullyFilled,
                        collateralDiff,
                        debtDiff,
                        Asset.ercDebtRate,
                        Vault.dethYieldRate
                    )
```
[218](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L218) | [301](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L301) | [631](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L631) | [642](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L642) | [679](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L679) | [732](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L732) | [901](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L901) | [913](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L913)

```solidity
File: contracts/libraries/LibSRUtil.sol

61: LibOrders.cancelShort(asset, shortOrderId)
66: LibOrders.cancelShort(asset, shortOrderId)
90: LibOrders.cancelShort(asset, shortOrderId)
135: LibOrders.cancelShort(asset, nft.shortOrderId)
139: LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId)
142: LibShortRecord.createShortRecord(
            asset, to, SR.FullyFilled, short.collateral, short.ercDebt, short.ercDebtRate, short.dethYieldRate, tokenId
        )
```
[61](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L61) | [66](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L66) | [90](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L90) | [135](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L135) | [139](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L139) | [142](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L142)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

39: U256.mulDiv(ratioX192, baseAmount, 1 << 192)
39: U256.mulDiv(1 << 192, baseAmount, ratioX192)
41: U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64)
43: U256.mulDiv(ratioX128, baseAmount, 1 << 128)
43: U256.mulDiv(1 << 128, baseAmount, ratioX128)
```
[39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39) | [39](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39) | [41](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L41) | [43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43) | [43](https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43)
</details>

### [N-15] Function Parameters in Public Accessible Functions Need `address(0)` Check

Parameters of type `address` in your functions should be checked to ensure that they are not assigned the null address (`address(0x0)`). 
Failure to validate these parameters can lead to transaction reverts, wasted gas, the need for transaction resubmission, and may even require redeployment of contracts within the protocol in certain situations.
Implement checks for `address(0x0)` to avoid these potential issues.

<details>
<summary><i>15 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit `asset` parameter without address(0) check
40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit `sender` parameter without address(0) check
/// @audit `asset` parameter without address(0) check
65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
    {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40) | [65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

/// @audit `asset` parameter without address(0) check
35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit `asset` parameter without address(0) check
/// @audit `shorter` parameter without address(0) check
47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
    {
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit `bridge` parameter without address(0) check
63: function deposit(address bridge, uint88 amount) external nonReentrant {
/// @audit `bridge` parameter without address(0) check
82: function depositEth(address bridge) external payable nonReentrant {
/// @audit `bridge` parameter without address(0) check
101: function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
/// @audit `bridge` parameter without address(0) check
133: function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
```
[63](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L63) | [82](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L82) | [101](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L101) | [133](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L133)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit `asset` parameter without address(0) check
41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
/// @audit `asset` parameter without address(0) check
87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
/// @audit `asset` parameter without address(0) check
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41) | [87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit `asset` parameter without address(0) check
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
/// @audit `asset` parameter without address(0) check
/// @audit `redeemer` parameter without address(0) check
/// @audit `disputeShorter` parameter without address(0) check
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
/// @audit `asset` parameter without address(0) check
310: function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
/// @audit `asset` parameter without address(0) check
/// @audit `redeemer` parameter without address(0) check
347: function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224) | [310](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L310) | [347](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L347)
</details>

### [N-16] Contract/Library Names Not in `CapWords` Style (CamelCase)

Contracts and libraries should be named using the `CapWords` style for better readability and consistency with Solidity style guidelines.
Examples of good practice include: SimpleToken, SmartBank, CertificateHashRepository, Player, Congress, Owned.
[More information in Documentation](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#contract-and-library-names)

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)
</details>

### [N-17] Events are missing sender information

Events should include the sender information when emitted in `public` or `external` functions for better traceability.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit external function `disputeRedemption()` emits an event without sender information
284: emit Events.DisputeRedemptionAll(d.asset, redeemer);
```
[284](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L284)
</details>

### [N-18] Non-constant/non-immutable variables using all capital letters

Variable names that consist of all capital letters should be reserved for constant/immutable variables. If the variable needs to be different based on which class it comes from, a view/pure function should be used instead.

<details>
<summary><i>4 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

165: STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
211: STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
241: STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
```
[165](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165) | [211](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L211) | [241](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241)

```solidity
File: contracts/libraries/LibBytes.sol

24: uint64 CR; // bytes8
```
[24](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L24)
</details>

### [N-19] Leverage Recent Solidity Features with `0.8.23`

The recent updates in Solidity provide several features and optimizations that, when leveraged appropriately, can significantly improve your contract's code clarity and maintainability.
Key enhancements include the use of push0 for placing 0 on the stack for EVM versions starting from "Shanghai", making your code simpler and more straightforward.
Moreover, Solidity has extended NatSpec documentation support to enum and struct definitions, facilitating more comprehensive and insightful code documentation.

Additionally, the re-implementation of the UnusedAssignEliminator and UnusedStoreEliminator in the Solidity optimizer provides the ability to remove unused assignments in deeply nested loops.
This results in a cleaner, more efficient contract code, reducing clutter and potential points of confusion during code review or debugging.
It's recommended to make full use of these features and optimizations to enhance the robustness and readability of your smart contracts.

<details>
<summary><i>12 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L2)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L2)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L2)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L2)

```solidity
File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L2)

```solidity
File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L2)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L2)

```solidity
File: contracts/libraries/LibBytes.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L2)

```solidity
File: contracts/libraries/LibOracle.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L2)

```solidity
File: contracts/libraries/LibOrders.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L2)

```solidity
File: contracts/libraries/LibSRUtil.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L2)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

2: pragma solidity 0.8.21;
```
[2](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L2)
</details>

### [N-20] NatSpec: Function `@param` tag is missing

Natural Specification (NatSpec) comments are crucial for understanding the role of function arguments in your Solidity code.
Including `@param` tags will not only improve your code's readability but also its maintainability by clearly defining each argument's purpose.

[More information in Documentation](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>69 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit Missed @param `sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray`
77: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit Missed @param `asset, b`
340: function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
/// @audit Missed @param `asset, lowestSell, incomingBid, b`
358: function _shortDirectionHandler(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.BidMatchAlgo memory b
    ) private view {
```
[77](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L77) | [340](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L340) | [358](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L358)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Missed @param `_dusd`
30: constructor(address _dusd) {
/// @audit Missed @param `shortOrderId`
47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
    {
/// @audit Missed @param `m`
96: function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {
/// @audit Missed @param `shortOrderId`
122: function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
        private
        returns (MTypes.PrimaryLiquidation memory)
    {
/// @audit Missed @param `a, b`
229: function min88(uint256 a, uint88 b) private pure returns (uint88) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30) | [47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47) | [96](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96) | [122](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122) | [229](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit Missed @param `_rethBridge, _stethBridge`
29: constructor(address _rethBridge, address _stethBridge) {
/// @audit Missed @param `vault, amount`
148: function maybeUpdateYield(uint256 vault, uint88 amount) private {
/// @audit Missed @param `bridge`
156: function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
/// @audit Missed @param `vault, amount`
169: function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29) | [148](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L148) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L156) | [169](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit Missed @param `_dusd`
28: constructor(address _dusd) {
/// @audit Missed @param `shortOrderId`
41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
/// @audit Missed @param `shortOrderId`
87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
/// @audit Missed @param `shortOrderId`
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
/// @audit Missed @param `short`
213: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L28) | [41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41) | [87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142) | [213](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit Missed @param `shortRecord, proposer, shorter, minShortErc`
31: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
    {
/// @audit Missed @param `asset, vault, shorter, shortId`
368: function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {
/// @audit Missed @param `asset, colRedeemed, ercDebtRedeemed`
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
    {
```
[31](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L31) | [368](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L368) | [382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit Missed @param `vault, bridgePointer, amount`
21: function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
/// @audit Missed @param `vault, bridgePointer, amount, rethBridge, stethBridge`
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
/// @audit Missed @param `bridgePointer, rethBridge, stethBridge`
113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
/// @audit Missed @param `asset, from, to, collateral`
144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
/// @audit Missed @param `vault, amount, fee`
198: function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L21) | [39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113) | [144](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L144) | [198](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
File: contracts/libraries/LibBytes.sol

/// @audit Missed @param `SSTORE2Pointer, slateLength`
11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit Missed @param `asset`
19: function getOraclePrice(address asset) internal view returns (uint256) {
/// @audit Missed @param `protocolPrice, roundId, chainlinkPrice, timeStamp, chainlinkPriceInEth`
69: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
/// @audit Missed @param `roundId, baseRoundId, chainlinkPrice, baseChainlinkPrice, timeStamp, baseTimeStamp`
117: function oracleCircuitBreaker(
        uint80 roundId,
        uint80 baseRoundId,
        int256 chainlinkPrice,
        int256 baseChainlinkPrice,
        uint256 timeStamp,
        uint256 baseTimeStamp
    ) private view {
/// @audit Missed @param `asset, oraclePrice, oracleTime`
149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
/// @audit Missed @param `asset`
156: function getTime(address asset) internal view returns (uint256 creationTime) {
/// @audit Missed @param `asset`
162: function getPrice(address asset) internal view returns (uint80 oraclePrice) {
/// @audit Missed @param `asset`
168: function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L19) | [69](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L69) | [117](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L117) | [149](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L149) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L156) | [162](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L162) | [168](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit Missed @param `cr`
35: function convertCR(uint16 cr) internal pure returns (uint256) {
/// @audit Missed @param `asset, order, matchTotal, eth`
40: function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {
/// @audit Missed @param `STypes.Order`
55: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
        internal
        view
        returns (STypes.Order[] memory)
    {
/// @audit Missed @param `order`
78: function isShort(STypes.Order memory order) internal pure returns (bool) {
/// @audit Missed @param `asset, order, orderHintArray`
82: function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
/// @audit Missed @param `asset, order, orderHintArray`
103: function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
/// @audit Missed @param `STypes.Order`
173: function addOrder(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) private {
/// @audit Missed @param `STypes.Order`
260: function verifySellId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 _prevId,
        uint256 _newPrice,
        uint16 _nextId
    ) private view returns (int256 direction) {
/// @audit Missed @param `STypes.Order`
289: function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
/// @audit Missed @param `STypes.Order`
314: function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
/// @audit Missed @param `STypes.Order`
320: function _reuseOrderIds(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        uint16 prevHEAD,
        O cancelledOrMatched
    ) private {
/// @audit Missed @param `STypes.Order`
362: function findPrevOfIncomingId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) internal view returns (uint16) {
/// @audit Missed @param `STypes.Order`
402: function verifyId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 prevId,
        uint256 newPrice,
        uint16 nextId,
        O orderType
    ) internal view returns (int256 direction) {
/// @audit Missed @param `o`
420: function normalizeOrderType(O o) private pure returns (O newO) {
/// @audit Missed @param `STypes.Order`
440: function getOrderId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        int256 direction,
        uint16 hintId,
        uint256 _newPrice,
        O orderType
    ) internal view returns (uint16 _hintId) {
/// @audit Missed @param `STypes.Order`
474: function updateBidOrdersOnMatch(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        bool isOrderFullyFilled
    ) internal {
/// @audit Missed @param `STypes.Order`
532: function _updateOrders(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 headId,
        uint16 lastMatchedId
    ) private {
/// @audit Missed @param `asset, incomingOrder, matchTotal`
628: function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {
/// @audit Missed @param `asset, shortHintArray`
728: function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
/// @audit Missed @param `asset, savedPrice, incomingOrder, shortHintArray`
783: function updateOracleAndStartingShortViaThreshold(
        address asset,
        uint256 savedPrice,
        STypes.Order memory incomingOrder,
        uint16[] memory shortHintArray
    ) internal {
/// @audit Missed @param `asset, shortHintArray`
803: function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {
/// @audit Missed @param `asset, incomingShort`
810: function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
/// @audit Missed @param `STypes.Order`
826: function findOrderHintId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        MTypes.OrderHint[] memory orderHintArray
    ) internal view returns (uint16 hintId) {
/// @audit Missed @param `asset, id`
854: function cancelBid(address asset, uint16 id) internal {
/// @audit Missed @param `asset, id`
868: function cancelAsk(address asset, uint16 id) internal {
/// @audit Missed @param `asset, id`
882: function cancelShort(address asset, uint16 id) internal {
/// @audit Missed @param `asset, price`
955: function handlePriceDiscount(address asset, uint80 price) internal {
/// @audit Missed @param `a, b`
985: function min(uint256 a, uint256 b) internal pure returns (uint256) {
/// @audit Missed @param `a, b`
989: function max(uint256 a, uint256 b) internal pure returns (uint256) {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L35) | [40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L40) | [55](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L55) | [78](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L78) | [82](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L82) | [103](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L103) | [173](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L173) | [260](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L260) | [289](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L289) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L314) | [320](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L320) | [362](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L362) | [402](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L402) | [420](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L420) | [440](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L440) | [474](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L474) | [532](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L532) | [628](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L628) | [728](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L728) | [783](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L783) | [803](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L803) | [810](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L810) | [826](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L826) | [854](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L854) | [868](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L868) | [882](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L882) | [955](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L955) | [985](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L985) | [989](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
File: contracts/libraries/LibSRUtil.sol

/// @audit Missed @param `asset, shorter, collateral, dethYieldRate, updatedAt`
22: function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
        internal
    {
/// @audit Missed @param `asset, initialStatus, shortOrderId, shortRecordId, shorter`
49: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
/// @audit Missed @param `asset, initialStatus, shortOrderId, shortRecordId, shorter`
72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
/// @audit Missed @param `asset, shortRecordCR, oraclePrice`
102: function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
        internal
        view
        returns (bool recoveryViolation)
    {
/// @audit Missed @param `from, to, tokenId`
124: function transferShortRecord(address from, address to, uint40 tokenId) internal {
/// @audit Missed @param `short, asset`
151: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```
[22](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L22) | [49](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L49) | [72](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L72) | [102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L102) | [124](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L124) | [151](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L151)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Missed @param `amountIn, secondsAgo, pool, baseToken, quoteToken`
47: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
        internal
        view
        returns (uint256 amountOut)
    {
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)
</details>

### [N-21] High cyclomatic complexity

Functions with high cyclomatic complexity are harder to understand, test, and maintain.
Consider breaking down these blocks into more manageable units, by splitting things into utility functions,
by reducing nesting, and by using early returns.

[Learn More About Cyclomatic Complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity)

<details>
<summary><i>15 issue instances in 8 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit function `bidMatchAlgo` has a cyclomatic complexity of 18
130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit function `matchIncomingBid` has a cyclomatic complexity of 9
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

/// @audit function `createLimitShort` has a cyclomatic complexity of 7
35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit function `exitShort` has a cyclomatic complexity of 7
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit function `proposeRedemption` has a cyclomatic complexity of 22
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
/// @audit function `disputeRedemption` has a cyclomatic complexity of 11
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit function `assessDeth` has a cyclomatic complexity of 16
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
/// @audit function `transferBridgeCredit` has a cyclomatic complexity of 11
144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [144](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L144)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit function `getOraclePrice` has a cyclomatic complexity of 6
18: function getOraclePrice(address asset) internal view returns (uint256) {
/// @audit function `baseOracleCircuitBreaker` has a cyclomatic complexity of 7
68: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L18) | [68](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L68)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit function `updateSellOrdersOnMatch` has a cyclomatic complexity of 6
499: function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
/// @audit function `sellMatchAlgo` has a cyclomatic complexity of 14
556: function sellMatchAlgo(
        address asset,
        STypes.Order memory incomingAsk,
        MTypes.OrderHint[] memory orderHintArray,
        uint256 minAskEth
    ) internal {
/// @audit function `_updateOracleAndStartingShort` has a cyclomatic complexity of 8
727: function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
/// @audit function `cancelShort` has a cyclomatic complexity of 8
881: function cancelShort(address asset, uint16 id) internal {
```
[499](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L499) | [556](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L556) | [727](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L727) | [881](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L881)

```solidity
File: contracts/libraries/LibSRUtil.sol

/// @audit function `checkShortMinErc` has a cyclomatic complexity of 7
71: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
```
[71](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L71)
</details>

### [N-22] Contract should expose an `interface`

Exposing an interface in a smart contract allows for easier integration by other projects and developers.
Without an interface, there's a risk that other projects will have to develop non-standard variants to interact with your contract.
It's highly recommended to define an interface for clearer and more robust collaboration.

<details>
<summary><i>36 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
    {
76: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
214: function matchlowestSell(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal
    ) private {
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
340: function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
357: function _shortDirectionHandler(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.BidMatchAlgo memory b
    ) private view {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40) | [65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65) | [76](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L76) | [130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [214](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L214) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275) | [340](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L340) | [357](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L357)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
    {
96: function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {
122: function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
        private
        returns (MTypes.PrimaryLiquidation memory)
    {
154: function _performForcedBid(MTypes.PrimaryLiquidation memory m, uint16[] memory shortHintArray) private {
209: function _liquidationFeeHandler(MTypes.PrimaryLiquidation memory m) private {
228: function min88(uint256 a, uint88 b) private pure returns (uint88) {
240: function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47) | [96](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L96) | [122](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122) | [154](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L154) | [209](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L209) | [228](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L228) | [240](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

40: function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
51: function getBridges(uint256 vault) external view returns (address[] memory) {
63: function deposit(address bridge, uint88 amount) external nonReentrant {
82: function depositEth(address bridge) external payable nonReentrant {
101: function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
133: function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
148: function maybeUpdateYield(uint256 vault, uint88 amount) private {
156: function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
169: function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L40) | [51](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L51) | [63](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L63) | [82](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L82) | [101](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L101) | [133](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L133) | [148](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L148) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L156) | [169](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
File: contracts/facets/ExitShortFacet.sol

41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
212: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41) | [87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142) | [212](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L212)

```solidity
File: contracts/facets/RedemptionFacet.sol

30: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
    {
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
310: function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
347: function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
368: function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
    {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L30) | [56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224) | [310](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L310) | [347](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L347) | [368](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L368) | [382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)
</details>

### [N-23] NatSpec: Function declarations should have descriptions

The Ethereum Natural Specification Format (NatSpec) is an integral part of the Solidity language, serving as a rich, machine-readable, language-agnostic metadata tool.

Documenting all functions, irrespective of their visibility, significantly enhances code readability and auditability.
This is especially vital in complex projects, where clear comprehension of functions, their arguments, and returns is paramount.

Specifically, the `@notice` tag should be used for explanations that anyone should understand, making it a key element in providing a clear understanding of a function's intention.
[More information in Documentation](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>4 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

30: constructor(address _dusd) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

29: constructor(address _rethBridge, address _stethBridge) {
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
File: contracts/facets/ExitShortFacet.sol

28: constructor(address _dusd) {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L28)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

11: function observe(uint32[] calldata secondsAgos)
        external
        view
        returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11)
</details>

### [N-24] Inconsistent spacing in comments

Some lines use // x and some use //x. The instances below point out the usages that don't follow the majority, within each file:

<details>
<summary><i>4 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

92: //PRIVATE FUNCTIONS
```
[92](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L92)

```solidity
File: contracts/facets/RedemptionFacet.sol

85: /// Evaluate proposed shortRecord
104: /// At this point, the shortRecord passes all checks and will be included in the slate
```
[85](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L85) | [104](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L104)

```solidity
File: contracts/libraries/LibOrders.sol

514: //@handles moving backwards only.
```
[514](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L514)
</details>

### [N-25] Critical system parameter changes should be behind a timelock

It is a good practice to give time for users to react and adjust to critical changes. A timelock provides more guarantees and reduces the level of trust required, thus decreasing risk for users. It also indicates that the project is legitimate (less risk of a malicious owner making a sandwich attack on a user).

<details>
<summary><i>7 issue instances in 3 files:</i></summary>

```solidity
File: contracts/libraries/LibOracle.sol

149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
```
[149](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L149)

```solidity
File: contracts/libraries/LibOrders.sol

474: function updateBidOrdersOnMatch(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        bool isOrderFullyFilled
    ) internal {
499: function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
783: function updateOracleAndStartingShortViaThreshold(
        address asset,
        uint256 savedPrice,
        STypes.Order memory incomingOrder,
        uint16[] memory shortHintArray
    ) internal {
803: function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {
809: function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
```
[474](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L474) | [499](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L499) | [783](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L783) | [803](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L803) | [809](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L809)

```solidity
File: contracts/libraries/LibSRUtil.sol

150: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```
[150](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L150)
</details>

### [N-26] Library Should be in a Separate File

Libraries should be declared in a separate file, variables/structs/errors/enums/constants etc should not be declared in the same file as library.
If they used in library, they should be declared in library scope.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

21: library OracleLibrary {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21)
</details>

### [N-27] Assembly blocks should have extensive comments

Large assembly blocks require extensive comments to aid understanding and code auditing. Assembly code takes more time to audit than normal Solidity code and often contains intricate details that aren't as apparent as in higher-level languages.

The identified assembly blocks in your contract appear to lack sufficient comments. Consider adding more comments explaining what each step of the assembly code does.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibBytes.sol

27: assembly {
                // mload works 32 bytes at a time
                let fullWord := mload(add(slate, offset))
                // read 20 bytes
                shorter := shr(96, fullWord) // 0x60 = 96 (256-160)
                // read 8 bytes
                shortId := and(0xff, shr(88, fullWord)) // 0x58 = 88 (96-8), mask of bytes1 = 0xff * 1
                // read 64 bytes
                CR := and(0xffffffffffffffff, shr(24, fullWord)) // 0x18 = 24 (88-64), mask of bytes8 = 0xff * 8

                fullWord := mload(add(slate, add(offset, 29))) // (29 offset)
                // read 88 bytes
                ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
                // read 88 bytes
                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
            }
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L27)
</details>

### [N-28] Function/Constructor Argument Names Not in mixedCase

Underscore before of after function argument names is a common convention in Solidity NOT a documentation requirement.

Function arguments should use mixedCase for better readability and consistency with Solidity style guidelines. 
Examples of good practice include: initialSupply, account, recipientAddress, senderAddress, newOwner. 
[More information in Documentation](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#function-argument-names)

Rule exceptions
- Allow constant variable name/symbol/decimals to be lowercase (ERC20).
- Allow `_` at the beginning of the mixedCase match for `private variables` and `unused parameters`.

<details>
<summary><i>4 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

29: constructor(address _dusd) {
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L29)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

28: constructor(address _rethBridge, address _stethBridge) {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L28)

```solidity
File: contracts/facets/ExitShortFacet.sol

27: constructor(address _dusd) {
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L27)

```solidity
File: contracts/libraries/LibOrders.sol

231: function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
        internal
        view
        returns (int256 direction)
    {
```
[231](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L231)
</details>

### [N-29] NatSpec: Function `@return` tag is missing

Natural Specification (NatSpec) comments are crucial for understanding the role of function arguments in your Solidity code.
Including `@return` tag will not only improve your code's readability but also its maintainability by clearly defining each argument's purpose.

[More information in Documentation](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>33 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit Missed @return `ethFilled, ercAmountLeft`
77: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit Missed @return `lowestSell`
340: function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
```
[77](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L77) | [340](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L340)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Missed @return ``
229: function min88(uint256 a, uint88 b) private pure returns (uint88) {
```
[229](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit Missed @return ``
40: function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
/// @audit Missed @return ``
51: function getBridges(uint256 vault) external view returns (address[] memory) {
/// @audit Missed @return `vault, bridgePointer`
156: function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
/// @audit Missed @return ``
169: function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L40) | [51](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L51) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L156) | [169](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L169)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit Missed @return `cRatio`
213: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[213](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L213)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit Missed @return ``
31: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
/// @audit Missed @return `redemptionFee`
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
```
[31](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L31) | [382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit Missed @return ``
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
/// @audit Missed @return `fee`
113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113)

```solidity
File: contracts/libraries/LibBytes.sol

/// @audit Missed @return ``
11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit Missed @return ``
19: function getOraclePrice(address asset) internal view returns (uint256) {
/// @audit Missed @return `_protocolPrice`
69: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
/// @audit Missed @return `twapPriceInEth`
131: function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
/// @audit Missed @return `creationTime`
156: function getTime(address asset) internal view returns (uint256 creationTime) {
/// @audit Missed @return `oraclePrice`
162: function getPrice(address asset) internal view returns (uint80 oraclePrice) {
/// @audit Missed @return ``
168: function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L19) | [69](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L69) | [131](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L131) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L156) | [162](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L162) | [168](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit Missed @return `timeInSeconds`
30: function getOffsetTime() internal view returns (uint32 timeInSeconds) {
/// @audit Missed @return ``
35: function convertCR(uint16 cr) internal pure returns (uint256) {
/// @audit Missed @return ``
55: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
        internal
        view
        returns (STypes.Order[] memory)
/// @audit Missed @return ``
78: function isShort(STypes.Order memory order) internal pure returns (bool) {
/// @audit Missed @return ``
362: function findPrevOfIncomingId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) internal view returns (uint16) {
/// @audit Missed @return `newO`
420: function normalizeOrderType(O o) private pure returns (O newO) {
/// @audit Missed @return `_hintId`
440: function getOrderId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        int256 direction,
        uint16 hintId,
        uint256 _newPrice,
        O orderType
    ) internal view returns (uint16 _hintId) {
/// @audit Missed @return `hintId`
826: function findOrderHintId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        MTypes.OrderHint[] memory orderHintArray
    ) internal view returns (uint16 hintId) {
/// @audit Missed @return ``
985: function min(uint256 a, uint256 b) internal pure returns (uint256) {
/// @audit Missed @return ``
989: function max(uint256 a, uint256 b) internal pure returns (uint256) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L30) | [35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L35) | [55](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L55) | [78](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L78) | [362](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L362) | [420](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L420) | [440](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L440) | [826](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L826) | [985](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L985) | [989](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L989)

```solidity
File: contracts/libraries/LibSRUtil.sol

/// @audit Missed @return `isCancelled`
49: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
/// @audit Missed @return `isCancelled`
72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
/// @audit Missed @return `recoveryViolation`
102: function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
        internal
        view
        returns (bool recoveryViolation)
```
[49](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L49) | [72](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L72) | [102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L102)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit Missed @return `amountOut`
47: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
        internal
        view
        returns (uint256 amountOut)
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47)
</details>

### [N-30] Duplicated `require()`/`revert()` checks should be refactored to a modifier or function

Duplicated require() or revert() checks should be refactored to a modifier or function.
This helps in maintaining a clean and organized codebase and saves deployment costs.

<details>
<summary><i>9 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/BridgeRouterFacet.sol

102: if (dethAmount == 0) revert Errors.ParameterIsZero();
134: if (dethAmount == 0) revert Errors.ParameterIsZero();
```
[102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L102) | [134](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L134)

```solidity
File: contracts/facets/RedemptionFacet.sol

235: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
314: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
353: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
```
[235](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L235) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L314) | [353](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L353)

```solidity
File: contracts/libraries/LibOrders.sol

859: if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
887: if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
```
[859](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L859) | [887](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L887)

```solidity
File: contracts/libraries/LibSRUtil.sol

57: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
84: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
```
[57](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L57) | [84](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L84)
</details>

### [N-31] Consider Adding Emergency-Stop Functionality

Smart contracts that hold significant value, interact with external contracts, or have complex logic should include an emergency-stop mechanism for added security. This allows pausing certain contract functionalities in case of emergencies, mitigating potential damages.

This contract seems to lack such a mechanism. Implementing an emergency stop can enhance contract security and reliability.

<details>
<summary><i>6 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L1)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L1)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L1)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L1)

```solidity
File: contracts/facets/ExitShortFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L1)

```solidity
File: contracts/facets/RedemptionFacet.sol

1: No emergency stop pattern found
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L1)
</details>

### [N-32] Non-uppercase/Constant-case Naming for `immutable` Variables

For better readability and adherence to common naming conventions, variable names declared as immutable should be written in all uppercase letters.

<details>
<summary><i>4 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

28: address private immutable dusd;
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

26: address private immutable rethBridge;
27: address private immutable stethBridge;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L26) | [27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L27)

```solidity
File: contracts/facets/ExitShortFacet.sol

26: address private immutable dusd;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L26)
</details>

### [N-33] Not using the named return variables anywhere in the function is confusing

Declaring a named return variable but returning a different value within the function is an inconsistent use of named return variables.
This practice can lead to confusion and misinterpretation of the function's intended behavior, as it contradicts the purpose of declaring named return variables, which is to enhance readability and reduce complexity in the code.

This inconsistency might signal an error in the function logic where the declared return variable is not being used as intended.
It is recommended to revisit the function's logic to ensure that the named return variables are being utilized correctly, or to adjust the return statements to reflect the actual values being returned, fostering better clarity and coherence in the code.

<details>
<summary><i>22 issue instances in 7 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit - `return _createBid(msg.sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray);` statement in functions but `ethFilled, ercAmountLeft` are declared
40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit - `return _createBid(sender, asset, price, ercAmount, C.MARKET_ORDER, orderHintArray, shortHintArray);` statement in functions but `ethFilled, ercAmountLeft` are declared
65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
    {
/// @audit - `return bidMatchAlgo(asset, incomingBid, orderHintArray, b);` statement in functions but `ethFilled, ercAmountLeft` are declared
/// @audit - `return (0, ercAmount);` statement in functions but `ethFilled, ercAmountLeft` are declared
76: function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit - `return matchIncomingBid(asset, incomingBid, matchTotal, b);` statement in functions but `ethFilled, ercAmountLeft` are declared
/// @audit - `return matchIncomingBid(asset, incomingBid, matchTotal, b);` statement in functions but `ethFilled, ercAmountLeft` are declared
/// @audit - `return matchIncomingBid(asset, incomingBid, matchTotal, b);` statement in functions but `ethFilled, ercAmountLeft` are declared
/// @audit - `return matchIncomingBid(asset, incomingBid, matchTotal, b);` statement in functions but `ethFilled, ercAmountLeft` are declared
130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit - `return (0, incomingBid.ercAmount);` statement in functions but `ethFilled, ercAmountLeft` are declared
/// @audit - `return (matchTotal.fillEth, incomingBid.ercAmount);` statement in functions but `ethFilled, ercAmountLeft` are declared
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit - `return lowestShort;` statement in functions but `lowestSell` are declared
/// @audit - `return lowestAsk;` statement in functions but `lowestSell` are declared
/// @audit - `return s.asks[asset][b.askId];` statement in functions but `lowestSell` are declared
340: function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40) | [65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65) | [76](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L76) | [130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275) | [340](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L340)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit - `return short.collateral.div(short.ercDebt);` statement in functions but `cRatio` are declared
212: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[212](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L212)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit - `return uint88(redemptionRate.mul(colRedeemed));` statement in functions but `redemptionFee` are declared
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
    {
```
[382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit - `return factorReth.div(factorSteth) - 1 ether;` statement in functions but `fee` are declared
/// @audit - `return factorSteth.div(factorReth) - 1 ether;` statement in functions but `fee` are declared
/// @audit - `return 0;` statement in functions but `fee` are declared
113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
```
[113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit - `return twapCircuitBreaker();` statement in functions but `_protocolPrice` are declared
/// @audit - `return chainlinkPriceInEth;` statement in functions but `_protocolPrice` are declared
/// @audit - `return chainlinkPriceInEth;` statement in functions but `_protocolPrice` are declared
/// @audit - `return chainlinkPriceInEth;` statement in functions but `_protocolPrice` are declared
/// @audit - `return twapPriceInEth;` statement in functions but `_protocolPrice` are declared
/// @audit - `return chainlinkPriceInEth;` statement in functions but `_protocolPrice` are declared
/// @audit - `return chainlinkPriceInEth;` statement in functions but `_protocolPrice` are declared
68: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
/// @audit - `return twapPriceNormalized.inv();` statement in functions but `twapPriceInEth` are declared
130: function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
/// @audit - `return s.bids[asset][C.HEAD].creationTime;` statement in functions but `creationTime` are declared
156: function getTime(address asset) internal view returns (uint256 creationTime) {
/// @audit - `return uint80(s.bids[asset][C.HEAD].ercAmount);` statement in functions but `oraclePrice` are declared
162: function getPrice(address asset) internal view returns (uint80 oraclePrice) {
```
[68](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L68) | [130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L130) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L156) | [162](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L162)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit - `return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)` statement in functions but `timeInSeconds` are declared
30: function getOffsetTime() internal view returns (uint32 timeInSeconds) {
/// @audit - `return C.EXACT;` statement in functions but `direction` are declared
/// @audit - `return C.PREV;` statement in functions but `direction` are declared
/// @audit - `return C.NEXT;` statement in functions but `direction` are declared
231: function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
        internal
        view
        returns (int256 direction)
    {
/// @audit - `return C.EXACT;` statement in functions but `direction` are declared
/// @audit - `return C.PREV;` statement in functions but `direction` are declared
/// @audit - `return C.NEXT;` statement in functions but `direction` are declared
260: function verifySellId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 _prevId,
        uint256 _newPrice,
        uint16 _nextId
    ) private view returns (int256 direction) {
/// @audit - `return verifySellId(orders, asset, prevId, newPrice, nextId);` statement in functions but `direction` are declared
/// @audit - `return verifyBidId(asset, prevId, newPrice, nextId);` statement in functions but `direction` are declared
402: function verifyId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 prevId,
        uint256 newPrice,
        uint16 nextId,
        O orderType
    ) internal view returns (int256 direction) {
/// @audit - `return O.LimitBid;` statement in functions but `newO` are declared
/// @audit - `return O.LimitAsk;` statement in functions but `newO` are declared
/// @audit - `return O.LimitShort;` statement in functions but `newO` are declared
420: function normalizeOrderType(O o) private pure returns (O newO) {
/// @audit - `return hintId;` statement in functions but `_hintId` are declared
440: function getOrderId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        int256 direction,
        uint16 hintId,
        uint256 _newPrice,
        O orderType
    ) internal view returns (uint16 _hintId) {
/// @audit - `return orderHint.hintId;` statement in functions but `hintId` are declared
/// @audit - `return C.HEAD;` statement in functions but `hintId` are declared
825: function findOrderHintId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        MTypes.OrderHint[] memory orderHintArray
    ) internal view returns (uint16 hintId) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L30) | [231](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L231) | [260](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L260) | [402](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L402) | [420](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L420) | [440](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L440) | [825](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L825)

```solidity
File: contracts/libraries/LibSRUtil.sol

/// @audit - `return true;` statement in functions but `isCancelled` are declared
/// @audit - `return true;` statement in functions but `isCancelled` are declared
48: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
/// @audit - `return true;` statement in functions but `recoveryViolation` are declared
101: function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
        internal
        view
        returns (bool recoveryViolation)
    {
```
[48](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L48) | [101](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L101)
</details>

### [N-34] Function Names Not in mixedCase

Function names should use mixedCase for better readability and consistency with Solidity style guidelines. 
Examples of good practice include: getBalance, transfer, verifyOwner, addMember, changeOwner. 
[More information in Documentation](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#function-names)

<details>
<summary><i>3 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

30: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L30)

```solidity
File: contracts/libraries/LibOrders.sol

34: function convertCR(uint16 cr) internal pure returns (uint256) {
```
[34](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L34)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

46: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
```
[46](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L46)
</details>

### [N-35] Insufficient Comments in Complex Functions

Complex functions spanning multiple lines should have more comments to better explain the purpose of each logic step.
Proper commenting can greatly improve the readability and maintainability of the codebase. Consider adding explicit comments
to provide insights into the function's operation.

<details>
<summary><i>15 issue instances in 8 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit function with 62 lines has only 3 comment lines
130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
/// @audit function with 34 lines has only 4 comment lines
214: function matchlowestSell(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal
    ) private {
/// @audit function with 39 lines has only 9 comment lines
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [214](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L214) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

/// @audit function with 34 lines has only 6 comment lines
35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit function with 39 lines has only 6 comment lines
240: function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {
```
[240](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit function with 42 lines has only 9 comment lines
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit function with 88 lines has only 15 comment lines
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
/// @audit function with 49 lines has only 8 comment lines
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit function with 53 lines has only 10 comment lines
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
/// @audit function with 42 lines has only 4 comment lines
144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [144](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L144)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit function with 37 lines has only 7 comment lines
18: function getOraclePrice(address asset) internal view returns (uint256) {
/// @audit function with 32 lines has only 4 comment lines
68: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L18) | [68](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L68)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit function with 57 lines has only 4 comment lines
556: function sellMatchAlgo(
        address asset,
        STypes.Order memory incomingAsk,
        MTypes.OrderHint[] memory orderHintArray,
        uint256 minAskEth
    ) internal {
/// @audit function with 44 lines has only 3 comment lines
727: function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
/// @audit function with 50 lines has only 7 comment lines
881: function cancelShort(address asset, uint16 id) internal {
```
[556](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L556) | [727](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L727) | [881](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L881)
</details>

### [N-36] NatSpec: Non-public state variable declarations should use `@dev` tags

Non-public state variables in smart contracts often have specialized purposes that may not be immediately clear to developers who did not write the original code.
Adding comments to explain the role and functionality of these variables can greatly aid in code readability and maintainability.
This is especially beneficial for future code reviews and audits.

<details>
<summary><i>4 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

28: address private immutable dusd;
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

26: address private immutable rethBridge;
27: address private immutable stethBridge;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L26) | [27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L27)

```solidity
File: contracts/facets/ExitShortFacet.sol

26: address private immutable dusd;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L26)
</details>

### [N-37] `constant`s should be defined rather than using magic numbers

Magic numbers are hardcoded numerical values used directly in the code, making it harder to read and maintain.
Consider using constants instead of magic numbers.

<details>
<summary><i>15 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit 10
56: if (shortHintArray.length > 10) revert Errors.TooManyHints();
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

/// @audit 30
118: uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);
/// @audit 30
122: uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);
```
[118](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L118) | [122](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L122)

```solidity
File: contracts/libraries/LibBytes.sol

/// @audit 51
14: require(slate.length % 51 == 0, "Invalid data length");
/// @audit 51
20: uint256 offset = i * 51 + 32;
/// @audit 32
20: uint256 offset = i * 51 + 32;
```
[14](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L14) | [20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L20) | [20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L20)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit 30
87: try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
/// @audit 100
104: if (wethBal < 100 ether) {
/// @audit 30
133: uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes);
/// @audit 100
139: if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();
/// @audit 15
169: if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
```
[87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L87) | [104](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L104) | [133](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L133) | [139](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L139) | [169](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L169)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit 15
805: if (timeDiff >= 15 minutes) {
```
[805](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L805)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit 192
39: baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
/// @audit 64
41: uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);
/// @audit 128
43: baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39) | [41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L41) | [43](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43)
</details>

### [N-38] Consider moving `msg.sender` checks to a common authorization `modifier`

Functions that are only allowed to be called by a specific actor should use a modifier to check if the caller is the specified actor (e.g., owner, specific role, etc.).
Using `require` to check `msg.sender` in the function body is less efficient and less clear.

Consider refactoring these `require` statements into a modifier for better readability, organization, and gas efficiency.

<details>
<summary><i>6 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/ShortOrdersFacet.sol

62: if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
```
[62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L62)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

54: if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
```
[54](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54)

```solidity
File: contracts/facets/RedemptionFacet.sol

86: if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
229: if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
360: if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
```
[86](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L86) | [229](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L229) | [360](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L360)

```solidity
File: contracts/libraries/LibSRUtil.sol

58: if (shorter == msg.sender) {
```
[58](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L58)
</details>

### [N-39] NatSpec: Contract declarations should have descriptions

NatSpec descriptions are crucial for self-documenting smart contracts. They provide vital information 
about the contract's purpose and behavior.

Specifically, the `@dev` or `@notice` tags are quintessential 
for detailed explanations about the contract. 

Ensure these descriptions are present directly above the contract definition braces. 
This positioning allows the compiler to correctly identify and associate the descriptions with the contract.

[Learn More about Proper NatSpec Formatting](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>12 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

19: contract BidOrdersFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L19)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

17: contract ShortOrdersFacet is Modifiers {
```
[17](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L17)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

20: contract PrimaryLiquidationFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L20)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

17: contract BridgeRouterFacet is Modifiers {
```
[17](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L17)

```solidity
File: contracts/facets/ExitShortFacet.sol

18: contract ExitShortFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L18)

```solidity
File: contracts/facets/RedemptionFacet.sol

20: contract RedemptionFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L20)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

15: library LibBridgeRouter {
```
[15](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L15)

```solidity
File: contracts/libraries/LibBytes.sol

8: library LibBytes {
```
[8](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L8)

```solidity
File: contracts/libraries/LibOracle.sol

15: library LibOracle {
```
[15](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L15)

```solidity
File: contracts/libraries/LibOrders.sol

19: library LibOrders {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L19)

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

9: interface IUniswapV3Pool {
```
[9](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L9)
</details>

### [N-40] NatSpec: Contract declarations should have `@author` tag

In the world of decentralized code, giving credit is key. NatSpec's `@author` tag acknowledges the minds behind the code.
It appears this Solidity contract omits the `@author` directive in its NatSpec annotations.
Properly attributing code to its contributors not only recognizes effort but also aids in establishing trust and credibility.
[Dive Deeper into NatSpec Guidelines](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>13 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L20)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L18)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L21)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L16)

```solidity
File: contracts/libraries/LibBytes.sol

9: library LibBytes {
```
[9](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L9)

```solidity
File: contracts/libraries/LibOracle.sol

16: library LibOracle {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L16)

```solidity
File: contracts/libraries/LibOrders.sol

20: library LibOrders {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L20)

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {
21: library OracleLibrary {
```
[10](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10) | [21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21)
</details>

### [N-41] Style guide: Non-`external`/`public` function names should begin with an underscore

In Solidity, it is suggested to use a leading underscore for non-public (private and internal) function names.
This convention helps to distinguish clearly between public/external and non-public functions, improving code clarity.
By adhering to this convention, developers can mitigate potential misinterpretation or errors, thus making the code more comprehensible and easier to maintain.

<details>
<summary><i>65 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
214: function matchlowestSell(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal
    ) private {
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [214](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L214) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

228: function min88(uint256 a, uint88 b) private pure returns (uint88) {
```
[228](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L228)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

148: function maybeUpdateYield(uint256 vault, uint88 amount) private {
```
[148](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L148)

```solidity
File: contracts/facets/ExitShortFacet.sol

212: function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```
[212](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L212)

```solidity
File: contracts/facets/RedemptionFacet.sol

30: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
    {
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
    {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L30) | [382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

21: function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
198: function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L21) | [39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113) | [144](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L144) | [198](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L198)

```solidity
File: contracts/libraries/LibBytes.sol

11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L11)

```solidity
File: contracts/libraries/LibOracle.sol

18: function getOraclePrice(address asset) internal view returns (uint256) {
68: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
116: function oracleCircuitBreaker(
        uint80 roundId,
        uint80 baseRoundId,
        int256 chainlinkPrice,
        int256 baseChainlinkPrice,
        uint256 timeStamp,
        uint256 baseTimeStamp
    ) private view {
130: function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
149: function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
156: function getTime(address asset) internal view returns (uint256 creationTime) {
162: function getPrice(address asset) internal view returns (uint80 oraclePrice) {
168: function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L18) | [68](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L68) | [116](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L116) | [130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L130) | [149](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L149) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L156) | [162](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L162) | [168](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L168)

```solidity
File: contracts/libraries/LibOrders.sol

30: function getOffsetTime() internal view returns (uint32 timeInSeconds) {
34: function convertCR(uint16 cr) internal pure returns (uint256) {
40: function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {
54: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
        internal
        view
        returns (STypes.Order[] memory)
    {
77: function isShort(STypes.Order memory order) internal pure returns (bool) {
81: function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
102: function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
128: function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {
153: function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {
173: function addOrder(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) private {
231: function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
        internal
        view
        returns (int256 direction)
    {
260: function verifySellId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 _prevId,
        uint256 _newPrice,
        uint16 _nextId
    ) private view returns (int256 direction) {
289: function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
314: function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
362: function findPrevOfIncomingId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        STypes.Order memory incomingOrder,
        uint16 hintId
    ) internal view returns (uint16) {
402: function verifyId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 prevId,
        uint256 newPrice,
        uint16 nextId,
        O orderType
    ) internal view returns (int256 direction) {
420: function normalizeOrderType(O o) private pure returns (O newO) {
440: function getOrderId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        int256 direction,
        uint16 hintId,
        uint256 _newPrice,
        O orderType
    ) internal view returns (uint16 _hintId) {
474: function updateBidOrdersOnMatch(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        uint16 id,
        bool isOrderFullyFilled
    ) internal {
499: function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
556: function sellMatchAlgo(
        address asset,
        STypes.Order memory incomingAsk,
        MTypes.OrderHint[] memory orderHintArray,
        uint256 minAskEth
    ) internal {
627: function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {
652: function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {
668: function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {
705: function matchHighestBid(
        STypes.Order memory incomingSell,
        STypes.Order memory highestBid,
        address asset,
        MTypes.Match memory matchTotal
    ) internal {
783: function updateOracleAndStartingShortViaThreshold(
        address asset,
        uint256 savedPrice,
        STypes.Order memory incomingOrder,
        uint16[] memory shortHintArray
    ) internal {
803: function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {
809: function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {
825: function findOrderHintId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        MTypes.OrderHint[] memory orderHintArray
    ) internal view returns (uint16 hintId) {
854: function cancelBid(address asset, uint16 id) internal {
867: function cancelAsk(address asset, uint16 id) internal {
881: function cancelShort(address asset, uint16 id) internal {
955: function handlePriceDiscount(address asset, uint80 price) internal {
984: function min(uint256 a, uint256 b) internal pure returns (uint256) {
988: function max(uint256 a, uint256 b) internal pure returns (uint256) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L30) | [34](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L34) | [40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L40) | [54](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L54) | [77](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L77) | [81](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L81) | [102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L102) | [128](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L128) | [153](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L153) | [173](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L173) | [231](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L231) | [260](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L260) | [289](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L289) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L314) | [362](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L362) | [402](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L402) | [420](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L420) | [440](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L440) | [474](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L474) | [499](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L499) | [556](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L556) | [627](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L627) | [652](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L652) | [668](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L668) | [705](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L705) | [783](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L783) | [803](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L803) | [809](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L809) | [825](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L825) | [854](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L854) | [867](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L867) | [881](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L881) | [955](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L955) | [984](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L984) | [988](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L988)

```solidity
File: contracts/libraries/LibSRUtil.sol

21: function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
        internal
    {
48: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
71: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
101: function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
        internal
        view
        returns (bool recoveryViolation)
    {
123: function transferShortRecord(address from, address to, uint40 tokenId) internal {
150: function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L21) | [48](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L48) | [71](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L71) | [101](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L101) | [123](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L123) | [150](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L150)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

28: function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)
        internal
        pure
        returns (uint256 quoteAmount)
    {
46: function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
        internal
        view
        returns (uint256 amountOut)
    {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L28) | [46](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L46)
</details>

### [N-42] Invalid NatSpec comment style

NatSpec comments in Solidity are meant to be recognized by tools for a variety of purposes such as documentation generation.
The correct style is to use `///` for single-line comments and `/* ... */` for multi-line comments.
Incorrect styles can cause tools to not recognize the comments as intended.

<details>
<summary><i>110 issue instances in 11 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

70: // @dev leave empty, don't need hint for market buys
73: // @dev update oracle in callers
102: // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
107: // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
113: // @dev no match, add to market if limit order
140: // @dev Handles scenario when no sells left after partial fill
291: // @dev needs to happen after updateSellOrdersOnMatch()
309: // @dev Approximates the startingShortId after bid is fully executed
334: // @dev match price is based on the order that was already on orderbook
339: // @dev If neither conditions are true, it returns an empty Order struct
344: // @dev Setting lowestSell after comparing short and ask prices
353: // @dev Handles scenario when there are no shorts
393: // @dev shortHintId should always be the first thing matched
401: // @dev Only set to true if actually moving forward
```
[70](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L70) | [73](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L73) | [102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L102) | [107](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L107) | [113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L113) | [140](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L140) | [291](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L291) | [309](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L309) | [334](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L334) | [339](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L339) | [344](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L344) | [353](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L353) | [393](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L393) | [401](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L401)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

47: // @dev create "empty" SR. Fail early.
55: // @dev minShortErc needs to be modified (bigger) when cr < 1
74: // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
84: // @dev reading spot oracle price
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L47) | [55](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L55) | [74](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L74) | [84](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L84)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

55: // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
58: // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile
67: // @dev liquidate requires more up-to-date oraclePrice
72: // @dev Can liquidate as long as CR is low enough
95: // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call
158: // @dev Provide higher price to better ensure it can fully fill the liquidation
164: // @dev Increase ethEscrowed by shorter's full collateral for forced bid
177: // @dev Max ethDebt can only be the ethEscrowed in the TAPP
186: // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP
192: // @dev virtually burning the repurchased debt
197: // @dev manually setting basefee to 1,000,000 in foundry.toml;
198: // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP
217: // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out.
```
[55](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L55) | [58](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L58) | [67](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L67) | [72](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L72) | [95](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L95) | [158](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L158) | [164](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L164) | [177](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L177) | [186](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L186) | [192](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L192) | [197](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L197) | [198](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L198) | [217](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L217)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

67: // @dev amount after deposit might be less, if bridge takes a fee
147: // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions
178: // @dev don't use mulU88 in rare case of overflow
```
[67](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L67) | [147](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L147) | [178](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L178)

```solidity
File: contracts/facets/ExitShortFacet.sol

157: // @dev Must prevent forcedBid from exitShort() matching with original shortOrder
168: // @dev if short order was cancelled, fully exit
203: // @dev Only allow partial exit if the CR is same or better than before
206: // @dev collateral already subtracted in exitShort()
```
[157](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L157) | [168](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L168) | [203](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L203) | [206](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L206)

```solidity
File: contracts/facets/RedemptionFacet.sol

36: // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition
37: // @dev Proposer can't redeem on self
72: // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
82: // @dev Setting this above _onlyValidShortRecord to allow skipping
92: // @dev Skip if proposal is not sorted correctly or if above redemption threshold
95: // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
100: // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
108: // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109: // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
127: // @dev directly write the properties of MTypes.ProposalData into bytes
145: // @dev SSTORE2 the entire proposalData after validating proposalInput
156: // @dev Calculate the dispute period
157: // @dev timeToDispute is immediate for shorts with CR <= 1.1x
261: // @dev All proposals from the incorrectIndex onward will be removed
262: // @dev Thus the proposer can only redeem a portion of their original slate
278: // @dev Update the redeemer's SSTORE2Pointer
282: // @dev this implies everything in the redeemer's proposal was incorrect
287: // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288: // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
295: // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
356: // @dev Only need to read up to the position of the SR to be claimed
372: // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already
375: // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS
381: // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated
391: // @dev Calculate Asset.ercDebt prior to proposal
393: // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
```
[36](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L36) | [37](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L37) | [72](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L72) | [82](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L82) | [92](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L92) | [95](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L95) | [100](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L100) | [108](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L108) | [109](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L109) | [127](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L127) | [145](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L145) | [156](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L156) | [157](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L157) | [261](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L261) | [262](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L262) | [278](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L278) | [282](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L282) | [287](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L287) | [288](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L288) | [295](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L295) | [356](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L356) | [372](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L372) | [375](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L375) | [381](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L381) | [391](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L391) | [393](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L393)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

74: // @dev Prevents abusing bridge for arbitrage
104: // @dev Prevents abusing bridge for arbitrage
112: // @dev Only applicable to VAULT.ONE which has mixed LST
143: // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system
```
[74](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L74) | [104](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L104) | [112](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L112) | [143](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L143)

```solidity
File: contracts/libraries/LibOracle.sol

29: // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
82: // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
146: @dev C.HEAD to marks the start/end of the linked list, so the only properties needed are id/nextId/prevId.
155: // @dev Intentionally using creationTime for oracleTime.
161: // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.
167: // @dev Allows caller to save gas since reading spot price costs ~16K
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L29) | [82](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L82) | [146](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L146) | [155](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L155) | [161](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L161) | [167](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L167)

```solidity
File: contracts/libraries/LibOrders.sol

29: // @dev in seconds
43: // @dev use the diff to get more time (2159), to prevent overflow at year 2106
172: // @dev partial addOrder
188: // @dev (ID) is exiting, [ID] is inserted
294: // @dev (ID) is exiting, [ID] is inserted
332: // @dev mark as cancelled instead of deleting the order itself
419: // @dev not used to change state, just which methods to call
507: // @dev Handles only matching one thing
508: // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block
511: // @dev Handles moving forward only
518: // @dev Handle going backward and forward
641: // @dev match price is based on the order that was already on orderbook
724: // @dev this happens at the end so fillErc isn't affected in previous calculations
760: // @dev force hint to be within 0.5% of oraclePrice
769: // @dev prevShortPrice >= oraclePrice
782: // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)
790: // @dev handle .5% deviations in either directions
802: // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough
846: // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD
899: // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId
900: // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId
905: // @dev prevents leaving behind a partially filled SR is under minShortErc
906: // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc
928: // @dev update the eth refund amount
931: // @dev virtually mint the increased debt
962: // @dev tithe is increased only if discount is greater than 1%
964: // @dev bound the new tithe amount between 25% and 100%
967: // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount
970: // @dev dethTitheMod is only set when setTithe is called.
974: // @dev change back to original tithe percent
981: // @dev exists because of ShortOrderFacet contract size
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L29) | [43](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L43) | [172](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L172) | [188](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L188) | [294](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L294) | [332](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L332) | [419](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L419) | [507](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L507) | [508](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L508) | [511](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L511) | [518](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L518) | [641](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L641) | [724](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L724) | [760](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L760) | [769](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L769) | [782](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L782) | [790](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L790) | [802](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L802) | [846](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L846) | [899](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L899) | [900](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L900) | [905](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L905) | [906](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L906) | [928](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L928) | [931](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L931) | [962](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L962) | [964](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L964) | [967](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L967) | [970](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L970) | [974](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L974) | [981](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L981)

```solidity
File: contracts/libraries/LibSRUtil.sol

37: @dev If somebody exits a short, gets liquidated, decreases their collateral before YIELD_DELAY_SECONDS duration is up,
89: // @dev The resulting SR will not have PartialFill status after cancel
133: // @dev shortOrderId is already validated in mintNFT
```
[37](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L37) | [89](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L89) | [133](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L133)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

58: // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
69: // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
```
[58](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L58) | [69](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L69)
</details>

### [N-43] Consider making contracts `Upgradeable`

Contract uses a non-upgradeable design.
Transitioning to an upgradeable contract structure is more aligned with contemporary smart contract practices.
This approach not only enhances flexibility but also allows for continuous improvement and adaptation, ensuring the contract stays relevant and robust in an ever-evolving ecosystem.

<details>
<summary><i>6 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit - Contract `BidOrdersFacet` is not upgradeable
19: contract BidOrdersFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L19)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

/// @audit - Contract `ShortOrdersFacet` is not upgradeable
17: contract ShortOrdersFacet is Modifiers {
```
[17](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L17)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit - Contract `PrimaryLiquidationFacet` is not upgradeable
20: contract PrimaryLiquidationFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L20)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit - Contract `BridgeRouterFacet` is not upgradeable
17: contract BridgeRouterFacet is Modifiers {
```
[17](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L17)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit - Contract `ExitShortFacet` is not upgradeable
18: contract ExitShortFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L18)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit - Contract `RedemptionFacet` is not upgradeable
20: contract RedemptionFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L20)
</details>

### [N-44] Style guide: Non-`external`/`public` variable names should begin with an underscore

The naming convention for non-public (private and internal) variables in Solidity recommends the use of a leading underscore.

Since `constants` can be public, to avoid confusion, they should also be prefixed with an underscore.

This practice clearly differentiates between public/external and non-public variables, enhancing code clarity and reducing the likelihood of misinterpretation or errors.
Following this convention improves code readability and maintainability.

<details>
<summary><i>4 issue instances in 3 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

28: address private immutable dusd;
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

26: address private immutable rethBridge;
27: address private immutable stethBridge;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L26) | [27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L27)

```solidity
File: contracts/facets/ExitShortFacet.sol

26: address private immutable dusd;
```
[26](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L26)
</details>

### [N-45] Style guide: Control structures do not follow the Solidity Style Guide

Following best practices for control structures in solidity code is vital for readability and maintainability. The control structures in contracts, libraries, functions, and structs should adhere to the following standards:

- Braces denoting the body should open on the same line as the declaration and close on their own line at the same indentation level as the beginning of the declaration. 
- A single space should precede the opening brace. 
- Control structures such as 'if', 'else', 'while', and 'for' should also follow these spacing and brace placement recommendations.

It is advised to revisit the [control structures](https://docs.soliditylang.org/en/latest/style-guide.html#control-structures) sections in documentation to ensure conformity with these best practices, fostering cleaner and more maintainable code.

<details>
<summary><i>52 issue instances in 10 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

/// @audit `Return or revert statement should be on new line.`
87: if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();
/// @audit `Return or revert statement should be on new line.`
90: if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();
```
[87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L87) | [90](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L90)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

/// @audit `Return or revert statement should be on new line.`
59: if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
/// @audit `Return or revert statement should be on new line.`
62: if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
```
[59](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L59) | [62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L62)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit `Return or revert statement should be on new line.`
54: if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
/// @audit `Return or revert statement should be on new line.`
56: if (shortHintArray.length > 10) revert Errors.TooManyHints();
/// @audit `Return or revert statement should be on new line.`
73: if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {
            // If CR is too high, check for recovery mode and violation to continue liquidation
            if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();
/// @audit `Return or revert statement should be on new line.`
230: if (a > type(uint88).max) revert Errors.InvalidAmount();
```
[54](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L54) | [56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56) | [73](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L73) | [230](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L230)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

/// @audit `Return or revert statement should be on new line.`
64: if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();
/// @audit `Return or revert statement should be on new line.`
83: if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();
/// @audit `Return or revert statement should be on new line.`
102: if (dethAmount == 0) revert Errors.ParameterIsZero();
/// @audit `Return or revert statement should be on new line.`
134: if (dethAmount == 0) revert Errors.ParameterIsZero();
/// @audit `Return or revert statement should be on new line.`
164: if (vault == 0) revert Errors.InvalidBridge();
```
[64](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L64) | [83](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L83) | [102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L102) | [134](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L134) | [164](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L164)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit `Return or revert statement should be on new line.`
53: if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();
/// @audit `Return or revert statement should be on new line.`
99: if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();
/// @audit `Return or revert statement should be on new line.`
103: if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();
/// @audit `Return or revert statement should be on new line.`
173: if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
/// @audit `Return or revert statement should be on new line.`
178: if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();
/// @audit `Return or revert statement should be on new line.`
188: if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
/// @audit `Return or revert statement should be on new line.`
201: if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();
/// @audit `Return or revert statement should be on new line.`
204: if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();
```
[53](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L53) | [99](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L99) | [103](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L103) | [173](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L173) | [178](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L178) | [188](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L188) | [201](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L201) | [204](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L204)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit `Return or revert statement should be on new line.`
62: if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
/// @audit `Return or revert statement should be on new line.`
67: if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
/// @audit `Return or revert statement should be on new line.`
69: if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
/// @audit `Return or revert statement should be on new line.`
73: if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
/// @audit `Return or revert statement should be on new line.`
111: if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
                if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
/// @audit `Return or revert statement should be on new line.`
141: }

        if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
/// @audit `Return or revert statement should be on new line.`
205: if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
/// @audit `Return or revert statement should be on new line.`
208: if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
/// @audit `Return or revert statement should be on new line.`
229: if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
/// @audit `Return or revert statement should be on new line.`
235: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
/// @audit `Return or revert statement should be on new line.`
236: if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
/// @audit `Return or revert statement should be on new line.`
251: if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
/// @audit `Return or revert statement should be on new line.`
314: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
/// @audit `Return or revert statement should be on new line.`
315: if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
/// @audit `Return or revert statement should be on new line.`
353: if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
/// @audit `Return or revert statement should be on new line.`
354: if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();
/// @audit `Return or revert statement should be on new line.`
360: if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
```
[62](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L62) | [67](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L67) | [69](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L69) | [73](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L73) | [111](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L111) | [141](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L141) | [205](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L205) | [208](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L208) | [229](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L229) | [235](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L235) | [236](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L236) | [251](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L251) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L314) | [315](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L315) | [353](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L353) | [354](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L354) | [360](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L360)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit `Return or revert statement should be on new line.`
25: if (address(oracle) == address(0)) revert Errors.InvalidAsset();
/// @audit `Return or revert statement should be on new line.`
60: if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
/// @audit `Return or revert statement should be on new line.`
85: } else if (priceDeviation) {
            // Check valid twap price
            try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
            {
                if (twapPrice == 0) {
                    return chainlinkPriceInEth;
/// @audit `Return or revert statement should be on new line.`
127: if (invalidFetchData) revert Errors.InvalidPrice();
/// @audit `Return or revert statement should be on new line.`
134: if (twapPrice == 0) revert Errors.InvalidTwapPrice();
/// @audit `Return or revert statement should be on new line.`
139: if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();
```
[25](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L25) | [60](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L60) | [85](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L85) | [127](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L127) | [134](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L134) | [139](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L139)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit `Return or revert statement should be on new line.`
859: if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
/// @audit `Return or revert statement should be on new line.`
887: if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();
```
[859](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L859) | [887](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L887)

```solidity
File: contracts/libraries/LibSRUtil.sol

/// @audit `Return or revert statement should be on new line.`
57: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
/// @audit `Return or revert statement should be on new line.`
84: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
/// @audit `Return or revert statement should be on new line.`
95: if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
/// @audit `Return or revert statement should be on new line.`
130: if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled();
/// @audit `Return or revert statement should be on new line.`
131: if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
```
[57](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L57) | [84](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L84) | [95](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L95) | [130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L130) | [131](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L131)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit `Return or revert statement should be on new line.`
52: if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
```
[52](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52)
</details>

### [N-46] Consider bounding input array length

The functions in question operate on arrays without established boundaries, executing function calls for each of their entries.
If these arrays become excessively long, a function might revert due to gas constraints.
To enhance user experience, consider incorporating a `require()` statement that enforces a sensible maximum array length.
This approach can avoid unnecessary computational work and ensure smoother transactions.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit `shortHintArray` is a function array parameter and `shortHintArray.length` is not bounded
743: for (uint256 i = 0; i < shortHintArray.length;) {
```
[743](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L743)
</details>

### [N-47] NatSpec: Function declarations should have `@notice` tag

In Solidity, the `@notice` tag in NatSpec comments is used to provide important explanations to end users about what a function does. 
It appears that this contract's function declarations are missing `@notice` tags in their NatSpec annotations.

The absence of `@notice` tags reduces the contract's transparency and could lead to misunderstandings about a function's purpose and behavior.
Note that the Solidity compiler treats comments beginning with `///` or `/**` as `@notice` tags if one wasn't explicitly provided.
[Learn More About NatSpec Guidelines](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>4 issue instances in 4 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

30: constructor(address _dusd) {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

29: constructor(address _rethBridge, address _stethBridge) {
```
[29](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L29)

```solidity
File: contracts/facets/ExitShortFacet.sol

28: constructor(address _dusd) {
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L28)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

11: function observe(uint32[] calldata secondsAgos)
        external
        view
        returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11)
</details>

### [N-48] Constants in comparisons should appear on the left side

Placing constants on the left side of comparison statements can help prevent accidental assignments and improve code readability.
In languages like C, placing constants on the left can protect against unintended assignments that would be treated as true conditions, leading to bugs.
Although Solidity does not have this specific issue, using the same practice can still be beneficial for code readability and consistency.

Consider placing constants on the left side of comparison operators like `==`, `!=`, `<`, `>`, `<=`, and `>=`."

<details>
<summary><i>41 issue instances in 10 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

281: if (matchTotal.fillEth == 0) {
292: if (b.dustAskId > 0) {
294: } else if (b.dustShortId > 0) {
299: if (matchTotal.shortFillEth > 0) {
```
[281](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L281) | [292](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L292) | [294](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L294) | [299](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L299)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

56: if (shortHintArray.length > 10) revert Errors.TooManyHints();
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

102: if (dethAmount == 0) revert Errors.ParameterIsZero();
109: if (dethAssessable > 0) {
111: if (withdrawalFeePct > 0) {
134: if (dethAmount == 0) revert Errors.ParameterIsZero();
164: if (vault == 0) revert Errors.InvalidBridge();
```
[102](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L102) | [109](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L109) | [111](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L111) | [134](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L134) | [164](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L164)

```solidity
File: contracts/facets/ExitShortFacet.sol

99: if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();
174: if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
188: if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
```
[99](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L99) | [174](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L174) | [188](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L188)

```solidity
File: contracts/facets/RedemptionFacet.sol

181: if (p.currentCR > 1.7 ether) {
184: } else if (p.currentCR > 1.5 ether) {
188: } else if (p.currentCR > 1.3 ether) {
192: } else if (p.currentCR > 1.2 ether) {
196: } else if (p.currentCR > 1.1 ether) {
279: if (incorrectIndex > 0) {
371: if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {
397: assert(newBaseRate > 0); // Base rate is always non-zero after redemption
```
[181](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L181) | [184](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L184) | [188](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L188) | [192](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L192) | [196](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L196) | [279](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L279) | [371](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L371) | [397](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L397)

```solidity
File: contracts/libraries/LibBytes.sol

14: require(slate.length % 51 == 0, "Invalid data length");
40: ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
42: colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
```
[14](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L14) | [40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L40) | [42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L42)

```solidity
File: contracts/libraries/LibOracle.sol

60: if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
89: if (twapPrice == 0) {
104: if (wethBal < 100 ether) {
134: if (twapPrice == 0) revert Errors.InvalidTwapPrice();
139: if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();
```
[60](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L60) | [89](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L89) | [104](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L104) | [134](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L134) | [139](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L139)

```solidity
File: contracts/libraries/LibOrders.sol

371: if (hintId == 0 || nextId == 0) {
501: if (b.matchedAskId != 0) {
505: if (b.matchedShortId != 0) {
805: if (timeDiff >= 15 minutes) {
```
[371](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L371) | [501](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L501) | [505](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L505) | [805](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L805)

```solidity
File: contracts/libraries/LibSRUtil.sol

35: if (yield > 0) {
113: if (Asset.ercDebt > 0) {
131: if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
158: if (ercDebt > 0) {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L35) | [113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L113) | [131](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L131) | [158](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L158)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

39: baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
43: baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
52: if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
65: if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39) | [43](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43) | [52](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L52) | [65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65)
</details>

### [N-49] NatSpec: Contract declarations should have `@notice` tag

The `@notice` tag in NatSpec annotations serves to provide information about the contract's functionality that is visible to end-users.
Including `@notice` comments helps to improve the contract's transparency and ease of understanding, contributing to the overall trust and credibility of the code.
[NatSpec Guidelines](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>12 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L20)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L18)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L21)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L16)

```solidity
File: contracts/libraries/LibBytes.sol

9: library LibBytes {
```
[9](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L9)

```solidity
File: contracts/libraries/LibOracle.sol

16: library LibOracle {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L16)

```solidity
File: contracts/libraries/LibOrders.sol

20: library LibOrders {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L20)

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {
```
[10](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10)
</details>

### [N-50] Long functions should be refactored into multiple, smaller, functions

Functions that span many lines can be hard to understand and maintain.
It is often beneficial to refactor long functions into multiple smaller functions.
This improves readability, makes testing easier, and can even lead to gas optimization if it eliminates the need for variables that would otherwise have to be stored in memory.

<details>
<summary><i>15 issue instances in 8 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

 /// @audit 62 lines (excluding comments)
130: function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
 /// @audit 34 lines (excluding comments)
214: function matchlowestSell(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal
    ) private {
 /// @audit 39 lines (excluding comments)
275: function matchIncomingBid(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[130](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L130) | [214](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L214) | [275](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L275)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

 /// @audit 34 lines (excluding comments)
35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

 /// @audit 39 lines (excluding comments)
240: function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {
```
[240](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240)

```solidity
File: contracts/facets/ExitShortFacet.sol

 /// @audit 42 lines (excluding comments)
142: function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```
[142](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L142)

```solidity
File: contracts/facets/RedemptionFacet.sol

 /// @audit 88 lines (excluding comments)
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
 /// @audit 49 lines (excluding comments)
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

 /// @audit 53 lines (excluding comments)
39: function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
 /// @audit 42 lines (excluding comments)
144: function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L39) | [144](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L144)

```solidity
File: contracts/libraries/LibOracle.sol

 /// @audit 37 lines (excluding comments)
18: function getOraclePrice(address asset) internal view returns (uint256) {
 /// @audit 32 lines (excluding comments)
68: function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L18) | [68](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L68)

```solidity
File: contracts/libraries/LibOrders.sol

 /// @audit 57 lines (excluding comments)
556: function sellMatchAlgo(
        address asset,
        STypes.Order memory incomingAsk,
        MTypes.OrderHint[] memory orderHintArray,
        uint256 minAskEth
    ) internal {
 /// @audit 44 lines (excluding comments)
727: function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
 /// @audit 50 lines (excluding comments)
881: function cancelShort(address asset, uint16 id) internal {
```
[556](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L556) | [727](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L727) | [881](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L881)
</details>

### [N-51] NatSpec: Contract declarations should have `@dev` tags

NatSpec comments are a critical part of Solidity's documentation system, designed to help developers and others understand the behavior and purpose of a contract.
The `@dev` tag, in particular, provides context and insight into the contract's development considerations.
A missing `@dev` comment can lead to misunderstandings about the contract, making it harder for others to contribute to or use the contract effectively.
Therefore, it's highly recommended to include `@dev` comments in the documentation to enhance code readability and maintainability.
[Refer to NatSpec Documentation](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>13 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L20)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L18)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L21)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L16)

```solidity
File: contracts/libraries/LibBytes.sol

9: library LibBytes {
```
[9](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L9)

```solidity
File: contracts/libraries/LibOracle.sol

16: library LibOracle {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L16)

```solidity
File: contracts/libraries/LibOrders.sol

20: library LibOrders {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L20)

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {
21: library OracleLibrary {
```
[10](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10) | [21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21)
</details>

### [N-52] The nonReentrant modifier should occur before all other modifiers

This is a best-practice to protect against reentrancy in other modifiers.

<details>
<summary><i>10 issue instances in 5 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

40: function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L40)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

35: function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```
[35](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L35)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47: function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, shorter, id)
        returns (uint88, uint88)
    {
```
[47](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47)

```solidity
File: contracts/facets/ExitShortFacet.sol

41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
87: function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
41: function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
```
[41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41) | [87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L87) | [41](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L41)

```solidity
File: contracts/facets/RedemptionFacet.sol

56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
310: function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
347: function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224) | [310](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L310) | [347](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L347)
</details>

### [N-53] Complex casting

Complex casting in Solidity contracts can introduce both readability issues and potential for overflows. 
Whenever multiple casts are found, consider whether the complexity is necessary.
If so, it is strongly recommended to add inline comments to explain why these casts are needed and to assure that no overflows are introduced.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

133: bytes8(uint64(p.currentCR)),
```
[133](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L133)
</details>

### [N-54] Equal `block.timestamp` Cases Not Handled

Solidity code that checks if `block.timestamp` is greater than a certain variable but fails to handle the case when `block.timestamp` is equal to the variable may lead to unintended behaviors and potential vulnerabilities.

To ensure correct and secure function execution, it's recommended to include checks for cases where `block.timestamp` equals the compared variable.

<details>
<summary><i>5 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOracle.sol

60: if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
76: bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
77: || block.timestamp > 2 hours + timeStamp;
125: bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
126: || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;
```
[60](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L60) | [76](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L76) | [77](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L77) | [125](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L125) | [126](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L126)
</details>

### [N-55] `else`-block not required

In Solidity, if an `if` block contains a `return` statement, subsequent `else` blocks become unnecessary.
This is because the `return` statement halts the execution of the function at that point, making any `else` conditions redundant.
Therefore, omitting `else` after such `if` blocks can lead to cleaner and more readable code without any change in the functionality.

<details>
<summary><i>17 issue instances in 6 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

106: if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
            // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
            b.shortHintId = b.shortId = Asset.startingShortId;
            b.oraclePrice = LibOracle.getPrice(asset);
            return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
        } else {
            // @dev no match, add to market if limit order
            LibOrders.addBid(asset, incomingBid, orderHintArray);
            return (0, ercAmount);
        }
341: if (b.shortId != C.HEAD) {
            STypes.Order storage lowestShort = s.shorts[asset][b.shortId];
            STypes.Order storage lowestAsk = s.asks[asset][b.askId];
            // @dev Setting lowestSell after comparing short and ask prices
            bool noAsks = b.askId == C.TAIL;
            bool shortPriceLessThanAskPrice = lowestShort.price < lowestAsk.price;
            if (noAsks || shortPriceLessThanAskPrice) {
                return lowestShort;
            } else {
                return lowestAsk;
            }
```
[106](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L106) | [341](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L341)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

173: if (dethTotalNew >= dethTotal) {
            // when yield is positive 1 deth = 1 eth
            return amount;
        } else {
            // negative yield means 1 deth < 1 eth
            // @dev don't use mulU88 in rare case of overflow
            return amount.mul(dethTotalNew).divU88(dethTotal);
        }
```
[173](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L173)

```solidity
File: contracts/facets/RedemptionFacet.sol

38: if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
            return false;
        } else {
            return true;
        }
```
[38](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L38)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

59: if (creditSteth < C.ROUNDING_ZERO) {
                // Valid withdraw when no STETH credits
                return amount;
            } else {
                if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    // Can withdraw RETH using STETH credit when STETH bridge is empty
                    if (creditSteth >= amount) {
                        VaultUser.bridgeCreditSteth -= amount;
                        return 0;
                    } else {
89: if (creditReth < C.ROUNDING_ZERO) {
                // Valid withdraw when no RETH credits
                return amount;
            } else {
                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    // Can withdraw STETH using RETH credit when RETH bridge is empty
                    if (creditReth >= amount) {
                        VaultUser.bridgeCreditReth -= amount;
                        return 0;
                    } else {
```
[59](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L59) | [89](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L89)

```solidity
File: contracts/libraries/LibOracle.sol

28: if (oracle == baseOracle) {
                // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
                uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;
                basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
                return basePriceInEth;
            } else {
                // prettier-ignore
                (
                    uint80 roundID,
                    int256 price,
                    /*uint256 startedAt*/
                    ,
                    uint256 timeStamp,
                    /*uint80 answeredInRound*/
                ) = oracle.latestRoundData();
                uint256 priceInEth = uint256(price).div(uint256(basePrice));
                oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp);
                return priceInEth;
            }
48: if (oracle == baseOracle) {
                return twapCircuitBreaker();
            } else {
                // prettier-ignore
                (
                    uint80 roundID,
                    int256 price,
                    /*uint256 startedAt*/
                    ,
                    uint256 timeStamp,
                    /*uint80 answeredInRound*/
                ) = oracle.latestRoundData();
                if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

                uint256 twapInv = twapCircuitBreaker();
                uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv);
                return priceInEth;
            }
83: if (invalidFetchData) {
            return twapCircuitBreaker();
        } else if (priceDeviation) {
            // Check valid twap price
            try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
            {
                if (twapPrice == 0) {
                    return chainlinkPriceInEth;
                }
98: if (chainlinkDiff <= twapDiff) {
                    return chainlinkPriceInEth;
                } else {
                    // Check valid twap liquidity
                    IERC20 weth = IERC20(C.WETH);
                    uint256 wethBal = weth.balanceOf(C.USDC_WETH);
                    if (wethBal < 100 ether) {
                        return chainlinkPriceInEth;
                    }
169: if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
            return getPrice(asset);
        } else {
            return getOraclePrice(asset);
        }
```
[28](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L28) | [48](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L48) | [83](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L83) | [98](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L98) | [169](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L169)

```solidity
File: contracts/libraries/LibOrders.sol

241: if (check1 && check2) {
            return C.EXACT;
        } else if (!check1) {
            return C.PREV;
        } else if (!check2) {
272: if (check1 && check2) {
            return C.EXACT;
        } else if (!check1) {
            return C.PREV;
        } else if (!check2) {
381: if (direction == C.EXACT) {
            return hintId;
        } else if (direction == C.NEXT) {
            return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
        } else {
412: if (orderType == O.LimitAsk || orderType == O.LimitShort) {
            return verifySellId(orders, asset, prevId, newPrice, nextId);
        } else if (orderType == O.LimitBid) {
            return verifyBidId(asset, prevId, newPrice, nextId);
        }
421: if (o == O.LimitBid || o == O.MarketBid) {
            return O.LimitBid;
        } else if (o == O.LimitAsk || o == O.MarketAsk) {
            return O.LimitAsk;
        } else if (o == O.LimitShort) {
765: if (isExactStartingShort) {
                    Asset.startingShortId = shortHintId;
                    return;
                } else if (startingShortWithinOracleRange) {
                    // @dev prevShortPrice >= oraclePrice
                    Asset.startingShortId = prevId;
                    return;
                } else if (allShortUnderOraclePrice) {
```
[241](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L241) | [272](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L272) | [381](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L381) | [412](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L412) | [421](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L421) | [765](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L765)
</details>

### [N-56] Style guide: Function ordering does not follow the Solidity style guide

Ordering helps readers identify which functions they can call and to find the constructor and fallback definitions easier.
But there are contracts in the project that do not comply with this.
Functions should be grouped according to their visibility and ordered:
- constructor 
- receive function (if exists)
- fallback function (if exists)
- external
- public
- internal
- private.

<details>
<summary><i>4 issue instances in 1 files:</i></summary>

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit `internal` function `validRedemptionSR()` declared before `external` function `proposeRedemption()`
30: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
        internal
        view
        returns (bool)
    {
56: function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
/// @audit `private` function `_claimRemainingCollateral()` declared before `internal` function `calculateRedemptionFee()`
368: function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {
382: function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
        internal
        returns (uint88 redemptionFee)
    {
```
[30](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L30) | [56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56) | [368](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L368) | [382](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L382)
</details>

### [N-57] Style guide: Lines are too long

It is generally recommended that lines in the source code should not exceed 80-120 characters.
Multiline output parameters and return statements should follow the same style recommended for wrapping long lines found in the Maximum Line Length section.

<details>
<summary><i>63 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

65: function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
106: if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
108: LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
190: if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
317: } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
332: emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
340: function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
384: Imagine the user passes in [ID5] as the hint, which corresponds to a price within 1% of the oracle, thus making it valid
```
[65](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L65) | [106](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L106) | [108](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L108) | [190](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L190) | [317](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L317) | [332](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L332) | [340](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L340) | [384](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L384)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

56: p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
76: LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
```
[56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L56) | [76](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L76)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

42: * @param shortHintArray Array of hintId for the id to start matching against shorts since you can't match a short < oracle price
75: if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();
140: m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
151: * @param shortHintArray Array of hintId for the id to start matching against shorts since you can't match a short < oracle price
180: m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)
188: IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
246: LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt);
```
[42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L42) | [75](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L75) | [140](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L140) | [151](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L151) | [180](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180) | [188](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L188) | [246](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L246)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

147: // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions
```
[147](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L147)

```solidity
File: contracts/facets/ExitShortFacet.sol

139: * @param shortHintArray Array of hintId for the id to start matching against shorts since you can't match a short < oracle price
187: IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
```
[139](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L139) | [187](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L187)

```solidity
File: contracts/facets/RedemptionFacet.sol

31: function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
95: // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
112: if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
138: LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
183: redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
224: function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
259: if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
266: STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
290: LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
```
[31](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L31) | [95](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L95) | [112](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L112) | [138](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L138) | [183](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L183) | [224](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L224) | [259](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L259) | [266](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L266) | [290](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L290)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

113: function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
122: uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);
```
[113](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L113) | [122](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L122)

```solidity
File: contracts/libraries/LibBytes.sol

11: function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
42: colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
```
[11](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L11) | [42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L42)

```solidity
File: contracts/libraries/LibOracle.sol

27: try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
31: basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
79: chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
87: try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
95: uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
```
[27](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L27) | [31](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L31) | [79](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L79) | [87](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L87) | [95](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L95)

```solidity
File: contracts/libraries/LibOrders.sol

40: function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {
153: function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {
218: emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount);
289: function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
314: function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
467: * @dev Instead of canceling each one, just wait till the last match and only swap prevId/nextId there, since the rest are gone
628: function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {
668: function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {
718: matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR));
752: if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
761: bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
782: // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)
802: // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough
911: uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));
954: // Approximates the match price compared to the oracle price and accounts for any discount by increasing dethTithePercent
```
[40](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L40) | [153](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L153) | [218](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L218) | [289](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L289) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L314) | [467](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L467) | [628](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L628) | [668](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L668) | [718](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L718) | [752](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L752) | [761](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L761) | [782](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L782) | [802](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L802) | [911](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L911) | [954](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L954)

```solidity
File: contracts/libraries/LibSRUtil.sol

22: function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
37: @dev If somebody exits a short, gets liquidated, decreases their collateral before YIELD_DELAY_SECONDS duration is up,
49: function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
57: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
72: function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
84: if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
```
[22](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L22) | [37](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L37) | [49](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L49) | [57](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L57) | [72](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L72) | [84](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L84)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

4: // https://github.com/Uniswap/v3-periphery/blob/b325bb0905d922ae61fcc7df85ee802e8df5e96c/contracts/libraries/OracleLibrary.sol
39: baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
43: baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
58: // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
```
[4](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L4) | [39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L39) | [43](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L43) | [58](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L58)
</details>

### [N-58] Style guide: Extraneous whitespace

See the [whitespace](https://docs.soliditylang.org/en/v0.8.24/style-guide.html#whitespace-in-expressions) section of the Solidity Style Guide

<details>
<summary><i>13 issue instances in 5 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit `More than one space around an assignment or other operator to align with another`
187: (m.ethFilled, ercAmountLeft) =
            IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
```
[187](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L187)

```solidity
File: contracts/facets/ExitShortFacet.sol

/// @audit `More than one space around an assignment or other operator to align with another`
186: (e.ethFilled, e.ercAmountLeft) =
            IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
```
[186](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L186)

```solidity
File: contracts/facets/RedemptionFacet.sol

/// @audit `More than one space around an assignment or other operator to align with another`
186: redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
/// @audit `More than one space around an assignment or other operator to align with another`
190: redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
/// @audit `More than one space around an assignment or other operator to align with another`
194: redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
/// @audit `More than one space around an assignment or other operator to align with another`
239: MTypes.ProposalData[] memory decodedProposalData =
            LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
/// @audit `More than one space around an assignment or other operator to align with another`
317: MTypes.ProposalData[] memory decodedProposalData =
            LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
/// @audit `More than one space around an assignment or other operator to align with another`
357: MTypes.ProposalData[] memory decodedProposalData =
            LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
```
[186](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L186) | [190](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L190) | [194](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L194) | [239](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L239) | [317](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L317) | [357](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L357)

```solidity
File: contracts/libraries/LibOracle.sol

/// @audit `Immediately before a comma`
39: ,
/// @audit `Immediately before a comma`
56: ,
/// @audit `More than one space around an assignment or other operator to align with another`
78: uint256 chainlinkDiff =
            chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
```
[39](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L39) | [56](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L56) | [78](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L78)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

/// @audit `More than one space around an assignment or other operator to align with another`
38: quoteAmount =
                baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);
/// @audit `More than one space around an assignment or other operator to align with another`
42: quoteAmount =
                baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
```
[38](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L38) | [42](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L42)
</details>

### [N-59] Contract/Libraries Names Do Not Match Their Filenames

According to the Solidity Style Guide, contract names should match their filenames. 
Mismatching contract names and filenames can lead to confusion and make the code harder to maintain and review.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

21: library OracleLibrary {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21)
</details>

### [N-60] `if`-statement can be converted to a ternary

The ternary operator provides a shorthand way to write if / else statements.
It can improve readability and reduce the number of lines of code.
Traditional `if / else` statements, particularly those spanning only a one lines, could potentially be refactored using the ternary operator.

<details>
<summary><i>8 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

317: } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
                Asset.startingShortId = b.prevShortId;
            } else {
                if (b.isMovingFwd) {
                    Asset.startingShortId = currentShort.nextId;
                } else {
```
[317](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L317)

```solidity
File: contracts/libraries/LibOrders.sol

90: if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.bids, asset, orderHintArray);
        }
111: if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.asks, asset, orderHintArray);
        }
132: if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) {
            hintId = C.HEAD;
        } else {
            hintId = findOrderHintId(s.shorts, asset, orderHintArray);
        }
196: if (prevCanceledID != C.HEAD) {
                orders[asset][C.HEAD].prevId = prevCanceledID;
            } else {
                // BEFORE: HEAD <- (ID) <- HEAD <-> .. <-> PREV <----------> NEXT
                // AFTER1: HEAD <--------- HEAD <-> .. <-> PREV <-> [ID] <-> NEXT
                orders[asset][C.HEAD].prevId = C.HEAD;
            }
339: if (prevHEAD != C.HEAD) {
            orders[asset][id].prevId = prevHEAD;
        } else {
            // if this is the first ID cancelled
            // HEAD.prevId needs to be HEAD
            // and one of the cancelled id.prevID should point to HEAD
            // BEFORE: HEAD <--------- HEAD <-> ... [ID]
            // AFTER1: HEAD <- [ID] <- HEAD <-> ...
            orders[asset][id].prevId = C.HEAD;
        }
791: if (incomingOrder.price >= savedPrice) {
            orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
        } else {
            orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
        }
944: if (prevPrice >= savedPrice) {
                Asset.startingShortId = shortOrder.prevId;
            } else {
                Asset.startingShortId = shortOrder.nextId;
            }
```
[90](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L90) | [111](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L111) | [132](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L132) | [196](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L196) | [339](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L339) | [791](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L791) | [944](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L944)
</details>

### [N-61] Consider using named mappings

As of Solidity version 0.8.18, it is possible to use named mappings to clarify the purpose of each mapping in the code. 
It is recommended to use this feature for better code readability and maintainability.

More information: [Solidity 0.8.18 Release Announcement](https://blog.soliditylang.org/2023/02/01/solidity-0.8.18-release-announcement/)

<details>
<summary><i>12 issue instances in 1 files:</i></summary>

```solidity
File: contracts/libraries/LibOrders.sol

55: function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
174: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
261: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
289: function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
314: function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {
321: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
363: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
403: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
441: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
475: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
533: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
827: mapping(address => mapping(uint16 => STypes.Order)) storage orders,
```
[55](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L55) | [174](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L174) | [261](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L261) | [289](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L289) | [314](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L314) | [321](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L321) | [363](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L363) | [403](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L403) | [441](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L441) | [475](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L475) | [533](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L533) | [827](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L827)
</details>

### [N-62] Setters should prevent re-setting of the same value

Setter functions should include a condition to check if the new value being assigned is different from the current value. This practice prevents redundant state changes and the emission of unnecessary events, ensuring that changes only occur when actual updates to the values are made.

This not only helps to maintain the integrity of the contract's state but also keeps the event logs cleaner and more meaningful by avoiding the recording of identical consecutive values. Such an approach can improve the clarity and efficiency of debugging and data tracking processes.

<details>
<summary><i>10 issue instances in 2 files:</i></summary>

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

/// @audit Missing `id` check before state change
126: LibShortRecord.updateErcDebt(asset, shorter, id);
```
[126](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L126)

```solidity
File: contracts/libraries/LibOrders.sol

/// @audit Missing `b` check before state change
502: _updateOrders(s.asks, asset, C.HEAD, b.matchedAskId);
/// @audit Missing `b` check before state change
509: _updateOrders(s.shorts, asset, b.prevShortId, b.matchedShortId);
/// @audit Missing `b` check before state change
512: _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, b.matchedShortId);
/// @audit Missing `b` check before state change
515: _updateOrders(s.shorts, asset, b.prevShortId, b.shortHintId);
/// @audit Missing `b` check before state change
519: _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, id);
/// @audit Missing `shortHintArray` check before state change
744: shortHintId = shortHintArray[i];
/// @audit Missing `shortHintArray` check before state change
798: _updateOracleAndStartingShort(asset, shortHintArray);
/// @audit Missing `asset` check before state change
804: uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset);
/// @audit Missing `shortHintArray` check before state change
806: _updateOracleAndStartingShort(asset, shortHintArray);
```
[502](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L502) | [509](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L509) | [512](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L512) | [515](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L515) | [519](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L519) | [744](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L744) | [798](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L798) | [804](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L804) | [806](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L806)
</details>

### [N-63] NatSpec: Contract declarations should have `@title` tags

NatSpec comments offer an intuitive way to understand the core purpose of a smart contract. 
Especially, the `@title` tag serves as a brief descriptor of the contract's function or intent.
In this Solidity file, the `@title` directive seems to be overlooked.
Incorporating the `@title` tag gives readers a concise overview, thus enhancing clarity.
[Refer to NatSpec Documentation](https://docs.soliditylang.org/en/develop/natspec-format.html)

<details>
<summary><i>12 issue instances in 12 files:</i></summary>

```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BidOrdersFacet.sol#L20)

```solidity
File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ShortOrdersFacet.sol#L18)

```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21)

```solidity
File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/BridgeRouterFacet.sol#L18)

```solidity
File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {
```
[19](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/ExitShortFacet.sol#L19)

```solidity
File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {
```
[21](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L21)

```solidity
File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBridgeRouter.sol#L16)

```solidity
File: contracts/libraries/LibBytes.sol

9: library LibBytes {
```
[9](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibBytes.sol#L9)

```solidity
File: contracts/libraries/LibOracle.sol

16: library LibOracle {
```
[16](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOracle.sol#L16)

```solidity
File: contracts/libraries/LibOrders.sol

20: library LibOrders {
```
[20](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L20)

```solidity
File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {
```
[18](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/LibSRUtil.sol#L18)

```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {
```
[10](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10)
</details>

### [N-64] Contracts should have full test coverage

It's recommended to have full test coverage for all contracts.
While 100% code coverage does not guarantee absence of bugs, it can catch simple bugs and reduce regressions during code modifications.
Moreover, to achieve full coverage, authors often have to refactor their code into more modular components, each testable separately.
This leads to lower interdependencies, and results in code that is easier to understand and audit.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: app/norace/2024-03-dittoeth

1: All files
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/app/norace/2024-03-dittoeth#L1)
</details>

### [N-65] Large or complicated code bases should implement invariant tests

Large or complex code bases should include invariant fuzzing tests, such as those provided by Echidna.
These tests require the identification of invariants that should not be violated under any circumstances, with the fuzzer testing various inputs and function calls to ensure these invariants always hold.
This is especially important for code with a lot of inline-assembly, complicated math, or complex interactions between contracts. Despite having 100% code coverage, bugs can still occur due to the order of operations a user performs.
Extensive and well-written invariant tests can significantly reduce this testing gap.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: app/norace/2024-03-dittoeth

1: All files
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/app/norace/2024-03-dittoeth#L1)
</details>

### [N-66] Implement Formal Verification Proofs to Improve Security

Formal verification offers a mathematical proof confirming that your code operates as intended and is devoid of edge cases 
that may lead to unintended behavior. By leveraging this rigorous audit technique, you not only enhance the robustness 
of your code but also strengthen the trust of stakeholders in the safety of your contract.

<details>
<summary><i>1 issue instances in 1 files:</i></summary>

```solidity
File: app/norace/2024-03-dittoeth

1: All files
```
[1](https://github.com/code-423n4/norace/2024-03-dittoeth/blob/main/app/norace/2024-03-dittoeth#L1)
</details>
