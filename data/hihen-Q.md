# QA Report

Issues in 4naly3er-report have been excluded.

## Summary

### Low Issues

Total **70 instances** over **11 issues**:

|ID|Issue|Instances|
|:--:|:---|:--:|
| [[L-01]](#l-01-missing-price-checks-for-chainlink-oracle) | Missing price checks for Chainlink oracle | 3 |
| [[L-02]](#l-02-multiplication-on-the-result-of-a-division) | Multiplication on the result of a division | 3 |
| [[L-03]](#l-03-events-may-be-emitted-out-of-order-due-to-reentrancy) | Events may be emitted out of order due to reentrancy | 7 |
| [[L-04]](#l-04-missing-zero-address-check-in-constructor) | Missing zero address check in constructor | 4 |
| [[L-05]](#l-05-unsafe-conversion-from-unsigned-to-signed-values) | Unsafe conversion from unsigned to signed values | 2 |
| [[L-06]](#l-06-vulnerable-versions-of-packages-are-being-used) | Vulnerable versions of packages are being used | 3 |
| [[L-07]](#l-07-constructor--initialization-function-lacks-parameter-validation) | Constructor / initialization function lacks parameter validation | 4 |
| [[L-08]](#l-08-critical-functions-should-be-controlled-by-time-locks) | Critical functions should be controlled by time locks | 1 |
| [[L-09]](#l-09-external-function-calls-within-loops) | External function calls within loops | 8 |
| [[L-10]](#l-10-use-descriptive-constant-instead-of-0-as-a-parameter) | Use descriptive constant instead of 0 as a parameter | 5 |
| [[L-11]](#l-11-code-does-not-follow-the-best-practice-of-check-effects-interaction) | Code does not follow the best practice of check-effects-interaction | 30 |

### Non Critical Issues

Total **787 instances** over **54 issues**:

|ID|Issue|Instances|
|:--:|:---|:--:|
| [[N-01]](#n-01-names-of-privateinternal-functions-should-be-prefixed-with-an-underscore) | Names of `private`/`internal` functions should be prefixed with an underscore | 65 |
| [[N-02]](#n-02-names-of-privateinternal-state-variables-should-be-prefixed-with-an-underscore) | Names of `private`/`internal` state variables should be prefixed with an underscore | 4 |
| [[N-03]](#n-03-the-nonreentrant-modifier-should-occur-before-all-other-modifiers) | The `nonReentrant` `modifier` should occur before all other modifiers | 10 |
| [[N-04]](#n-04-custom-errors-should-be-used-rather-than-revertrequire) | Custom errors should be used rather than `revert()`/`require()` | 1 |
| [[N-05]](#n-05-consider-splitting-complex-checks-into-multiple-steps) | Consider splitting complex checks into multiple steps | 5 |
| [[N-06]](#n-06-complex-casting) | Complex casting | 1 |
| [[N-07]](#n-07-complex-math-should-be-split-into-multiple-steps) | Complex math should be split into multiple steps | 11 |
| [[N-08]](#n-08-consider-adding-a-blockdeny-list) | Consider adding a block/deny-list | 6 |
| [[N-09]](#n-09-constantsimmutables-redefined-elsewhere) | Constants/Immutables redefined elsewhere | 2 |
| [[N-10]](#n-10-convert-simple-if-statements-to-ternary-expressions) | Convert simple `if`-statements to ternary expressions | 8 |
| [[N-11]](#n-11-contracts-should-each-be-defined-in-separate-files) | Contracts should each be defined in separate files | 1 |
| [[N-12]](#n-12-contract-name-does-not-match-its-filename) | Contract name does not match its filename | 1 |
| [[N-13]](#n-13-upper_case-names-should-be-reserved-for-constantimmutable-variables) | UPPER_CASE names should be reserved for `constant`/`immutable` variables | 4 |
| [[N-14]](#n-14-contract-timekeeping-will-break-earlier-than-the-ethereum-network-itself-will-stop-working) | Contract timekeeping will break earlier than the Ethereum network itself will stop working | 1 |
| [[N-15]](#n-15-consider-emitting-an-event-at-the-end-of-the-constructor) | Consider emitting an event at the end of the constructor | 3 |
| [[N-16]](#n-16-events-are-emitted-without-the-sender-information) | Events are emitted without the sender information | 1 |
| [[N-17]](#n-17-imports-could-be-organized-more-systematically) | Imports could be organized more systematically | 6 |
| [[N-18]](#n-18-invalid-natspec-comment-style) | Invalid NatSpec comment style | 111 |
| [[N-19]](#n-19-openzeppelincontracts-should-be-upgraded-to-a-newer-version) | @openzeppelin/contracts should be upgraded to a newer version | 1 |
| [[N-20]](#n-20-lib-prbmath-should-be-upgraded-to-a-newer-version) | Lib @prb/math should be upgraded to a newer version | 1 |
| [[N-21]](#n-21-functions-should-be-named-in-mixedcase-style) | Functions should be named in mixedCase style | 3 |
| [[N-22]](#n-22-variable-names-for-immutables-should-use-upper_case_with_underscores) | Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES | 4 |
| [[N-23]](#n-23-consider-adding-validation-of-user-inputs) | Consider adding validation of user inputs | 7 |
| [[N-24]](#n-24-constants-should-be-put-on-the-left-side-of-comparisons) | Constants should be put on the left side of comparisons | 34 |
| [[N-25]](#n-25-libraries-should-be-defined-in-separate-files) | Libraries should be defined in separate files | 1 |
| [[N-26]](#n-26-else-block-not-required) | `else`-block not required | 27 |
| [[N-27]](#n-27-high-cyclomatic-complexity) | High cyclomatic complexity | 2 |
| [[N-28]](#n-28-typos) | Typos | 2 |
| [[N-29]](#n-29-consider-bounding-input-array-length) | Consider bounding input array length | 2 |
| [[N-30]](#n-30-unnecessary-casting) | Unnecessary casting | 1 |
| [[N-31]](#n-31-unused-contract-variables) | Unused contract variables | 2 |
| [[N-32]](#n-32-unused-import) | Unused import | 60 |
| [[N-33]](#n-33-unused-local-variables) | Unused local variables | 1 |
| [[N-34]](#n-34-unused-named-return) | Unused named return | 27 |
| [[N-35]](#n-35-consider-using-delete-rather-than-assigning-zero-to-clear-values) | Consider using `delete` rather than assigning zero to clear values | 17 |
| [[N-36]](#n-36-use-the-latest-solidity-version) | Use the latest Solidity version | 12 |
| [[N-37]](#n-37-consider-using-named-function-arguments) | Consider using named function arguments | 2 |
| [[N-38]](#n-38-named-returns-are-recommended) | Named returns are recommended | 17 |
| [[N-39]](#n-39-consider-using-the-using-for-syntax) | Consider using the `using`-`for` syntax | 197 |
| [[N-40]](#n-40-use-a-struct-to-encapsulate-multiple-function-parameters) | Use a struct to encapsulate multiple function parameters | 7 |
| [[N-41]](#n-41-returning-a-struct-instead-of-a-bunch-of-variables-is-better) | Returning a struct instead of a bunch of variables is better | 8 |
| [[N-42]](#n-42-contract-variables-should-have-comments) | Contract variables should have comments | 4 |
| [[N-43]](#n-43-function-state-mutability-can-be-restricted-to-view) | Function state mutability can be restricted to view | 2 |
| [[N-44]](#n-44-inconsistent-spacing-in-comments) | Inconsistent spacing in comments | 2 |
| [[N-45]](#n-45-missing-event-for-critical-changes) | Missing event for critical changes | 13 |
| [[N-46]](#n-46-duplicated-requirerevert-checks-should-be-refactored) | Duplicated `require()`/`revert()` checks should be refactored | 9 |
| [[N-47]](#n-47-consider-adding-emergency-stop-functionality) | Consider adding emergency-stop functionality | 6 |
| [[N-48]](#n-48-use-the-modern-upgradeable-contract-paradigm) | Use the Modern Upgradeable Contract Paradigm | 6 |
| [[N-49]](#n-49-large-or-complicated-code-bases-should-implement-invariant-tests) | Large or complicated code bases should implement invariant tests | 1 |
| [[N-50]](#n-50-the-default-value-is-manually-set-when-it-is-declared) | The default value is manually set when it is declared | 6 |
| [[N-51]](#n-51-contracts-should-have-all-publicexternal-functions-exposed-by-interfaces) | Contracts should have all `public`/`external` functions exposed by `interface`s | 6 |
| [[N-52]](#n-52-top-level-declarations-should-be-separated-by-at-least-two-lines) | Top-level declarations should be separated by at least two lines | 39 |
| [[N-53]](#n-53-consider-adding-formal-verification-proofs) | Consider adding formal verification proofs | 12 |
| [[N-54]](#n-54-use-scopes-sparingly) | Use scopes sparingly | 5 |

## Low Issues

### [L-01] Missing price checks for Chainlink oracle

`latestRoundData` may return invalid data, and there aren't any checks to ensure that this doesn't happen.
This can be caused by any issues with Chainlink, such as oracle consensus problems or chain congestion, which may result in this contract relying on outdated data.'_filePath,

There are 3 instances:

- *LibOracle.sol* ( [27-27](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L27-L27), [42-42](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L42-L42), [59-59](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L59-L59) ):

```solidity
/// @audit missing price check, which could be equal to 0
27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {

/// @audit missing price check, which could be equal to 0
42:                 ) = oracle.latestRoundData();

/// @audit missing price check, which could be equal to 0
59:                 ) = oracle.latestRoundData();
```

### [L-02] Multiplication on the result of a division

Dividing a number by another often results in a loss of precision. Multiplying the result by another number increases the loss of precision, often significantly.
For example: `x*(y/z)` should be re-written as `(x*z)/y`.

There are 3 instances:

- *LibOracle.sol* ( [93-93](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L93-L93), [141-141](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L141-L141) ):

```solidity
93:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);

141:         uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
```

- *LibOrders.sol* ( [47-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L47-L47) ):

```solidity
47:             uint88 shares = eth * (timeTillMatch / 1 days);
```

### [L-03] Events may be emitted out of order due to reentrancy

Ensure that events follow the best practice of check-effects-interaction, and are emitted before external calls.

<details>
<summary>There are 7 instances (click to show):</summary>

- *BridgeRouterFacet.sol* ( [72-72](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L72-L72), [90-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L90-L90), [122-122](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L122-L122), [143-143](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L143-L143) ):

```solidity
/// @audit deposit() is called prior to this emission in deposit()
72:         emit Events.Deposit(bridge, msg.sender, dethAmount);

/// @audit depositEth() is called prior to this emission in depositEth()
90:         emit Events.DepositEth(bridge, msg.sender, dethAmount);

/// @audit withdraw() is called prior to this emission in withdraw()
122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);

/// @audit withdraw() is called prior to this emission in withdrawTapp()
143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
```

- *ExitShortFacet.sol* ( [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L75-L75), [210-210](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L210-L210) ):

```solidity
/// @audit burnMsgSenderDebt() is called prior to this emission in exitShortWallet(), which will call `burnFrom()`
75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);

/// @audit createForcedBid() is called prior to this emission in exitShort()
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
```

- *PrimaryLiquidationFacet.sol* ( [87-87](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L87-L87) ):

```solidity
/// @audit _performForcedBid() is called prior to this emission in liquidate(), which will call `createForcedBid()`
87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
```

</details>

### [L-04] Missing zero address check in constructor

Constructors often take address parameters to initialize important components of a contract, such as owner or linked contracts. However, without a checking, there's a risk that an address parameter could be mistakenly set to the zero address (0x0). This could be due to an error or oversight during contract deployment. A zero address in a crucial role can cause serious issues, as it cannot perform actions like a normal address, and any funds sent to it will be irretrievable. It's therefore crucial to include a zero address check in constructors to prevent such potential problems. If a zero address is detected, the constructor should revert the transaction.

There are 4 instances:

- *BridgeRouterFacet.sol* ( [29-29](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L29-L29) ):

```solidity
/// @audit `_rethBridge not checked`
/// @audit `_stethBridge not checked`
29:     constructor(address _rethBridge, address _stethBridge) {
```

- *ExitShortFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L28-L28) ):

```solidity
/// @audit `_dusd not checked`
28:     constructor(address _dusd) {
```

- *PrimaryLiquidationFacet.sol* ( [30-30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L30-L30) ):

```solidity
/// @audit `_dusd not checked`
30:     constructor(address _dusd) {
```

### [L-05] Unsafe conversion from unsigned to signed values

The `int` type in Solidity uses the [two's complement system](https://en.wikipedia.org/wiki/Two%27s_complement), so it is possible to accidentally overflow a very large `uint` to an `int`, even if they share the same number of bytes (e.g. a `uint256 number > type(uint128).max` will overflow a `int256` cast).

Consider using the [SafeCast](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeCast.sol) library to prevent any overflows.

There are 2 instances:

- *UniswapOracleLibrary.sol* ( [62-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L62-L62), [65-65](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L65-L65) ):

```solidity
/// @audit uint -> int
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));

/// @audit uint -> int
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
```

### [L-06] Vulnerable versions of packages are being used

This project is using specific package versions which are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities.
- [CVE-2023-49798](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-49798) - **HIGH** - (`@openzeppelin/contracts 4.9.4`): OpenZeppelin Contracts is a library for smart contract development. A merge issue when porting the 5.0.1 patch to the 4.9 branch caused a line duplication. In the version of `Multicall.sol` released in `@openzeppelin/contracts@4.9.4` and `@openzeppelin/contracts-upgradeable@4.9.4`, all subcalls are executed twice. Concretely, this exposes a user to unintentionally duplicate operations like asset transfers. The duplicated delegatecall was removed in version 4.9.5. The 4.9.4 version is marked as deprecated. Users are advised to upgrade. There are no known workarounds for this issue.

- [CVE-2023-40014](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-40014) - **MEDIUM** - (`@openzeppelin/contracts >=4.0.0 <4.9.3`): OpenZeppelin Contracts is a library for secure smart contract development. Starting in version 4.0.0 and prior to version 4.9.3, contracts using `ERC2771Context` along with a custom trusted forwarder may see `_msgSender` return `address(0)` in calls that originate from the forwarder with calldata shorter than 20 bytes. This combination of circumstances does not appear to be common, in particular it is not the case for `MinimalForwarder` from OpenZeppelin Contracts, or any deployed forwarder the team is aware of, given that the signer address is appended to all calls that originate from these forwarders. The problem has been patched in v4.9.3.

- [CVE-2023-34459](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-34459) - **MEDIUM** - (`@openzeppelin/contracts >=4.7.0 <4.9.2`): OpenZeppelin Contracts is a library for smart contract development. Starting in version 4.7.0 and prior to version 4.9.2, when the `verifyMultiProof`, `verifyMultiProofCalldata`, `procesprocessMultiProof`, or `processMultiProofCalldat` functions are in use, it is possible to construct merkle trees that allow forging a valid multiproof for an arbitrary set of leaves. A contract may be vulnerable if it uses multiproofs for verification and the merkle tree that is processed includes a node with value 0 at depth 1 (just under the root). This could happen inadvertedly for balanced trees with 3 leaves or less, if the leaves are not hashed. This could happen deliberately if a malicious tree builder includes such a node in the tree. A contract is not vulnerable if it uses single-leaf proving (`verify`, `verifyCalldata`, `processProof`, or `processProofCalldata`), or if it uses multiproofs with a known tree that has hashed leaves. Standard merkle trees produced or validated with the @openzeppelin/merkle-tree library are safe. The problem has been patched in version 4.9.2. Some workarounds are available. For those using multiproofs: When constructing merkle trees hash the leaves and do not insert empty nodes in your trees. Using the @openzeppelin/merkle-tree package eliminates this issue. Do not accept user-provided merkle roots without reconstructing at least the first level of the tree. Verify the merkle tree structure by reconstructing it from the leaves.

There are 3 instances:

- Global finding

### [L-07] Constructor / initialization function lacks parameter validation

Constructors and initialization functions play a critical role in contracts by setting important initial states when the contract is first deployed before the system starts. The parameters passed to the constructor and initialization functions directly affect the behavior of the contract / protocol. If incorrect parameters are provided, the system may fail to run, behave abnormally, be unstable, or lack security. Therefore, it's crucial to carefully check each parameter in the constructor and initialization functions. If an exception is found, the transaction should be rolled back.

There are 4 instances:

- *BridgeRouterFacet.sol* ( [29-29](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L29-L29) ):

```solidity
/// @audit `_rethBridge`
/// @audit `_stethBridge`
29:     constructor(address _rethBridge, address _stethBridge) {
```

- *ExitShortFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L28-L28) ):

```solidity
/// @audit `_dusd`
28:     constructor(address _dusd) {
```

- *PrimaryLiquidationFacet.sol* ( [30-30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L30-L30) ):

```solidity
/// @audit `_dusd`
30:     constructor(address _dusd) {
```

### [L-08] Critical functions should be controlled by time locks

It is a good practice to give time for users to react and adjust to critical changes. A timelock provides more guarantees and reduces the level of trust required, thus decreasing risk for users. It also indicates that the project is legitimate (less risk of a malicious owner making a sandwich attack on a user).

There is 1 instance:

- *PrimaryLiquidationFacet.sol* ( [122-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L122-L124) ):

```solidity
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
```

### [L-09] External function calls within loops

Calling external functions within loops can easily result in insufficient gas. This greatly increases the likelihood of transaction failures, DOS attacks, and other unexpected actions. It is recommended to limit the number of loops within loops that call external functions, and to limit the gas line for each external call.

<details>
<summary>There are 8 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [145-145](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L145-L145), [153-153](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L153-L153), [195-195](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L195-L195), [201-201](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L201-L201) ):

```solidity
/// @audit Calling `matchIncomingBid()` within `while` loop, it will trigger an external call - `_cancelAsk()`
145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);

/// @audit Calling `matchIncomingBid()` within `while` loop, it will trigger an external call - `_cancelAsk()`
153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

/// @audit Calling `matchIncomingBid()` within `while` loop, it will trigger an external call - `_cancelAsk()`
195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

/// @audit Calling `matchIncomingBid()` within `while` loop, it will trigger an external call - `_cancelAsk()`
201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
```

- *LibOrders.sol* ( [579-579](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L579-L579), [591-591](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L591-L591), [613-613](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L613-L613), [618-618](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L618-L618) ):

```solidity
/// @audit Calling `matchIncomingSell()` within `while` loop, it will trigger an external call - `_updateYieldDiamond()`
579:                     matchIncomingSell(asset, incomingAsk, matchTotal);

/// @audit Calling `matchIncomingSell()` within `while` loop, it will trigger an external call - `_updateYieldDiamond()`
591:                         matchIncomingSell(asset, incomingAsk, matchTotal);

/// @audit Calling `matchIncomingSell()` within `while` loop, it will trigger an external call - `_updateYieldDiamond()`
613:                     matchIncomingSell(asset, incomingAsk, matchTotal);

/// @audit Calling `matchIncomingSell()` within `while` loop, it will trigger an external call - `_updateYieldDiamond()`
618:                 matchIncomingSell(asset, incomingAsk, matchTotal);
```

</details>

### [L-10] Use descriptive constant instead of 0 as a parameter

Passing `0` or `0x0` as a function argument can sometimes result in a security issue(e.g. passing zero as the slippage parameter). A historical example is the infamous `0x0` address bug where numerous tokens were lost. This happens because `0` can be interpreted as an uninitialized `address`, leading to transfers to the `0x0` `address`, effectively burning tokens. Moreover, `0` as a denominator in division operations would cause a runtime exception. It's also often indicative of a logical error in the caller's code.

Consider using a constant variable with a descriptive name, so it's clear that the argument is intentionally being used, and for the right reasons.

There are 5 instances:

- *ShortOrdersFacet.sol* ( [48-48](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L48-L48) ):

```solidity
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
```

### [L-11] Code does not follow the best practice of check-effects-interaction

Code should follow the best-practice of [check-effects-interaction](https://blockchain-academy.hs-mittweida.de/courses/solidity-coding-beginners-to-intermediate/lessons/solidity-11-coding-patterns/topic/checks-effects-interactions/), where state variables are updated before any external calls are made. Doing so prevents a large class of reentrancy bugs.

<details>
<summary>There are 30 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [157-157](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L157-L157), [158-158](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L158-L158), [160-160](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L160-L160), [161-161](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L161-L161), [165-165](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L165-L165), [167-167](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L167-L167), [172-172](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L172-L172), [173-173](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L173-L173), [176-176](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L176-L176), [180-180](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L180-L180), [182-182](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L182-L182), [184-184](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L184-L184), [186-186](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L186-L186), [187-187](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L187-L187), [191-191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L191-L191), [191-191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L191-L191), [194-194](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L194-L194) ):

```solidity
/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
157:                     incomingBid.ercAmount -= lowestSell.ercAmount;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
158:                     lowestSell.ercAmount = 0;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
160:                         b.matchedShortId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
161:                         b.prevShortId = lowestSell.prevId;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
165:                         b.matchedAskId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
167:                         b.askId = lowestSell.nextId;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
172:                             b.matchedShortId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
173:                             b.prevShortId = lowestSell.prevId;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
176:                             b.matchedAskId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
180:                         lowestSell.ercAmount -= incomingBid.ercAmount;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
182:                             b.dustShortId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
184:                             lowestShort.ercAmount = lowestSell.ercAmount;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
186:                             b.dustAskId = lowestSell.id;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
187:                             s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
191:                             b.dustShortId = b.dustAskId = 0;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
191:                             b.dustShortId = b.dustAskId = 0;

/// @audit `matchIncomingBid()` is called on line 145, triggering an external call - `_cancelAsk()`
194:                     incomingBid.ercAmount = 0;
```

- *ExitShortFacet.sol* ( [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L56-L56), [60-60](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L60-L60), [64-64](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L64-L64), [189-189](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L189-L189), [190-190](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L190-L190), [191-191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L191-L191), [199-199](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L199-L199), [200-200](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L200-L200), [207-207](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L207-L207) ):

```solidity
/// @audit `burnMsgSenderDebt()` is called on line 55, triggering an external call - `balanceOf()`
56:         Asset.ercDebt -= buybackAmount;

/// @audit `burnMsgSenderDebt()` is called on line 55, triggering an external call - `balanceOf()`
60:             s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;

/// @audit `burnMsgSenderDebt()` is called on line 55, triggering an external call - `balanceOf()`
64:             short.ercDebt -= buybackAmount;

/// @audit `createForcedBid()` is called on line 187
189:         e.ercFilled = e.buybackAmount - e.ercAmountLeft;

/// @audit `createForcedBid()` is called on line 187
190:         Asset.ercDebt -= e.ercFilled;

/// @audit `createForcedBid()` is called on line 187
191:         s.assetUser[e.asset][msg.sender].ercEscrowed -= e.ercFilled;

/// @audit `createForcedBid()` is called on line 187
199:             short.collateral -= e.ethFilled;

/// @audit `createForcedBid()` is called on line 187
200:             short.ercDebt -= e.ercFilled;

/// @audit `createForcedBid()` is called on line 187
207:             VaultUser.ethEscrowed -= e.collateral - e.ethFilled;
```

- *PrimaryLiquidationFacet.sol* ( [190-190](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L190-L190), [193-193](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L193-L193), [194-194](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L194-L194), [199-199](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L199-L199) ):

```solidity
/// @audit `createForcedBid()` is called on line 188
190:         m.ercDebtMatched = m.short.ercDebt - ercAmountLeft;

/// @audit `createForcedBid()` is called on line 188
193:         s.assetUser[m.asset][address(this)].ercEscrowed -= m.ercDebtMatched;

/// @audit `createForcedBid()` is called on line 188
194:         s.asset[m.asset].ercDebt -= m.ercDebtMatched;

/// @audit `createForcedBid()` is called on line 188
199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast)
```

</details>

## Non Critical Issues

### [N-01] Names of `private`/`internal` functions should be prefixed with an underscore

It is recommended by the [Solidity Style Guide](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#underscore-prefix-for-non-external-functions-and-variables).

<details>
<summary>There are 65 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [130-135](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L130-L135), [215-220](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L215-L220), [275-280](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L275-L280) ):

```solidity
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
```

- *BridgeRouterFacet.sol* ( [148-148](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L148-L148) ):

```solidity
148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {
```

- *ExitShortFacet.sol* ( [213-213](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L213-L213) ):

```solidity
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```

- *PrimaryLiquidationFacet.sol* ( [229-229](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L229-L229) ):

```solidity
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {
```

- *RedemptionFacet.sol* ( [31-34](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L31-L34), [382-384](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L382-L384) ):

```solidity
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32:         internal
33:         view
34:         returns (bool)

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383:         internal
384:         returns (uint88 redemptionFee)
```

- *LibBridgeRouter.sol* ( [21-21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L21-L21), [39-41](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L39-L41), [113-113](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L113-L113), [144-144](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L144-L144), [198-198](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L198-L198) ):

```solidity
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40:         internal
41:         returns (uint88)

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
```

- *LibBytes.sol* ( [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L11-L11) ):

```solidity
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```

- *LibOracle.sol* ( [19-19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L19-L19), [69-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L69-L75), [117-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L117-L124), [131-131](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L131-L131), [149-149](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L149-L149), [156-156](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L156-L156), [162-162](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L162-L162), [168-168](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L168-L168) ):

```solidity
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

- *LibOrders.sol* ( [30-30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L30-L30), [35-35](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L35-L35), [40-40](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L40-L40), [55-58](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L55-L58), [78-78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L78-L78), [82-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L82-L82), [103-103](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L103-L103), [128-128](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L128-L128), [153-153](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L153-L153), [173-178](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L173-L178), [231-234](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L231-L234), [260-266](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L260-L266), [289-289](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L289-L289), [314-314](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L314-L314), [362-367](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L362-L367), [402-409](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L402-L409), [420-420](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L420-L420), [440-447](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L440-L447), [474-479](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L474-L479), [499-499](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L499-L499), [556-561](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L556-L561), [628-628](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L628-L628), [652-652](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L652-L652), [668-668](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L668-L668), [705-710](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L705-L710), [783-788](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L783-L788), [803-803](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L803-L803), [810-810](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L810-L810), [826-830](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L826-L830), [854-854](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L854-L854), [868-868](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L868-L868), [882-882](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L882-L882), [955-955](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L955-L955), [985-985](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L985-L985), [989-989](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L989-L989) ):

```solidity
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
56:         internal
57:         view
58:         returns (STypes.Order[] memory)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {

173:     function addOrder(
174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
175:         address asset,
176:         STypes.Order memory incomingOrder,
177:         uint16 hintId
178:     ) private {

231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
232:         internal
233:         view
234:         returns (int256 direction)

260:     function verifySellId(
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

362:     function findPrevOfIncomingId(
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {

420:     function normalizeOrderType(O o) private pure returns (O newO) {

440:     function getOrderId(
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

474:     function updateBidOrdersOnMatch(
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled
479:     ) internal {

499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {

556:     function sellMatchAlgo(
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {

668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {

705:     function matchHighestBid(
706:         STypes.Order memory incomingSell,
707:         STypes.Order memory highestBid,
708:         address asset,
709:         MTypes.Match memory matchTotal
710:     ) internal {

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

- *LibSRUtil.sol* ( [22-24](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L22-L24), [49-51](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L49-L51), [72-74](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L72-L74), [102-105](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L102-L105), [124-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L124-L124), [151-151](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L151-L151) ):

```solidity
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23:         internal
24:     {

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
50:         internal
51:         returns (bool isCancelled)

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
73:         internal
74:         returns (bool isCancelled)

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
103:         internal
104:         view
105:         returns (bool recoveryViolation)

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
```

- *UniswapOracleLibrary.sol* ( [28-31](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L28-L31), [47-50](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L47-L50) ):

```solidity
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)
29:         internal
30:         pure
31:         returns (uint256 quoteAmount)

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
48:         internal
49:         view
50:         returns (uint256 amountOut)
```

</details>

### [N-02] Names of `private`/`internal` state variables should be prefixed with an underscore

It is recommended by the [Solidity Style Guide](https://docs.soliditylang.org/en/v0.8.20/style-guide.html#underscore-prefix-for-non-external-functions-and-variables).

There are 4 instances:

- *BridgeRouterFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L26-L26), [27-27](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L27-L27) ):

```solidity
26:     address private immutable rethBridge;

27:     address private immutable stethBridge;
```

- *ExitShortFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L26) ):

```solidity
26:     address private immutable dusd;
```

- *PrimaryLiquidationFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) ):

```solidity
28:     address private immutable dusd;
```

### [N-03] The `nonReentrant` `modifier` should occur before all other modifiers

This is a best-practice to protect against reentrancy in other modifiers

<details>
<summary>There are 10 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [40-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L40-L47) ):

```solidity
40:     function createBid(
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

- *ExitShortFacet.sol* ( [41-44](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L41-L44), [87-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L87-L90), [142-149](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L142-L149) ):

```solidity
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
42:         external
43:         isNotFrozen(asset)
44:         nonReentrant

87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
88:         external
89:         isNotFrozen(asset)
90:         nonReentrant

142:     function exitShort(
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

- *PrimaryLiquidationFacet.sol* ( [47-50](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L50) ):

```solidity
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
```

- *RedemptionFacet.sol* ( [56-61](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L56-L61), [224-227](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L224-L227), [310-310](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L310-L310), [347-350](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L347-L350) ):

```solidity
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

310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {

347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
348:         external
349:         isNotFrozen(asset)
350:         nonReentrant
```

- *ShortOrdersFacet.sol* ( [35-42](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L35-L42) ):

```solidity
35:     function createLimitShort(
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

</details>

### [N-04] Custom errors should be used rather than `revert()`/`require()`

Custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain.

There is 1 instance:

- *LibBytes.sol* ( [14-14](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L14-L14) ):

```solidity
14:         require(slate.length % 51 == 0, "Invalid data length");
```

### [N-05] Consider splitting complex checks into multiple steps

Assign the expression's parts to intermediate local variables, and check against those instead.

There are 5 instances:

- *BidOrdersFacet.sol* ( [106-106](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L106-L106), [317-317](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L317-L317) ):

```solidity
106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {

317:             } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
```

- *RedemptionFacet.sol* ( [38-38](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L38-L38) ):

```solidity
38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
```

- *LibOracle.sol* ( [60-60](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L60-L60) ):

```solidity
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
```

- *LibOrders.sol* ( [752-752](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L752-L752) ):

```solidity
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
```

### [N-06] Complex casting

Consider whether the number of casts is really necessary, or whether using a different type would be more appropriate. Alternatively, add comments to explain in detail why the casts are necessary, and any implicit reasons why the cast does not introduce an overflow.

There is 1 instance:

- *UniswapOracleLibrary.sol* ( [62-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L62-L62) ):

```solidity
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
```

### [N-07] Complex math should be split into multiple steps

Consider splitting long arithmetic calculations into multiple steps to improve the code readability.

<details>
<summary>There are 11 instances (click to show):</summary>

- *PrimaryLiquidationFacet.sol* ( [140-140](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L140-L140), [180-180](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L180-L180) ):

```solidity
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees

180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)
```

- *RedemptionFacet.sol* ( [183-183](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L183-L183), [186-187](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L186-L187), [190-191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L190-L191), [194-195](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L194-L195), [198-198](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L198-L198), [289-291](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L289-L291) ):

```solidity
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

186:             redeemerAssetUser.timeToDispute =
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);

190:             redeemerAssetUser.timeToDispute =
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);

194:             redeemerAssetUser.timeToDispute =
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);

198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);

289:             uint256 penaltyPct = LibOrders.min(
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );
```

- *LibOrders.sol* ( [965-965](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L965-L965) ):

```solidity
965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));
```

- *UniswapOracleLibrary.sol* ( [38-39](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L38-L39), [42-43](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L42-L43) ):

```solidity
38:             quoteAmount =
39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

42:             quoteAmount =
43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);
```

</details>

### [N-08] Consider adding a block/deny-list

Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens

<details>
<summary>There are 6 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [20](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L20) ):

```solidity
20: contract BidOrdersFacet is Modifiers {
```

- *BridgeRouterFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L18) ):

```solidity
18: contract BridgeRouterFacet is Modifiers {
```

- *ExitShortFacet.sol* ( [19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L19) ):

```solidity
19: contract ExitShortFacet is Modifiers {
```

- *PrimaryLiquidationFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L21) ):

```solidity
21: contract PrimaryLiquidationFacet is Modifiers {
```

- *RedemptionFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L21) ):

```solidity
21: contract RedemptionFacet is Modifiers {
```

- *ShortOrdersFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L18) ):

```solidity
18: contract ShortOrdersFacet is Modifiers {
```

</details>

### [N-09] Constants/Immutables redefined elsewhere

Consider defining in only one contract so that values cannot become out of sync when only one location is updated. A [cheap way](https://medium.com/coinmonks/gas-cost-of-solidity-library-functions-dbe0cedd4678) to store constants/immutables in a single location is to create an `internal constant` in a `library`. If the variable is a local cache of another contract's value, consider making the cache variable internal or private, which will require external users to query the contract with the source of truth, so that callers don't get out of sync.

There are 2 instances:

- *ExitShortFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L26) ):

```solidity
/// @audit Seen in contracts/facets/PrimaryLiquidationFacet.sol#28
26:     address private immutable dusd;
```

- *PrimaryLiquidationFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) ):

```solidity
/// @audit Seen in contracts/facets/ExitShortFacet.sol#26
28:     address private immutable dusd;
```

### [N-10] Convert simple `if`-statements to ternary expressions

Converting some if statements to ternaries (such as `z = (a < b) ? x : y`) can make the code more concise and easier to read.

<details>
<summary>There are 8 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [320-324](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L320-L324) ):

```solidity
320:                 if (b.isMovingFwd) {
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }
```

- *LibOrders.sol* ( [90-94](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L90-L94), [111-115](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L111-L115), [132-136](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L132-L136), [196-202](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L196-L202), [339-348](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L339-L348), [791-795](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L791-L795), [944-948](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L944-L948) ):

```solidity
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

</details>

### [N-11] Contracts should each be defined in separate files

Keeping each contract in a separate file makes it easier to work with multiple people, makes the code easier to maintain, and is a common practice on most projects. The following files each contains more than one contract/library/interface.

There is 1 instance:

- [*UniswapOracleLibrary.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol)

### [N-12] Contract name does not match its filename

According to the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#contract-and-library-names), contract and library names should also match their filenames.

There is 1 instance:

- *UniswapOracleLibrary.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L21) ):

```solidity
/// @audit Not match filename `UniswapOracleLibrary.sol`
21: library OracleLibrary {
```

### [N-13] UPPER_CASE names should be reserved for `constant`/`immutable` variables

If the variable needs to be different based on which class it comes from, a `view`/`pure` _function_ should be used instead (e.g. like [this](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/76eee35971c2541585e05cbf258510dda7b2fbc6/contracts/token/ERC20/extensions/draft-IERC20Permit.sol#L59)).

There are 4 instances:

- *PrimaryLiquidationFacet.sol* ( [165](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L165), [211](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L211), [241](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L241) ):

```solidity
165:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];

211:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];

241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];
```

- *LibBytes.sol* ( [24](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L24) ):

```solidity
24:             uint64 CR; // bytes8
```

### [N-14] Contract timekeeping will break earlier than the Ethereum network itself will stop working

When a timestamp is downcast from `uint256` to `uint32`, the value will wrap in the year 2106, and the contracts will break. Other downcasts will have different endpoints. Consider whether your contract is intended to live past the size of the type being used.

There is 1 instance:

- *LibOrders.sol* ( [32-32](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L32-L32) ):

```solidity
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)
```

### [N-15] Consider emitting an event at the end of the constructor

This will allow users to easily exactly pinpoint when and by whom a contract was constructed.

There are 3 instances:

- *BridgeRouterFacet.sol* ( [29-29](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L29-L29) ):

```solidity
29:     constructor(address _rethBridge, address _stethBridge) {
```

- *ExitShortFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L28-L28) ):

```solidity
28:     constructor(address _dusd) {
```

- *PrimaryLiquidationFacet.sol* ( [30-30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L30-L30) ):

```solidity
30:     constructor(address _dusd) {
```

### [N-16] Events are emitted without the sender information

When an action is triggered based on a user's action, not being able to filter based on who triggered the action makes event processing a lot more cumbersome. Including the `msg.sender` the events of these types of action will make events much more useful to end users, especially when `msg.sender` is not `tx.origin`.

There is 1 instance:

- *RedemptionFacet.sol* ( [284-284](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L284-L284) ):

```solidity
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);
```

### [N-17] Imports could be organized more systematically

The contract's interface should be imported first, followed by each of the interfaces it uses, followed by all other files. The examples below do not follow this layout.

<details>
<summary>There are 6 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {IDiamond} from "interfaces/IDiamond.sol";
```

- *BridgeRouterFacet.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {IBridge} from "contracts/interfaces/IBridge.sol";
```

- *ExitShortFacet.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {IDiamond} from "interfaces/IDiamond.sol";
```

- *PrimaryLiquidationFacet.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {IDiamond} from "interfaces/IDiamond.sol";
```

- *LibOracle.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {AggregatorV3Interface} from "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
```

- *LibOrders.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L6-L6) ):

```solidity
/// @audit Out of order with the prev import️ ⬆
6: import {IDiamond} from "interfaces/IDiamond.sol";
```

</details>

### [N-18] Invalid NatSpec comment style

NatSpec comment in solidity should use `///` or `/* ... */` syntax.

<details>
<summary>There are 111 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [70-70](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L70-L70), [72-73](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L72-L73), [102-102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L102-L102), [107-107](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L107-L107), [113-113](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L113-L113), [140-140](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L140-L140), [291-291](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L291-L291), [308-309](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L308-L309), [333-334](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L333-L334), [338-339](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L338-L339), [344-344](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L344-L344), [353-353](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L353-L353), [393-393](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L393-L393), [401-401](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L401-L401) ):

```solidity
70:         // @dev leave empty, don't need hint for market buys

72: 
73:         // @dev update oracle in callers

102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)

107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId

113:             // @dev no match, add to market if limit order

140:             // @dev Handles scenario when no sells left after partial fill

291:         // @dev needs to happen after updateSellOrdersOnMatch()

308: 
309:             // @dev Approximates the startingShortId after bid is fully executed

333: 
334:         // @dev match price is based on the order that was already on orderbook

338: 
339:     // @dev If neither conditions are true, it returns an empty Order struct

344:             // @dev Setting lowestSell after comparing short and ask prices

353:             // @dev Handles scenario when there are no shorts

393:             // @dev shortHintId should always be the first thing matched

401:             // @dev Only set to true if actually moving forward
```

- *BridgeRouterFacet.sol* ( [67-67](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L67-L67), [147-147](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L147-L147), [178-178](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L178-L178) ):

```solidity
67:         // @dev amount after deposit might be less, if bridge takes a fee

147:     // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions

178:             // @dev don't use mulU88 in rare case of overflow
```

- *ExitShortFacet.sol* ( [156-157](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L156-L157), [167-168](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L167-L168), [202-203](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L202-L203), [205-206](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L205-L206) ):

```solidity
156: 
157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder

167: 
168:         // @dev if short order was cancelled, fully exit

202: 
203:             // @dev Only allow partial exit if the CR is same or better than before

205: 
206:             // @dev collateral already subtracted in exitShort()
```

- *PrimaryLiquidationFacet.sol* ( [55-55](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L55-L55), [57-58](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L57-L58), [66-67](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L66-L67), [71-72](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L71-L72), [95-95](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L95-L95), [157-158](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L157-L158), [163-164](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L163-L164), [177-177](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L177-L177), [185-186](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L185-L186), [191-192](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L191-L192), [197-197](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L197-L197), [198-198](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L198-L198), [217-217](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L217-L217) ):

```solidity
55:         // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost

57: 
58:         // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile

66: 
67:         // @dev liquidate requires more up-to-date oraclePrice

71: 
72:         // @dev Can liquidate as long as CR is low enough

95:     // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call

157: 
158:         // @dev Provide higher price to better ensure it can fully fill the liquidation

163: 
164:         // @dev Increase ethEscrowed by shorter's full collateral for forced bid

177:             // @dev Max ethDebt can only be the ethEscrowed in the TAPP

185: 
186:         // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP

191: 
192:         // @dev virtually burning the repurchased debt

197:         // @dev manually setting basefee to 1,000,000 in foundry.toml;

198:         // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP

217:         // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out.
```

- *RedemptionFacet.sol* ( [36-36](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L36-L36), [37-37](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L37-L37), [71-72](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L71-L72), [82-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L82-L82), [91-92](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L91-L92), [94-95](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L94-L95), [100-100](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L100-L100), [107-108](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L107-L108), [109-109](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L109-L109), [126-127](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L126-L127), [144-145](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L144-L145), [156-156](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L156-L156), [157-157](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L157-L157), [261-261](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L261-L261), [262-262](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L262-L262), [277-278](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L277-L278), [282-282](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L282-L282), [286-287](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L286-L287), [288-288](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L288-L288), [294-295](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L294-L295), [355-356](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L355-L356), [372-372](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L372-L372), [375-375](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L375-L375), [380-381](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L380-L381), [391-391](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L391-L391), [393-393](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L393-L393) ):

```solidity
36:         // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition

37:         // @dev Proposer can't redeem on self

71: 
72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption

82:             // @dev Setting this above _onlyValidShortRecord to allow skipping

91: 
92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold

94: 
95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount

100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate

107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR

109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()

126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes

144: 
145:         // @dev SSTORE2 the entire proposalData after validating proposalInput

156:         // @dev Calculate the dispute period

157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x

261:             // @dev All proposals from the incorrectIndex onward will be removed

262:             // @dev Thus the proposer can only redeem a portion of their original slate

277: 
278:             // @dev Update the redeemer's SSTORE2Pointer

282:                 // @dev this implies everything in the redeemer's proposal was incorrect

286: 
287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)

288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees

294: 
295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)

355: 
356:         // @dev Only need to read up to the position of the SR to be claimed

372:             // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already

375:             // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS

380: 
381:     // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated

391:         // @dev Calculate Asset.ercDebt prior to proposal

393:         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
```

- *ShortOrdersFacet.sol* ( [46-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L46-L47), [54-55](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L54-L55), [74-74](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L74-L74), [83-84](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L83-L84) ):

```solidity
46: 
47:         // @dev create "empty" SR. Fail early.

54: 
55:         // @dev minShortErc needs to be modified (bigger) when cr < 1

74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId

83: 
84:         // @dev reading spot oracle price
```

- *LibBridgeRouter.sol* ( [74-74](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L74-L74), [104-104](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L104-L104), [112-112](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L112-L112), [142-143](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L142-L143) ):

```solidity
74:                     // @dev Prevents abusing bridge for arbitrage

104:                     // @dev Prevents abusing bridge for arbitrage

112:     // @dev Only applicable to VAULT.ONE which has mixed LST

142: 
143:     // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system
```

- *LibOracle.sol* ( [29-29](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L29-L29), [81-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L81-L82), [154-155](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L154-L155), [160-161](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L160-L161), [166-167](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L166-L167) ):

```solidity
29:                 // @dev multiply base oracle by 10**10 to give it 18 decimals of precision

81: 
82:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink

154: 
155:     // @dev Intentionally using creationTime for oracleTime.

160: 
161:     // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.

166: 
167:     // @dev Allows caller to save gas since reading spot price costs ~16K
```

- *LibOrders.sol* ( [28-29](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L28-L29), [42-43](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L42-L43), [137-138](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L137-L138), [171-172](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L171-L172), [188-188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L188-L188), [237-237](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L237-L237), [267-267](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L267-L267), [294-294](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L294-L294), [331-332](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L331-L332), [418-419](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L418-L419), [507-507](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L507-L507), [508-508](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L508-L508), [511-511](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L511-L511), [518-518](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L518-L518), [640-641](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L640-L641), [723-724](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L723-L724), [760-760](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L760-L760), [769-769](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L769-L769), [781-782](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L781-L782), [790-790](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L790-L790), [801-802](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L801-L802), [846-846](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L846-L846), [899-899](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L899-L899), [900-900](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L900-L900), [905-905](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L905-L905), [906-906](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L906-L906), [927-928](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L927-L928), [931-931](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L931-L931), [961-962](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L961-L962), [964-964](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L964-L964), [966-967](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L966-L967), [970-970](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L970-L970), [974-974](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L974-L974), [980-981](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L980-L981) ):

```solidity
28: 
29:     // @dev in seconds

42: 
43:         // @dev use the diff to get more time (2159), to prevent overflow at year 2106

137: 
138:         // @dev: Only need to set this when placing incomingShort onto market

171: 
172:     // @dev partial addOrder

188:         // @dev (ID) is exiting, [ID] is inserted

237:         // @dev: TAIL can't be prevId because it will always be last item in list

267:         // @dev: TAIL can't be prevId because it will always be last item in list

294:         // @dev (ID) is exiting, [ID] is inserted

331: 
332:         // @dev mark as cancelled instead of deleting the order itself

418: 
419:     // @dev not used to change state, just which methods to call

507:                 // @dev Handles only matching one thing

508:                 // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block

511:                 // @dev Handles moving forward only

518:                 // @dev Handle going backward and forward

640: 
641:         // @dev match price is based on the order that was already on orderbook

723: 
724:         // @dev this happens at the end so fillErc isn't affected in previous calculations

760:                 // @dev force hint to be within 0.5% of oraclePrice

769:                     // @dev prevShortPrice >= oraclePrice

781: 
782:     // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)

790:         // @dev handle .5% deviations in either directions

801: 
802:     // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough

846:             // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD

899:             // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId

900:             // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId

905:                 // @dev prevents leaving behind a partially filled SR is under minShortErc

906:                 // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc

927: 
928:                     // @dev update the eth refund amount

931:                 // @dev virtually mint the increased debt

961: 
962:         // @dev tithe is increased only if discount is greater than 1%

964:             // @dev bound the new tithe amount between 25% and 100%

966: 
967:             // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount

970:             // @dev dethTitheMod is only set when setTithe is called.

974:                 // @dev change back to original tithe percent

980: 
981:         // @dev exists because of ShortOrderFacet contract size
```

- *LibSRUtil.sol* ( [89-89](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L89-L89), [132-133](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L132-L133) ):

```solidity
89:                     // @dev The resulting SR will not have PartialFill status after cancel

132: 
133:         // @dev shortOrderId is already validated in mintNFT
```

- *UniswapOracleLibrary.sol* ( [57-58](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L57-L58), [68-69](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L68-L69) ):

```solidity
57: 
58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp

68: 
69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
```

</details>

### [N-19] @openzeppelin/contracts should be upgraded to a newer version

These contracts import contracts from `@openzeppelin/contracts`, but they are not using [the latest version](https://github.com/OpenZeppelin/openzeppelin-contracts/releases). Using the latest version ensures contract security with fixes for known vulnerabilities, access to the latest feature updates, and enhanced community support and engagement.

The imported version is `^4.9.0`.

There is 1 instance:

- *LibOracle.sol* ( [7](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L7) ):

```solidity
7: import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";
```

### [N-20] Lib @prb/math should be upgraded to a newer version

These contracts import contracts from lib @prb/math, but they are not using [the latest version](https://github.com/PaulRBerg/prb-math/releases).

The imported version is `^4.0.1`.

There is 1 instance:

- Global finding

### [N-21] Functions should be named in mixedCase style

As the [Solidity Style Guide](https://docs.soliditylang.org/en/v0.8.21/style-guide.html#function-names) suggests: functions should be named in mixedCase style.

There are 3 instances:

- *RedemptionFacet.sol* ( [31](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L31) ):

```solidity
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
```

- *LibOrders.sol* ( [35](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L35) ):

```solidity
35:     function convertCR(uint16 cr) internal pure returns (uint256) {
```

- *UniswapOracleLibrary.sol* ( [47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L47) ):

```solidity
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
```

### [N-22] Variable names for `immutable`s should use UPPER_CASE_WITH_UNDERSCORES

For `immutable` variable names, each word should use all capital letters, with underscores separating each word (UPPER_CASE_WITH_UNDERSCORES)

There are 4 instances:

- *BridgeRouterFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L26-L26), [27-27](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L27-L27) ):

```solidity
26:     address private immutable rethBridge;

27:     address private immutable stethBridge;
```

- *ExitShortFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L26) ):

```solidity
26:     address private immutable dusd;
```

- *PrimaryLiquidationFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) ):

```solidity
28:     address private immutable dusd;
```

### [N-23] Consider adding validation of user inputs

There are no validations done on the arguments below. Consider that the Solidity [documentation](https://docs.soliditylang.org/en/latest/control-structures.html#panic-via-assert-and-error-via-require) states that `Properly functioning code should never create a Panic, not even on invalid external input. If this happens, then there is a bug in your contract which you should fix`. This means that there should be explicit checks for expected ranges of inputs. Underflows/overflows result in panics should not be used as range checks, and allowing funds to be sent to  `0x0`, which is the default value of address variables and has many gotchas, should be avoided.

There are 7 instances:

- *BidOrdersFacet.sol* ( [65-65](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L65-L65) ):

```solidity
/// @audit `sender not checked`
/// @audit `asset not checked`
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
```

- *BridgeRouterFacet.sol* ( [63-63](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L63-L63), [82-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L82-L82), [101-101](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L101-L101), [133-133](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L133-L133) ):

```solidity
/// @audit `bridge not checked`
63:     function deposit(address bridge, uint88 amount) external nonReentrant {

/// @audit `bridge not checked`
82:     function depositEth(address bridge) external payable nonReentrant {

/// @audit `bridge not checked`
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant {

/// @audit `bridge not checked`
133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
```

- *RedemptionFacet.sol* ( [347-347](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L347-L347) ):

```solidity
/// @audit `redeemer not checked`
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
```

### [N-24] Constants should be put on the left side of comparisons

Putting constants on the left side of comparison statements is a best practice known as [Yoda conditions](https://en.wikipedia.org/wiki/Yoda_conditions).
Although solidity's static typing system prevents accidental assignments within conditionals, adopting this practice can improve code readability and consistency, especially when working across multiple languages.

<details>
<summary>There are 34 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [281](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L281) ):

```solidity
/// @audit put `0` on the left
281:         if (matchTotal.fillEth == 0) {
```

- *BridgeRouterFacet.sol* ( [102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L102), [134](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L134), [164](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L164) ):

```solidity
/// @audit put `0` on the left
102:         if (dethAmount == 0) revert Errors.ParameterIsZero();

/// @audit put `0` on the left
134:         if (dethAmount == 0) revert Errors.ParameterIsZero();

/// @audit put `0` on the left
164:             if (vault == 0) revert Errors.InvalidBridge();
```

- *ExitShortFacet.sol* ( [53](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L53), [99](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L99), [174](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L174), [188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L188) ):

```solidity
/// @audit put `0` on the left
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();

/// @audit put `0` on the left
99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();

/// @audit put `0` on the left
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();

/// @audit put `0` on the left
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
```

- *RedemptionFacet.sol* ( [73](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L73), [235](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L235), [314](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L314), [353](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L353), [371](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L371) ):

```solidity
/// @audit put `address(0)` on the left
73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();

/// @audit put `address(0)` on the left
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

/// @audit put `address(0)` on the left
314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

/// @audit put `address(0)` on the left
353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

/// @audit put `0` on the left
371:         if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {
```

- *LibOracle.sol* ( [60](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L60), [60](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L60), [76](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L76), [76](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L76), [89](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L89), [125](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L125), [125](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L125), [126](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L126), [126](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L126), [134](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L134) ):

```solidity
/// @audit put `0` on the left
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

/// @audit put `0` on the left
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

/// @audit put `0` on the left
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
89:                 if (twapPrice == 0) {

/// @audit put `0` on the left
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

/// @audit put `0` on the left
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

/// @audit put `0` on the left
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

/// @audit put `0` on the left
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

/// @audit put `0` on the left
134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice();
```

- *LibOrders.sol* ( [371](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L371), [371](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L371), [501](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L501), [505](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L505), [677](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L677), [805](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L805) ):

```solidity
/// @audit put `0` on the left
371:         if (hintId == 0 || nextId == 0) {

/// @audit put `0` on the left
371:         if (hintId == 0 || nextId == 0) {

/// @audit put `0` on the left
501:         if (b.matchedAskId != 0) {

/// @audit put `0` on the left
505:         if (b.matchedShortId != 0) {

/// @audit put `0` on the left
677:         SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill;

/// @audit put `15 minutes` on the left
805:         if (timeDiff >= 15 minutes) {
```

- *LibSRUtil.sol* ( [131](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L131) ):

```solidity
/// @audit put `0` on the left
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();
```

- *UniswapOracleLibrary.sol* ( [52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L52) ):

```solidity
/// @audit put `0` on the left
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
```

</details>

### [N-25] Libraries should be defined in separate files

The libraries below should be defined in separate files, so that it's easier for future projects to import them, and to avoid duplication later on if they need to be used elsewhere in the project.

There is 1 instance:

- *UniswapOracleLibrary.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L21) ):

```solidity
21: library OracleLibrary {
```

### [N-26] `else`-block not required

One level of nesting can be removed by not having an `else` block when the `if`-block always jumps at the end. For example:
```solidity
if (condition) {
    body1...
    return x;
} else {
    body2...
}
```
can be changed to:
```solidity
if (condition) {
    body1...
    return x;
}
body2...
```

<details>
<summary>There are 27 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [106-112](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L106-L112), [347-349](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L347-L349) ):

```solidity
106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109:             b.shortHintId = b.shortId = Asset.startingShortId;
110:             b.oraclePrice = LibOracle.getPrice(asset);
111:             return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112:         } else {

347:             if (noAsks || shortPriceLessThanAskPrice) {
348:                 return lowestShort;
349:             } else {
```

- *BridgeRouterFacet.sol* ( [173-176](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L173-L176) ):

```solidity
173:         if (dethTotalNew >= dethTotal) {
174:             // when yield is positive 1 deth = 1 eth
175:             return amount;
176:         } else {
```

- *RedemptionFacet.sol* ( [38-40](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L38-L40) ):

```solidity
38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
39:             return false;
40:         } else {
```

- *LibBridgeRouter.sol* ( [59-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L59-L62), [65-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L65-L68), [89-92](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L89-L92), [95-98](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L95-L98) ):

```solidity
59:             if (creditSteth < C.ROUNDING_ZERO) {
60:                 // Valid withdraw when no STETH credits
61:                 return amount;
62:             } else {

65:                     if (creditSteth >= amount) {
66:                         VaultUser.bridgeCreditSteth -= amount;
67:                         return 0;
68:                     } else {

89:             if (creditReth < C.ROUNDING_ZERO) {
90:                 // Valid withdraw when no RETH credits
91:                 return amount;
92:             } else {

95:                     if (creditReth >= amount) {
96:                         VaultUser.bridgeCreditReth -= amount;
97:                         return 0;
98:                     } else {
```

- *LibOracle.sol* ( [28-33](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L28-L33), [48-50](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L48-L50), [83-85](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L83-L85), [98-100](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L98-L100), [169-171](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L169-L171) ):

```solidity
28:             if (oracle == baseOracle) {
29:                 // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
30:                 uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;
31:                 basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
32:                 return basePriceInEth;
33:             } else {

48:             if (oracle == baseOracle) {
49:                 return twapCircuitBreaker();
50:             } else {

83:         if (invalidFetchData) {
84:             return twapCircuitBreaker();
85:         } else if (priceDeviation) {

98:                 if (chainlinkDiff <= twapDiff) {
99:                     return chainlinkPriceInEth;
100:                 } else {

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
170:             return getPrice(asset);
171:         } else {
```

- *LibOrders.sol* ( [241-243](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L241-L243), [243-245](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L243-L245), [272-274](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L272-L274), [274-276](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L274-L276), [381-383](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L381-L383), [383-385](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L383-L385), [412-414](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L412-L414), [421-423](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L421-L423), [423-425](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L423-L425), [765-768](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L765-L768), [768-772](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L768-L772), [836-838](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L836-L838), [838-840](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L838-L840) ):

```solidity
241:         if (check1 && check2) {
242:             return C.EXACT;
243:         } else if (!check1) {

243:         } else if (!check1) {
244:             return C.PREV;
245:         } else if (!check2) {

272:         if (check1 && check2) {
273:             return C.EXACT;
274:         } else if (!check1) {

274:         } else if (!check1) {
275:             return C.PREV;
276:         } else if (!check2) {

381:         if (direction == C.EXACT) {
382:             return hintId;
383:         } else if (direction == C.NEXT) {

383:         } else if (direction == C.NEXT) {
384:             return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
385:         } else {

412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413:             return verifySellId(orders, asset, prevId, newPrice, nextId);
414:         } else if (orderType == O.LimitBid) {

421:         if (o == O.LimitBid || o == O.MarketBid) {
422:             return O.LimitBid;
423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {

423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {
424:             return O.LimitAsk;
425:         } else if (o == O.LimitShort) {

765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {

768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {

836:             if (hintOrderType == O.Cancelled || hintOrderType == O.Matched) {
837:                 continue;
838:             } else if (order.creationTime == orderHint.creationTime) {

838:             } else if (order.creationTime == orderHint.creationTime) {
839:                 return orderHint.hintId;
840:             } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
```

- *LibSRUtil.sol* ( [59-64](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L59-L64) ):

```solidity
59:             if (shorter == msg.sender) {
60:                 // If call comes from exitShort() or combineShorts() then always cancel
61:                 LibOrders.cancelShort(asset, shortOrderId);
62:                 assert(shortRecord.status != SR.PartialFill);
63:                 return true;
64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
```

</details>

### [N-27] High cyclomatic complexity

Consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns.

<details>
<summary>There are 2 instances (click to show):</summary>

- *ExitShortFacet.sol* ( [142-211](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L142-L211) ):

```solidity
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
...... OMITTED ......
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

- *ShortOrdersFacet.sol* ( [35-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L35-L90) ):

```solidity
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
57:         p.eth = price.mul(ercAmount);
58:         p.minAskEth = LibAsset.minAskEth(asset);
59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
...... OMITTED ......
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

</details>

### [N-28] Typos

All typos should be corrected.

There are 2 instances:

- *RedemptionFacet.sol* ( [393](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L393) ):

```solidity
/// @audit forumula
393:         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)
```

- *LibBytes.sol* ( [19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L19) ):

```solidity
/// @audit mulitply
19:             // 32 offset for array length, mulitply by each ProposalData
```

### [N-29] Consider bounding input array length

The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to require() that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.

There are 2 instances:

- *BidOrdersFacet.sol* ( [139](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L139) ):

```solidity
139:         while (true) {
```

- *RedemptionFacet.sol* ( [78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L78) ):

```solidity
78:         for (uint8 i = 0; i < proposalInput.length; i++) {
```

### [N-30] Unnecessary casting

Unnecessary castings can be removed.

There is 1 instance:

- *RedemptionFacet.sol* ( [197-197](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L197-L197) ):

```solidity
/// @audit uint256(C.ONE_THIRD.div(0.1 ether))
197:             m = uint256(C.ONE_THIRD.div(0.1 ether));
```

### [N-31] Unused contract variables

The following state variables are defined but not used.
It is recommended to check the code for logical omissions that cause them not to be used. If it's determined that they are not needed anywhere, it's best to remove them from the codebase to improve code clarity and minimize confusion.

There are 2 instances:

- *ExitShortFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L26) ):

```solidity
26:     address private immutable dusd;
```

- *PrimaryLiquidationFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) ):

```solidity
28:     address private immutable dusd;
```

### [N-32] Unused import

The identifier is imported but never used within the file.

<details>
<summary>There are 60 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L4-L4), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L8-L8), [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L11-L11) ):

```solidity
/// @audit U256
/// @audit U88
/// @audit U80
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

/// @audit Modifiers
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

/// @audit STypes
/// @audit MTypes
11: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";
```

- *BridgeRouterFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L4-L4), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L8-L8), [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L11-L11), [13-13](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L13-L13) ):

```solidity
/// @audit U256
/// @audit U88
4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";

/// @audit Modifiers
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

/// @audit LibBridge
11: import {LibBridge} from "contracts/libraries/LibBridge.sol";

/// @audit LibVault
13: import {LibVault} from "contracts/libraries/LibVault.sol";
```

- *ExitShortFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L4-L4), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L8-L8), [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L11-L11) ):

```solidity
/// @audit U256
/// @audit U80
/// @audit U88
4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";

/// @audit Modifiers
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

/// @audit STypes
/// @audit MTypes
/// @audit SR
11: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";
```

- *PrimaryLiquidationFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L4-L4), [10-10](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L10-L10), [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L11-L11) ):

```solidity
/// @audit U256
/// @audit U96
/// @audit U88
/// @audit U80
4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

/// @audit STypes
/// @audit MTypes
10: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";

/// @audit Modifiers
11: import {Modifiers} from "contracts/libraries/AppStorage.sol";
```

- *RedemptionFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L4-L4), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L8-L8), [9-9](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L9-L9), [19-19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L19-L19) ):

```solidity
/// @audit U256
/// @audit U104
/// @audit U88
/// @audit U80
/// @audit U64
/// @audit U32
4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";

/// @audit Modifiers
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";

/// @audit STypes
/// @audit MTypes
9: import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";

/// @audit console
19: import {console} from "contracts/libraries/console.sol";
```

- *ShortOrdersFacet.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L4-L4), [7-7](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L7-L7), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L8-L8) ):

```solidity
/// @audit U256
/// @audit U88
/// @audit U80
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

/// @audit STypes
/// @audit MTypes
7: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";

/// @audit Modifiers
8: import {Modifiers} from "contracts/libraries/AppStorage.sol";
```

- *LibBridgeRouter.sol* ( [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L6-L6), [7-7](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L7-L7), [12-12](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L12-L12) ):

```solidity
/// @audit STypes
6: import {STypes} from "contracts/libraries/DataTypes.sol";

/// @audit AppStorage
7: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";

/// @audit U256
/// @audit U88
12: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";
```

- *LibOracle.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L4-L4), [9-9](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L9-L9) ):

```solidity
/// @audit U256
4: import {U256} from "contracts/libraries/PRBMathHelper.sol";

/// @audit AppStorage
9: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
```

- *LibOrders.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L4-L4), [8-8](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L8-L8), [9-9](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L9-L9), [15-15](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L15-L15) ):

```solidity
/// @audit U256
/// @audit U104
/// @audit U80
/// @audit U88
/// @audit U16
4: import {U256, U104, U80, U88, U16} from "contracts/libraries/PRBMathHelper.sol";

/// @audit AppStorage
8: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";

/// @audit STypes
/// @audit MTypes
9: import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";

/// @audit LibVault
15: import {LibVault} from "contracts/libraries/LibVault.sol";
```

- *LibSRUtil.sol* ( [4-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L4-L4), [6-6](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L6-L6), [7-7](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L7-L7) ):

```solidity
/// @audit U88
/// @audit U256
4: import {U88, U256} from "contracts/libraries/PRBMathHelper.sol";

/// @audit STypes
6: import {STypes, SR} from "contracts/libraries/DataTypes.sol";

/// @audit AppStorage
7: import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
```

</details>

### [N-33] Unused local variables

The following local variables are not used. It is recommended to check the code for logical omissions that cause them not to be used. If it's determined that they are not needed anywhere, it's best to remove them from the codebase to improve code clarity and minimize confusion.

There is 1 instance:

- *LibOracle.sol* ( [27-27](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L27-L27) ):

```solidity
27:         try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
```

### [N-34] Unused named return

Declaring named returns, but not using them, is confusing to the reader. Consider either completely removing them (by declaring just the type without a name), or remove the return statement and do a variable assignment. This would improve the readability of the code, and it may also help reduce regressions during future code refactors.

<details>
<summary>There are 27 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [40-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L40-L47), [65-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L65-L68), [77-85](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L77-L85), [130-135](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L130-L135), [275-280](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L275-L280), [340-340](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L340-L340) ):

```solidity
/// @audit ethFilled
/// @audit ercAmountLeft
40:     function createBid(
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit ethFilled
/// @audit ercAmountLeft
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)

/// @audit ethFilled
/// @audit ercAmountLeft
77:     function _createBid(
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit ethFilled
/// @audit ercAmountLeft
130:     function bidMatchAlgo(
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit ethFilled
/// @audit ercAmountLeft
275:     function matchIncomingBid(
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

/// @audit lowestSell
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {
```

- *ExitShortFacet.sol* ( [213-213](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L213-L213) ):

```solidity
/// @audit cRatio
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```

- *RedemptionFacet.sol* ( [382-384](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L382-L384) ):

```solidity
/// @audit redemptionFee
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)
383:         internal
384:         returns (uint88 redemptionFee)
```

- *LibBridgeRouter.sol* ( [113-113](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L113-L113) ):

```solidity
/// @audit fee
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
```

- *LibOracle.sol* ( [69-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L69-L75), [131-131](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L131-L131), [156-156](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L156-L156), [162-162](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L162-L162) ):

```solidity
/// @audit _protocolPrice
69:     function baseOracleCircuitBreaker(
70:         uint256 protocolPrice,
71:         uint80 roundId,
72:         int256 chainlinkPrice,
73:         uint256 timeStamp,
74:         uint256 chainlinkPriceInEth
75:     ) private view returns (uint256 _protocolPrice) {

/// @audit twapPriceInEth
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

/// @audit creationTime
156:     function getTime(address asset) internal view returns (uint256 creationTime) {

/// @audit oraclePrice
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {
```

- *LibOrders.sol* ( [30-30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L30-L30), [231-234](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L231-L234), [260-266](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L260-L266), [402-409](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L402-L409), [420-420](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L420-L420), [440-447](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L440-L447), [826-830](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L826-L830) ):

```solidity
/// @audit timeInSeconds
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

/// @audit direction
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)
232:         internal
233:         view
234:         returns (int256 direction)

/// @audit direction
260:     function verifySellId(
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {

/// @audit direction
402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {

/// @audit newO
420:     function normalizeOrderType(O o) private pure returns (O newO) {

/// @audit _hintId
440:     function getOrderId(
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {

/// @audit hintId
826:     function findOrderHintId(
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {
```

- *LibSRUtil.sol* ( [49-51](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L49-L51), [102-105](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L102-L105) ):

```solidity
/// @audit isCancelled
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
50:         internal
51:         returns (bool isCancelled)

/// @audit recoveryViolation
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
103:         internal
104:         view
105:         returns (bool recoveryViolation)
```

</details>

### [N-35] Consider using `delete` rather than assigning zero to clear values

The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic.

<details>
<summary>There are 17 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [158-158](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L158-L158), [191-191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L191-L191), [194-194](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L194-L194) ):

```solidity
158:                     lowestSell.ercAmount = 0;

191:                             b.dustShortId = b.dustAskId = 0;

194:                     incomingBid.ercAmount = 0;
```

- *LibBridgeRouter.sol* ( [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L56-L56), [69-69](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L69-L69), [86-86](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L86-L86), [99-99](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L99-L99), [167-167](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L167-L167), [176-176](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L176-L176), [188-188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L188-L188), [189-189](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L189-L189) ):

```solidity
56:             VaultUser.bridgeCreditReth = 0;

69:                         VaultUser.bridgeCreditSteth = 0;

86:             VaultUser.bridgeCreditSteth = 0;

99:                         VaultUser.bridgeCreditReth = 0;

167:                     VaultUserFrom.bridgeCreditReth = 0;

176:                     VaultUserFrom.bridgeCreditSteth = 0;

188:                     VaultUserFrom.bridgeCreditReth = 0;

189:                     VaultUserFrom.bridgeCreditSteth = 0;
```

- *LibOrders.sol* ( [578-578](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L578-L578), [585-585](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L585-L585), [612-612](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L612-L612) ):

```solidity
578:                     incomingAsk.ercAmount = 0;

585:                     highestBid.ercAmount = 0;

612:                     incomingAsk.ercAmount = 0;
```

- *LibSRUtil.sol* ( [138-138](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L138-L138), [148-148](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L148-L148) ):

```solidity
138:         short.tokenId = 0;

148:         nft.shortOrderId = 0;
```

- *UniswapOracleLibrary.sol* ( [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L56-L56) ):

```solidity
56:         secondsAgos[1] = 0;
```

</details>

### [N-36] Use the latest Solidity version

Upgrading to the [latest solidity version](https://github.com/ethereum/solc-js/tags) (0.8.19 for L2s) can optimize gas usage, take advantage of new features and improve overall contract efficiency. Where possible, based on compatibility requirements, it is recommended to use newer/latest solidity version to take advantage of the latest optimizations and features.

<details>
<summary>There are 12 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *BridgeRouterFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *ExitShortFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *PrimaryLiquidationFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *RedemptionFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *ShortOrdersFacet.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *LibBridgeRouter.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *LibBytes.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *LibOracle.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *LibOrders.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *LibSRUtil.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

- *UniswapOracleLibrary.sol* ( [2](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L2) ):

```solidity
2: pragma solidity 0.8.21;
```

</details>

### [N-37] Consider using named function arguments

When calling functions with multiple arguments, consider using [named function parameters](https://docs.soliditylang.org/en/latest/control-structures.html#function-calls-with-named-parameters), rather than positional ones.

There are 2 instances:

- *ExitShortFacet.sol* ( [187-187](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L187-L187) ):

```solidity
187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
```

- *PrimaryLiquidationFacet.sol* ( [188-188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L188-L188) ):

```solidity
188:             IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);
```

### [N-38] Named returns are recommended

Using named returns makes the code more self-documenting, makes it easier to fill out NatSpec, and in some cases can save gas. The cases below are where there currently is at most one return statement, which is ideal for named returns.

<details>
<summary>There are 17 instances (click to show):</summary>

- *BridgeRouterFacet.sol* ( [40-40](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L40-L40), [51-51](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L51-L51), [169-169](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L169-L169) ):

```solidity
40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {

51:     function getBridges(uint256 vault) external view returns (address[] memory) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {
```

- *PrimaryLiquidationFacet.sol* ( [47-52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L52), [122-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L122-L124), [229-229](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L229-L229) ):

```solidity
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)

122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {
```

- *RedemptionFacet.sol* ( [31-34](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L31-L34) ):

```solidity
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32:         internal
33:         view
34:         returns (bool)
```

- *LibBridgeRouter.sol* ( [39-41](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L39-L41) ):

```solidity
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40:         internal
41:         returns (uint88)
```

- *LibBytes.sol* ( [11-11](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L11-L11) ):

```solidity
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
```

- *LibOracle.sol* ( [19-19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L19-L19), [168-168](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L168-L168) ):

```solidity
19:     function getOraclePrice(address asset) internal view returns (uint256) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
```

- *LibOrders.sol* ( [35-35](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L35-L35), [55-58](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L55-L58), [78-78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L78-L78), [362-367](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L362-L367), [985-985](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L985-L985), [989-989](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L989-L989) ):

```solidity
35:     function convertCR(uint16 cr) internal pure returns (uint256) {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
56:         internal
57:         view
58:         returns (STypes.Order[] memory)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

362:     function findPrevOfIncomingId(
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {
```

</details>

### [N-39] Consider using the `using`-`for` syntax

The `using`-`for` [syntax](https://docs.soliditylang.org/en/latest/contracts.html#using-for) is the more common way of calling library functions.

<details>
<summary>There are 197 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [48-48](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L48-L48), [87-87](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L87-L87), [87-87](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L87-L87), [90-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L90-L90), [98-98](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L98-L98), [108-108](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L108-L108), [108-108](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L108-L108), [110-110](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L110-L110), [114-114](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L114-L114), [136-136](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L136-L136), [143-143](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L143-L143), [162-162](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L162-L162), [166-166](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L166-L166), [174-174](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L174-L174), [177-177](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L177-L177), [190-190](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L190-L190), [199-199](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L199-L199), [226-226](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L226-L226), [227-227](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L227-L227), [243-252](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L243-L252), [288-288](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L288-L288), [332-332](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L332-L332), [335-335](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L335-L335) ):

```solidity
48:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();

90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();

98:         incomingBid.creationTime = LibOrders.getOffsetTime();

108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);

108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);

110:             b.oraclePrice = LibOracle.getPrice(asset);

114:             LibOrders.addBid(asset, incomingBid, orderHintArray);

136:         uint256 minBidEth = LibAsset.minBidEth(asset);

143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);

162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);

166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);

174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);

177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);

190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {

199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);

226:             uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR));

227:             LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);

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

288:         LibOrders.updateSellOrdersOnMatch(asset, b);

332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);

335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);
```

- *BridgeRouterFacet.sol* ( [64-64](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L64-L64), [72-72](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L72-L72), [83-83](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L83-L83), [90-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L90-L90), [102-102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L102-L102), [110-110](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L110-L110), [122-122](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L122-L122), [134-134](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L134-L134), [143-143](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L143-L143), [164-164](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L164-L164) ):

```solidity
64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

72:         emit Events.Deposit(bridge, msg.sender, dethAmount);

83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

90:         emit Events.DepositEth(bridge, msg.sender, dethAmount);

102:         if (dethAmount == 0) revert Errors.ParameterIsZero();

110:                 uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);

122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);

134:         if (dethAmount == 0) revert Errors.ParameterIsZero();

143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);

164:             if (vault == 0) revert Errors.InvalidBridge();
```

- *ExitShortFacet.sol* ( [53-53](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L53-L53), [61-61](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L61-L61), [62-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L62-L62), [67-73](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L67-L73), [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L75-L75), [99-99](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L99-L99), [103-103](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L103-L103), [113-113](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L113-L113), [115-115](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L115-L115), [120-126](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L120-L126), [128-128](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L128-L128), [152-152](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L152-L152), [158-164](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L158-L164), [174-174](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L174-L174), [178-178](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L178-L178), [188-188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L188-L188), [196-196](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L196-L196), [197-197](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L197-L197), [201-201](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L201-L201), [201-201](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L201-L201), [204-204](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L204-L204), [208-208](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L208-L208), [210-210](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L210-L210) ):

```solidity
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();

61:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

62:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);

67:         LibSRUtil.checkShortMinErc({
68:             asset: asset,
69:             initialStatus: initialStatus,
70:             shortOrderId: shortOrderId,
71:             shortRecordId: id,
72:             shorter: msg.sender
73:         });

75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);

99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();

103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();

113:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

115:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);

120:         LibSRUtil.checkShortMinErc({
121:             asset: asset,
122:             initialStatus: initialStatus,
123:             shortOrderId: shortOrderId,
124:             shortRecordId: id,
125:             shorter: msg.sender
126:         });

128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);

152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray);

158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
159:             asset: asset,
160:             initialStatus: short.status,
161:             shortOrderId: shortOrderId,
162:             shortRecordId: id,
163:             shorter: msg.sender
164:         });

174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();

178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();

188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();

196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt);

197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();

204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();

208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt);

210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
```

- *PrimaryLiquidationFacet.sol* ( [54-54](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L54-L54), [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L56-L56), [59-65](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L59-L65), [68-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L68-L68), [73-73](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L73-L73), [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L75-L75), [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L75-L75), [87-87](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L87-L87), [109-109](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L109-L109), [126-126](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L126-L126), [134-134](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L134-L134), [135-135](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L135-L135), [137-137](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L137-L137), [138-138](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L138-L138), [139-139](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L139-L139), [174-174](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L174-L174), [230-230](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L230-L230), [246-246](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L246-L246), [247-247](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L247-L247), [260-260](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L260-L260), [265-265](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L265-L265), [267-276](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L267-L276), [282-288](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L282-L288) ):

```solidity
54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();

56:         if (shortHintArray.length > 10) revert Errors.TooManyHints();

59:         LibSRUtil.checkCancelShortOrder({
60:             asset: asset,
61:             initialStatus: s.shortRecords[asset][shorter][id].status,
62:             shortOrderId: shortOrderId,
63:             shortRecordId: id,
64:             shorter: shorter
65:         });

68:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);

73:         if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {

75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();

75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();

87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);

109:             revert Errors.NoSells();

126:         LibShortRecord.updateErcDebt(asset, shorter, id);

134:             m.penaltyCR = LibAsset.penaltyCR(asset);

135:             m.oraclePrice = LibOracle.getPrice(asset);

137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);

138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);

139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);

174:                 revert Errors.CannotSocializeDebt();

230:         if (a > type(uint88).max) revert Errors.InvalidAmount();

246:             LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt);

247:             LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);

260:             LibSRUtil.disburseCollateral(m.asset, m.shorter, decreaseCol, m.short.dethYieldRate, m.short.updatedAt);

265:                 LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);

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

282:             LibSRUtil.checkShortMinErc({
283:                 asset: m.asset,
284:                 initialStatus: m.short.status,
285:                 shortOrderId: m.shortOrderId,
286:                 shortRecordId: m.short.id,
287:                 shorter: m.shorter
288:             });
```

- *RedemptionFacet.sol* ( [62-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L62-L62), [66-66](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L66-L66), [68-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L68-L68), [70-70](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L70-L70), [73-73](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L73-L73), [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L75-L75), [112-112](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L112-L112), [113-113](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L113-L113), [138-138](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L138-L138), [143-143](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L143-L143), [146-146](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L146-L146), [154-154](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L154-L154), [202-202](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L202-L202), [205-205](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L205-L205), [208-208](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L208-L208), [210-210](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L210-L210), [229-229](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L229-L229), [235-235](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L235-L235), [237-237](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L237-L237), [237-237](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L237-L237), [240-240](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L240-L240), [244-244](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L244-L244), [250-250](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L250-L250), [251-251](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L251-L251), [284-284](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L284-L284), [289-291](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L289-L291), [290-290](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L290-L290), [290-290](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L290-L290), [299-299](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L299-L299), [314-314](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L314-L314), [315-315](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L315-L315), [315-315](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L315-L315), [318-318](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L318-L318), [333-333](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L333-L333), [353-353](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L353-L353), [354-354](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L354-L354), [354-354](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L354-L354), [358-358](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L358-L358), [361-361](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L361-L361), [376-376](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L376-L376), [377-377](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L377-L377), [387-387](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L387-L387), [396-396](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L396-L396), [401-401](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L401-L401) ):

```solidity
62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();

66:         uint256 minShortErc = LibAsset.minShortErc(p.asset);

68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();

70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();

73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();

75:         p.oraclePrice = LibOracle.getPrice(p.asset);

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();

113:                 LibOrders.cancelShort(asset, p.shortOrderId);

138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);

143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();

146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);

154:         uint32 protocolTime = LibOrders.getOffsetTime();

202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();

205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();

208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();

210:         emit Events.ProposeRedemption(p.asset, msg.sender);

229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();

235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();

237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();

240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

244:                 revert Errors.CannotDisputeWithRedeemerProposal();

250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);

251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();

284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);

289:             uint256 penaltyPct = LibOrders.min(
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );

290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

299:             revert Errors.InvalidRedemptionDispute();

314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

333:         emit Events.ClaimRedemption(asset, msg.sender);

353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);

361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();

376:             LibSRUtil.disburseCollateral(asset, shorter, collateral, shortRecord.dethYieldRate, shortRecord.updatedAt);

377:             LibShortRecord.deleteShortRecord(asset, shorter, shortId);

387:         uint32 protocolTime = LibOrders.getOffsetTime();

396:         newBaseRate = LibOrders.min(newBaseRate, 1 ether); // cap baseRate at a maximum of 100%

401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);
```

- *ShortOrdersFacet.sol* ( [48-48](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L48-L48), [50-50](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L50-L50), [52-52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L52-L52), [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L56-L56), [56-56](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L56-L56), [58-58](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L58-L58), [59-59](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L59-L59), [62-62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L62-L62), [69-69](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L69-L69), [76-76](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L76-L76), [76-76](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L76-L76), [79-79](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L79-L79), [80-80](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L80-L80), [81-81](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L81-L81), [86-86](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L86-L86), [88-88](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L88-L88) ):

```solidity
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

50:         uint256 cr = LibOrders.convertCR(shortOrderCR);

52:             revert Errors.InvalidCR();

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);

58:         p.minAskEth = LibAsset.minAskEth(asset);

59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();

62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();

69:         incomingShort.creationTime = LibOrders.getOffsetTime();

76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);

76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);

79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);

80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {

81:             revert Errors.BelowRecoveryModeCR();

86:             LibOrders.addShort(asset, incomingShort, orderHintArray);

88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
```

- *LibBridgeRouter.sol* ( [75-75](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L75-L75), [105-105](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L105-L105), [118-118](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L118-L118), [122-122](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L122-L122) ):

```solidity
75:                     revert Errors.MustUseExistingBridgeCredit();

105:                     revert Errors.MustUseExistingBridgeCredit();

118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);

122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);
```

- *LibBytes.sol* ( [12-12](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L12-L12) ):

```solidity
12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer);
```

- *LibOracle.sol* ( [25-25](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L25-L25), [60-60](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L60-L60), [128-128](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L128-L128), [134-134](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L134-L134), [139-139](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L139-L139), [169-169](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L169-L169) ):

```solidity
25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset();

60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

128:         if (invalidFetchData) revert Errors.InvalidPrice();

134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice();

139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
```

- *LibOrders.sol* ( [142-142](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L142-L142), [218-218](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L218-L218), [301-301](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L301-L301), [608-608](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L608-L608), [631-633](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L631-L633), [642-642](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L642-L642), [679-688](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L679-L688), [718-718](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L718-L718), [730-730](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L730-L730), [778-778](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L778-L778), [804-804](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L804-L804), [813-813](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L813-L813), [850-850](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L850-L850), [859-859](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L859-L859), [874-874](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L874-L874), [887-887](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L887-L887), [889-889](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L889-L889), [901-901](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L901-L901), [903-903](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L903-L903), [911-911](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L911-L911), [913-922](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L913-L922), [942-942](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L942-L942), [959-959](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L959-L959) ):

```solidity
142:         uint88 eth = order.ercAmount.mulU88(order.price).mulU88(LibOrders.convertCR(order.shortOrderCR));

218:         emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount);

301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType);

608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {

631:         emit Events.MatchOrder(
632:             asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, matchTotal.fillEth, matchTotal.fillErc
633:         );

642:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);

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

718:             matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR));

730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset);

778:             revert Errors.BadShortHint();

804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset);

813:         uint256 savedPrice = LibOracle.getPrice(asset);

850:         revert Errors.BadHintIdArray();

859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();

874:             revert Errors.NotActiveOrder();

887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();

889:         uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

901:             LibShortRecord.deleteShortRecord(asset, shorter, shortRecordId);

903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset));

911:                     uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

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

942:             uint256 savedPrice = LibOracle.getPrice(asset);

959:         uint256 savedPrice = LibOracle.getPrice(asset);
```

- *LibSRUtil.sol* ( [40-40](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L40-L40), [57-57](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L57-L57), [61-61](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L61-L61), [64-64](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L64-L64), [66-66](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L66-L66), [79-79](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L79-L79), [84-84](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L84-L84), [90-90](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L90-L90), [95-95](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L95-L95), [98-98](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L98-L98), [109-109](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L109-L109), [130-130](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L130-L130), [131-131](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L131-L131), [135-135](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L135-L135), [139-139](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L139-L139), [140-140](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L140-L140), [142-144](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L142-L144) ):

```solidity
40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;

57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

61:                 LibOrders.cancelShort(asset, shortOrderId);

64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {

66:                 LibOrders.cancelShort(asset, shortOrderId);

79:         uint256 minShortErc = LibAsset.minShortErc(asset);

84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

90:                     LibOrders.cancelShort(asset, shortOrderId);

95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();

98:             revert Errors.CannotLeaveDustAmount();

109:         uint256 recoveryCR = LibAsset.recoveryCR(asset);

130:         if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled();

131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

135:             LibOrders.cancelShort(asset, nft.shortOrderId);

139:         LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId);

140:         LibBridgeRouter.transferBridgeCredit(asset, from, to, short.collateral);

142:         uint8 id = LibShortRecord.createShortRecord(
143:             asset, to, SR.FullyFilled, short.collateral, short.ercDebt, short.ercDebtRate, short.dethYieldRate, tokenId
144:         );
```

- *UniswapOracleLibrary.sol* ( [33-33](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L33-L33), [39-39](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L39-L39), [39-39](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L39-L39), [41-41](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L41-L41), [43-43](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L43-L43), [43-43](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L43-L43), [52-52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L52-L52) ):

```solidity
33:         uint160 sqrtRatioX96 = TickMath.getSqrtRatioAtTick(tick);

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

41:             uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
```

</details>

### [N-40] Use a struct to encapsulate multiple function parameters

If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.

<details>
<summary>There are 7 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [40-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L40-L47), [65-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L65-L68), [77-85](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L77-L85) ):

```solidity
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

77:     function _createBid(
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

- *ExitShortFacet.sol* ( [142-149](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L142-L149) ):

```solidity
142:     function exitShort(
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
```

- *PrimaryLiquidationFacet.sol* ( [47-52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L52) ):

```solidity
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
```

- *RedemptionFacet.sol* ( [224-228](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L224-L228) ):

```solidity
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
```

- *ShortOrdersFacet.sol* ( [35-42](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L35-L42) ):

```solidity
35:     function createLimitShort(
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
```

</details>

### [N-41] Returning a struct instead of a bunch of variables is better

If a function returns [too many variables](https://docs.soliditylang.org/en/v0.8.21/contracts.html#returning-multiple-values), replacing them with a struct can improve code readability, maintainability and reusability.

<details>
<summary>There are 8 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [40-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L40-L47), [65-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L65-L68), [77-85](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L77-L85), [130-135](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L130-L135), [275-280](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L275-L280) ):

```solidity
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

77:     function _createBid(
78:         address sender,
79:         address asset,
80:         uint80 price,
81:         uint88 ercAmount,
82:         bool isMarketOrder,
83:         MTypes.OrderHint[] memory orderHintArray,
84:         uint16[] memory shortHintArray
85:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

130:     function bidMatchAlgo(
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {

275:     function matchIncomingBid(
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
```

- *BridgeRouterFacet.sol* ( [156-156](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L156-L156) ):

```solidity
156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {
```

- *PrimaryLiquidationFacet.sol* ( [47-52](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L52) ):

```solidity
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
```

- *UniswapOracleLibrary.sol* ( [11-14](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L11-L14) ):

```solidity
11:     function observe(uint32[] calldata secondsAgos)
12:         external
13:         view
14:         returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
```

</details>

### [N-42] Contract variables should have comments

Consider adding some comments on non-public contract variables to explain what they are supposed to do. This will help for future code reviews.

There are 4 instances:

- *BridgeRouterFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L26-L26), [27-27](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L27-L27) ):

```solidity
26:     address private immutable rethBridge;

27:     address private immutable stethBridge;
```

- *ExitShortFacet.sol* ( [26-26](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L26) ):

```solidity
26:     address private immutable dusd;
```

- *PrimaryLiquidationFacet.sol* ( [28-28](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) ):

```solidity
28:     address private immutable dusd;
```

### [N-43] Function state mutability can be restricted to view

Function state mutability can be restricted to view

There are 2 instances:

- *LibOrders.sol* ( [320-326](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L320-L326), [532-537](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L532-L537) ):

```solidity
320:     function _reuseOrderIds(
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

532:     function _updateOrders(
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {
```

### [N-44] Inconsistent spacing in comments

The comments below are in the `//x` format, which differs from the commonly used idiomatic comment syntax of `//<space>x`. It is recommended to use a consistent comment syntax throughout.

There are 2 instances:

- *PrimaryLiquidationFacet.sol* ( [92](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L92) ):

```solidity
92:     //PRIVATE FUNCTIONS
```

- *LibOrders.sol* ( [514](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L514) ):

```solidity
514:                 //@handles moving backwards only.
```

### [N-45] Missing event for critical changes

Events should be emitted when critical changes are made to the contracts.

<details>
<summary>There are 13 instances (click to show):</summary>

- *PrimaryLiquidationFacet.sol* ( [122-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L122-L124) ):

```solidity
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)
```

- *LibBridgeRouter.sol* ( [21-36](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L21-L36), [198-202](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L198-L202) ):

```solidity
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
22:         AppStorage storage s = appStorage();
23:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];
24: 
25:         if (vault == VAULT.ONE) {
26:             // Only VAULT.ONE has mixed LST
27:             if (bridgePointer == VAULT.BRIDGE_RETH) {
28:                 VaultUser.bridgeCreditReth += amount;
29:             } else {
30:                 VaultUser.bridgeCreditSteth += amount;
31:             }
32:         }
33: 
34:         VaultUser.ethEscrowed += amount;
35:         s.vault[vault].dethTotal += amount;
36:     }

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
199:         AppStorage storage s = appStorage();
200:         s.vaultUser[vault][msg.sender].ethEscrowed -= (amount + fee);
201:         s.vault[vault].dethTotal -= amount;
202:     }
```

- *LibOracle.sol* ( [149-153](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L149-L153) ):

```solidity
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
150:         AppStorage storage s = appStorage();
151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
152:         s.bids[asset][C.HEAD].creationTime = oracleTime;
153:     }
```

- *LibOrders.sol* ( [82-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L82-L82), [103-119](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L103-L119), [128-144](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L128-L144), [474-490](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L474-L490), [532-545](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L532-L545), [728-728](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L728-L728), [783-800](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L783-L800), [810-824](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L810-L824) ):

```solidity
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

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

474:     function updateBidOrdersOnMatch(
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled
479:     ) internal {
480:         // BEFORE: HEAD <-> ... <-> (ID) <-> NEXT
481:         // AFTER : HEAD <------------------> NEXT
482:         if (isOrderFullyFilled) {
483:             _updateOrders(orders, asset, C.HEAD, id);
484:         } else {
485:             // BEFORE: HEAD <-> ... <-> (ID)
486:             // AFTER : HEAD <---------> (ID)
487:             orders[asset][id].prevId = C.HEAD;
488:             orders[asset][C.HEAD].nextId = id;
489:         }
490:     }

532:     function _updateOrders(
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {
538:         // BEFORE: FIRST <-> ... <-> (LAST) <-> NEXT
539:         // AFTER : FIRST <--------------------> NEXT
540:         uint16 nextAskId = orders[asset][lastMatchedId].nextId;
541:         if (nextAskId != C.TAIL) {
542:             orders[asset][nextAskId].prevId = headId;
543:         }
544:         orders[asset][headId].nextId = nextAskId;
545:     }

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

783:     function updateOracleAndStartingShortViaThreshold(
784:         address asset,
785:         uint256 savedPrice,
786:         STypes.Order memory incomingOrder,
787:         uint16[] memory shortHintArray
788:     ) internal {
789:         bool orderPriceGtThreshold;
790:         // @dev handle .5% deviations in either directions
791:         if (incomingOrder.price >= savedPrice) {
792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
793:         } else {
794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
795:         }
796: 
797:         if (orderPriceGtThreshold) {
798:             _updateOracleAndStartingShort(asset, shortHintArray);
799:         }
800:     }

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
```

- *LibSRUtil.sol* ( [151-162](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L151-L162) ):

```solidity
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
152:         AppStorage storage s = appStorage();
153: 
154:         // Distribute ercDebt
155:         uint64 ercDebtRate = s.asset[asset].ercDebtRate;
156:         uint88 ercDebt = short.ercDebt.mulU88(ercDebtRate - short.ercDebtRate);
157: 
158:         if (ercDebt > 0) {
159:             short.ercDebt += ercDebt;
160:             short.ercDebtRate = ercDebtRate;
161:         }
162:     }
```

</details>

### [N-46] Duplicated `require()`/`revert()` checks should be refactored

Refactoring duplicate `require()`/`revert()` checks into a modifier or function can make the code more concise, readable and maintainable, and less likely to make errors or omissions when modifying the `require()` or `revert()`.

There are 9 instances:

- *BridgeRouterFacet.sol* ( [64-64](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L64-L64), [102-102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L102-L102) ):

```solidity
/// @audit Duplicated on line 83
64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

/// @audit Duplicated on line 134
102:         if (dethAmount == 0) revert Errors.ParameterIsZero();
```

- *ExitShortFacet.sol* ( [53-53](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L53-L53) ):

```solidity
/// @audit Duplicated on line 99, 174
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();
```

- *RedemptionFacet.sol* ( [68-68](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L68-L68), [235-235](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L235-L235), [315-315](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L315-L315) ):

```solidity
/// @audit Duplicated on line 143
68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();

/// @audit Duplicated on line 251, 314, 353
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

/// @audit Duplicated on line 354
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
```

### [N-47] Consider adding emergency-stop functionality

Adding a way to quickly halt protocol functionality in an emergency, rather than having to pause individual contracts one-by-one, will make in-progress hack mitigation faster and much less stressful.

<details>
<summary>There are 6 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [20-20](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L20-L20) ):

```solidity
20: contract BidOrdersFacet is Modifiers {
```

- *BridgeRouterFacet.sol* ( [18-18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L18-L18) ):

```solidity
18: contract BridgeRouterFacet is Modifiers {
```

- *ExitShortFacet.sol* ( [19-19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L19-L19) ):

```solidity
19: contract ExitShortFacet is Modifiers {
```

- *PrimaryLiquidationFacet.sol* ( [21-21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) ):

```solidity
21: contract PrimaryLiquidationFacet is Modifiers {
```

- *RedemptionFacet.sol* ( [21-21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L21-L21) ):

```solidity
21: contract RedemptionFacet is Modifiers {
```

- *ShortOrdersFacet.sol* ( [18-18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L18-L18) ):

```solidity
18: contract ShortOrdersFacet is Modifiers {
```

</details>

### [N-48] Use the Modern Upgradeable Contract Paradigm

Modern smart contract development often employs upgradeable contract structures, utilizing proxy patterns like OpenZeppelin’s Upgradeable Contracts. This paradigm separates logic and state, allowing developers to amend and enhance the contract's functionality without altering its state or the deployed contract address. Transitioning to this approach enhances long-term maintainability.
Resolution: Adopt a well-established proxy pattern for upgradeability, ensuring proper initialization and employing transparent proxies to mitigate potential risks. Embrace comprehensive testing and audit practices, particularly when updating contract logic, to ensure state consistency and security are preserved across upgrades. This ensures your contract remains robust and adaptable to future requirements.

<details>
<summary>There are 6 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [20](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L20) ):

```solidity
20: contract BidOrdersFacet is Modifiers {
```

- *BridgeRouterFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L18) ):

```solidity
18: contract BridgeRouterFacet is Modifiers {
```

- *ExitShortFacet.sol* ( [19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L19) ):

```solidity
19: contract ExitShortFacet is Modifiers {
```

- *PrimaryLiquidationFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L21) ):

```solidity
21: contract PrimaryLiquidationFacet is Modifiers {
```

- *RedemptionFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L21) ):

```solidity
21: contract RedemptionFacet is Modifiers {
```

- *ShortOrdersFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L18) ):

```solidity
18: contract ShortOrdersFacet is Modifiers {
```

</details>

### [N-49] Large or complicated code bases should implement invariant tests

This includes: large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts.
Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold.
Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers may help significantly.

There is 1 instance:

- Global finding

### [N-50] The default value is manually set when it is declared

In instances where a new variable is defined, there is no need to set it to it's default value.

There are 6 instances:

- *RedemptionFacet.sol* ( [78-78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L78-L78), [242-242](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L242-L242), [321-321](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L321-L321) ):

```solidity
78:         for (uint8 i = 0; i < proposalInput.length; i++) {

242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {

321:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
```

- *LibBytes.sol* ( [18-18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L18-L18) ):

```solidity
18:         for (uint256 i = 0; i < slateLength; i++) {
```

- *LibOrders.sol* ( [71-71](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L71-L71), [743-743](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L743-L743) ):

```solidity
71:         for (uint256 i = 0; i < size; i++) {

743:             for (uint256 i = 0; i < shortHintArray.length;) {
```

### [N-51] Contracts should have all `public`/`external` functions exposed by `interface`s

All `external`/`public` functions should extend an `interface`. This is useful to ensure that the whole API is extracted and can be more easily integrated by other projects.

<details>
<summary>There are 6 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [20](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L20) ):

```solidity
20: contract BidOrdersFacet is Modifiers {
```

- *BridgeRouterFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L18) ):

```solidity
18: contract BridgeRouterFacet is Modifiers {
```

- *ExitShortFacet.sol* ( [19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L19) ):

```solidity
19: contract ExitShortFacet is Modifiers {
```

- *PrimaryLiquidationFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L21) ):

```solidity
21: contract PrimaryLiquidationFacet is Modifiers {
```

- *RedemptionFacet.sol* ( [21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L21) ):

```solidity
21: contract RedemptionFacet is Modifiers {
```

- *ShortOrdersFacet.sol* ( [18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L18) ):

```solidity
18: contract ShortOrdersFacet is Modifiers {
```

</details>

### [N-52] Top-level declarations should be separated by at least two lines

-

<details>
<summary>There are 39 instances (click to show):</summary>

- *BidOrdersFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L2-L4), [75-77](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L75-L77), [356-358](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L356-L358) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

75:     }
76: 
77:     function _createBid(

356:     }
357: 
358:     function _shortDirectionHandler(
```

- *BridgeRouterFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";
```

- *ExitShortFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L2-L4), [211-213](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L211-L213) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";

211:     }
212: 
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {
```

- *PrimaryLiquidationFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L2-L4), [227-229](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L227-L229) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";

227:     }
228: 
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {
```

- *RedemptionFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L2-L4), [19-21](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L19-L21) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";

19: import {console} from "contracts/libraries/console.sol";
20: 
21: contract RedemptionFacet is Modifiers {
```

- *ShortOrdersFacet.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";
```

- *LibBridgeRouter.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {IBridge} from "contracts/interfaces/IBridge.sol";
```

- *LibBytes.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L2-L4) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {MTypes} from "contracts/libraries/DataTypes.sol";
```

- *LibOracle.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L2-L4), [67-69](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L67-L69), [115-117](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L115-L117), [129-131](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L129-L131) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256} from "contracts/libraries/PRBMathHelper.sol";

67:     }
68: 
69:     function baseOracleCircuitBreaker(

115:     }
116: 
117:     function oracleCircuitBreaker(

129:     }
130: 
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
```

- *LibOrders.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L2-L4), [33-35](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L33-L35), [53-55](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L53-L55), [76-78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L76-L78), [80-82](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L80-L82), [101-103](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L101-L103), [626-628](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L626-L628), [726-728](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L726-L728), [808-810](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L808-L810), [824-826](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L824-L826), [866-868](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L866-L868), [880-882](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L880-L882), [983-985](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L983-L985), [987-989](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L987-L989) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U256, U104, U80, U88, U16} from "contracts/libraries/PRBMathHelper.sol";

33:     }
34: 
35:     function convertCR(uint16 cr) internal pure returns (uint256) {

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
```

- *LibSRUtil.sol* ( [2-4](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L2-L4), [47-49](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L47-L49), [70-72](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L70-L72), [100-102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L100-L102), [122-124](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L122-L124), [149-151](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L149-L151) ):

```solidity
2: pragma solidity 0.8.21;
3: 
4: import {U88, U256} from "contracts/libraries/PRBMathHelper.sol";

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

- *UniswapOracleLibrary.sol* ( [8-10](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L8-L10), [45-47](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L45-L47) ):

```solidity
8: import {U256} from "contracts/libraries/PRBMathHelper.sol";
9: 
10: interface IUniswapV3Pool {

45:     }
46: 
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
```

</details>

### [N-53] Consider adding formal verification proofs

Formal verification is the act of proving or disproving the correctness of intended algorithms underlying a system with respect to a certain formal specification/property/invariant, using formal methods of mathematics.

Some tools that are currently available to perform these tests on smart contracts are [SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html) and [Certora Prover](https://www.certora.com/).

There are 12 instances:

- [*BidOrdersFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol)

- [*BridgeRouterFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol)

- [*ExitShortFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol)

- [*PrimaryLiquidationFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol)

- [*RedemptionFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol)

- [*ShortOrdersFacet.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol)

- [*LibBridgeRouter.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol)

- [*LibBytes.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol)

- [*LibOracle.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol)

- [*LibOrders.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol)

- [*LibSRUtil.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol)

- [*UniswapOracleLibrary.sol*](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol)

### [N-54] Use scopes sparingly

The use of scoped blocks, denoted by `{}` without a preceding control structure like `if`, `for`, etc., allows for the creation of isolated scopes within a function. While this can be useful for managing memory and preventing naming conflicts, it should be used sparingly. Excessive use of these scope blocks can obscure the code's logic flow and make it more difficult to understand, impeding code maintainability. As a best practice, only employ scoped blocks when necessary for memory management or to avoid clear naming conflicts. Otherwise, aim for clarity and simplicity in your code structure for optimal readability and maintainability.

There are 5 instances:

- *ExitShortFacet.sol* ( [101-102](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L101-L102), [176-177](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L176-L177) ):

```solidity
101:         {
102:             STypes.AssetUser storage AssetUser = s.assetUser[asset][msg.sender];

176:         {
177:             uint256 ethAmount = price.mul(e.buybackAmount);
```

- *PrimaryLiquidationFacet.sol* ( [127-128](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L127-L128) ):

```solidity
127:         {
128:             MTypes.PrimaryLiquidation memory m;
```

- *LibOrders.sol* ( [750-751](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L750-L751), [908-909](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L908-L909) ):

```solidity
750:                 {
751:                     O shortOrderType = short.orderType;

908:                 {
909:                     STypes.Vault storage Vault = s.vault[vault];
```
