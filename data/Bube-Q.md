# QA Report

## Content

| Number  | Severity    | Issue Title                                                                               |
| --------| ------------|-------------------------------------------------------------------------------------------|
| [1]     | Low         | Possible revert in `BridgeRouterFacet::withdraw` function                                 |
| [2]     | Low         | Redundant variable update in `RedemptionFacet::proposeRedemtion` function                 |
| [3]     | Low         | Missing check for the value of `incorrectIndex` in `RedemptionFacet::disputeRedemption` function can lead to out of bound error  |
| [4]     | Low         | Missing check for the value of `claimIndex` in `RedemptionFacet::claimRemainingCollateraln` function can lead to out of bound error|
| [5]     | Low         | The `secondsAgo` parameter in `estimateWETHInUSDC` function must be dynamically updateable|
| [6]     | Low         | Unlimited approval of `stETH` tokens in `BridgeSteth` contract                            |
| [7]     | Low         | Time Weighted Average Price oracles can be manipulated                                    |
| [8]     | Non-critical| Discrepancy between the comment and code                                                  |

-------------------------------------------------------------------------------------------------------------------------------------------------

### [1] Low

## Title
Possible revert in `BridgeRouterFacet::withdraw` function

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L101C4-L124C1

## Description

The `fee` in the `BridgeRouterFacet::withdraw` function is calculated as a percentage of `dethAssessable`, which is derived from `dethAmount`:

```javascript

function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
    if (dethAmount == 0) revert Errors.ParameterIsZero();

    (uint256 vault, uint256 bridgePointer) = _getVault(bridge);

    uint88 fee;
    if (vault == VAULT.ONE) {
        uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
        if (dethAssessable > 0) {
            uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
            if (withdrawalFeePct > 0) {
@>              fee = dethAssessable.mulU88(withdrawalFeePct);
@>              dethAmount -= fee;
                s.vaultUser[vault][address(this)].ethEscrowed += fee;
            }
        }
    }

    uint88 ethAmount = _ethConversion(vault, dethAmount);
    vault.removeDeth(dethAmount, fee);
    IBridge(bridge).withdraw(msg.sender, ethAmount);
    emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
}

```

If the withdrawal fee percentage (`withdrawalFeePct`) is high enough, it could result in a `fee` that is greater than the input parameter `dethAmount`. However, the line `dethAmount -= fee;` would then result in an underflow since `dethAmount` is an unsigned integer and cannot represent negative values.

Solidity 0.8.21 includes automatic overflow and underflow checks, which would cause the transaction to revert in case of an underflow. Therefore, in the current Solidity version, if `dethAmount` were to become less than `fee`, the transaction would fail, preventing `dethAmount` from being lower than `fee`.

## Tools Used
Manual Review

## Recommendations
It is important to explicitly handle the case where the `fee` could exceed the `dethAmount` to prevent unexpected revert. You can add the check: `if (dethAmount >= fee)` before the subtraction.

-------------------------------------------------------------------------------------------------------------------------------

### [2] Low

## Title
Redundant variable update in `RedemptionFacet::proposeRedemtion` function

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L148
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L154-L155
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L201-L202

## Description
In the `RedemptionFacet::proposeRedemtion` function there are two state varibles that are updated twice. The variables are: `redeemerAssetUser.oraclePrice` and `redeemerAssetUser.timeProposed`:

```javascript

    function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
        .
        .
        .

        // @dev SSTORE2 the entire proposalData after validating proposalInput
        redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
        redeemerAssetUser.slateLength = p.redemptionCounter;
@>      redeemerAssetUser.oraclePrice = p.oraclePrice;
        redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;

        STypes.Asset storage Asset = s.asset[p.asset];
        Asset.ercDebt -= p.totalAmountProposed;

        uint32 protocolTime = LibOrders.getOffsetTime();
@>      redeemerAssetUser.timeProposed = protocolTime;
        
        uint256 m;

        if (p.currentCR > 1.7 ether) {
            m = uint256(3 ether).div(0.3 ether);
            redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.5 ether) {
            m = uint256(1.5 ether).div(0.2 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.3 ether) {
            m = uint256(0.75 ether).div(0.2 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.2 ether) {
            m = uint256(0.417 ether).div(0.1 ether);
            redeemerAssetUser.timeToDispute =
                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
        } else if (p.currentCR > 1.1 ether) {
            m = uint256(C.ONE_THIRD.div(0.1 ether));
            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
        }

@>      redeemerAssetUser.oraclePrice = p.oraclePrice;
@>      redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();

        uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
        if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();

        STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
        if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
        VaultUser.ethEscrowed -= redemptionFee;
        emit Events.ProposeRedemption(p.asset, msg.sender);
    }

```

The `oraclePrice` and `timeProposed` are not changed after the first assignment. Therefore, the second retrieve of these variables is unnecessary and wrong. The unnecessary state changes consume extra gas, leading to higher transaction costs.

