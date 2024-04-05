# [L-01] Incorrect verification of `shorter` and `shortRecordId` in `RedemptionFacet::claimRemainingCollateral()`

## Impact

The `RedemptionFacet::claimRemainingCollateral()` incorrectly verifies the `shorter` (`msg.sender`) and `shortRecordId` (the inputted `id`) parameters, which can lead to further exploits or unexpected circumstances.

## Proof of Concept

As you can see below, the `claimRemainingCollateral()` verifies the `shorter` (`msg.sender`) and `shortRecordId` (the inputted `id`) parameters using the [`&&` operator](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L361).

Therefore, the function caller can easily bypass the verification by inputting one of the two logical expressions to be `false`. For example, inputting the `id` parameter == `claimProposal.shortId`.

```solidity
    function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
        STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];
        if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
        if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

        // @dev Only need to read up to the position of the SR to be claimed
        MTypes.ProposalData[] memory decodedProposalData =
            LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
        MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];

        //@audit -- Incorrect conditional logic (must use the "||" operator instead of the "&&" operator)
@>      if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();

        STypes.Asset storage Asset = s.asset[asset];
        _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
    }
```

- `Incorrect conditional logic (must use the "||" operator instead of the "&&" operator)`: https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L361

## Tools Used

Manual Review

## Recommended Mitigation Steps

Use the operator `||` instead of the `&&`.

```diff
    function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
        external
        isNotFrozen(asset)
        nonReentrant
    {
        STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];
        if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
        if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

        // @dev Only need to read up to the position of the SR to be claimed
        MTypes.ProposalData[] memory decodedProposalData =
            LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
        MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];

-       if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
+       if (claimProposal.shorter != msg.sender || claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();

        STypes.Asset storage Asset = s.asset[asset];
        _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
    }
```

---

# [L-02] Incorrectly executing the `updateErcDebt()` leads to virtually minting the `ercDebt` more than necessary

## Impact

The `ExitShortFacet::exitShort()` executes the `checkCancelShortOrder()` before the `updateErcDebt()`. 

Consequently, if the `shortRecord` is partially filled and has the `ercDebt` less than the `minShortErc` threshold, the `shortOrder` will be canceled and the `ercDebt` will be virtually minted more than necessary to the `shortRecord` (to maintain the `minShortErc` threshold).

## Proof of Concept

The `exitShort()` executes the [`checkCancelShortOrder()`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L158-L164) to check whether the `shortRecord` is partially filled. The `checkCancelShortOrder()` will cancel the `shortOrder` if the `shortRecord` is partially filled.

Then, the `exitShort()` invokes the [`updateErcDebt()`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L166) to update the `ercDebt` of the `shortRecord`.

```solidity
    function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
        ...

        //@audit -- The checkCancelShortOrder() is executed before the updateErcDebt()
@1      e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
@1          asset: asset,
@1          initialStatus: short.status,
@1          shortOrderId: shortOrderId,
@1          shortRecordId: id,
@1          shorter: msg.sender
@1      });
@1
@1      short.updateErcDebt(e.asset);

        ...
    }
```
- `@1 -- The checkCancelShortOrder() is executed before the updateErcDebt()`: https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L158-L166

To cancel the `shortOrder`, the [`cancelShort()`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L882) is triggered. The function will check if the position has the `ercDebt` less than the `minShortErc` threshold. If that is the case, the function will [spend some of the `collateral` to virtually mint the `ercDebt`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L907-L932) (to be == `minShortErc`).

However, since the `updateErcDebt()` is executed after the `shortOrder` has already been canceled, the `cancelShort()` will virtually mint the `ercDebt` more than necessary.

*Note: the `updateErcDebt()` will [increase the `ercDebt` of the shortRecord](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L159). Therefore, if we execute the `updateErcDebt()` before, the `cancelShort()` will mint the `ercDebt` lesser to maintain the `minShortErc` threshold.*

```solidity
    function cancelShort(address asset, uint16 id) internal {
        ...

        if (shortRecord.status == SR.Closed) {
            ...

        } else {
            uint88 minShortErc = uint88(LibAsset.minShortErc(asset));
            if (shortRecord.ercDebt < minShortErc) {
                // @dev prevents leaving behind a partially filled SR is under minShortErc
                // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc
@2              uint88 debtDiff = minShortErc - shortRecord.ercDebt;
                {
                    STypes.Vault storage Vault = s.vault[vault];

@2                  uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

                    //@audit -- If the shortRecord is partially filled, the shortOrder will be canceled,
                    //          and if shortRecord.ercDebt < minShortErc, the collateral will be used to 
                    //          virtually mint ercDebt (to be == minShortErc) more than expected
                    LibShortRecord.fillShortRecord(
                        asset,
                        shorter,
                        shortRecordId,
                        SR.FullyFilled,
@2                      collateralDiff,
@2                      debtDiff,
                        Asset.ercDebtRate,
                        Vault.dethYieldRate
                    );

@2                  Vault.dethCollateral += collateralDiff;
@2                  Asset.dethCollateral += collateralDiff;
@2                  Asset.ercDebt += debtDiff;

                    // @dev update the eth refund amount
@2                  eth -= collateralDiff;
                }
                // @dev virtually mint the increased debt
@2              s.assetUser[asset][shorter].ercEscrowed += debtDiff;
            } else {
                shortRecord.status = SR.FullyFilled;
            }
        }

        ...
    }
```
- `@2 -- If the shortRecord is partially filled, the shortOrder will be canceled, and if shortRecord.ercDebt < minShortErc, the collateral will be used to virtually mint ercDebt (to be == minShortErc) more than expected`: https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L907-L932

