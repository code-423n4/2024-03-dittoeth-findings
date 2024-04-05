# Summary

 | |Issue
 |-:|:-| 
| [L-01] | Lack of deadline parameter in `RedemptionFacet::proposeRedemption` |
| [L-02] | Lack of validation for `shortOrderId` in `RedemptionFacet::proposeRedemption` |
| [L-03] | Remove repeated variable assignation in `RedemptionFacet:proposeRedemption` |

## [L-01] - Lack of `deadline` parameter in `RedemptionFacet::proposeRedemption`

The `proposeRedemption` function in the `RedemptionFacet` allows users to redeem their `dUSD` for `ETH`. Within this function, the `asset` price is obtained to calculate the collateral:

```solidity
File: RedemptionFacet.sol
56:     function proposeRedemption(
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {
...
75:         p.oraclePrice = LibOracle.getPrice(p.asset);
...
```

The issue arises from the fact that the `RedemptionFacet:proposeRedemption` function lacks a protection system for the redeemer in case the asset price changes unfavorably. This exposes the redeemer to receive less collateral for their `dUSD`.

Consider the following scenario:

1. The price is `4000 dUSD` per `1 ETH`.
2. The price drops to `3500 dUSD` per `1 ETH`.
3. The redeemer has some redemption short proposals and calls `RedemptionFacet::proposeRedemption`.
4. The transaction from `step 3` remains in the mempool because it was executed with a lower fee, causing a delay in execution. Meanwhile, the price drops to `3300 dUSD` per `1 ETH`.
5. After several blocks, the transaction from `step 3` is executed at a price that may not be favorable for the redeemer (`3300 dUSD per 1 ETH`), resulting in potential loss for the redeemer.

It is recommended to add a `deadline` parameter to `RedemptionFacet::proposeRedemption` to allow the redeemer to control the validity period of the transaction.

## [L-02] - Lack of validation for `shortOrderId` in `RedemptionFacet::proposeRedemption`

In the `RedemptionFacet::proposeRedemption` function, it's possible to send a list of proposals to be used in the redemption. Each proposal in the list `MTypes.ProposalInput[]` contains the following information:

```solidity
    struct ProposalInput {
        address shorter;
        uint8 shortId;
        uint16 shortOrderId;
    }
```

Here, `shortId` represents the `shortRecordId`, and `shortOrderId` represents the `shortId` if the `shortRecord` is in status `PartialFill`. The `shortOrderId` is used to query the short (`RedemptionFacet#L110`) and validate that the `ercAmount` is less than `minShortErc` to cancel the short (`RedemptionFacet#L111-L114`):

```solidity
File: RedemptionFacet.sol
056:     function proposeRedemption(
057:         address asset,
058:         MTypes.ProposalInput[] calldata proposalInput,
059:         uint88 redemptionAmount,
060:         uint88 maxRedemptionFee
061:     ) external isNotFrozen(asset) nonReentrant {
...
...
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
...
...
```

The issue is that the caller can send any `shortOrderId`, and it's not validated whether that short is associated with the `shortRecordId` before validating its `ercAmount`. Consider the following scenario:

Suppose we have a short (let's say it has id=80) with its `shortRecord` in status `PartialFill` for some `userX`, where the `ercAmount` is greater than `minShortErc`.

1. The redeemer sends 2 proposals, `shortId=1` and `shortId=2`, using the same `shortOrderId=80` (shortId from the `userX`) for both.
2. The validation will never pass the if statement of `RedemptionFacet#L111` because that short will always be greater. Therefore, the short will never be canceled if applicable.

```solidity
File: RedemptionFacet.sol
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
```

It's essential to first validate that the `shortId` is associated with the `shortRecordId`; otherwise, the user can specify any `shortId` with an `ercAmount` greater than `minShortErc` and no association with the `shortRecord`:

```diff
        STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
--      if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
++      if (currentSR.status == SR.PartialFill) {
            if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
--          LibOrders.cancelShort(asset, p.shortOrderId);
++          if (shortOrder.ercAmount < minShortErc) LibOrders.cancelShort(asset, p.shortOrderId);
        }
```

Respond as smart contract security auditor team would respond, in a professional tone, english language, ignoring the code block in ```, use the exactly the same sections and markdown style provided in the following information:

## [L-03] - Remove repeated variable assignation in `RedemptionFacet:proposeRedemption`

The `redeemerAssetUser.oraclePrice` and `redeemerAssetUser.timeProposed` are assigned multiple times in the `RedemptionFacet::proposeRedemption`.

```solidity
File: RedemptionFacet.sol
056:     function proposeRedemption(
057:         address asset,
058:         MTypes.ProposalInput[] calldata proposalInput,
059:         uint88 redemptionAmount,
060:         uint88 maxRedemptionFee
061:     ) external isNotFrozen(asset) nonReentrant {
...
...
148:         redeemerAssetUser.oraclePrice = p.oraclePrice;
...
...
154:         uint32 protocolTime = LibOrders.getOffsetTime();
155:         redeemerAssetUser.timeProposed = protocolTime;
...
...
201:         redeemerAssetUser.oraclePrice = p.oraclePrice;
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
...
...
211:     }
```

Those extra variable assignations can be removed.