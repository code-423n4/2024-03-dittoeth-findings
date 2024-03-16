# Missing checks for `address(0)`
In Solidity, the Ethereum address `0x0000000000000000000000000000000000000000` is known as the "zero address". This address has significance because it's the default value for uninitialized address variables and is often used to represent an invalid or non-existent address. The "
Missing zero address control" issue arises when a Solidity smart contract does not properly check or prevent interactions with the zero address, leading to unintended behavior.
For instance, a contract might allow tokens to be sent to the zero address without any checks, which essentially burns those tokens as they become irretrievable. While sometimes this is intentional, without proper control or checks, accidental transfers could occur.    


```solidity
Path: ./contracts/facets/PrimaryLiquidationFacet.sol

31:        dusd = _dusd;	// @audit-issue
```
[31](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L31-L31), 


```solidity
Path: ./contracts/facets/BridgeRouterFacet.sol

30:        rethBridge = _rethBridge;	// @audit-issue

31:        stethBridge = _stethBridge;	// @audit-issue
```
[30](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/BridgeRouterFacet.sol#L30-L30), [31](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/BridgeRouterFacet.sol#L31-L31), 

#### Recommendation
It is strongly recommended to implement checks to prevent the zero address from being set during the initialization of contracts. This can be achieved by adding require statements that ensure address parameters are not the zero address. 



# Unsafe `uint` to `int` conversion
The `int` type in Solidity uses the [two's complement system](https://en.wikipedia.org/wiki/Two%27s_complement), so it is possible to accidentally overflow a very large `uint` to an `int`, even if they share the same number of bytes (e.g. a `uint256 number > type(uint128).max` will overflow a `int256` cast).

Consider using the [SafeCast](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeCast.sol) library to prevent any overflows.



```solidity
Path: ./contracts/libraries/UniswapOracleLibrary.sol

62:        int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));	// @audit-issue: Variable `secondsAgo` is type `uint32` and it is casted to `int32`

65:        if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {	// @audit-issue: Variable `secondsAgo` is type `uint32` and it is casted to `int32`
```
[62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/UniswapOracleLibrary.sol#L62-L62), [65](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/UniswapOracleLibrary.sol#L65-L65), 


#### Recommendation

To prevent potential overflow issues when converting from `uint` to `int` in Solidity, consider using the SafeCast library. This library helps ensure safe type conversions and avoids unexpected behavior, especially when dealing with very large `uint` values that could overflow when cast to `int`.


# Vulnerable versions of packages are being used
This project is using specific package versions which are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities.



```solidity
Path: ./contracts/facets/ShortOrdersFacet.sol
- [CVE-2023-40014](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-40014) - **MEDIUM** - (`openzeppelin/contracts >=4.0.0 <4.9.3`): OpenZeppelin Contracts is a library for secure smart contract development. Starting in version 4.0.0 and prior to version 4.9.3, contracts using `ERC2771Context` along with a custom trusted forwarder may see `_msgSender` return `address(0)` in calls that originate from the forwarder with calldata shorter than 20 bytes. This combination of circumstances does not appear to be common, in particular it is not the case for `MinimalForwarder` from OpenZeppelin Contracts, or any deployed forwarder the team is aware of, given that the signer address is appended to all calls that originate from these forwarders. The problem has been patched in v4.9.3.

```

#### Recommendation
Consider updating packages to safest version.




# Unnecessary Assert
Unnecessary `assert` statements in Solidity contracts can have several detrimental impacts on code readability, gas efficiency, and overall contract functionality. `assert` statements are typically used to check for conditions that should never occur under normal circumstances. While they can be valuable for catching unexpected errors and halting contract execution, their misuse can lead to unnecessary complexity and increased gas costs.


```solidity
Path: ./contracts/facets/RedemptionFacet.sol

397:        assert(newBaseRate > 0); // Base rate is always non-zero after redemption	// @audit-issue
```
[397](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L397-L397), 


```solidity
Path: ./contracts/libraries/LibSRUtil.sol

62:                assert(shortRecord.status != SR.PartialFill);	// @audit-issue
```
[62](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibSRUtil.sol#L62-L62), 


#### Recommendation

Use 'assert' statements in Solidity judiciously, reserving them for conditions that indicate critical and unforeseen errors. Avoid overuse to maintain code clarity and prevent unnecessary gas consumption due to these costly checks.





# Unneeded initializations of integer variable to `0`.
In Solidity, it is common practice to initialize variables with default values when declaring them. However, initializing integer variables to `0` when they are not subsequently used in the code can lead to unnecessary gas consumption and code clutter. This issue points out instances where such initializations are present but serve no functional purpose.

```solidity
Path: ./contracts/facets/RedemptionFacet.sol

78:        for (uint8 i = 0; i < proposalInput.length; i++) {	// @audit-issue

242:        for (uint256 i = 0; i < decodedProposalData.length; i++) {	// @audit-issue

321:        for (uint256 i = 0; i < decodedProposalData.length; i++) {	// @audit-issue
```
[78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L78-L78), [242](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L242-L242), [321](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L321-L321), 


```solidity
Path: ./contracts/libraries/LibBytes.sol

18:        for (uint256 i = 0; i < slateLength; i++) {	// @audit-issue
```
[18](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBytes.sol#L18-L18), 


```solidity
Path: ./contracts/libraries/LibOrders.sol

71:        for (uint256 i = 0; i < size; i++) {	// @audit-issue

743:            for (uint256 i = 0; i < shortHintArray.length;) {	// @audit-issue
```
[71](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L71-L71), [743](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L743-L743), 


#### Recommendation


It is recommended not to initialize integer variables to `0` to save some Gas.



# The `nonReentrant modifier` should occur before all other modifiers
In Solidity, the order in which modifiers are applied to a function can significantly impact the function's behavior and security. The `nonReentrant` modifier is crucial for preventing reentrancy attacks, a common vulnerability in smart contracts. This modifier should be the first in the list of applied modifiers to ensure that the reentrancy check is performed before any other logic in the function. Placing `nonReentrant` after other modifiers could potentially lead to security weaknesses, as other modifiers might perform state changes or external calls before the reentrancy protection takes effect. Therefore, correct positioning of the `nonReentrant` modifier is essential for maintaining the integrity and security of the function and, by extension, the entire contract.


```solidity
Path: ./contracts/facets/ShortOrdersFacet.sol

35:    function createLimitShort(
36:        address asset,
37:        uint80 price,
38:        uint88 ercAmount,
39:        MTypes.OrderHint[] memory orderHintArray,
40:        uint16[] memory shortHintArray,
41:        uint16 shortOrderCR
42:    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {	// @audit-issue
```
[42](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/ShortOrdersFacet.sol#L35-L42), 


```solidity
Path: ./contracts/facets/PrimaryLiquidationFacet.sol

47:    function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
```
[50](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L47-L47), 


```solidity
Path: ./contracts/facets/RedemptionFacet.sol

56:    function proposeRedemption(
57:        address asset,
58:        MTypes.ProposalInput[] calldata proposalInput,
59:        uint88 redemptionAmount,
60:        uint88 maxRedemptionFee
61:    ) external isNotFrozen(asset) nonReentrant {	// @audit-issue

224:    function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)

310:    function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {	// @audit-issue

347:    function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
```
[61](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L56-L61), [227](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L224-L224), [310](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L310-L310), [350](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L347-L347), 


#### Recommendation

To ensure the effectiveness of the `nonReentrant` modifier in protecting against reentrancy, it should be placed as the first modifier in a function's list of modifiers, before all other modifiers. This helps prevent reentrancy attacks from being triggered by other modifiers.


# Unused import
The identifier is imported but never used within the file.

```solidity
Path: ./contracts/facets/RedemptionFacet.sol

19:import {console} from "contracts/libraries/console.sol";	// @audit-issue: console not used in the contract.
```
[19](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L19-L19), 


#### Recommendation

Regularly review your Solidity code to remove unused imports. This practice declutters the codebase, making it easier to understand and maintain. In addition, consider using tools or IDE features that can automatically detect and highlight unused imports for cleanup. Keeping imports limited to only what is necessary helps maintain a clear understanding of the contract's dependencies and reduces potential confusion for developers working on or reviewing the code.