## Tools Used

Manual Review

## Recommended Mitigation Steps

Execute the `updateErcDebt()` before the `checkCancelShortOrder()`.

```diff
    function exitShort(
        address asset,
        uint8 id,
        uint88 buybackAmount,
        uint80 price,
        uint16[] memory shortHintArray,
        uint16 shortOrderId
    ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
        ...

+       short.updateErcDebt(e.asset);

        e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
            asset: asset,
            initialStatus: short.status,
            shortOrderId: shortOrderId,
            shortRecordId: id,
            shorter: msg.sender
        });

-       short.updateErcDebt(e.asset);

        ...
    }
```

---

# [L-03] The price deviation in `LibOracle::baseOracleCircuitBreaker()` should not be hardcoded

## Impact

The hardcoded value of 50% price deviation (`0.5 ether`) may be too large when using ETH as a base price reference. Moreover, the fixed % deviation is considered too risky because the protocol's DAO or admin will not be able to update it in production.

Consequently, the [check for price deviation](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L85) in the `LibOracle::baseOracleCircuitBreaker()` may not be effective enough to filter out the stale price in production, directly affecting the quality of the oracle price that will be consumed by the core functions of the `Ditto` protocol.

## Proof of Concept

The `baseOracleCircuitBreaker()` verifies the price reported by Chainlink. If the reported price is invalid or its [price deviation when compared to the protocol's cached oracle price is more than 50%](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L80), the function will fall back to get Uniswap's TWAP price instead.

However, the `baseOracleCircuitBreaker()` uses a [hardcoded value of 50% price deviation](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L80) (`0.5 ether`), which may be too large when using ETH as a base price reference. Moreover, the fixed % deviation is considered too risky because the protocol's DAO or admin will not be able to update it in production.

```solidity
    function baseOracleCircuitBreaker(
        uint256 protocolPrice,
        uint80 roundId,
        int256 chainlinkPrice,
        uint256 timeStamp,
        uint256 chainlinkPriceInEth
    ) private view returns (uint256 _protocolPrice) {
        bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
            || block.timestamp > 2 hours + timeStamp;
        uint256 chainlinkDiff =
            chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
@>      bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

        // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
        if (invalidFetchData) {
            ...

@>      } else if (priceDeviation) {
            ...

        } else {
            ...
        }
    }
```

- https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L80

- https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L85

## Tools Used

Manual Review

## Recommended Mitigation Steps

The % price deviation should be a variable updatable by the protocol's DAO or admin in production.

---

# [L-04] Inconsistency in calculating the `minShortErc` in the `ShortOrdersFacet::createLimitShort()`

## Impact

I noticed the inconsistency in calculating the [`p.minShortErc`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L56) in the `ShortOrdersFacet::createLimitShort()` when the `cr` param < `1 ether` and when the param >= `1 ether`.

If the `cr` param < `1 ether`, the `p.minShortErc` has to be modified to be bigger. But, the resulting `p.minShortErc` will be bigger than expected. Consequently, a shorter must supply the `ercAmount` more than expected to create a limit `shortOrder` with the `cr` < `1 ether`.

## Proof of Concept

If the `cr` param < `1 ether`, `p.minShortErc` = `LibAsset.minShortErc(asset).mul(1 ether + cr.inv())`. 

Suppose the `cr` == `0.5 ether`. 
> `p.minShortErc` = `LibAsset.minShortErc(asset).mul(1 ether + (1/0.5 ether))`
                = `LibAsset.minShortErc(asset).mul(1 ether + 2 ether)`
                = `LibAsset.minShortErc(asset).mul(3 ether)`

As you can see, the resulting multiplier will be `3 ether` instead of `2 ether` *(compared to the case `cr` param >= `1 ether`)*.

```solidity
    function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
        ...

        // @dev minShortErc needs to be modified (bigger) when cr < 1
@>      p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
        p.eth = price.mul(ercAmount);
        p.minAskEth = LibAsset.minAskEth(asset);
        if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();

        ...
    }
```

- https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L56

## Tools Used

Manual Review

## Recommended Mitigation Steps

The formula for calculating the `p.minShortErc` when the `cr` param < `1 ether` should be `LibAsset.minShortErc(asset).mul(cr.inv())`.

```diff
    function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
        ...

        // @dev minShortErc needs to be modified (bigger) when cr < 1
-       p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
+       p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(cr.inv()) : LibAsset.minShortErc(asset);
        p.eth = price.mul(ercAmount);
        p.minAskEth = LibAsset.minAskEth(asset);
        if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();

        ...
    }
```