## Tools Used
Manual Review

## Recommendations
Remove the redundant update of the variables `oraclePrice` and `timeProposed`.

---------------------------------------------------------------------------------------------------------------

### [3] Low

## Title
Missing check for the value of `incorrectIndex` in `RedemptionFacet::disputeRedemption` function can lead to out of bound error

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L253

## Description
The `RedemptionFacet::disputeRedemption` function allows users to dispute a redemption proposal based on an index (`incorrectIndex`) that points to a specific proposal within an array of proposals (`decodedProposalData`). This function is critical for maintaining the integrity of the redemption process by allowing users to challenge potentially incorrect redemption proposals:

```javascript

    function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
        external
        isNotFrozen(asset)
        nonReentrant
    {
        .
        .
        .

@>      MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
        MTypes.ProposalData memory currentProposal;
        STypes.Asset storage Asset = s.asset[d.asset];

        uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);

        if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
        {
            // @dev All proposals from the incorrectIndex onward will be removed
            // @dev Thus the proposer can only redeem a portion of their original slate
            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
                currentProposal = decodedProposalData[i];

                STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
                currentSR.collateral += currentProposal.colRedeemed;
                currentSR.ercDebt += currentProposal.ercDebtRedeemed;

                d.incorrectCollateral += currentProposal.colRedeemed;
                d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
            }

            s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
            Asset.dethCollateral += d.incorrectCollateral;
            Asset.ercDebt += d.incorrectErcDebt;

            // @dev Update the redeemer's SSTORE2Pointer
            if (incorrectIndex > 0) {
                redeemerAssetUser.slateLength = incorrectIndex;
            } else {
                // @dev this implies everything in the redeemer's proposal was incorrect
                delete redeemerAssetUser.SSTORE2Pointer;
                emit Events.DisputeRedemptionAll(d.asset, redeemer);
            }

            // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
            // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
            uint256 penaltyPct = LibOrders.min(
                LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
            );

            uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);

            // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
            redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
            s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
        } else {
            revert Errors.InvalidRedemptionDispute();
        }
    }

```
The `incorrectIndex` parameter is used to access an element within the `decodedProposalData` array without a prior explicit check to ensure that the index is within the bounds of the array.
If `incorrectIndex` is out of bounds, the transaction will fail. A transaction that reverts due to an out of bounds access will consume all provided gas up to the gas limit. Additionally, the user will not receive a clear error message explaining the reason for the failure, which can lead to confusion.

## Tools Used
Manual Review

## Recommendations
Implement an explicit check to ensure that `incorrectIndex` is within the bounds of the `decodedProposalData` array. If the index is out of bounds, the function should revert with a descriptive error message.
For examlpe, you can add this check to the function:

```diff
+ if (incorrectIndex >= decodedProposalData.length) revert Errors.InvalidIndex("The provided index is out of bounds.");
```

-----------------------------------------------------------------------------------------------------------------------------

### [4] Low

## Title
Missing check for the value of `claimIndex` in `RedemptionFacet::claimRemainingCollateraln` function can lead to out of bound error

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L358-L359

## Description
The `RedemptionFacet::claimRemainingCollateral` function is designed to allow shorters to claim any remaining collateral from their short positions after full redemption. The function uses a `claimIndex` to reference a specific proposal within an array of proposals `decodedProposalData`:

```javascript

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
@>          LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
@>      MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];

        if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();

        STypes.Asset storage Asset = s.asset[asset];
        _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
    }

```
The `claimIndex` parameter is used to access an element within the `decodedProposalData` array without an explicit check to ensure that the index is within the bounds of the array. Relying on Solidity's automatic reversion on out of bounds access can lead to unnecessary gas costs and a lack of clarity for the user.
Also, the `LibBytes::readProposalData` function assumes the input parameter `slateLength` matches the actual number of proposals encoded in the slate. In this case the `stateLength` is `claimIndex + 1`. If this parameter is incorrect, it leads to out of bounds memory access.
If `claimIndex` is out of bounds, the transaction will revert, consuming all provided gas up to the gas limit. And the user will not receive a clear explanation for the transaction failure.

## Tools Used
Manual Review

## Recommendations
Implement an explicit check to ensure that `incorrectIndex` is within the bounds of the `decodedProposalData` array. If the index is out of bounds, the function should revert with a descriptive error message.
For examlpe, you can add this check to the function:

```diff
+ if (claimIndex >= decodedProposalData.length) revert Errors.InvalidClaimIndex("The claim index is out of bounds.");
```

-----------------------------------------------------------------------------------------------------------------------------

### [5] Low

## Title
The `secondsAgo` parameter in `estimateWETHInUSDC` function must be dynamically updateable

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L87
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L133


