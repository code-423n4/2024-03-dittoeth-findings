# Cache Local Variable Array Length In For Loop
If not cached, the solidity compiler will always read the length of the array during each iteration. If it is a memory array, this is an extra mload operation (3 additional gas for each iteration except for the first).

```solidity
Path: ./contracts/facets/RedemptionFacet.sol

78:        for (uint8 i = 0; i < proposalInput.length; i++) {	// @audit-issue

242:        for (uint256 i = 0; i < decodedProposalData.length; i++) {	// @audit-issue

263:            for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {	// @audit-issue

321:        for (uint256 i = 0; i < decodedProposalData.length; i++) {	// @audit-issue
```
[78](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L78-L78), [242](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L242-L242), [263](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L263-L263), [321](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L321-L321), 


```solidity
Path: ./contracts/libraries/LibOrders.sol

743:            for (uint256 i = 0; i < shortHintArray.length;) {	// @audit-issue

832:        for (uint256 i; i < orderHintArray.length; i++) {	// @audit-issue
```
[743](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L743-L743), [832](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L832-L832), 


#### Recommendation

To optimize gas consumption, cache the length of memory arrays before for loop iterations in Solidity. This reduces redundant mload operations, saving 3 gas per iteration after the first and improving overall contract efficiency.

# Unnecessary Assignment
The identified issue involves an unnecessary step of assigning a condition's result to a boolean variable before using it in an if-statement. This extra variable assignment is not required as the condition can be directly evaluated within the if-statement itself, making the code more concise and efficient.

