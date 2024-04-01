### Report 1:
#### Fund Loss due to Precision Loss
The convertCR(...) function in the LibOrders contract shows how covert is done for Cr to a lower decimal which means certain amount of value would be lost during the division, the problem is that this lost value is not accounted for by protocol and would be completely lost
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L36
```solidity
  function convertCR(uint16 cr) internal pure returns (uint256) {
>>>        return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;
    }
```
###  Report 2:
#### Missing Implementation to handle hintIds with same Creation Time
The function below from the LibOrders contract shows how hint id is returned by using creation time as noted in the pointer but the protocol miss the fact that two or more hint ids can have the same creation time and no implementation was done in this regards
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L838
```solidity
   function findOrderHintId(
        mapping(address => mapping(uint16 => STypes.Order)) storage orders,
        address asset,
        MTypes.OrderHint[] memory orderHintArray
    ) internal view returns (uint16 hintId) {
        bool anyOrderHintPrevMatched;
        for (uint256 i; i < orderHintArray.length; i++) {
            MTypes.OrderHint memory orderHint = orderHintArray[i];
            STypes.Order storage order = orders[asset][orderHint.hintId];
            O hintOrderType = order.orderType;
            if (hintOrderType == O.Cancelled || hintOrderType == O.Matched) {
                continue;
>>>            } else if (order.creationTime == orderHint.creationTime) {
                return orderHint.hintId;
            } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
                anyOrderHintPrevMatched = true;
            }
        }

        if (anyOrderHintPrevMatched) {
            // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD
            return C.HEAD;
        }

        revert Errors.BadHintIdArray();
    }
```