## Description
In the `LibOracle::baseOracleCircuitBreaker` and `LibOracle::twapCircuitBreaker` functions is used the `IDiamond::estimateWETHInUSDC` function to retrieve the `twapPrice`.

`LibOracle::baseOracleCircuitBreaker`:
```javascript

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
        bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

        // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
        if (invalidFetchData) {
            return twapCircuitBreaker();
        } else if (priceDeviation) {
            // Check valid twap price
@>          try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
            {
                if (twapPrice == 0) {
                    return chainlinkPriceInEth;
                }

                uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
                uint256 twapPriceInEth = twapPriceNormalized.inv();
                uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;

                // Save the price that is closest to saved oracle price
                if (chainlinkDiff <= twapDiff) {
                    return chainlinkPriceInEth;
                } else {
                    // Check valid twap liquidity
                    IERC20 weth = IERC20(C.WETH);
                    uint256 wethBal = weth.balanceOf(C.USDC_WETH);
                    if (wethBal < 100 ether) {
                        return chainlinkPriceInEth;
                    }
                    return twapPriceInEth;
                }
            } catch {
                return chainlinkPriceInEth;
            }
        } else {
            return chainlinkPriceInEth;
        }
    }

```

`LibOracle::twapCircuitBreaker`:
```javascript

    function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
        // Check valid price
@>      uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes);
        if (twapPrice == 0) revert Errors.InvalidTwapPrice();

        // Check valid liquidity
        IERC20 weth = IERC20(C.WETH);
        uint256 wethBal = weth.balanceOf(C.USDC_WETH);
        if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();

        uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
        return twapPriceNormalized.inv();
    }

```

The `estimateWETHInUSDC` function accepts as second argument the `secondsAgo`. This parameter determines the time period for that the average value is taken over. The recommended TWAP period is between 30 minutes and 12 hours and the input parameter in the `estimateEETHInUSDC` set to 30 minutes is proper. 
However, it is recommended this value to be set to a variable that can be updated. In this way the time period can be changed by the owner of contract in accordance to the market conditions. In the current code the seconnd input parameter in the `estimateWETHInUSDC` function can not be changed after the deployment of contract.

## Tools Used
Manual Review

## Recommendations
Define a variable (for example: `secondsAgo`) and add a function that can update this variable. This function should be called only by the owner of contract:

```javascript
function updateSecondsAgo (uint256 newSecondsAgo) internal onlyOwner {
    secondsAgo = newSecondsAgo;
}
```
-------------------------------------------------------------------

### [6] Low

## Title
Unlimited approval of `stETH` tokens in `BridgeSteth` contract

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/bridges/BridgeSteth.sol#L26

## Description

In the `BridgeSteth` contract is given an unlimited approval to the `unsteth` contract. This can lead to loss of huge amount (or all) `stETH` tokens in the `BridgeSteth`, if the `unstETH` contract is malicious and has the ability to transfer unlimited amout of `stETH` tokens from the `BridgeSteth` contract.

```javascript

    constructor(ISTETH _steth, IUNSTETH _unsteth, address diamondAddr) {
        steth = ISTETH(_steth);
        unsteth = IUNSTETH(_unsteth);
        diamond = diamondAddr;
        steth.approve(address(unsteth), 0xffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffff);
    }

```


## Tools Used
Manual Review

## Recommendations
It is recommended to approve only the required amount of `stETH` tokens to the `unstETH` contract before the execution of a given transaction.

----------------------------------------------------------------------------

### [7] Low

## Title
Time Weighted Average Price oracles can be manipulated

## Description

The protocol uses TWAP (in `LibOracle` and `UniswapOracleLibrary` contracts) to retrieve the price. But the on-chain TWAP oracles can be manipulated. Relying on them for a critical parts of on-chain protocol can be dangerous:

https://blog.openzeppelin.com/secure-smart-contract-guidelines-the-dangers-of-price-oracles

-----------------------------------------------------------------------------------------------------------------------

### [8] Non-critical

## Title
Discrepancy between the comment and code

## Links
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L92C13-L93C92

## Description
In the `RedemptionFacet::proposeRedemtion` function in the comment is written: `// @dev Skip if proposal is not sorted correctly or if above redemption threshold`, but the code is following:

```javascript

    function proposeRedemption(
        address asset,
        MTypes.ProposalInput[] calldata proposalInput,
        uint88 redemptionAmount,
        uint88 maxRedemptionFee
    ) external isNotFrozen(asset) nonReentrant {
        .
        .
        .

        // @dev Skip if proposal is not sorted correctly or if above redemption threshold
        if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
        .
        .
        .
    }
```

In the code the proposal is skip if the `currentCR` is also equal to the `C.MAX_REDEMPTION_CR` that is 2 ether.

## Tools Used
Manual Review

## Recommendations
If you want to skip the proposal for `currentCR` equals to `C.MAX_REDEMPTION_CR`, changed the comment above, otherwise change the condition in the code.