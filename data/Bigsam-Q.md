
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

** Impact **
The `getOrderId` function in the contract returns the `hintId` instead of the intended `_hintId`. 


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

**Tools Used**

Manual code analysis

**Recommended Mitigation Steps**

To resolve the inconsistency in the return variable and avoid potential misunderstandings and errors, update the `getOrderId` function to set `_hintId = hintId` before returning it.

Implement the following mitigation code:

```solidity
_hintId = hintId;
return _hintId;
```

---

## [L-03] Code Duplication and Clean-Up Needed in Matching Logic

---

** Impact **
The repeated code segment from lines 564 to 569 is unnecessary duplication and affects the readability and maintainability of the contract. It can be cleaned up to streamline the code and improve its maintainability.

**GitHub Code:**  
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L556-L624

**Code Before Mitigation:**
```solidity
if (incomingAsk.price > s.bids[asset][startingId].price) {
    if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
        addSellOrder(incomingAsk, asset, orderHintArray);
    }
    return;
}
```

**Common Code Segment/duplicate:**
```solidity
else {
    updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
    matchIncomingSell(asset, incomingAsk, matchTotal);

    if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
        addSellOrder(incomingAsk, asset, orderHintArray);
    }
    return;
}
```

**Code in the while loop:**
```solidity
while (true) {
    STypes.Order memory highestBid = s.bids[asset][startingId];
    if (incomingAsk.price <= highestBid.price) {
        // Consider ask filled if only dust amount left
        if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
            updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
            incomingAsk.ercAmount = 0;
            matchIncomingSell(asset, incomingAsk, matchTotal);
            return;
        }
        matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
        if (incomingAsk.ercAmount > highestBid.ercAmount) {
            incomingAsk.ercAmount -= highestBid.ercAmount;
            highestBid.ercAmount = 0;
            matchOrder(s.bids, asset, highestBid.id);

            // loop
            startingId = highestBid.nextId;
            if (startingId == C.TAIL) {
                matchIncomingSell(asset, incomingAsk, matchTotal);

                if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
                    addSellOrder(incomingAsk, asset, orderHintArray);
                }
                s.bids[asset][C.HEAD].nextId = C.TAIL;
                return;
            }
        } else {
            if (incomingAsk.ercAmount == highestBid.ercAmount) {
                matchOrder(s.bids, asset, highestBid.id);
                updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
            } else {
                highestBid.ercAmount -= incomingAsk.ercAmount;
                s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
                updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
                // Check reduced dust threshold for existing limit orders
                if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
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
        return;
    }
}
```

**Mitigation Code:**
already present at line 616 to 623
```solidity
else {
    updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
    matchIncomingSell(asset, incomingAsk, matchTotal);

    if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
        addSellOrder(incomingAsk, asset, orderHintArray);
    }
    return;
}
```

** Tools Used **
Manual code analysis

** Recommended Mitigation Steps**
To clean up the code and improve its readability and maintainability, delete the repeated code segment from lines 564 to 569 as it is a duplication of the else statement in the while loop.

Implement the following mitigation code:

```solidity
// Remove the redundant code segment from lines 564 to 569
```

## [L-04]: Ether Representation in Arithmetic Operations in `LibOrder` Code, 
_Inconsistent Use of Ether in Arithmetic Operations in `LibOrder`_

---
**Github link **
1. https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L761
2. https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L960
3. https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L968

**Issue Identified:**  
The use of `ether` directly in `mul` and `div` external operations does not conform to the standard way of representing ether in the provided `LibOrder` code.

**Code Snippets:**

1.  
```solidity
bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
```

2.  
```solidity
Vault.dethTitheMod = (C.MAX_TITHE - Vault.dethTithePercent).mulU16(discountPct.div(0.04 ether));
```

3.  
```solidity
bool isDiscounted = savedPrice > price.mul(1.01 ether);
```

**Analysis:**

The direct use of `ether` in arithmetic calculations is not a standard practice in Solidity. The most consistent and error-free approach is to use the smallest denomination of ether, which is `wei`, in the calculations.

**Mitigation:**

To ensure consistent and accurate arithmetic calculations, the code should use the `wei` unit to represent the smallest denomination of ether. Below are the corrected versions of the provided code snippets:

1.  
```solidity
bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005e18) && prevShortPrice >= oraclePrice;
```

2.  
```solidity
Vault.dethTitheMod = (C.MAX_TITHE - Vault.dethTithePercent).mulU16(discountPct.div(40e14));
```

3.  
```solidity
bool isDiscounted = savedPrice > price.mul(1.01e18);
```

By representing ether in `wei`, the code adheres to the standard arithmetic practices in Solidity and reduces the risk of computational errors.

--- 


