
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

Certainly, here is the revised report:

---

## [L-05] Report: Inconsistency in depositEth Function

### Summary

The `depositEth` function in the `bridgefacet` contract is designed to interact with the `depositEth` function in the `IBridge` interface. However, the `depositEth` function in the interface is designed to accept no parameters but the contract implementation is sending the `bridge` address as a parameter. This discrepancy could lead to a potential vulnerability or misbehavior in the protocol.

### Github code
1. https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L82-L91
2. https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/interfaces/IBridge.sol#L12


#### Code Snippet from `bridgefacet`:

```solidity
/**
 * @notice Deposit ETH into the protocol
 * @dev User receives equivalent value in dETH at a 1:1 ratio, and withdrawal credit if applicable
 *
 * @param bridge The address of the bridge corresponding to the LST deposited (via ETH exchange)
 *
 */
function depositEth(address bridge) external payable nonReentrant {
    if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

    (uint256 vault, uint256 bridgePointer) = _getVault(bridge);

    uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
    vault.addDeth(bridgePointer, dethAmount);
    maybeUpdateYield(vault, dethAmount);
    emit Event ..
}
```

#### Code Snippet from `IBridge` Interface:

```solidity
interface IBridge {
    ...
    function depositEth() external payable returns (uint256);
    ...
}
```

### Issue

The `depositEth` function in the `bridgefacet` contract is incorrectly passing the `bridge` address as a parameter when interacting with the `IBridge` interface. The `depositEth` function in the `IBridge` interface is supposed to accept no parameters. This inconsistency could lead to unexpected behavior or vulnerabilities.



### Mitigation

To mitigate this issue, the contract should either:

1. Rename the `depositEth` function in the `bridgefacet` contract to `depositEthWithBridgeAddress` and pass the `bridge` address as a parameter.
2. Or, correct the `depositEth` function in the `bridgefacet` contract to match the interface by removing the `bridge` address parameter.

### Recommendation

It is recommended to update the code to maintain consistency between the `bridgefacet` contract and the `IBridge` interface to ensure the correct and secure functioning of the protocol.

---


## [L-06] Missing Update of colUsed in matchTotal struct in matchlowestSell Function
---

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L215-L262
## Impact
Failure to update the `colUsed` in the `matchTotal` struct can lead to incorrect calculations and potential loss of funds or undesired behavior in the contract's operations that will rely on this parameter later in the future/including the record keeping/wrong information displayed as matchtotal.col will always be 0.


### Code Vulnerability
```solidity
    /**
     * @notice Settles lowest ask and updates incoming bid
     * @dev DittoMatchedShares only assigned for asks sitting > 2 weeks of seconds
     *
     * @param asset The market that will be impacted
     * @param lowestSell Lowest sell order (ask or short) on market
     * @param incomingBid Active bid order
     * @param matchTotal Struct of the running matched totals
     */

    function matchlowestSell(
        address asset,
        STypes.Order memory lowestSell,
        STypes.Order memory incomingBid,
        MTypes.Match memory matchTotal
    ) private {
        uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount;
        uint88 fillEth = lowestSell.price.mulU88(fillErc);

        if (lowestSell.orderType == O.LimitShort) {
            // Match short
            uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR));
            LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);
            uint88 shortFillEth = fillEth + colUsed;
            matchTotal.shortFillEth += shortFillEth;
            // Saves gas when multiple shorts are matched
            if (!matchTotal.ratesQueried) {
                STypes.Asset storage Asset = s.asset[asset];
                matchTotal.ratesQueried = true;
                matchTotal.ercDebtRate = Asset.ercDebtRate;
                matchTotal.dethYieldRate = s.vault[Asset.vault].dethYieldRate;
            }
            // Default enum is PartialFill
            SR status;
            if (incomingBid.ercAmount >= lowestSell.ercAmount) {
                status = SR.FullyFilled;
            }

            LibShortRecord.fillShortRecord(
                asset,
                lowestSell.addr,
                lowestSell.shortRecordId,
                status,
                shortFillEth,
                fillErc,
                matchTotal.ercDebtRate,
                matchTotal.dethYieldRate
                 );
        } else {
            // Match ask
            s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth;
            matchTotal.askFillErc += fillErc;
        }

        matchTotal.fillErc += fillErc;
        matchTotal.fillEth += fillEth;
        matchTotal.lastMatchPrice = lowestSell.price;
    }

```
in the code matchtotal updates all value in the match struct but omits colused  

```solidity
struct Match {
        uint88 fillEth;
        uint88 fillErc;
        uint88 colUsed;
        uint88 dittoMatchedShares;
        uint80 lastMatchPrice;
        // Below used only for bids
        uint88 shortFillEth; // Includes colUsed + fillEth from shorts
        uint96 askFillErc; // Subset of fillErc
        bool ratesQueried; // Save gas when matching shorts
        uint80 dethYieldRate;
        uint64 ercDebtRate;
    }

```


## Tools Used
Manual code analysis.

## Recommended Mitigation Steps
It is essential to always ensure that all the relevant parameters in a struct are correctly updated to avoid vulnerabilities and maintain the contract's integrity and security. The mitigation includes updating the `matchTotal.colUsed` with the calculated `colUsed` value.

