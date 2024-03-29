### These issues are not listed in the automated findings report.

# 1. No duplicate checks for `proposalInput` parameter on RedemptionFacet#`proposeRedemption()`

### Description

On RedemptionFacet#`proposeRedemption()`, no duplicate checks for `proposalInput` parameter.

### Impact

It might happens protocol violation for proposing `Redemption`.

### Links to affected code
 
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56-L211
### Recommended Mitigation Steps

```diff
++	function checkDuplicatesProposal(
++		MTypes.ProposalInput[] calldata proposalInput
++	) public pure returns(bool) {
++	    uint i;
++	    bool[] memory tmp4ShortRecordId;
++	    bool[] memory tmp4ShortOrderId;
++	
++	    for(;i<proposalInput.length;) {
++	        if(tmp4ShortRecordId[proposalInput[i].shortId] == true) {
++	            return false;
++	        }
++	        tmp4ShortRecordId[proposalInput[i].shortId] = true;
++			
++			if(tmp4ShortOrderId[proposalInput[i].shortOrderId] == true) {
++	            return false;
++	        }
++	        tmp4ShortOrderId[proposalInput[i].shortOrderId] = true;
++	
++	        unchecked {
++	            i++;
++	        }
++	    }
++	
++	    return true;
++	}

	function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
        if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
++		require( checkDuplicatesProposal(proposalInput), "Proposal is duplicated");
        MTypes.ProposeRedemption memory p;
        ...
	}
```


# 2. Short Order validation can be skipped on RedemptionFacet#`proposeRedemption()`

### Description

On RedemptionFacet#`proposeRedemption()`, Short Order validation can be skipped if current short record is not partially filled and related short order's `ercAmount` is larger than asset's  `minShortErc`.

### Impact

It might happens protocol violation for proposing `Redemption`.

### Links to affected code
 
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/facets/RedemptionFacet.sol#L56-L211
### Recommended Mitigation Steps

```diff
	function proposeRedemption(
		address asset,
		MTypes.ProposalInput[] calldata proposalInput,
		uint88 redemptionAmount,
		uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
		...
		for (uint8 i = 0; i < proposalInput.length; i++) {
			p.shorter = proposalInput[i].shorter;
			p.shortId = proposalInput[i].shortId;
			p.shortOrderId = proposalInput[i].shortOrderId;
			STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
++			STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
++			if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
			...
--			STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
			if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
--				if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
				LibOrders.cancelShort(asset, p.shortOrderId);
			}
			...
		}
		...
	}
```

