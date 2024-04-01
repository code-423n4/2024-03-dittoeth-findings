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
###  Report 3:
#### Dos from Underflow Error
The function below shows how short is canceled in the LibOrders contract, the problem is that protocol did not handle situation where collateralDiff is greater than eth as noted from the pointer and adjusted provided, this is due to precision loss that would have adjusted the value of eth in relation to the collateralDiff  to be deducted which would cause the code to revert causing Denial of service. A checked should be added before deduction as adjusted in code snippet below
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L929
```solidity
    function cancelShort(address asset, uint16 id) internal {
        AppStorage storage s = appStorage();
        STypes.Order storage shortOrder = s.shorts[asset][id];

        O orderType = shortOrder.orderType;
        if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();

        uint88 eth = shortOrder.ercAmount.mulU88(shortOrder.price).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;

        uint8 shortRecordId = shortOrder.shortRecordId;
        address shorter = shortOrder.addr;
        STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];

        if (shortRecord.status == SR.Closed) {
            ...
        } else {
            uint88 minShortErc = uint88(LibAsset.minShortErc(asset));
            if (shortRecord.ercDebt < minShortErc) {
                // @dev prevents leaving behind a partially filled SR is under minShortErc
                // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc
                uint88 debtDiff = minShortErc - shortRecord.ercDebt;
                {
                    STypes.Vault storage Vault = s.vault[vault];

                    uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

                    LibShortRecord.fillShortRecord(
                        asset,
                        shorter,
                        shortRecordId,
                        SR.FullyFilled,
                        collateralDiff,
                        debtDiff,
                        Asset.ercDebtRate,
                        Vault.dethYieldRate
                    );

                    Vault.dethCollateral += collateralDiff;
                    Asset.dethCollateral += collateralDiff;
                    Asset.ercDebt += debtDiff;

                    // @dev update the eth refund amount
+++             if (eth >= collateralDiff ){
 >>>                   eth -= collateralDiff;
+++               }
+++             else{
+++               eth  = 0;
+++             }
                }
                // @dev virtually mint the increased debt
                s.assetUser[asset][shorter].ercEscrowed += debtDiff;
            } else {
                shortRecord.status = SR.FullyFilled;
            }
        }

        s.vaultUser[vault][shorter].ethEscrowed += eth;

        // Approximating the startingShortId, rather than expecting exact match
        if (id == Asset.startingShortId) {
           ...
        }

        cancelOrder(s.shorts, asset, id);
    }
```