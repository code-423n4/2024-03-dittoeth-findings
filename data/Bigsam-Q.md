
[L-01] Incorrect Check for `secondsAgo` Value in Contract

**Introduction:**  
The contract contains an incorrect check for the `secondsAgo` value, which deviates from the standard implemented by Uniswap. The current check `if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();` is not effectively validating the `secondsAgo` value as intended. 

**GitHub Code:**  
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L52C1-L52C68

**Explanation:**  
Uniswap's standard code implements the following check for `secondsAgo`:
```solidity
require(secondsAgo != 0, 'BP');
```
This check ensures that `secondsAgo` is a positive value and not zero. However, the contract's current implementation uses:
```solidity
if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
```
Given that `secondsAgo` is declared as `uint32`, it can never accept a negative value, making the check ineffective in validating the value as intended.

**Code:**  
**Current Code in Contract:**  
```solidity
if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
```
**Mitigation Code:**  
Replace the current check with the following to align with Uniswap's standard:
```solidity
if (secondsAgo == 0) revert Errors.InvalidTWAPSecondsAgo();
```

---