### Mitigated Code
```solidity
function matchlowestSell(
    address asset,
    STypes.Order memory lowestSell,
    STypes.Order memory incomingBid,
    MTypes.Match memory matchTotal
) private {
    uint88 fillErc = incomingBid.ercAmount > lowestSell.ercAmount ? lowestSell.ercAmount : incomingBid.ercAmount;
    uint88 fillEth = lowestSell.price.mulU88(fillErc);

    if (lowestSell.orderType == O.LimitShort) {
        // Match short
        uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR));
        LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);
        uint88 shortFillEth = fillEth + colUsed;
        matchTotal.shortFillEth += shortFillEth;

        // Updated code to fix the vulnerability
   ++   matchTotal.colUsed += colUsed;

        // Saves gas when multiple shorts are matched
        if (!matchTotal.ratesQueried) {
            STypes.Asset storage Asset = s.asset[asset];
            matchTotal.ratesQueried = true;
            matchTotal.ercDebtRate = Asset.ercDebtRate;
            matchTotal.dethYieldRate = s.vault[Asset.vault].dethYieldRate;
        }
        // Default enum is PartialFill
        SR status;
        if (incomingBid.ercAmount >= lowestSell.ercAmount) {
            status = SR.FullyFilled;
        }

        LibShortRecord.fillShortRecord(
            asset,
            lowestSell.addr,
            lowestSell.shortRecordId,
            status,
            shortFillEth,
            fillErc,
            matchTotal.ercDebtRate,
            matchTotal.dethYieldRate
        );
    } else {
        // Match ask
        s.vaultUser[s.asset[asset].vault][lowestSell.addr].ethEscrowed += fillEth;
        matchTotal.askFillErc += fillErc;
    }

    matchTotal.fillErc += fillErc;
    matchTotal.fillEth += fillEth;
    matchTotal.lastMatchPrice = lowestSell.price;
}
```


--- 

## [L-07] Enhanced Record Management: Addressing the Vulnerability in the sellAlgo Matching Algorithm
---
**Github code**
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L599-L602
## Impact

The `sellAlgo` function in the provided code had a critical vulnerability that could lead to substantial financial losses. The core issue was in the matching mechanism between the highest bidder and market sellers. The implementation allows a bidder to retain their ERC20 amount demand while they have received the ERC20 amount ,  but to prevent any unforeseen issues in the future highestbider’s demand should be 0 when filled .

## Proof of Concept

The flawed code snippet:

```solidity
} else {
    if (incomingAsk.ercAmount == highestBid.ercAmount) {
        matchOrder(s.bids, asset, highestBid.id);
        updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
      
    } 
```

## Description

The condition `if (incomingAsk.ercAmount == highestBid.ercAmount)` was met during the matching process. For instance, when Larry is the seller and Abass is the highest bidder:

- Abass bids $1000 for 50 ETH, wanting to exchange his ERC20 (e.g., USDC) at the market price.
- Larry wants to exchange 50 ETH for USDC at the same market price.

At the point of matching, the contract sets Larry's ETH value to zero and increases Abass's ETH to $1000. Even though Abass has received his ERC20, he remains the highest bidder since the price is constant and the ercamount demanded is the same. But his id was reused thus removing it from the order block, it was removed but all this detials were never updated as the should be.

## Recommended Mitigation Steps

To address this, the contract should ensure that once a bidder is matched, their ERC20 demand and ETH values are correctly updated to prevent re-matching and exploitation which an incorrect updgrade or attack can reopen. Here's a revised code snippet to mitigate this issue:

```solidity
} else {
    if (incomingAsk.ercAmount == highestBid.ercAmount) {
        matchOrder(s.bids, asset, highestBid.id);
        updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
        // Ensure highestBid is not considered in further matching
        highestBid.ercAmount = 0;
    } 
```

This revised code ensures that once a bidder is matched, their ERC20 demand and ETH values are appropriately updated, preventing potential re-matching and financial loss for the contract.

--- 

Your revised report is well-structured and effectively communicates the vulnerability and its mitigation. I've made a few minor adjustments for clarity and coherence. Here's the further refined report:

---

## [L-08] Enhanced Record Management: Addressing the Vulnerability in the BidAlgo Matching Algorithm
---

**Github code**
[https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L169-L178](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L169-L178)

## Impact

The `BidAlgo` function in the provided code exhibited a critical vulnerability that could lead to substantial financial losses. The core issue was in the matching mechanism between the lowest seller and market order of bidders. The flawed implementation allowed a seller to retain their ERC20 amount supplied to sell and receive the corresponding ETH without correctly updating the seller's records. This oversight could lead to potential exploitation and significant financial loss to the contract if there is a breakdown in the contract, while there was no identified exploits while the contract runs fine all records should be updated well before discarding.

## Proof of Concept

The flawed code snippet:

```solidity
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
    } 
```

## Description

The vulnerability arises when the condition `if (incomingBid.ercAmount == lowestSell.ercAmount)` is met during the matching process. For instance:

- Larry wants to exchange 50 ETH for 1000 USDC.
- Abass bids $1000 at the market price.

At the point of matching, the contract sets Abass's USDC value to zero and increases Abass's ETH to 50 ETH. Even though Larry has received his ERC20 - 1000 USDC, he retains his ERC amount, which is not set to 0. His ID was reused, thus removing it from the order block, but the details were never updated as they should have been. Since the seller is bringing ERC into the market for exchange, there is significant risk here if users can gain access to their tokens that were never subtracted during the match when demand and supply was balance.
updating bider's side and neglecting sell side will leave a gap in demand and supply in the record.
## Recommended Mitigation Steps

To address this vulnerability, the contract should ensure that once a lowest sell is matched, their ERC20 being supplied and ETH values are correctly updated to prevent re-matching and potential exploitation. Here's a revised code snippet to mitigate this issue:

```solidity
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
        // Ensure lowestSell's ercAmount is set to zero to prevent further matching
        lowestSell.ercAmount = 0;
    } 
```

--- 




