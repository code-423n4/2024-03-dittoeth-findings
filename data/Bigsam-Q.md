
## [L-01] Incorrect Check for `secondsAgo` Value in Contract

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


## [L-02] Incorrect Return Variable in `getOrderId` Function

---

## Impact
The `getOrderId` function in the contract returns the `hintId` instead of the intended `_hintId`. 

## Proof of Concept
**GitHub Code:**  
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L447-L452

**Code Before Mitigation:**
```solidity

) internal view returns (uint16 _hintId) {
    while (true) {
        uint16 nextId = orders[asset][hintId].nextId;

        if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
            return hintId;
        }

        if (direction == C.PREV) {
            uint16 prevId = orders[asset][hintId].prevId;
            hintId = prevId;
        } else {
            hintId = nextId;
        }
    }
}
```

## Tools Used

Manual code analysis

## Recommended Mitigation Steps

To resolve the inconsistency in the return variable and avoid potential misunderstandings and errors, update the `getOrderId` function to set `_hintId = hintId` before returning it.

Implement the following mitigation code:

```solidity
_hintId = hintId;
return _hintId;
```