```solidity
Path: ./contracts/libraries/LibSRUtil.sol

40:            bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;	// @audit-issue: This assignment is not needed. Binary operation can be used in condition directly.
41:            if (isNotRecentlyModified) {
```
[40](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibSRUtil.sol#L40-L41), 


```solidity
Path: ./contracts/libraries/LibOrders.sol

738:        bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;	// @audit-issue: This assignment is not needed. Binary operation can be used in condition directly.
739:        if (shortOrdersIsEmpty) {

815:        bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;	// @audit-issue: This assignment is not needed. Binary operation can be used in condition directly.
816:
817:        if (shortOrdersIsEmpty || Asset.startingShortId == C.HEAD) {

960:        bool isDiscounted = savedPrice > price.mul(1.01 ether);	// @audit-issue: This assignment is not needed. Binary operation can be used in condition directly.
961:
962:        // @dev tithe is increased only if discount is greater than 1%
963:        if (isDiscounted) {

971:            bool titheWasChanged = Vault.dethTitheMod != C.INITIAL_TITHE_MOD;	// @audit-issue: This assignment is not needed. Binary operation can be used in condition directly.
972:
973:            if (titheWasChanged) {
```
[738](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L738-L739), [815](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L815-L817), [960](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L960-L963), [971](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L971-L973), 


#### Recommendation

Review your Solidity code for instances where boolean variables are unnecessarily assigned from conditions only to be used in immediate if-statements. Simplify these constructs by directly placing the conditional expression within the if-statement, eliminating the intermediary boolean variable. This practice not only streamlines your code, making it more concise, but also potentially reduces gas costs by minimizing the operations performed. Refactoring in this manner can enhance the readability and efficiency of your smart contracts. Always ensure that such optimizations maintain the original logic and intent of the code.

# Add `unchecked {}` for subtractions where the operands cannot underflow because of a previous `require()` or `if`-statement
`require(a <= b); x = b - a` => `require(a <= b); unchecked { x = b - a }`

```solidity
Path: ./contracts/facets/PrimaryLiquidationFacet.sol

183:            Asset.ercDebtRate += ercDebtSocialized.divU64(Asset.ercDebt - ercDebtPrev);	// @audit-issue

219:            TAPP.ethEscrowed -= callerFee;	// @audit-issue

255:            m.short.ercDebt -= m.ercDebtMatched;	// @audit-issue
```
[183](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L183-L183), [219](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L219-L219), [255](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L255-L255), 


```solidity
Path: ./contracts/facets/RedemptionFacet.sol

121:            currentSR.collateral -= p.colRedeemed;	// @audit-issue

183:            redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);	// @audit-issue

187:                protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);	// @audit-issue

191:                protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);	// @audit-issue

195:                protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);	// @audit-issue

198:            redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);	// @audit-issue

209:        VaultUser.ethEscrowed -= redemptionFee;	// @audit-issue
```
[121](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L121-L121), [183](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L183-L183), [187](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L187-L187), [191](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L191-L191), [195](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L195-L195), [198](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L198-L198), [209](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L209-L209), 


```solidity
Path: ./contracts/libraries/LibBridgeRouter.sol

57:            amount -= creditReth;	// @audit-issue

70:                        return amount - creditSteth;	// @audit-issue

87:            amount -= creditSteth;	// @audit-issue

100:                        return amount - creditReth;	// @audit-issue
```
[57](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBridgeRouter.sol#L57-L57), [70](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBridgeRouter.sol#L70-L70), [87](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBridgeRouter.sol#L87-L87), [100](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBridgeRouter.sol#L100-L100), 


```solidity
Path: ./contracts/libraries/LibOrders.sol

584:                    incomingAsk.ercAmount -= highestBid.ercAmount;	// @audit-issue

604:                        highestBid.ercAmount -= incomingAsk.ercAmount;	// @audit-issue

907:                uint88 debtDiff = minShortErc - shortRecord.ercDebt;	// @audit-issue
```
[584](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L584-L584), [604](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L604-L604), [907](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibOrders.sol#L907-L907), 


#### Recommendation

In scenarios where subtraction cannot result in underflow due to prior `require()` or `if`-statements, wrap these operations in an `unchecked` block to save gas. This optimization should only be applied when the safety of the operation is assured. Carefully analyze each case to confirm that underflow is impossible before implementing `unchecked` blocks, as incorrect usage can lead to vulnerabilities in the contract.


# Custom Errors in Solidity for Gas Efficiency
Starting from Solidity version 0.8.4, the language introduced a feature known as "custom errors". These custom errors provide a way for developers to define more descriptive and semantically meaningful error conditions without relying on string messages. Prior to this version, developers often used the `require` statement with string error messages to handle specific conditions or validations. However, every unique string used as a revert reason consumes gas, making transactions more expensive.

Custom errors, on the other hand, are identified by their name and the types of their parameters only, and they do not have the overhead of string storage. This means that, when using custom errors instead of `require` statements with string messages, the gas consumption can be significantly reduced, leading to more gas-efficient contracts.

```solidity
Path: ./contracts/facets/RedemptionFacet.sol

397:        assert(newBaseRate > 0); // Base rate is always non-zero after redemption	// @audit-issue
```
[397](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/RedemptionFacet.sol#L397-L397), 


```solidity
Path: ./contracts/libraries/LibSRUtil.sol

62:                assert(shortRecord.status != SR.PartialFill);
```
[54](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibSRUtil.sol#L62-L62), 


```solidity
Path: ./contracts/libraries/LibBytes.sol

14:        require(slate.length % 51 == 0, "Invalid data length");	// @audit-issue
```
[14](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/libraries/LibBytes.sol#L14-L14), 


#### Recommendation


It is recommended to use custom errors instead of revert strings to reduce gas costs, especially during contract deployment. Custom errors can be defined using the error keyword and can include dynamic information.


# `address(this)` should be cached
Cacheing saves gas when compared to repeating the calculation at each point it is used in the contract.

```solidity
Path: ./contracts/facets/PrimaryLiquidationFacet.sol

188:            IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);	// @audit-issue: `adress(this)` also used on line(s): [193, 165]

269:                    address(this),	// @audit-issue: `adress(this)` also used on line(s): [280, 241, 263]
```
[188](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L188-L188), [269](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/./contracts/facets/PrimaryLiquidationFacet.sol#L269-L269), 


#### Recommendation

To enhance gas efficiency, cache the contract's address by storing `address(this)` in a state variable at the point of contract deployment or initialization. Use this cached address throughout the contract instead of repeatedly calling `address(this)`. This practice reduces the gas cost associated with multiple computations of the contract's address, leading to more efficient contract execution, especially in scenarios with frequent usage of the contract's address.
