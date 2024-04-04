## Summary

### Low Risk Issues

| |Issue|Instances|
|-|:-|:-:|
| [[L&#x2011;1](#l1-vulnerable-versions-of-packages-are-being-used)] | Vulnerable versions of packages are being used | 1 | 
| [[L&#x2011;2](#l2-array-lengths-not-checked)] | Array lengths not checked | 1 | 
| [[L&#x2011;3](#l3-for-loops-in-public-or-external-functions-should-be-avoided-due-to-high-gas-costs-and-possible-dos)] | For loops in public or external functions should be avoided due to high gas costs and possible DOS | 4 | 
| [[L&#x2011;4](#l4-external-calls-in-an-un-bounded-loop-may-result-in-a-dos)] | `external` calls in an un-bounded loop may result in a DOS | 4 | 
| [[L&#x2011;5](#l5-internal-function-calls-within-for-loops)] | `internal` Function calls within for loops | 24 | 
| [[L&#x2011;6](#l6-consider-using-openzeppelin-s-safecast-library-to-prevent-unexpected-overflows-when-casting-from-various-type-int-uint-values)] | Consider using OpenZeppelin’s SafeCast library to prevent unexpected overflows when casting from various type int/uint values | 9 | 
| [[L&#x2011;7](#l7-unsafe-downcast)] | Unsafe downcast | 16 | 
| [[L&#x2011;8](#l8-consider-using-descriptive-constant-s-when-passing-zero-as-a-function-argument)] | Consider using descriptive `constant`s when passing zero as a function argument | 4 | 

Total: 63 instances over 8 issues

### Non-critical Issues

| |Issue|Instances|
|-|:-|:-:|
| [[NC&#x2011;1](#nc1-assembly-blocks-should-have-extensive-comments)] | Assembly blocks should have extensive comments | 1 | 
| [[NC&#x2011;2](#nc2-natspec-natspec-author-is-missing-from-contract)] | [NatSpec] Natspec `@author` is missing from `contract` | 13 | 
| [[NC&#x2011;3](#nc3-avoid-the-use-of-sensitive-terms)] | Avoid the use of sensitive terms | 1 | 
| [[NC&#x2011;4](#nc4-variable-names-that-consist-of-all-capital-letters-should-be-reserved-for-constant-immutable-variables)] | Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables | 4 | 
| [[NC&#x2011;5](#nc5-constant-redefined-elsewhere)] | Constant redefined elsewhere | 1 | 
| [[NC&#x2011;6](#nc6-constants-in-comparisons-should-appear-on-the-left-side)] | Constants in comparisons should appear on the left side | 60 | 
| [[NC&#x2011;7](#nc7-natspec-natspec-description-is-missing-from-contract)] | [NatSpec] Natspec description is missing from `contract` | 74 | 
| [[NC&#x2011;8](#nc8-consider-using-delete-rather-than-assigning-zero-to-clear-values)] | Consider using `delete` rather than assigning `zero` to clear values | 17 | 
| [[NC&#x2011;9](#nc9-dependence-on-external-protocols)] | Dependence on external protocols | 3 | 
| [[NC&#x2011;10](#nc10-else-block-not-required)] | `else`-block not required | 36 | 
| [[NC&#x2011;11](#nc11-events-are-missing-sender-information)] | Events are missing sender information | 5 | 
| [[NC&#x2011;12](#nc12-some-if-statement-can-be-converted-to-a-ternary)] | Some if-statement can be converted to a ternary | 16 | 
| [[NC&#x2011;13](#nc13-inconsistent-spacing-in-comments)] | Inconsistent spacing in comments | 2 | 
| [[NC&#x2011;14](#nc14-inconsistent-usage-of-require-error)] | Inconsistent usage of `require`/`error` | 1 | 
| [[NC&#x2011;15](#nc15-incorrect-natspec-syntax)] | Incorrect NatSpec Syntax | 115 | 
| [[NC&#x2011;16](#nc16-internal-functions-not-called-by-the-contract-should-be-removed)] | `internal` functions not called by the contract should be removed | 3 | 
| [[NC&#x2011;17](#nc17-large-numeric-literals-should-use-underscores-for-readability)] | Large numeric literals should use underscores for readability | 12 | 
| [[NC&#x2011;18](#nc18-file-is-missing-natspec)] | File is missing NatSpec | 1 | 
| [[NC&#x2011;19](#nc19-the-nonreentrant-modifier-should-occur-before-all-other-modifiers)] | The `nonReentrant` `modifier` should occur before all other modifiers | 10 | 
| [[NC&#x2011;20](#nc20-natspec-return-argument-is-missing)] | NatSpec `@return` argument is missing | 4 | 
| [[NC&#x2011;21](#nc21-chainlink-oracle-roundid-and-answeredin-variables-no-longer-contain-useful-information)] | Chainlink oracle `roundId` and `answeredIn` variables no longer contain useful information | 2 | 
| [[NC&#x2011;22](#nc22-state-variables-should-have-natspec-comments)] | State variables should have `Natspec` comments | 4 | 
| [[NC&#x2011;23](#nc23-contracts-should-have-full-test-coverage)] | Contracts should have full test coverage | 1 | 
| [[NC&#x2011;24](#nc24-natspec-natspec-title-is-missing-from-contract)] | [NatSpec] Natspec `@title` is missing from `contract` | 12 | 
| [[NC&#x2011;25](#nc25-top-level-pragma-declarations-should-be-separated-by-two-blank-lines)] | Top level pragma declarations should be separated by two blank lines | 13 | 
| [[NC&#x2011;26](#nc26-unused-import)] | Unused Import | 1 | 
| [[NC&#x2011;27](#nc27-missing-upgradability-functionality)] | Missing upgradability functionality | 13 | 
| [[NC&#x2011;28](#nc28-consider-using-smtchecker)] | Consider using SMTChecker | 12 | 
| [[NC&#x2011;29](#nc29-complex-function-controle-flow)] | Complex function controle flow | 13 | 
| [[NC&#x2011;30](#nc30-consider-bounding-input-array-length)] | Consider bounding input array length | 2 | 
| [[NC&#x2011;31](#nc31-natspec-natspec-dev-is-missing-from-contract)] | [NatSpec] Natspec `@dev` is missing from `contract` | 89 | 
| [[NC&#x2011;32](#nc32-natspec-natspec-notice-is-missing-from-contract)] | [NatSpec] Natspec `@notice` is missing from `contract` | 70 | 
| [[NC&#x2011;33](#nc33-consider-splitting-long-calculations)] | Consider splitting long calculations | 5 | 
| [[NC&#x2011;34](#nc34-immutable-variable-names-don-t-follow-the-solidity-style-guide)] | `immutable` variable names don\'t follow the Solidity style guide | 4 | 
| [[NC&#x2011;35](#nc35-private-public-function-name-should-start-with-underscore)] | `private`/`public` function name should start with underscore | 65 | 
| [[NC&#x2011;36](#nc36-assembly-block-creates-dirty-bits)] | Assembly block creates dirty bits | 1 | 
| [[NC&#x2011;37](#nc37-consider-adding-formal-verification-proofs)] | Consider adding formal verification proofs | 1 | 
| [[NC&#x2011;38](#nc38-missing-zero-address-check-in-functions-with-address-parameters)] | Missing zero address check in functions with address parameters | 18 | 
| [[NC&#x2011;39](#nc39-use-a-struct-to-encapsulate-multiple-function-parameters)] | Use a struct to encapsulate multiple function parameters | 18 | 
| [[NC&#x2011;40](#nc40-use-custom-errors-rather-than-revert-require-strings-for-better-readability)] | Use custom errors rather than `revert()`/`require()` strings for better readability | 1 | 
| [[NC&#x2011;41](#nc41-constructor-should-emit-an-event)] | constructor should emit an event | 3 | 
| [[NC&#x2011;42](#nc42-complex-functions-should-include-comments)] | Complex functions should include comments | 4 | 
| [[NC&#x2011;43](#nc43-make-use-of-solidiy-s-using-keyword)] | Make use of Solidiy's `using` keyword | 193 | 
| [[NC&#x2011;44](#nc44-solidity-all-verbatim-blocks-are-considered-identical-by-deduplicator-and-can-incorrectly-be-unified)] | [Solidity]: All `verbatim` blocks are considered identical by deduplicator and can incorrectly be unified | 12 | 
| [[NC&#x2011;45](#nc45-natspec-natspec-param-is-missing-from-error)] | [NatSpec] Natspec `@param` is missing from `error` | 56 | 
| [[NC&#x2011;46](#nc46-natspec-natspec-comment-is-missing-from-scope-block)] | [NatSpec] Natspec comment is missing from scope `block` | 5 | 
| [[NC&#x2011;47](#nc47-openzeppelin-libraries-should-be-upgraded-to-a-newer-version)] | OpenZeppelin libraries should be upgraded to a newer version | 1 | 
| [[NC&#x2011;48](#nc48-not-using-the-latest-version-of-prb-math-from-dependencies)] | Not using the latest version of `prb-math` from dependencies | 1 | 
| [[NC&#x2011;49](#nc49-establishing-best-practices-for-initial-version-in-package-json)] | Establishing Best Practices for Initial Version in package.json | 1 | 
| [[NC&#x2011;50](#nc50-consider-making-private-state-variables-internal-to-increase-flexibility)] | Consider making private state variables internal to increase flexibility | 4 | 
| [[NC&#x2011;51](#nc51-lack-of-space-near-the-operator)] | Lack of space near the operator | 8 | 
| [[NC&#x2011;52](#nc52-incorrect-withdraw-declaration)] | Incorrect withdraw declaration | 1 | 
| [[NC&#x2011;53](#nc53-avoid-mutating-function-parameters)] | Avoid mutating function parameters | 4 | 
| [[NC&#x2011;54](#nc54-a-event-should-be-emitted-if-a-non-immutable-state-variable-is-set-in-a-constructor)] | A event should be emitted if a non immutable state variable is set in a constructor | 4 | 
| [[NC&#x2011;55](#nc55-contracts-use-both-1-and-and-1)] | Contracts use both += 1 and ++ (-- and -= 1) | 1 | 
| [[NC&#x2011;56](#nc56-not-using-the-named-return-variables-anywhere-in-the-function-is-confusing)] | Not using the named return variables anywhere in the function is confusing | 22 | 
| [[NC&#x2011;57](#nc57-use-named-return-values)] | Use named return values | 17 | 
| [[NC&#x2011;58](#nc58-consider-moving-duplicated-strings-to-constants)] | Consider moving duplicated strings to constants | 1 | 
| [[NC&#x2011;59](#nc59-consider-adding-validation-of-user-inputs)] | Consider adding validation of user inputs | 56 | 
| [[NC&#x2011;60](#nc60-interfaces-should-use-floating-version-pragmas)] | Interfaces should use floating version pragmas | 1 | 
| [[NC&#x2011;61](#nc61-consider-using-named-function-calls)] | Consider using named function calls | 74 | 

Total: 1193 instances over 61 issues

## Low Risk Issues

### [L&#x2011;1] Vulnerable versions of packages are being used 
This project's specific package versions are vulnerable to the specific CVEs listed below. Consider switching to more recent versions of these packages that don't have these vulnerabilities


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: package.json


<details><summary>Vulnerabilities related to `@openzeppelin/contracts`:</summary>


- [CVE-2023-34459](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-wprv-93r4-jj2p) :When the verifyMultiProof, verifyMultiProofCalldata, processMultiProof, or processMultiProofCalldata functions are in use, it is possible to construct merkle trees that allow forging a valid multiproof for an arbitrary set of leaves.
A contract may be vulnerable if it uses multiproofs for verification and the merkle tree that is processed includes a node with value 0 at depth 1(just under the root).This could happen inadvertently for balanced trees with 3 leaves or less, if the leaves are not hashed.This could happen deliberately if a malicious tree builder includes such a node in the tree.
A contract is not vulnerable if it uses single- leaf proving(verify, verifyCalldata, processProof, or processProofCalldata), or if it uses multiproofs with a known tree that has hashed leaves.Standard merkle trees produced or validated with the @openzeppelin/merkle-tree library are safe.


- [CVE-2023-34234](https://github.com/OpenZeppelin/openzeppelin-contracts/security/advisories/GHSA-5h3x-9wvq-w4m2) :By frontrunning the creation of a proposal, an attacker can become the proposer and gain the ability to cancel it. The attacker can do this repeatedly to try to prevent a proposal from being proposed at all.
This impacts the Governor contract in v4.9.0 only, and the GovernorCompatibilityBravo contract since v4.3.0.
</details>
1: 


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//package.json#L1-L1) 


</details>


### [L&#x2011;2] Array lengths not checked 
If the length of the arrays are not required to be of the same length, user operations may not be fully executed due to a mismatch in the number of items iterated over, versus the number of items provided in the second array


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

//@audit , orderHintArray, shortHintArray length are not checked
40:     function createBid(
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L40-L47) 


</details>


### [L&#x2011;3] For loops in public or external functions should be avoided due to high gas costs and possible DOS 
In Solidity, for loops can potentially cause Denial of Service (DoS) attacks if not handled carefully. DoS attacks can occur when an attacker intentionally exploits the gas cost of a function, causing it to run out of gas or making it too expensive for other users to call. Below are some scenarios where for loops can lead to DoS attacks: Nested for loops can become exceptionally gas expensive and should be used sparingly


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

56:     function proposeRedemption(
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee
61:     ) external isNotFrozen(asset) nonReentrant {
62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63:         MTypes.ProposeRedemption memory p;
64:         p.asset = asset;
65:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66:         uint256 minShortErc = LibAsset.minShortErc(p.asset);
67: 
68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69: 
70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71: 
72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74: 
75:         p.oraclePrice = LibOracle.getPrice(p.asset);
76: 
77:         bytes memory slate;
78:         for (uint8 i = 0; i < proposalInput.length; i++) {

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230:         MTypes.DisputeRedemption memory d;
231:         d.asset = asset;
232:         d.redeemer = redeemer;
233: 
234:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236: 
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238: 
239:         MTypes.ProposalData[] memory decodedProposalData =
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241: 
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230:         MTypes.DisputeRedemption memory d;
231:         d.asset = asset;
232:         d.redeemer = redeemer;
233: 
234:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236: 
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238: 
239:         MTypes.ProposalData[] memory decodedProposalData =
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241: 
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244:                 revert Errors.CannotDisputeWithRedeemerProposal();
245:             }
246:         }
247: 
248:         STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249:         // Match continue (skip) conditions in proposeRedemption()
250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);
251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252: 
253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254:         MTypes.ProposalData memory currentProposal;
255:         STypes.Asset storage Asset = s.asset[d.asset];
256: 
257:         uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258: 
259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260:         {
261:             // @dev All proposals from the incorrectIndex onward will be removed
262:             // @dev Thus the proposer can only redeem a portion of their original slate
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {

310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
311:         uint256 vault = s.asset[asset].vault;
312:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
313:         STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
316: 
317:         MTypes.ProposalData[] memory decodedProposalData =
318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
319: 
320:         uint88 totalColRedeemed;
321:         for (uint256 i = 0; i < decodedProposalData.length; i++) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L56-L78) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L242), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L263), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L310-L321)


</details>


### [L&#x2011;4] `external` calls in an un-bounded loop may result in a DOS 
Consider limiting the number of iterations in loops that make external calls


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();

129:             slate = bytes.concat(

244:                 revert Errors.CannotDisputeWithRedeemerProposal();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L112-L112) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L129-L129), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L244-L244)


```solidity

File: contracts/libraries/LibBytes.sol

45:             data[i] = MTypes.ProposalData({


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L45-L45) 


</details>


### [L&#x2011;5] `internal` Function calls within for loops 
Making function calls or external calls within loops in Solidity can lead to inefficient gas usage, potential bottlenecks, and increased vulnerability to attacks. Each function call or external call consumes gas, and when executed within a loop, the gas cost multiplies, potentially causing the transaction to run out of gas or exceed block gas limits. This can result in transaction failure or unpredictable behavior.


*There are 24 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);

148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);

153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);

163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);

195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L145-L145) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L153-L153), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L155-L155), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L163-L163), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L195-L195), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L201-L201)


```solidity

File: contracts/facets/RedemptionFacet.sol

87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;

324:             _claimRemainingCollateral({


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L87-L87) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L324-L324)


```solidity

File: contracts/libraries/LibOrders.sol

451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {

577:                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

579:                     matchIncomingSell(asset, incomingAsk, matchTotal);

582:                 matchHighestBid(incomingAsk, highestBid, asset, matchTotal);

586:                     matchOrder(s.bids, asset, highestBid.id);

591:                         matchIncomingSell(asset, incomingAsk, matchTotal);

594:                             addSellOrder(incomingAsk, asset, orderHintArray);

601:                         matchOrder(s.bids, asset, highestBid.id);

602:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);

606:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

609:                             cancelBid(asset, highestBid.id);

613:                     matchIncomingSell(asset, incomingAsk, matchTotal);

617:                 updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

618:                 matchIncomingSell(asset, incomingAsk, matchTotal);

621:                     addSellOrder(incomingAsk, asset, orderHintArray);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L451-L451) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L577-L577), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L579-L579), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L582-L582), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L586-L586), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L591-L591), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L594-L594), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L601-L601), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L602-L602), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L606-L606), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L609-L609), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L613-L613), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L617-L617), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L618-L618), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L621-L621)


</details>


### [L&#x2011;6] Consider using OpenZeppelin’s SafeCast library to prevent unexpected overflows when casting from various type int/uint values 



*There are 9 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit `a` is getting converted from `uint256` to `uint88`
231:         return a < b ? uint88(a) : b;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L231-L231) 


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit `newBaseRate` is getting converted from `uint256` to `uint64`
399:         Asset.baseRate = uint64(newBaseRate);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L399-L399) 


```solidity

File: contracts/libraries/LibOracle.sol

//@audit `basePrice` is getting converted from `int256` to `uint256`
43:                 uint256 priceInEth = uint256(price).div(uint256(basePrice));

//@audit `price` is getting converted from `int256` to `uint256`
43:                 uint256 priceInEth = uint256(price).div(uint256(basePrice));

//@audit `oraclePrice` is getting converted from `uint256` to `uint80`
151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L43-L43) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L43-L43), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L151-L151)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit `cr` is getting converted from `uint16` to `uint256`
36:         return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L36-L36) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

//@audit `sqrtRatioX96` is getting converted from `uint160` to `uint256`
37:             uint256 ratioX192 = uint256(sqrtRatioX96) * sqrtRatioX96;

//@audit `secondsAgo` is getting converted from `uint32` to `int32`
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));

//@audit `secondsAgo` is getting converted from `uint32` to `int32`
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L37-L37) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L62-L62), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L65-L65)


</details>


### [L&#x2011;7] Unsafe downcast 
When a type is downcast to a smaller type, the higher order bits are truncated, effectively applying a modulo to the original value. Without any other checks, this wrapping will lead to unexpected behavior and bugs


*There are 16 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BridgeRouterFacet.sol

//@audit converting from `uint256` to `uint88`
68:         uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast)

//@audit converting from `uint256` to `uint88`
87:         uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L68-L68) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L87-L87)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit converting from `uint256` to `uint88`
180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)

//@audit converting from `uint256` to `uint88`
199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L180-L180) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L199-L199)


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit converting from `uint256` to `uint64`
133:                 bytes8(uint64(p.currentCR)),

//@audit converting from `uint256` to `uint32`
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

//@audit converting from `uint256` to `uint32`
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);

//@audit converting from `uint256` to `uint32`
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);

//@audit converting from `uint256` to `uint32`
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);

//@audit converting from `uint256` to `uint32`
198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);

//@audit converting from `uint256` to `uint88`
402:         return uint88(redemptionRate.mul(colRedeemed));


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L133-L133) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L183-L183), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L187-L187), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L191-L191), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L195-L195), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L198-L198), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L402-L402)


```solidity

File: contracts/libraries/LibOracle.sol

//@audit `oraclePrice` is getting converted from `uint256` to `uint80`
151:         s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);

//@audit converting from `uint88` to `uint80`
164:         return uint80(s.bids[asset][C.HEAD].ercAmount);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L151-L151) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L164-L164)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit converting from `uint256` to `uint32`
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)

//@audit converting from `uint256` to `uint88`
903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset));


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L32-L32) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L903-L903)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

//@audit converting from `int56` to `int24`
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L62-L62) 


</details>


### [L&#x2011;8] Consider using descriptive `constant`s when passing zero as a function argument 
Passing zero as a function argument can sometimes result in a security issue (e.g. passing zero as the slippage parameter). Consider using a `constant` variable with a descriptive name, so it's clear that the argument is intentionally being used, and for the right reasons.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/ShortOrdersFacet.sol

//@audit parameter number 4 starting from left
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

//@audit parameter number 5 starting from left
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

//@audit parameter number 6 starting from left
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

//@audit parameter number 7 starting from left
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L48-L48) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L48-L48), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L48-L48), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L48-L48)


</details>


## Non-critical Issues

### [NC&#x2011;1] Assembly blocks should have extensive comments 
Assembly blocks are taking a lot more time to audit than normal Solidity code, and often have gotchas and side-effects that the Solidity versions of the same code do not. Consider adding more comments explaining what is being done in every step of the assembly code


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

28:             assembly {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L28-L28) 


</details>


### [NC&#x2011;2] [NatSpec] Natspec `@author` is missing from `contract` 



*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) 


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) 


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) 


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) 


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) 


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) 


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {

19: /// @title Oracle library
20: /// @notice Provides functions to integrate with V3 pool oracle
21: library OracleLibrary {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L19-L21)


</details>


### [NC&#x2011;3] Avoid the use of sensitive terms 
Use [alternative variants](https://www.zdnet.com/article/mysql-drops-master-slave-and-blacklist-whitelist-terminology/), e.g. allowlist/denylist instead of whitelist/blacklist


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

204:      * @dev liquidationFee is taken into consideration when determining black swan


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L204-L204) 


</details>


### [NC&#x2011;4] Variable names that consist of all capital letters should be reserved for `constant`/`immutable` variables 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

165:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];

211:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];

241:         STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L165-L165) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L211-L211), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L241-L241)


```solidity

File: contracts/libraries/LibBytes.sol

24:             uint64 CR; // bytes8


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L24-L24) 


</details>


### [NC&#x2011;5] Constant redefined elsewhere 
Consider defining in only one contract so that values cannot become out of sync when only one location is updated. A [cheap way](https://medium.com/coinmonks/gas-cost-of-solidity-library-functions-dbe0cedd4678) to store constants in a single location is to create an `internal constant` in a `library`. If the variable is a local cache of another contract's value, consider making the cache variable internal or private, which will require external users to query the contract with the source of truth, so that callers don't get out of sync.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/ExitShortFacet.sol

//@audit The same constant is already defined on file : contracts/facets/PrimaryLiquidationFacet.sol
26:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L26-L26) 


</details>


### [NC&#x2011;6] Constants in comparisons should appear on the left side 



*There are 60 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

//@audit `0`
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {

//@audit `0`
281:         if (matchTotal.fillEth == 0) {

//@audit `0`
292:         if (b.dustAskId > 0) {

//@audit `0`
299:         if (matchTotal.shortFillEth > 0) {

//@audit `0`
294:         } else if (b.dustShortId > 0) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L152-L152) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L281-L281), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L292-L292), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L299-L299), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L294-L294)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

//@audit `1`
56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L56-L56) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit `10`
56:         if (shortHintArray.length > 10) revert Errors.TooManyHints();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L56-L56) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

//@audit `0`
102:         if (dethAmount == 0) revert Errors.ParameterIsZero();

//@audit `0`
109:             if (dethAssessable > 0) {

//@audit `0`
111:                 if (withdrawalFeePct > 0) {

//@audit `0`
134:         if (dethAmount == 0) revert Errors.ParameterIsZero();

//@audit `0`
164:             if (vault == 0) revert Errors.InvalidBridge();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L102-L102) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L109-L109), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L111-L111), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L134-L134), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L164-L164)


```solidity

File: contracts/facets/ExitShortFacet.sol

//@audit `0`
53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();

//@audit `0`
99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();

//@audit `0`
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();

//@audit `0`
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L53-L53) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L99-L99), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L188-L188), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L174-L174)


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit `1.7`
181:         if (p.currentCR > 1.7 ether) {

//@audit `1.5`
184:         } else if (p.currentCR > 1.5 ether) {

//@audit `1.3`
188:         } else if (p.currentCR > 1.3 ether) {

//@audit `1.2`
192:         } else if (p.currentCR > 1.2 ether) {

//@audit `1.1`
196:         } else if (p.currentCR > 1.1 ether) {

//@audit `0`
279:             if (incorrectIndex > 0) {

//@audit `0`
371:         if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {

//@audit `0`
397:         assert(newBaseRate > 0); // Base rate is always non-zero after redemption


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L181-L181) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L184-L184), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L188-L188), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L192-L192), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L196-L196), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L279-L279), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L371-L371), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L397-L397)


```solidity

File: contracts/libraries/LibBytes.sol

//@audit `0`
14:         require(slate.length % 51 == 0, "Invalid data length");


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L14-L14) 


```solidity

File: contracts/libraries/LibOracle.sol

//@audit `0`
30:                 uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;

//@audit `0`
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

//@audit `0`
60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

//@audit `0`
80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

//@audit `0.5`
80:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;

//@audit `0`
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
76:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
89:                 if (twapPrice == 0) {

//@audit `100`
104:                     if (wethBal < 100 ether) {

//@audit `0`
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

//@audit `0`
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

//@audit `0`
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

//@audit `0`
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0

//@audit `0`
134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice();

//@audit `100`
139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();

//@audit `15`
169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L30-L30) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L60-L60), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L60-L60), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L80-L80), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L80-L80), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L76-L76), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L76-L76), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L76-L76), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L89-L89), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L104-L104), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L126-L126), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L126-L126), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L126-L126), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L125-L125), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L125-L125), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L125-L125), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L134-L134), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L139-L139), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L169-L169)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit `0`
371:         if (hintId == 0 || nextId == 0) {

//@audit `0`
371:         if (hintId == 0 || nextId == 0) {

//@audit `0`
501:         if (b.matchedAskId != 0) {

//@audit `0`
505:         if (b.matchedShortId != 0) {

//@audit `0`
576:                 if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {

//@audit `0`
677:         SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill;

//@audit `0.005`
794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;

//@audit `0.005`
792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;

//@audit `15`
805:         if (timeDiff >= 15 minutes) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L371-L371) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L371-L371), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L501-L501), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L505-L505), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L576-L576), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L677-L677), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L794-L794), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L792-L792), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L805-L805)


```solidity

File: contracts/libraries/LibSRUtil.sol

//@audit `0`
35:         if (yield > 0) {

//@audit `0`
113:             if (Asset.ercDebt > 0) {

//@audit `0`
131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

//@audit `0`
158:         if (ercDebt > 0) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L35-L35) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L158-L158)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

//@audit `0`
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();

//@audit `0`
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {

//@audit `0`
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L52-L52) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L65-L65), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L65-L65)


</details>


### [NC&#x2011;7] [NatSpec] Natspec description is missing from `contract` 
It is recommended that Solidity contracts are fully annotated using NatSpec for all public interfaces (everything in the ABI). It is clearly stated in the Solidity official documentation. In complex projects such as Defi, the interpretation of all functions and their arguments and returns is important for code readability and auditability.[source](https://docs.soliditylang.org/en/v0.8.15/natspec-format.html)


*There are 74 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {

77:     function _createBid(

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

358:     function _shortDirectionHandler(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L77), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L358)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {

28:     address private immutable dusd;

30:     constructor(address _dusd) {

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L28-L28), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L96-L96), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {

26:     address private immutable rethBridge;

27:     address private immutable stethBridge;

29:     constructor(address _rethBridge, address _stethBridge) {

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L26-L26), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L27-L27), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L29), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L169-L169)


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {

26:     address private immutable dusd;

28:     constructor(address _dusd) {

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L26-L26), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L28), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213)


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L31), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L368-L368), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L21-L21), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L198-L198)


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11)


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {

19:     function getOraclePrice(address asset) internal view returns (uint256) {

69:     function baseOracleCircuitBreaker(

117:     function oracleCircuitBreaker(

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

156:     function getTime(address asset) internal view returns (uint256 creationTime) {

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L117), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

320:     function _reuseOrderIds(

420:     function normalizeOrderType(O o) private pure returns (O newO) {

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

783:     function updateOracleAndStartingShortViaThreshold(

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

826:     function findOrderHintId(

854:     function cancelBid(address asset, uint16 id) internal {

868:     function cancelAsk(address asset, uint16 id) internal {

882:     function cancelShort(address asset, uint16 id) internal {

955:     function handlePriceDiscount(address asset, uint80 price) internal {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L320), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L728), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L783), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L803-L803), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L810-L810), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {

11:     function observe(uint32[] calldata secondsAgos)

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L11-L11), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47)


</details>


### [NC&#x2011;8] Consider using `delete` rather than assigning `zero` to clear values 
The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic


*There are 17 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

194:                     incomingBid.ercAmount = 0;

158:                     lowestSell.ercAmount = 0;

191:                             b.dustShortId = b.dustAskId = 0;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L194-L194) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L158-L158), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L191-L191)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

86:             VaultUser.bridgeCreditSteth = 0;

56:             VaultUser.bridgeCreditReth = 0;

167:                     VaultUserFrom.bridgeCreditReth = 0;

188:                     VaultUserFrom.bridgeCreditReth = 0;

189:                     VaultUserFrom.bridgeCreditSteth = 0;

176:                     VaultUserFrom.bridgeCreditSteth = 0;

99:                         VaultUser.bridgeCreditReth = 0;

69:                         VaultUser.bridgeCreditSteth = 0;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L86-L86) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L56-L56), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L167-L167), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L188-L188), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L189-L189), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L176-L176), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L99-L99), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L69-L69)


```solidity

File: contracts/libraries/LibOrders.sol

578:                     incomingAsk.ercAmount = 0;

612:                     incomingAsk.ercAmount = 0;

585:                     highestBid.ercAmount = 0;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L578-L578) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L612-L612), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L585-L585)


```solidity

File: contracts/libraries/LibSRUtil.sol

138:         short.tokenId = 0;

148:         nft.shortOrderId = 0;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L138-L138) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L148-L148)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

56:         secondsAgos[1] = 0;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L56-L56) 


</details>


### [NC&#x2011;9] Dependence on external protocols 
External protocols should be monitored as such dependencies may introduce vulnerabilities if a vulnerability is found /introduced in the external protocol


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBridgeRouter.sol

8: import {OracleLibrary} from "contracts/libraries/UniswapOracleLibrary.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L8-L8) 


```solidity

File: contracts/libraries/LibOracle.sol

6: import {AggregatorV3Interface} from "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L6-L6) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

7: import {TickMath} from "contracts/libraries/UniswapTickMath.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L7-L7) 


</details>


### [NC&#x2011;10] `else`-block not required 
One level of nesting can be removed by not having an `else` block when the `if`-block returns:


*There are 36 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {

341:         if (b.shortId != C.HEAD) {

150:             if (incomingBid.price >= lowestSell.price) {

347:             if (noAsks || shortPriceLessThanAskPrice) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L106-L106) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L341-L341), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L150-L150), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L347-L347)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

173:         if (dethTotalNew >= dethTotal) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L173-L173) 


```solidity

File: contracts/facets/RedemptionFacet.sol

38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L38-L38) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

48:         if (bridgePointer == VAULT.BRIDGE_RETH) {

125:         if (factorReth > factorSteth) {

131:         } else if (factorSteth > factorReth) {

89:             if (creditReth < C.ROUNDING_ZERO) {

59:             if (creditSteth < C.ROUNDING_ZERO) {

93:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {

63:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {

95:                     if (creditReth >= amount) {

65:                     if (creditSteth >= amount) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L48-L48) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L125-L125), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L89-L89), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L59-L59), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L93-L93), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L63-L63), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L95-L95), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L65-L65)


```solidity

File: contracts/libraries/LibOracle.sol

83:         if (invalidFetchData) {

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {

85:         } else if (priceDeviation) {

28:             if (oracle == baseOracle) {

48:             if (oracle == baseOracle) {

98:                 if (chainlinkDiff <= twapDiff) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L83-L83) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L169-L169), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L85-L85), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L28-L28), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L48-L48), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L98-L98)


```solidity

File: contracts/libraries/LibOrders.sol

241:         if (check1 && check2) {

272:         if (check1 && check2) {

381:         if (direction == C.EXACT) {

412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {

421:         if (o == O.LimitBid || o == O.MarketBid) {

243:         } else if (!check1) {

274:         } else if (!check1) {

383:         } else if (direction == C.NEXT) {

423:         } else if (o == O.LimitAsk || o == O.MarketAsk) {

574:             if (incomingAsk.price <= highestBid.price) {

838:             } else if (order.creationTime == orderHint.creationTime) {

583:                 if (incomingAsk.ercAmount > highestBid.ercAmount) {

765:                 if (isExactStartingShort) {

768:                 } else if (startingShortWithinOracleRange) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L241-L241) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L272-L272), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L381-L381), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L412-L412), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L421-L421), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L243-L243), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L274-L274), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L383-L383), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L423-L423), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L574-L574), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L838-L838), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L583-L583), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L765-L765), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L768-L768)


```solidity

File: contracts/libraries/LibSRUtil.sol

59:             if (shorter == msg.sender) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L59-L59) 


</details>


### [NC&#x2011;11] Events are missing sender information 
When an action is triggered based on a user's action, not being able to filter based on who triggered the action makes event processing a lot more cumbersome. Including the `msg.sender` the events of these types of action will make events much more useful to end users, especially when `msg.sender` is not `tx.origin`.


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L332-L332) 


```solidity

File: contracts/facets/RedemptionFacet.sol

284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L284-L284) 


```solidity

File: contracts/libraries/LibOrders.sol

218:         emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount);

301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType);

631:         emit Events.MatchOrder(
632:             asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, matchTotal.fillEth, matchTotal.fillErc
633:         );


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L218-L218) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L301-L301), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L631-L633)


</details>


### [NC&#x2011;12] Some if-statement can be converted to a ternary 
Improving code readability and compactness is an integral part of optimal programming practices. The use of ternary operators in place of if-else conditions is one such measure. Ternary operators allow us to write conditional statements in a more concise manner, thereby enhancing readability and simplicity. They follow the syntax `condition ? exprIfTrue : exprIfFalse`, which interprets as "if the condition is true, evaluate to `exprIfTrue`, else evaluate to `exprIfFalse`". By adopting this approach, we make our code more streamlined and intuitive, which could potentially aid in better understanding and maintenance of the codebase.


*There are 16 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

347:             if (noAsks || shortPriceLessThanAskPrice) {
348:                 return lowestShort;
349:             } else {
350:                 return lowestAsk;
351:             }

320:                 if (b.isMovingFwd) {
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L347-L351) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L320-L324)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

85:         if (incomingShort.price < p.oraclePrice) {
86:             LibOrders.addShort(asset, incomingShort, orderHintArray);
87:         } else {
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L85-L89) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

173:         if (dethTotalNew >= dethTotal) {
174:             // when yield is positive 1 deth = 1 eth
175:             return amount;
176:         } else {
177:             // negative yield means 1 deth < 1 eth
178:             // @dev don't use mulU88 in rare case of overflow
179:             return amount.mul(dethTotalNew).divU88(dethTotal);
180:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L173-L180) 


```solidity

File: contracts/facets/RedemptionFacet.sol

38:         if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
39:             return false;
40:         } else {
41:             return true;
42:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L38-L42) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

27:             if (bridgePointer == VAULT.BRIDGE_RETH) {
28:                 VaultUser.bridgeCreditReth += amount;
29:             } else {
30:                 VaultUser.bridgeCreditSteth += amount;
31:             }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L27-L31) 


```solidity

File: contracts/libraries/LibOracle.sol

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
170:             return getPrice(asset);
171:         } else {
172:             return getOraclePrice(asset);
173:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L169-L173) 


```solidity

File: contracts/libraries/LibOrders.sol

90:         if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) {
91:             hintId = C.HEAD;
92:         } else {
93:             hintId = findOrderHintId(s.bids, asset, orderHintArray);
94:         }

111:         if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) {
112:             hintId = C.HEAD;
113:         } else {
114:             hintId = findOrderHintId(s.asks, asset, orderHintArray);
115:         }

132:         if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) {
133:             hintId = C.HEAD;
134:         } else {
135:             hintId = findOrderHintId(s.shorts, asset, orderHintArray);
136:         }

339:         if (prevHEAD != C.HEAD) {
340:             orders[asset][id].prevId = prevHEAD;
341:         } else {
342:             // if this is the first ID cancelled
343:             // HEAD.prevId needs to be HEAD
344:             // and one of the cancelled id.prevID should point to HEAD
345:             // BEFORE: HEAD <--------- HEAD <-> ... [ID]
346:             // AFTER1: HEAD <- [ID] <- HEAD <-> ...
347:             orders[asset][id].prevId = C.HEAD;
348:         }

791:         if (incomingOrder.price >= savedPrice) {
792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
793:         } else {
794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
795:         }

196:             if (prevCanceledID != C.HEAD) {
197:                 orders[asset][C.HEAD].prevId = prevCanceledID;
198:             } else {
199:                 // BEFORE: HEAD <- (ID) <- HEAD <-> .. <-> PREV <----------> NEXT
200:                 // AFTER1: HEAD <--------- HEAD <-> .. <-> PREV <-> [ID] <-> NEXT
201:                 orders[asset][C.HEAD].prevId = C.HEAD;
202:             }

944:             if (prevPrice >= savedPrice) {
945:                 Asset.startingShortId = shortOrder.prevId;
946:             } else {
947:                 Asset.startingShortId = shortOrder.nextId;
948:             }

973:             if (titheWasChanged) {
974:                 // @dev change back to original tithe percent
975:                 Vault.dethTitheMod = C.INITIAL_TITHE_MOD;
976:             } else {
977:                 return;
978:             }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L90-L94) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L111-L115), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L132-L136), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L339-L348), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L791-L795), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L196-L202), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L944-L948), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L973-L978)


```solidity

File: contracts/libraries/LibSRUtil.sol

41:             if (isNotRecentlyModified) {
42:                 s.vaultUser[vault][shorter].ethEscrowed += yield;
43:             } else {
44:                 s.vaultUser[vault][address(this)].ethEscrowed += yield;
45:             }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L41-L45) 


</details>


### [NC&#x2011;13] Inconsistent spacing in comments 
Some lines use `// x` and some use `//x`. The instances below point out the usages that don't follow the majority, within each file


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

92:     //PRIVATE FUNCTIONS


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L92-L92) 


```solidity

File: contracts/libraries/LibOrders.sol

514:                 //@handles moving backwards only.


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L514-L514) 


</details>


### [NC&#x2011;14] Inconsistent usage of `require`/`error` 
Some parts of the codebase use `require` statements, while others use custom `error`s. Consider refactoring the code to use the same approach: the following findings represent the minority of `require` vs `error`, and they show the first occurance in each file, for brevity.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

14:         require(slate.length % 51 == 0, "Invalid data length");


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L14-L14) 


</details>


### [NC&#x2011;15] Incorrect NatSpec Syntax 
In Solidity, just like in most other programming languages, regular comments serve to make code more understandable for developers. These are usually denoted by `//` for single line comments, or `/* ... */` for multi-line comments, and are ignored by the compiler.
On the other hand, NatSpec comments in Solidity, denoted by `///` for single - line comments, or`/** ... */` for multi - line comments, serve a different purpose.Besides aiding developer comprehension, they also form a part of the contract's interface, as they can be parsed and used by tools such as automated documentation generators or IDEs to provide users with details about the contract's functions, parameters and behavior.NatSpec comments can also be retrieved via JSON interfaces, and as such, they're included in the contract's ABI.
Thus, using`///` and `/** ... */` appropriately ensures not only proper documentation for developers, but also helps create a richer and more informative interface for users and external tools interacting with your contract.


*There are 115 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

70:         // @dev leave empty, don't need hint for market buys

73:         // @dev update oracle in callers

102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)

107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId

113:             // @dev no match, add to market if limit order

140:             // @dev Handles scenario when no sells left after partial fill

291:         // @dev needs to happen after updateSellOrdersOnMatch()

309:             // @dev Approximates the startingShortId after bid is fully executed

334:         // @dev match price is based on the order that was already on orderbook

339:     // @dev If neither conditions are true, it returns an empty Order struct

344:             // @dev Setting lowestSell after comparing short and ask prices

353:             // @dev Handles scenario when there are no shorts

393:             // @dev shortHintId should always be the first thing matched

401:             // @dev Only set to true if actually moving forward


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L70-L70) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L73-L73), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L107-L107), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L140-L140), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L291-L291), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L309-L309), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L334-L334), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L339-L339), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L344-L344), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L353-L353), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L393-L393), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L401-L401)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

47:         // @dev create "empty" SR. Fail early.

55:         // @dev minShortErc needs to be modified (bigger) when cr < 1

74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId

84:         // @dev reading spot oracle price


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L47-L47) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L74-L74), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L84-L84)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

55:         // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost

58:         // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile

67:         // @dev liquidate requires more up-to-date oraclePrice

72:         // @dev Can liquidate as long as CR is low enough

95:     // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call

158:         // @dev Provide higher price to better ensure it can fully fill the liquidation

164:         // @dev Increase ethEscrowed by shorter's full collateral for forced bid

177:             // @dev Max ethDebt can only be the ethEscrowed in the TAPP

180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)

186:         // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP

192:         // @dev virtually burning the repurchased debt

197:         // @dev manually setting basefee to 1,000,000 in foundry.toml;

198:         // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP

199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast)

217:         // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out.


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L55-L55) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L58-L58), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L67-L67), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L95-L95), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L158-L158), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L164-L164), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L177-L177), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L180-L180), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L186-L186), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L192-L192), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L197-L197), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L198-L198), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L199-L199), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L217-L217)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

67:         // @dev amount after deposit might be less, if bridge takes a fee

68:         uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast)

147:     // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions

178:             // @dev don't use mulU88 in rare case of overflow


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L67-L67) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L68-L68), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L147-L147), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L178-L178)


```solidity

File: contracts/facets/ExitShortFacet.sol

157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder

168:         // @dev if short order was cancelled, fully exit

203:             // @dev Only allow partial exit if the CR is same or better than before

206:             // @dev collateral already subtracted in exitShort()


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L157-L157) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L168-L168), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L203-L203), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L206-L206)


```solidity

File: contracts/facets/RedemptionFacet.sol

36:         // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition

37:         // @dev Proposer can't redeem on self

72:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption

82:             // @dev Setting this above _onlyValidShortRecord to allow skipping

92:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold

95:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount

100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate

108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR

109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()

127:             // @dev directly write the properties of MTypes.ProposalData into bytes

145:         // @dev SSTORE2 the entire proposalData after validating proposalInput

156:         // @dev Calculate the dispute period

157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x

261:             // @dev All proposals from the incorrectIndex onward will be removed

262:             // @dev Thus the proposer can only redeem a portion of their original slate

278:             // @dev Update the redeemer's SSTORE2Pointer

282:                 // @dev this implies everything in the redeemer's proposal was incorrect

287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)

288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees

295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)

356:         // @dev Only need to read up to the position of the SR to be claimed

372:             // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already

375:             // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS

381:     // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated

391:         // @dev Calculate Asset.ercDebt prior to proposal

393:         // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L36-L36) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L37-L37), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L92-L92), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L95-L95), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L100-L100), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L108-L108), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L109-L109), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L127-L127), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L145-L145), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L157-L157), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L261-L261), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L262-L262), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L278-L278), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L282-L282), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L287-L287), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L288-L288), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L295-L295), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L356-L356), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L372-L372), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L375-L375), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L381-L381), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L391-L391), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L393-L393)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

74:                     // @dev Prevents abusing bridge for arbitrage

104:                     // @dev Prevents abusing bridge for arbitrage

112:     // @dev Only applicable to VAULT.ONE which has mixed LST

143:     // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L74-L74) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L104-L104), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L112-L112), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L143-L143)


```solidity

File: contracts/libraries/LibOracle.sol

29:                 // @dev multiply base oracle by 10**10 to give it 18 decimals of precision

82:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink

155:     // @dev Intentionally using creationTime for oracleTime.

161:     // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.

167:     // @dev Allows caller to save gas since reading spot price costs ~16K


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L29-L29) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L155-L155), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L161-L161), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L167-L167)


```solidity

File: contracts/libraries/LibOrders.sol

29:     // @dev in seconds

32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)

43:         // @dev use the diff to get more time (2159), to prevent overflow at year 2106

138:         // @dev: Only need to set this when placing incomingShort onto market

172:     // @dev partial addOrder

188:         // @dev (ID) is exiting, [ID] is inserted

237:         // @dev: TAIL can't be prevId because it will always be last item in list

267:         // @dev: TAIL can't be prevId because it will always be last item in list

294:         // @dev (ID) is exiting, [ID] is inserted

332:         // @dev mark as cancelled instead of deleting the order itself

419:     // @dev not used to change state, just which methods to call

507:                 // @dev Handles only matching one thing

508:                 // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block

511:                 // @dev Handles moving forward only

518:                 // @dev Handle going backward and forward

641:         // @dev match price is based on the order that was already on orderbook

724:         // @dev this happens at the end so fillErc isn't affected in previous calculations

760:                 // @dev force hint to be within 0.5% of oraclePrice

769:                     // @dev prevShortPrice >= oraclePrice

782:     // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)

790:         // @dev handle .5% deviations in either directions

802:     // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough

846:             // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD

899:             // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId

900:             // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId

905:                 // @dev prevents leaving behind a partially filled SR is under minShortErc

906:                 // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc

928:                     // @dev update the eth refund amount

931:                 // @dev virtually mint the increased debt

962:         // @dev tithe is increased only if discount is greater than 1%

964:             // @dev bound the new tithe amount between 25% and 100%

967:             // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount

970:             // @dev dethTitheMod is only set when setTithe is called.

974:                 // @dev change back to original tithe percent

981:         // @dev exists because of ShortOrderFacet contract size


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L29-L29) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L32-L32), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L43-L43), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L138-L138), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L172-L172), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L188-L188), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L237-L237), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L267-L267), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L294-L294), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L332-L332), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L419-L419), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L507-L507), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L508-L508), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L511-L511), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L518-L518), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L641-L641), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L724-L724), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L760-L760), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L769-L769), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L782-L782), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L790-L790), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L802-L802), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L846-L846), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L899-L899), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L900-L900), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L905-L905), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L906-L906), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L928-L928), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L931-L931), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L962-L962), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L964-L964), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L967-L967), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L970-L970), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L974-L974), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L981-L981)


```solidity

File: contracts/libraries/LibSRUtil.sol

89:                     // @dev The resulting SR will not have PartialFill status after cancel

133:         // @dev shortOrderId is already validated in mintNFT


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L89-L89) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L133-L133)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp

69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L58-L58) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L69-L69)


</details>


### [NC&#x2011;16] `internal` functions not called by the contract should be removed 
If the functions are required by an interface, the contract should inherit from that interface and use the `override` keyword


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibOrders.sol

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

868:     function cancelAsk(address asset, uint16 id) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868)


```solidity

File: contracts/libraries/LibSRUtil.sol

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124) 


</details>


### [NC&#x2011;17] Large numeric literals should use underscores for readability 



*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);

189:             m = uint256(0.75 ether).div(0.2 ether);

193:             m = uint256(0.417 ether).div(0.1 ether);

191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L290-L290) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L401-L401), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L189-L189), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L193-L193), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L191-L191)


```solidity

File: contracts/libraries/LibOrders.sol

960:         bool isDiscounted = savedPrice > price.mul(1.01 ether);

965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));

794:             orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;

792:             orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;

965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));

968:             Vault.dethTitheMod = (C.MAX_TITHE - Vault.dethTithePercent).mulU16(discountPct.div(0.04 ether));

761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L960-L960) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L965-L965), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L794-L794), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L792-L792), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L965-L965), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L968-L968), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L761-L761)


</details>


### [NC&#x2011;18] File is missing NatSpec 



*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

0: 


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L0-L0) 


</details>


### [NC&#x2011;19] The `nonReentrant` `modifier` should occur before all other modifiers 
This is a best-practice to protect against reentrancy in other modifiers


*There are 10 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

40:     function createBid(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L40-L40) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

35:     function createLimitShort(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L35-L35) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L47-L47) 


```solidity

File: contracts/facets/ExitShortFacet.sol

41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)

87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)

142:     function exitShort(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L41-L41) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L87-L87), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L142-L142)


```solidity

File: contracts/facets/RedemptionFacet.sol

56:     function proposeRedemption(

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)

310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {

347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L56-L56) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L224), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L310-L310), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L347-L347)


</details>


### [NC&#x2011;20] NatSpec `@return` argument is missing 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BridgeRouterFacet.sol

// @audit the @return is missing
 @notice Returns the present value of all bridges within a given vault
 @param vault The vault being queried

// @audit the @return is missing
 @notice Returns an array of the bridge addresses of the vault
 @dev does not need read only reentrancy
 @param vault The vault being queried


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L40-L1) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L51-L1)


```solidity

File: contracts/libraries/LibOrders.sol

// @audit the @return is missing
 @notice Helper function for finding the (previous) id so that an incoming
 @notice order can be placed onto the correct market.
 @notice Uses hintId if possible, otherwise fallback to traversing the
 @notice list of orders starting from HEAD
 @param orders the order mapping
 @param asset The market that will be impacted
 @param incomingOrder the Order to be placed
 @param hintId Id used to optimize finding the place to insert into ob

// @audit the @return is missing
 @notice Helper function for finding and returning id of potential order
 @param orders the order mapping
 @param asset The market that will be impacted
 @param direction int direction to search (PREV, EXACT, NEXT)
 @param hintId hint id
 @param _newPrice price of prospective order used to find the id
 @param orderType which OrderType to verify


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L362-L1) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L1)


</details>


### [NC&#x2011;21] Chainlink oracle `roundId` and `answeredIn` variables no longer contain useful information 
The new Chainlink [OCR](https://docs.chain.link/architecture-overview/off-chain-reporting) methodology no longer relies on rounds, so adding checks related to the `roundId`/`answeredIn` return values is unnecessary, and may cause issues down the line.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibOracle.sol

35:                 (
36:                     uint80 roundID,
37:                     int256 price,
38:                     /*uint256 startedAt*/
39:                     ,
40:                     uint256 timeStamp,
41:                     /*uint80 answeredInRound*/
42:                 ) = oracle.latestRoundData();

52:                 (
53:                     uint80 roundID,
54:                     int256 price,
55:                     /*uint256 startedAt*/
56:                     ,
57:                     uint256 timeStamp,
58:                     /*uint80 answeredInRound*/
59:                 ) = oracle.latestRoundData();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L35-L42) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L52-L59)


</details>


### [NC&#x2011;22] State variables should have `Natspec` comments 
Consider adding some `Natspec` comments on critical state variables to explain what they are supposed to do: this will help for future code reviews.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit dusd need comments
28:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

//@audit rethBridge need comments
26:     address private immutable rethBridge;

//@audit stethBridge need comments
27:     address private immutable stethBridge;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L26-L26) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L27-L27)


```solidity

File: contracts/facets/ExitShortFacet.sol

//@audit dusd need comments
26:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L26-L26) 


</details>


### [NC&#x2011;23] Contracts should have full test coverage 
While 100% code coverage does not guarantee that there are no bugs, it often will catch easy-to-find bugs, and will ensure that there are fewer regressions when the code invariably has to be modified. Furthermore, in order to get full coverage, code authors will often have to re-organize their code so that it is more modular, so that each component can be tested separately, which reduces interdependencies between modules and layers, and makes for code that is easier to reason about and audit.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

@audit Multiple files
1: 


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L1-L1) 


</details>


### [NC&#x2011;24] [NatSpec] Natspec `@title` is missing from `contract` 



*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) 


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) 


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) 


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) 


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) 


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) 


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) 


</details>


### [NC&#x2011;25] Top level pragma declarations should be separated by two blank lines 



*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L2-L4) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U88, U80} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L2-L4) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U96, U88, U80} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L2-L4) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L2-L4) 


```solidity

File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U80, U88} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L2-L4) 


```solidity

File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U104, U88, U80, U64, U32} from "contracts/libraries/PRBMathHelper.sol";

19: import {console} from "contracts/libraries/console.sol";
20: 
21: contract RedemptionFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L2-L4) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L19-L21)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

2: pragma solidity 0.8.21;
3: 
4: import {IBridge} from "contracts/interfaces/IBridge.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L2-L4) 


```solidity

File: contracts/libraries/LibBytes.sol

2: pragma solidity 0.8.21;
3: 
4: import {MTypes} from "contracts/libraries/DataTypes.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L2-L4) 


```solidity

File: contracts/libraries/LibOracle.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L2-L4) 


```solidity

File: contracts/libraries/LibOrders.sol

2: pragma solidity 0.8.21;
3: 
4: import {U256, U104, U80, U88, U16} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L2-L4) 


```solidity

File: contracts/libraries/LibSRUtil.sol

2: pragma solidity 0.8.21;
3: 
4: import {U88, U256} from "contracts/libraries/PRBMathHelper.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L2-L4) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

08: import {U256} from "contracts/libraries/PRBMathHelper.sol";
09: 
10: interface IUniswapV3Pool {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L8-L10) 


</details>


### [NC&#x2011;26] Unused Import 
Some files/Items are imported but never used


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

//@audit `console` is not used
19: import {console} from "contracts/libraries/console.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L19-L19) 


</details>


### [NC&#x2011;27] Missing upgradability functionality 
At the begining of a project, there is always the need to modify of add something to the source code especialy if any vulnerability is discovered. Therefore, having such system is crusial at least at the first stages of the project


*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) 


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) 


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) 


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) 


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) 


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) 


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {

21: library OracleLibrary {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L21-L21)


</details>


### [NC&#x2011;28] Consider using SMTChecker 
The SMTChecker is a valuable tool for Solidity developers as it helps detect potential vulnerabilities and logical errors in the contract's code. By utilizing Satisfiability Modulo Theories (SMT) solvers, it can reason about the potential states a contract can be in, and therefore, identify conditions that could lead to undesirable behavior. This automatic formal verification can catch issues that might otherwise be missed in manual code reviews or standard testing, enhancing the overall contract's security and reliability.


*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L2-L2) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L2-L2) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L2-L2) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L2-L2) 


```solidity

File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L2-L2) 


```solidity

File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L2-L2) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L2-L2) 


```solidity

File: contracts/libraries/LibBytes.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L2-L2) 


```solidity

File: contracts/libraries/LibOracle.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L2-L2) 


```solidity

File: contracts/libraries/LibOrders.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L2-L2) 


```solidity

File: contracts/libraries/LibSRUtil.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L2-L2) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L2-L2) 


</details>


### [NC&#x2011;29] Complex function controle flow 
Due to multiple if, loop and conditions the following functions has a very complex controle flow that could make auditing very difficult to cover all possible path\nTherefore, consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns


*There are 13 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

130:     function bidMatchAlgo(
131:         address asset,
132:         STypes.Order memory incomingBid,
133:         MTypes.OrderHint[] memory orderHintArray,
134:         MTypes.BidMatchAlgo memory b
135:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
136:         uint256 minBidEth = LibAsset.minBidEth(asset);
137:         MTypes.Match memory matchTotal;
138: 
139:         while (true) {
140:             // @dev Handles scenario when no sells left after partial fill
141:             if (b.askId == C.TAIL && b.shortId == C.TAIL) {
142:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
144:                 }
145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
146:             }
147: 
148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);
149: 
150:             if (incomingBid.price >= lowestSell.price) {
151:                 // Consider bid filled if only dust amount left
152:                 if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
154:                 }
155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
156:                 if (incomingBid.ercAmount > lowestSell.ercAmount) {
157:                     incomingBid.ercAmount -= lowestSell.ercAmount;
158:                     lowestSell.ercAmount = 0;
159:                     if (lowestSell.isShort()) {
160:                         b.matchedShortId = lowestSell.id;
161:                         b.prevShortId = lowestSell.prevId;
162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);
164:                     } else {
165:                         b.matchedAskId = lowestSell.id;
166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);
167:                         b.askId = lowestSell.nextId;
168:                     }
169:                 } else {
170:                     if (incomingBid.ercAmount == lowestSell.ercAmount) {
171:                         if (lowestSell.isShort()) {
172:                             b.matchedShortId = lowestSell.id;
173:                             b.prevShortId = lowestSell.prevId;
174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
175:                         } else {
176:                             b.matchedAskId = lowestSell.id;
177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);
178:                         }
179:                     } else {
180:                         lowestSell.ercAmount -= incomingBid.ercAmount;
181:                         if (lowestSell.isShort()) {
182:                             b.dustShortId = lowestSell.id;
183:                             STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
184:                             lowestShort.ercAmount = lowestSell.ercAmount;
185:                         } else {
186:                             b.dustAskId = lowestSell.id;
187:                             s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
188:                         }
189:                         // Check reduced dust threshold for existing limit orders
190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
191:                             b.dustShortId = b.dustAskId = 0;
192:                         }
193:                     }
194:                     incomingBid.ercAmount = 0;
195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);
196:                 }
197:             } else {
198:                 if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);
200:                 }
201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);
202:             }
203:         }
204:     }

275:     function matchIncomingBid(
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b
280:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
281:         if (matchTotal.fillEth == 0) {
282:             return (0, incomingBid.ercAmount);
283:         }
284: 
285:         STypes.Asset storage Asset = s.asset[asset];
286:         uint256 vault = Asset.vault;
287: 
288:         LibOrders.updateSellOrdersOnMatch(asset, b);
289: 
290:         // Remove last sell order from order book if under dust threshold
291:         // @dev needs to happen after updateSellOrdersOnMatch()
292:         if (b.dustAskId > 0) {
293:             IDiamond(payable(address(this)))._cancelAsk(asset, b.dustAskId);
294:         } else if (b.dustShortId > 0) {
295:             IDiamond(payable(address(this)))._cancelShort(asset, b.dustShortId);
296:         }
297: 
298:         // If at least one short was matched
299:         if (matchTotal.shortFillEth > 0) {
300:             STypes.Vault storage Vault = s.vault[vault];
301: 
302:             // Matched Shares
303:             Vault.dittoMatchedShares += matchTotal.dittoMatchedShares;
304:             // Yield Accounting
305:             Vault.dethCollateral += matchTotal.shortFillEth;
306:             Asset.dethCollateral += matchTotal.shortFillEth;
307:             Asset.ercDebt += matchTotal.fillErc - matchTotal.askFillErc;
308: 
309:             // @dev Approximates the startingShortId after bid is fully executed
310:             STypes.Order storage currentShort = s.shorts[asset][b.shortId];
311:             O shortOrderType = currentShort.orderType;
312:             STypes.Order storage prevShort = s.shorts[asset][b.prevShortId];
313:             O prevShortOrderType = prevShort.orderType;
314: 
315:             if (shortOrderType != O.Cancelled && shortOrderType != O.Matched) {
316:                 Asset.startingShortId = b.shortId;
317:             } else if (prevShortOrderType != O.Cancelled && prevShortOrderType != O.Matched && prevShort.price >= b.oraclePrice) {
318:                 Asset.startingShortId = b.prevShortId;
319:             } else {
320:                 if (b.isMovingFwd) {
321:                     Asset.startingShortId = currentShort.nextId;
322:                 } else {
323:                     Asset.startingShortId = s.shorts[asset][b.shortHintId].nextId;
324:                 }
325:             }
326:         }
327: 
328:         // Match bid
329:         address bidder = incomingBid.addr; // saves 18 gas
330:         s.vaultUser[vault][bidder].ethEscrowed -= matchTotal.fillEth;
331:         s.assetUser[asset][bidder].ercEscrowed += matchTotal.fillErc;
332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);
333: 
334:         // @dev match price is based on the order that was already on orderbook
335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);
336:         return (matchTotal.fillEth, incomingBid.ercAmount);
337:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L130-L204) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L275-L337)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

35:     function createLimitShort(
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43:         MTypes.CreateLimitShortParam memory p;
44:         STypes.Asset storage Asset = s.asset[asset];
45:         STypes.Order memory incomingShort;
46: 
47:         // @dev create "empty" SR. Fail early.
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49: 
50:         uint256 cr = LibOrders.convertCR(shortOrderCR);
51:         if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52:             revert Errors.InvalidCR();
53:         }
54: 
55:         // @dev minShortErc needs to be modified (bigger) when cr < 1
56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57:         p.eth = price.mul(ercAmount);
58:         p.minAskEth = LibAsset.minAskEth(asset);
59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60: 
61:         // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63: 
64:         incomingShort.addr = msg.sender;
65:         incomingShort.price = price;
66:         incomingShort.ercAmount = ercAmount;
67:         incomingShort.id = Asset.orderIdCounter;
68:         incomingShort.orderType = O.LimitShort;
69:         incomingShort.creationTime = LibOrders.getOffsetTime();
70:         incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71: 
72:         p.startingId = s.bids[asset][C.HEAD].nextId;
73:         STypes.Order storage highestBid = s.bids[asset][p.startingId];
74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75:         if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77:         }
78: 
79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81:             revert Errors.BelowRecoveryModeCR();
82:         }
83: 
84:         // @dev reading spot oracle price
85:         if (incomingShort.price < p.oraclePrice) {
86:             LibOrders.addShort(asset, incomingShort, orderHintArray);
87:         } else {
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89:         }
90:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L35-L90) 


```solidity

File: contracts/facets/ExitShortFacet.sol

142:     function exitShort(
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
150:         MTypes.ExitShort memory e;
151:         e.asset = asset;
152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray);
153: 
154:         STypes.Asset storage Asset = s.asset[e.asset];
155:         STypes.ShortRecord storage short = s.shortRecords[e.asset][msg.sender][id];
156: 
157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder
158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
159:             asset: asset,
160:             initialStatus: short.status,
161:             shortOrderId: shortOrderId,
162:             shortRecordId: id,
163:             shorter: msg.sender
164:         });
165: 
166:         short.updateErcDebt(e.asset);
167: 
168:         // @dev if short order was cancelled, fully exit
169:         e.buybackAmount = e.shortOrderIsCancelled ? short.ercDebt : buybackAmount;
170:         e.beforeExitCR = getCollateralRatioNonPrice(short);
171:         e.ercDebt = short.ercDebt;
172:         e.collateral = short.collateral;
173: 
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
175: 
176:         {
177:             uint256 ethAmount = price.mul(e.buybackAmount);
178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();
179:         }
180: 
181:         // Temporary accounting to enable bid
182:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
183:         VaultUser.ethEscrowed += e.collateral;
184: 
185:         // Create bid with current msg.sender
186:         (e.ethFilled, e.ercAmountLeft) =
187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
189:         e.ercFilled = e.buybackAmount - e.ercAmountLeft;
190:         Asset.ercDebt -= e.ercFilled;
191:         s.assetUser[e.asset][msg.sender].ercEscrowed -= e.ercFilled;
192: 
193:         // Refund the rest of the collateral if ercDebt is fully paid back
194:         if (e.ercDebt == e.ercFilled) {
195:             // Full Exit
196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt);
197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy
198:         } else {
199:             short.collateral -= e.ethFilled;
200:             short.ercDebt -= e.ercFilled;
201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();
202: 
203:             // @dev Only allow partial exit if the CR is same or better than before
204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();
205: 
206:             // @dev collateral already subtracted in exitShort()
207:             VaultUser.ethEscrowed -= e.collateral - e.ethFilled;
208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt);
209:         }
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
211:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L142-L211) 


```solidity

File: contracts/facets/RedemptionFacet.sol

056:     function proposeRedemption(
057:         address asset,
058:         MTypes.ProposalInput[] calldata proposalInput,
059:         uint88 redemptionAmount,
060:         uint88 maxRedemptionFee
061:     ) external isNotFrozen(asset) nonReentrant {
062:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
063:         MTypes.ProposeRedemption memory p;
064:         p.asset = asset;
065:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
066:         uint256 minShortErc = LibAsset.minShortErc(p.asset);
067: 
068:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
069: 
070:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
071: 
072:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
073:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
074: 
075:         p.oraclePrice = LibOracle.getPrice(p.asset);
076: 
077:         bytes memory slate;
078:         for (uint8 i = 0; i < proposalInput.length; i++) {
079:             p.shorter = proposalInput[i].shorter;
080:             p.shortId = proposalInput[i].shortId;
081:             p.shortOrderId = proposalInput[i].shortOrderId;
082:             // @dev Setting this above _onlyValidShortRecord to allow skipping
083:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
084: 
085:             /// Evaluate proposed shortRecord
086: 
087:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
088: 
089:             currentSR.updateErcDebt(p.asset);
090:             p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
091: 
092:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold
093:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
094: 
095:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
096:             if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
097:                 p.amountProposed = currentSR.ercDebt;
098:             } else {
099:                 p.amountProposed = redemptionAmount - p.totalAmountProposed;
100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102:             }
103: 
104:             /// At this point, the shortRecord passes all checks and will be included in the slate
105: 
106:             p.previousCR = p.currentCR;
107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
115: 
116:             p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117:             if (p.colRedeemed > currentSR.collateral) {
118:                 p.colRedeemed = currentSR.collateral;
119:             }
120: 
121:             currentSR.collateral -= p.colRedeemed;
122:             currentSR.ercDebt -= p.amountProposed;
123: 
124:             p.totalAmountProposed += p.amountProposed;
125:             p.totalColRedeemed += p.colRedeemed;
126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes
128:             // instead of usual abi.encode to save on extra zeros being written
129:             slate = bytes.concat(
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
137: 
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139:             p.redemptionCounter++;
140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141:         }
142: 
143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144: 
145:         // @dev SSTORE2 the entire proposalData after validating proposalInput
146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147:         redeemerAssetUser.slateLength = p.redemptionCounter;
148:         redeemerAssetUser.oraclePrice = p.oraclePrice;
149:         redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150: 
151:         STypes.Asset storage Asset = s.asset[p.asset];
152:         Asset.ercDebt -= p.totalAmountProposed;
153: 
154:         uint32 protocolTime = LibOrders.getOffsetTime();
155:         redeemerAssetUser.timeProposed = protocolTime;
156:         // @dev Calculate the dispute period
157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158: 
159:         /*
160:         +-------+------------+
161:         | CR(X) |  Hours(Y)  |
162:         +-------+------------+
163:         | 1.1   |     0      |
164:         | 1.2   |    .333    |
165:         | 1.3   |    .75     |
166:         | 1.5   |    1.5     |
167:         | 1.7   |     3      |
168:         | 2.0   |     6      |
169:         +-------+------------+
170: 
171:         Creating fixed points and interpolating between points on the graph without using exponentials
172:         Using simple y = mx + b formula
173:         
174:         where x = currentCR - previousCR
175:         m = (y2-y1)/(x2-x1)
176:         b = previous fixed point (Y)
177:         */
178: 
179:         uint256 m;
180: 
181:         if (p.currentCR > 1.7 ether) {
182:             m = uint256(3 ether).div(0.3 ether);
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184:         } else if (p.currentCR > 1.5 ether) {
185:             m = uint256(1.5 ether).div(0.2 ether);
186:             redeemerAssetUser.timeToDispute =
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188:         } else if (p.currentCR > 1.3 ether) {
189:             m = uint256(0.75 ether).div(0.2 ether);
190:             redeemerAssetUser.timeToDispute =
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192:         } else if (p.currentCR > 1.2 ether) {
193:             m = uint256(0.417 ether).div(0.1 ether);
194:             redeemerAssetUser.timeToDispute =
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196:         } else if (p.currentCR > 1.1 ether) {
197:             m = uint256(C.ONE_THIRD.div(0.1 ether));
198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199:         }
200: 
201:         redeemerAssetUser.oraclePrice = p.oraclePrice;
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203: 
204:         uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206: 
207:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209:         VaultUser.ethEscrowed -= redemptionFee;
210:         emit Events.ProposeRedemption(p.asset, msg.sender);
211:     }

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230:         MTypes.DisputeRedemption memory d;
231:         d.asset = asset;
232:         d.redeemer = redeemer;
233: 
234:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236: 
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238: 
239:         MTypes.ProposalData[] memory decodedProposalData =
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241: 
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244:                 revert Errors.CannotDisputeWithRedeemerProposal();
245:             }
246:         }
247: 
248:         STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249:         // Match continue (skip) conditions in proposeRedemption()
250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);
251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252: 
253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254:         MTypes.ProposalData memory currentProposal;
255:         STypes.Asset storage Asset = s.asset[d.asset];
256: 
257:         uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258: 
259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260:         {
261:             // @dev All proposals from the incorrectIndex onward will be removed
262:             // @dev Thus the proposer can only redeem a portion of their original slate
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264:                 currentProposal = decodedProposalData[i];
265: 
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267:                 currentSR.collateral += currentProposal.colRedeemed;
268:                 currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269: 
270:                 d.incorrectCollateral += currentProposal.colRedeemed;
271:                 d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272:             }
273: 
274:             s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275:             Asset.dethCollateral += d.incorrectCollateral;
276:             Asset.ercDebt += d.incorrectErcDebt;
277: 
278:             // @dev Update the redeemer's SSTORE2Pointer
279:             if (incorrectIndex > 0) {
280:                 redeemerAssetUser.slateLength = incorrectIndex;
281:             } else {
282:                 // @dev this implies everything in the redeemer's proposal was incorrect
283:                 delete redeemerAssetUser.SSTORE2Pointer;
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);
285:             }
286: 
287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289:             uint256 penaltyPct = LibOrders.min(
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );
292: 
293:             uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294: 
295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296:             redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297:             s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298:         } else {
299:             revert Errors.InvalidRedemptionDispute();
300:         }
301:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L56-L211) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L301)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

039:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
040:         internal
041:         returns (uint88)
042:     {
043:         AppStorage storage s = appStorage();
044:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];
045: 
046:         uint88 creditReth;
047:         uint88 creditSteth;
048:         if (bridgePointer == VAULT.BRIDGE_RETH) {
049:             // Withdraw RETH
050:             creditReth = VaultUser.bridgeCreditReth;
051:             if (creditReth >= amount) {
052:                 VaultUser.bridgeCreditReth -= amount;
053:                 return 0;
054:             }
055: 
056:             VaultUser.bridgeCreditReth = 0;
057:             amount -= creditReth;
058:             creditSteth = VaultUser.bridgeCreditSteth;
059:             if (creditSteth < C.ROUNDING_ZERO) {
060:                 // Valid withdraw when no STETH credits
061:                 return amount;
062:             } else {
063:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
064:                     // Can withdraw RETH using STETH credit when STETH bridge is empty
065:                     if (creditSteth >= amount) {
066:                         VaultUser.bridgeCreditSteth -= amount;
067:                         return 0;
068:                     } else {
069:                         VaultUser.bridgeCreditSteth = 0;
070:                         return amount - creditSteth;
071:                     }
072:                 } else {
073:                     // Must use available bridge credits on withdrawal
074:                     // @dev Prevents abusing bridge for arbitrage
075:                     revert Errors.MustUseExistingBridgeCredit();
076:                 }
077:             }
078:         } else {
079:             // Withdraw STETH
080:             creditSteth = VaultUser.bridgeCreditSteth;
081:             if (creditSteth >= amount) {
082:                 VaultUser.bridgeCreditSteth -= amount;
083:                 return 0;
084:             }
085: 
086:             VaultUser.bridgeCreditSteth = 0;
087:             amount -= creditSteth;
088:             creditReth = VaultUser.bridgeCreditReth;
089:             if (creditReth < C.ROUNDING_ZERO) {
090:                 // Valid withdraw when no RETH credits
091:                 return amount;
092:             } else {
093:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
094:                     // Can withdraw STETH using RETH credit when RETH bridge is empty
095:                     if (creditReth >= amount) {
096:                         VaultUser.bridgeCreditReth -= amount;
097:                         return 0;
098:                     } else {
099:                         VaultUser.bridgeCreditReth = 0;
100:                         return amount - creditReth;
101:                     }
102:                 } else {
103:                     // Must use available bridge credits on withdrawal
104:                     // @dev Prevents abusing bridge for arbitrage
105:                     revert Errors.MustUseExistingBridgeCredit();
106:                 }
107:             }
108:         }
109:     }

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
145:         AppStorage storage s = appStorage();
146: 
147:         STypes.Asset storage Asset = s.asset[asset];
148:         uint256 vault = Asset.vault;
149: 
150:         if (vault == VAULT.ONE) {
151:             STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
152:             uint88 creditReth = VaultUserFrom.bridgeCreditReth;
153:             uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
154:             STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];
155: 
156:             if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
157:                 // No bridge credits
158:                 return;
159:             }
160: 
161:             if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
162:                 // Only creditReth
163:                 if (creditReth > collateral) {
164:                     VaultUserFrom.bridgeCreditReth -= collateral;
165:                     VaultUserTo.bridgeCreditReth += collateral;
166:                 } else {
167:                     VaultUserFrom.bridgeCreditReth = 0;
168:                     VaultUserTo.bridgeCreditReth += creditReth;
169:                 }
170:             } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
171:                 // Only creditSteth
172:                 if (creditSteth > collateral) {
173:                     VaultUserFrom.bridgeCreditSteth -= collateral;
174:                     VaultUserTo.bridgeCreditSteth += collateral;
175:                 } else {
176:                     VaultUserFrom.bridgeCreditSteth = 0;
177:                     VaultUserTo.bridgeCreditSteth += creditSteth;
178:                 }
179:             } else {
180:                 // Both creditReth and creditSteth
181:                 uint88 creditTotal = creditReth + creditSteth;
182:                 if (creditTotal > collateral) {
183:                     creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
184:                     creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
185:                     VaultUserFrom.bridgeCreditReth -= creditReth;
186:                     VaultUserFrom.bridgeCreditSteth -= creditSteth;
187:                 } else {
188:                     VaultUserFrom.bridgeCreditReth = 0;
189:                     VaultUserFrom.bridgeCreditSteth = 0;
190:                 }
191:                 VaultUserTo.bridgeCreditReth += creditReth;
192:                 VaultUserTo.bridgeCreditSteth += creditSteth;
193:             }
194:         }
195:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L109) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L195)


```solidity

File: contracts/libraries/LibOracle.sol

069:     function baseOracleCircuitBreaker(
070:         uint256 protocolPrice,
071:         uint80 roundId,
072:         int256 chainlinkPrice,
073:         uint256 timeStamp,
074:         uint256 chainlinkPriceInEth
075:     ) private view returns (uint256 _protocolPrice) {
076:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
077:             || block.timestamp > 2 hours + timeStamp;
078:         uint256 chainlinkDiff =
079:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
080:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;
081: 
082:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
083:         if (invalidFetchData) {
084:             return twapCircuitBreaker();
085:         } else if (priceDeviation) {
086:             // Check valid twap price
087:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
088:             {
089:                 if (twapPrice == 0) {
090:                     return chainlinkPriceInEth;
091:                 }
092: 
093:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
094:                 uint256 twapPriceInEth = twapPriceNormalized.inv();
095:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
096: 
097:                 // Save the price that is closest to saved oracle price
098:                 if (chainlinkDiff <= twapDiff) {
099:                     return chainlinkPriceInEth;
100:                 } else {
101:                     // Check valid twap liquidity
102:                     IERC20 weth = IERC20(C.WETH);
103:                     uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104:                     if (wethBal < 100 ether) {
105:                         return chainlinkPriceInEth;
106:                     }
107:                     return twapPriceInEth;
108:                 }
109:             } catch {
110:                 return chainlinkPriceInEth;
111:             }
112:         } else {
113:             return chainlinkPriceInEth;
114:         }
115:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L115) 


```solidity

File: contracts/libraries/LibOrders.sol

499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
500:         AppStorage storage s = appStorage();
501:         if (b.matchedAskId != 0) {
502:             _updateOrders(s.asks, asset, C.HEAD, b.matchedAskId);
503:         }
504: 
505:         if (b.matchedShortId != 0) {
506:             if (!b.isMovingBack && !b.isMovingFwd) {
507:                 // @dev Handles only matching one thing
508:                 // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block
509:                 _updateOrders(s.shorts, asset, b.prevShortId, b.matchedShortId);
510:             } else if (!b.isMovingBack && b.isMovingFwd) {
511:                 // @dev Handles moving forward only
512:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, b.matchedShortId);
513:             } else if (b.isMovingBack && !b.isMovingFwd) {
514:                 //@handles moving backwards only.
515:                 _updateOrders(s.shorts, asset, b.prevShortId, b.shortHintId);
516:             } else if (b.isMovingBack && b.isMovingFwd) {
517:                 uint16 id = b.prevShortId == b.firstShortIdBelowOracle ? b.shortHintId : b.matchedShortId;
518:                 // @dev Handle going backward and forward
519:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, id);
520:             }
521:         }
522:     }

556:     function sellMatchAlgo(
557:         address asset,
558:         STypes.Order memory incomingAsk,
559:         MTypes.OrderHint[] memory orderHintArray,
560:         uint256 minAskEth
561:     ) internal {
562:         AppStorage storage s = appStorage();
563:         uint16 startingId = s.bids[asset][C.HEAD].nextId;
564:         if (incomingAsk.price > s.bids[asset][startingId].price) {
565:             if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
566:                 addSellOrder(incomingAsk, asset, orderHintArray);
567:             }
568:             return;
569:         }
570:         // matching loop starts
571:         MTypes.Match memory matchTotal;
572:         while (true) {
573:             STypes.Order memory highestBid = s.bids[asset][startingId];
574:             if (incomingAsk.price <= highestBid.price) {
575:                 // Consider ask filled if only dust amount left
576:                 if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577:                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578:                     incomingAsk.ercAmount = 0;
579:                     matchIncomingSell(asset, incomingAsk, matchTotal);
580:                     return;
581:                 }
582:                 matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
583:                 if (incomingAsk.ercAmount > highestBid.ercAmount) {
584:                     incomingAsk.ercAmount -= highestBid.ercAmount;
585:                     highestBid.ercAmount = 0;
586:                     matchOrder(s.bids, asset, highestBid.id);
587: 
588:                     // loop
589:                     startingId = highestBid.nextId;
590:                     if (startingId == C.TAIL) {
591:                         matchIncomingSell(asset, incomingAsk, matchTotal);
592: 
593:                         if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594:                             addSellOrder(incomingAsk, asset, orderHintArray);
595:                         }
596:                         s.bids[asset][C.HEAD].nextId = C.TAIL;
597:                         return;
598:                     }
599:                 } else {
600:                     if (incomingAsk.ercAmount == highestBid.ercAmount) {
601:                         matchOrder(s.bids, asset, highestBid.id);
602:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603:                     } else {
604:                         highestBid.ercAmount -= incomingAsk.ercAmount;
605:                         s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607:                         // Check reduced dust threshold for existing limit orders
608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609:                             cancelBid(asset, highestBid.id);
610:                         }
611:                     }
612:                     incomingAsk.ercAmount = 0;
613:                     matchIncomingSell(asset, incomingAsk, matchTotal);
614:                     return;
615:                 }
616:             } else {
617:                 updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
618:                 matchIncomingSell(asset, incomingAsk, matchTotal);
619: 
620:                 if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621:                     addSellOrder(incomingAsk, asset, orderHintArray);
622:                 }
623:                 return;
624:             }
625:         }
626:     }

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
729:         AppStorage storage s = appStorage();
730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset);
731:         uint256 savedPrice = asset.getPrice();
732:         asset.setPriceAndTime(oraclePrice, getOffsetTime());
733:         if (oraclePrice == savedPrice) {
734:             return; // no need to update startingShortId
735:         }
736: 
737:         STypes.Asset storage Asset = s.asset[asset];
738:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;
739:         if (shortOrdersIsEmpty) {
740:             Asset.startingShortId = C.HEAD;
741:         } else {
742:             uint16 shortHintId;
743:             for (uint256 i = 0; i < shortHintArray.length;) {
744:                 shortHintId = shortHintArray[i];
745:                 unchecked {
746:                     ++i;
747:                 }
748: 
749:                 STypes.Order storage short = s.shorts[asset][shortHintId];
750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }
756: 
757:                 uint80 shortPrice = short.price;
758:                 uint16 prevId = short.prevId;
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;
760:                 // @dev force hint to be within 0.5% of oraclePrice
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764: 
765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {
773:                     Asset.startingShortId = C.HEAD;
774:                     return;
775:                 }
776:             }
777: 
778:             revert Errors.BadShortHint();
779:         }
780:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L499-L522) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L556-L626), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L780)


```solidity

File: contracts/libraries/LibSRUtil.sol

072:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
073:         internal
074:         returns (bool isCancelled)
075:     {
076:         AppStorage storage s = appStorage();
077: 
078:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
079:         uint256 minShortErc = LibAsset.minShortErc(asset);
080: 
081:         if (initialStatus == SR.PartialFill) {
082:             // Verify shortOrder
083:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
084:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
085: 
086:             if (shortRecord.status == SR.Closed) {
087:                 // Check remaining shortOrder
088:                 if (shortOrder.ercAmount < minShortErc) {
089:                     // @dev The resulting SR will not have PartialFill status after cancel
090:                     LibOrders.cancelShort(asset, shortOrderId);
091:                     isCancelled = true;
092:                 }
093:             } else {
094:                 // Check remaining shortOrder and remaining shortRecord
095:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
096:             }
097:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) {
098:             revert Errors.CannotLeaveDustAmount();
099:         }
100:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L100) 


</details>


### [NC&#x2011;30] Consider bounding input array length 
The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to `require()` that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.


*There are 2 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

//@audit array name proposalInput
056:     function proposeRedemption(
057:         address asset,
058:         MTypes.ProposalInput[] calldata proposalInput,
059:         uint88 redemptionAmount,
060:         uint88 maxRedemptionFee
061:     ) external isNotFrozen(asset) nonReentrant {
062:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
063:         MTypes.ProposeRedemption memory p;
064:         p.asset = asset;
065:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
066:         uint256 minShortErc = LibAsset.minShortErc(p.asset);
067: 
068:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
069: 
070:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
071: 
072:         // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
073:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
074: 
075:         p.oraclePrice = LibOracle.getPrice(p.asset);
076: 
077:         bytes memory slate;
078:         for (uint8 i = 0; i < proposalInput.length; i++) {
079:             p.shorter = proposalInput[i].shorter;
080:             p.shortId = proposalInput[i].shortId;
081:             p.shortOrderId = proposalInput[i].shortOrderId;
082:             // @dev Setting this above _onlyValidShortRecord to allow skipping
083:             STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
084: 
085:             /// Evaluate proposed shortRecord
086: 
087:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
088: 
089:             currentSR.updateErcDebt(p.asset);
090:             p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
091: 
092:             // @dev Skip if proposal is not sorted correctly or if above redemption threshold
093:             if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
094: 
095:             // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
096:             if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
097:                 p.amountProposed = currentSR.ercDebt;
098:             } else {
099:                 p.amountProposed = redemptionAmount - p.totalAmountProposed;
100:                 // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101:                 if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102:             }
103: 
104:             /// At this point, the shortRecord passes all checks and will be included in the slate
105: 
106:             p.previousCR = p.currentCR;
107: 
108:             // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109:             // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110:             STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111:             if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113:                 LibOrders.cancelShort(asset, p.shortOrderId);
114:             }
115: 
116:             p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117:             if (p.colRedeemed > currentSR.collateral) {
118:                 p.colRedeemed = currentSR.collateral;
119:             }
120: 
121:             currentSR.collateral -= p.colRedeemed;
122:             currentSR.ercDebt -= p.amountProposed;
123: 
124:             p.totalAmountProposed += p.amountProposed;
125:             p.totalColRedeemed += p.colRedeemed;
126: 
127:             // @dev directly write the properties of MTypes.ProposalData into bytes
128:             // instead of usual abi.encode to save on extra zeros being written
129:             slate = bytes.concat(
130:                 slate,
131:                 bytes20(p.shorter),
132:                 bytes1(p.shortId),
133:                 bytes8(uint64(p.currentCR)),
134:                 bytes11(p.amountProposed),
135:                 bytes11(p.colRedeemed)
136:             );
137: 
138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139:             p.redemptionCounter++;
140:             if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141:         }
142: 
143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144: 
145:         // @dev SSTORE2 the entire proposalData after validating proposalInput
146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147:         redeemerAssetUser.slateLength = p.redemptionCounter;
148:         redeemerAssetUser.oraclePrice = p.oraclePrice;
149:         redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150: 
151:         STypes.Asset storage Asset = s.asset[p.asset];
152:         Asset.ercDebt -= p.totalAmountProposed;
153: 
154:         uint32 protocolTime = LibOrders.getOffsetTime();
155:         redeemerAssetUser.timeProposed = protocolTime;
156:         // @dev Calculate the dispute period
157:         // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158: 
159:         /*
160:         +-------+------------+
161:         | CR(X) |  Hours(Y)  |
162:         +-------+------------+
163:         | 1.1   |     0      |
164:         | 1.2   |    .333    |
165:         | 1.3   |    .75     |
166:         | 1.5   |    1.5     |
167:         | 1.7   |     3      |
168:         | 2.0   |     6      |
169:         +-------+------------+
170: 
171:         Creating fixed points and interpolating between points on the graph without using exponentials
172:         Using simple y = mx + b formula
173:         
174:         where x = currentCR - previousCR
175:         m = (y2-y1)/(x2-x1)
176:         b = previous fixed point (Y)
177:         */
178: 
179:         uint256 m;
180: 
181:         if (p.currentCR > 1.7 ether) {
182:             m = uint256(3 ether).div(0.3 ether);
183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184:         } else if (p.currentCR > 1.5 ether) {
185:             m = uint256(1.5 ether).div(0.2 ether);
186:             redeemerAssetUser.timeToDispute =
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188:         } else if (p.currentCR > 1.3 ether) {
189:             m = uint256(0.75 ether).div(0.2 ether);
190:             redeemerAssetUser.timeToDispute =
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192:         } else if (p.currentCR > 1.2 ether) {
193:             m = uint256(0.417 ether).div(0.1 ether);
194:             redeemerAssetUser.timeToDispute =
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196:         } else if (p.currentCR > 1.1 ether) {
197:             m = uint256(C.ONE_THIRD.div(0.1 ether));
198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199:         }
200: 
201:         redeemerAssetUser.oraclePrice = p.oraclePrice;
202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203: 
204:         uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206: 
207:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209:         VaultUser.ethEscrowed -= redemptionFee;
210:         emit Events.ProposeRedemption(p.asset, msg.sender);
211:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L56-L211) 


```solidity

File: contracts/libraries/LibOrders.sol

//@audit array name shortHintArray
728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
729:         AppStorage storage s = appStorage();
730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset);
731:         uint256 savedPrice = asset.getPrice();
732:         asset.setPriceAndTime(oraclePrice, getOffsetTime());
733:         if (oraclePrice == savedPrice) {
734:             return; // no need to update startingShortId
735:         }
736: 
737:         STypes.Asset storage Asset = s.asset[asset];
738:         bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;
739:         if (shortOrdersIsEmpty) {
740:             Asset.startingShortId = C.HEAD;
741:         } else {
742:             uint16 shortHintId;
743:             for (uint256 i = 0; i < shortHintArray.length;) {
744:                 shortHintId = shortHintArray[i];
745:                 unchecked {
746:                     ++i;
747:                 }
748: 
749:                 STypes.Order storage short = s.shorts[asset][shortHintId];
750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }
756: 
757:                 uint80 shortPrice = short.price;
758:                 uint16 prevId = short.prevId;
759:                 uint80 prevShortPrice = s.shorts[asset][prevId].price;
760:                 // @dev force hint to be within 0.5% of oraclePrice
761:                 bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762:                 bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763:                 bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764: 
765:                 if (isExactStartingShort) {
766:                     Asset.startingShortId = shortHintId;
767:                     return;
768:                 } else if (startingShortWithinOracleRange) {
769:                     // @dev prevShortPrice >= oraclePrice
770:                     Asset.startingShortId = prevId;
771:                     return;
772:                 } else if (allShortUnderOraclePrice) {
773:                     Asset.startingShortId = C.HEAD;
774:                     return;
775:                 }
776:             }
777: 
778:             revert Errors.BadShortHint();
779:         }
780:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L780) 


</details>


### [NC&#x2011;31] [NatSpec] Natspec `@dev` is missing from `contract` 



*There are 89 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {

53:     /**
54:      * @notice create a bid order for exiting a short, only callable by specific contracts
55:      *
56:      * @param sender Address of caller (only for exiting a short)
57:      * @param asset The market that will be impacted
58:      * @param price Unit price in eth for erc
59:      * @param ercAmount Amount of erc to buy
60:      * @param shortHintArray Array of hint ID for gas-optimized short matching above oracle price
61:      *
62:      * @return ethFilled Amount of eth filled
63:      * @return ercAmountLeft Amount of erc not matched
64:      */

77:     function _createBid(

119:     /**
120:      * @notice The matching algorithm for bids
121:      *
122:      * @param asset The market that will be impacted
123:      * @param incomingBid Active bid order
124:      * @param orderHintArray Array of hint ID for gas-optimized sorted placement on market
125:      * @param b Memory struct used throughout bidMatchAlgo
126:      *
127:      * @return ethFilled Amount of eth filled
128:      * @return ercAmountLeft Amount of erc not matched
129:      */

264:     /**
265:      * @notice Final settlement of incoming bid
266:      *
267:      * @param asset The market that will be impacted
268:      * @param incomingBid Active bid order
269:      * @param matchTotal Struct of the running matched totals
270:      * @param b Memory struct used throughout bidMatchAlgo
271:      *
272:      * @return ethFilled Amount of eth filled
273:      * @return ercAmountLeft Amount of erc not matched
274:      */

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

358:     function _shortDirectionHandler(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L53-L64), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L77), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L119-L129), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L264-L274), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L358)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {

30:     constructor(address _dusd) {

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {

113:     /**
114:      * @notice Sets the memory struct m with initial data
115:      *
116:      * @param asset The market that will be impacted
117:      * @param shorter Shorter getting liquidated
118:      * @param id Id of short getting liquidated
119:      *
120:      * @return m Memory struct used throughout PrimaryLiquidationFacet.sol
121:      */

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {

234:     /**
235:      * @notice Handles accounting in event of full or partial liquidations
236:      *
237:      * @param m Memory struct used throughout PrimaryLiquidationFacet.sol
238:      *
239:      */


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L96-L96), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L113-L121), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L234-L239)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {

29:     constructor(address _rethBridge, address _stethBridge) {

34:     /**
35:      * @notice Returns the present value of all bridges within a given vault
36:      *
37:      * @param vault The vault being queried
38:      *
39:      */

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L29), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L34-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L169-L169)


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {

28:     constructor(address _dusd) {

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L28), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213)


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L31), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L368-L368), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L21-L21), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L198-L198)


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11)


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {

19:     function getOraclePrice(address asset) internal view returns (uint256) {

69:     function baseOracleCircuitBreaker(

117:     function oracleCircuitBreaker(

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

156:     function getTime(address asset) internal view returns (uint256 creationTime) {

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L117), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

121:     /**
122:      * @notice Add short struct onto market
123:      *
124:      * @param asset The market that will be impacted
125:      * @param order The short struct passed from shortMatchAlgo
126:      * @param orderHintArray array of Id passed in front end for optimized looping
127:      */

146:     /**
147:      * @notice Add ask/short struct onto market
148:      *
149:      * @param asset The market that will be impacted
150:      * @param incomingOrder The ask or short struct passed from sellMatchAlgo
151:      * @param orderHintArray array of Id passed in front end for optimized looping
152:      */

221:     /**
222:      * @notice Verifies that bid id is between two id based on price
223:      *
224:      * @param asset The market that will be impacted
225:      * @param _prevId The first id supposedly preceding the new price
226:      * @param _newPrice price of prospective order
227:      * @param _nextId The first id supposedly following the new price
228:      *
229:      * @return direction int direction to search (PREV, EXACT, NEXT)
230:      */

250:     /**
251:      * @notice Verifies that short id is between two id based on price
252:      *
253:      * @param asset The market that will be impacted
254:      * @param _prevId The first id supposedly preceding the new price
255:      * @param _newPrice price of prospective order
256:      * @param _nextId The first id supposedly following the new price
257:      *
258:      * @return direction int direction to search (PREV, EXACT, NEXT)
259:      */

320:     function _reuseOrderIds(

351:     /**
352:      * @notice Helper function for finding the (previous) id so that an incoming
353:      * @notice order can be placed onto the correct market.
354:      * @notice Uses hintId if possible, otherwise fallback to traversing the
355:      * @notice list of orders starting from HEAD
356:      *
357:      * @param orders the order mapping
358:      * @param asset The market that will be impacted
359:      * @param incomingOrder the Order to be placed
360:      * @param hintId Id used to optimize finding the place to insert into ob
361:      */

391:     /**
392:      * @notice Verifies that an id is between two id based on price and orderType
393:      *
394:      * @param asset The market that will be impacted
395:      * @param prevId The first id supposedly preceding the new price
396:      * @param newPrice price of prospective order
397:      * @param nextId The first id supposedly following the new price
398:      * @param orderType order type (bid, ask, short)
399:      *
400:      * @return direction int direction to search (PREV, EXACT, NEXT)
401:      */

420:     function normalizeOrderType(O o) private pure returns (O newO) {

430:     /**
431:      * @notice Helper function for finding and returning id of potential order
432:      *
433:      * @param orders the order mapping
434:      * @param asset The market that will be impacted
435:      * @param direction int direction to search (PREV, EXACT, NEXT)
436:      * @param hintId hint id
437:      * @param _newPrice price of prospective order used to find the id
438:      * @param orderType which OrderType to verify
439:      */

524:     /**
525:      * @notice Base helper function for updating any kind of orders
526:      *
527:      * @param orders the order mapping
528:      * @param asset The market that will be impacted
529:      * @param headId Either HEAD or first SHORT with price >= oracle price
530:      * @param lastMatchedId Most recent matched SHORT in a specific Bid transaction
531:      */

547:     /**
548:      * @notice The matching algorithm for asks
549:      *
550:      * @param asset The market that will be impacted
551:      * @param incomingAsk Newly created ask struct
552:      * @param orderHintArray Id passed in from front end for optimized looping
553:      * @param minAskEth Minimum ask dust amount
554:      *
555:      */

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

645:     /**
646:      * @notice Final settlement of incoming ask
647:      *
648:      * @param asset The market that will be impacted
649:      * @param incomingAsk Newly created ask struct
650:      * @param matchTotal Struct of the running matched totals
651:      */

661:     /**
662:      * @notice Final settlement of incoming short
663:      *
664:      * @param asset The market that will be impacted
665:      * @param incomingShort Newly created short struct
666:      * @param matchTotal Struct of the running matched totals
667:      */

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

783:     function updateOracleAndStartingShortViaThreshold(

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

826:     function findOrderHintId(

854:     function cancelBid(address asset, uint16 id) internal {

868:     function cancelAsk(address asset, uint16 id) internal {

882:     function cancelShort(address asset, uint16 id) internal {

955:     function handlePriceDiscount(address asset, uint80 price) internal {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L121-L127), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L146-L152), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L221-L230), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L250-L259), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L320), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L351-L361), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L391-L401), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L430-L439), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L524-L531), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L547-L555), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L645-L651), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L661-L667), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L728), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L783), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L803-L803), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L810-L810), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {

19: /// @title Oracle library
20: /// @notice Provides functions to integrate with V3 pool oracle
21: library OracleLibrary {

11:     function observe(uint32[] calldata secondsAgos)

22:     /// @notice Given a tick and a token amount, calculates the amount of token received in exchange
23:     /// @param tick Tick value used to calculate the quote
24:     /// @param baseAmount Amount of token to be converted
25:     /// @param baseToken Address of an ERC20 token contract used as the baseAmount denomination
26:     /// @param quoteToken Address of an ERC20 token contract used as the quoteAmount denomination
27:     /// @return quoteAmount Amount of quoteToken received for baseAmount of baseToken

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L19-L21), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L11-L11), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L22-L27), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47)


</details>


### [NC&#x2011;32] [NatSpec] Natspec `@notice` is missing from `contract` 



*There are 70 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

20: contract BidOrdersFacet is Modifiers {

77:     function _createBid(

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

358:     function _shortDirectionHandler(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L77), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L358)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

18: contract ShortOrdersFacet is Modifiers {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L18-L18) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

21: contract PrimaryLiquidationFacet is Modifiers {

30:     constructor(address _dusd) {

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L96-L96), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

18: contract BridgeRouterFacet is Modifiers {

29:     constructor(address _rethBridge, address _stethBridge) {

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L29), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L169-L169)


```solidity

File: contracts/facets/ExitShortFacet.sol

19: contract ExitShortFacet is Modifiers {

28:     constructor(address _dusd) {

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L28), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213)


```solidity

File: contracts/facets/RedemptionFacet.sol

21: contract RedemptionFacet is Modifiers {

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L31), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L368-L368), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

16: library LibBridgeRouter {

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L21-L21), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L198-L198)


```solidity

File: contracts/libraries/LibBytes.sol

9: library LibBytes {

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L9-L9) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11)


```solidity

File: contracts/libraries/LibOracle.sol

16: library LibOracle {

19:     function getOraclePrice(address asset) internal view returns (uint256) {

69:     function baseOracleCircuitBreaker(

117:     function oracleCircuitBreaker(

131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

156:     function getTime(address asset) internal view returns (uint256 creationTime) {

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L16-L16) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L117), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

20: library LibOrders {

30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

320:     function _reuseOrderIds(

420:     function normalizeOrderType(O o) private pure returns (O newO) {

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

783:     function updateOracleAndStartingShortViaThreshold(

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

826:     function findOrderHintId(

854:     function cancelBid(address asset, uint16 id) internal {

868:     function cancelAsk(address asset, uint16 id) internal {

882:     function cancelShort(address asset, uint16 id) internal {

955:     function handlePriceDiscount(address asset, uint80 price) internal {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L20-L20) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L30-L30), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L320), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L728), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L783), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L803-L803), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L810-L810), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


```solidity

File: contracts/libraries/LibSRUtil.sol

18: library LibSRUtil {

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L18-L18) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

10: interface IUniswapV3Pool {

11:     function observe(uint32[] calldata secondsAgos)

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L10-L10) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L11-L11), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47)


</details>


### [NC&#x2011;33] Consider splitting long calculations 
The longer a string of operations is, the harder it is to understand it. Consider splitting the full calculation into more steps, with more descriptive temporary variable names, and add extensive comments.


*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/RedemptionFacet.sol

183:             redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

186:             redeemerAssetUser.timeToDispute =
187:                 protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);

190:             redeemerAssetUser.timeToDispute =
191:                 protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);

194:             redeemerAssetUser.timeToDispute =
195:                 protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);

198:             redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L183-L183) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L186-L187), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L190-L191), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L194-L195), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L198-L198)


</details>


### [NC&#x2011;34] `immutable` variable names don\'t follow the Solidity style guide 
For `immutable` variable names, each word should use all capital letters, with underscores separating each word (CONSTANT_CASE)


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

28:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge;

27:     address private immutable stethBridge;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L26-L26) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L27-L27)


```solidity

File: contracts/facets/ExitShortFacet.sol

26:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L26-L26) 


</details>


### [NC&#x2011;35] `private`/`public` function name should start with underscore 
According to solidity style guide, Private or Public function name should start with underscore.


*There are 65 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

//@audit `bidMatchAlgo` is not in CamelCase
130:     function bidMatchAlgo(

//@audit `matchlowestSell` is not in CamelCase
215:     function matchlowestSell(

//@audit `matchIncomingBid` is not in CamelCase
275:     function matchIncomingBid(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L130-L130) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L215-L215), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L275-L275)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit `min88` is not in CamelCase
229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

//@audit `maybeUpdateYield` is not in CamelCase
148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L148-L148) 


```solidity

File: contracts/facets/ExitShortFacet.sol

//@audit `getCollateralRatioNonPrice` is not in CamelCase
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213) 


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit `validRedemptionSR` is not in CamelCase
31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

//@audit `calculateRedemptionFee` is not in CamelCase
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L31) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

//@audit `addDeth` is not in CamelCase
21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

//@audit `assessDeth` is not in CamelCase
39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)

//@audit `withdrawalFeePct` is not in CamelCase
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

//@audit `transferBridgeCredit` is not in CamelCase
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

//@audit `removeDeth` is not in CamelCase
198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L198-L198)


```solidity

File: contracts/libraries/LibBytes.sol

//@audit `readProposalData` is not in CamelCase
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11) 


```solidity

File: contracts/libraries/LibOracle.sol

//@audit `getOraclePrice` is not in CamelCase
19:     function getOraclePrice(address asset) internal view returns (uint256) {

//@audit `baseOracleCircuitBreaker` is not in CamelCase
69:     function baseOracleCircuitBreaker(

//@audit `oracleCircuitBreaker` is not in CamelCase
117:     function oracleCircuitBreaker(

//@audit `twapCircuitBreaker` is not in CamelCase
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

//@audit `setPriceAndTime` is not in CamelCase
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

//@audit `getTime` is not in CamelCase
156:     function getTime(address asset) internal view returns (uint256 creationTime) {

//@audit `getPrice` is not in CamelCase
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {

//@audit `getSavedOrSpotOraclePrice` is not in CamelCase
168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L117), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit `getOffsetTime` is not in CamelCase
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

//@audit `convertCR` is not in CamelCase
35:     function convertCR(uint16 cr) internal pure returns (uint256) {

//@audit `increaseSharesOnMatch` is not in CamelCase
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

//@audit `currentOrders` is not in CamelCase
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

//@audit `isShort` is not in CamelCase
78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

//@audit `addBid` is not in CamelCase
82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

//@audit `addAsk` is not in CamelCase
103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

//@audit `addShort` is not in CamelCase
128:     function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

//@audit `addSellOrder` is not in CamelCase
153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {

//@audit `addOrder` is not in CamelCase
173:     function addOrder(

//@audit `verifyBidId` is not in CamelCase
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)

//@audit `verifySellId` is not in CamelCase
260:     function verifySellId(

//@audit `cancelOrder` is not in CamelCase
289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

//@audit `matchOrder` is not in CamelCase
314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

//@audit `findPrevOfIncomingId` is not in CamelCase
362:     function findPrevOfIncomingId(

//@audit `verifyId` is not in CamelCase
402:     function verifyId(

//@audit `normalizeOrderType` is not in CamelCase
420:     function normalizeOrderType(O o) private pure returns (O newO) {

//@audit `getOrderId` is not in CamelCase
440:     function getOrderId(

//@audit `updateBidOrdersOnMatch` is not in CamelCase
474:     function updateBidOrdersOnMatch(

//@audit `updateSellOrdersOnMatch` is not in CamelCase
499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {

//@audit `sellMatchAlgo` is not in CamelCase
556:     function sellMatchAlgo(

//@audit `matchIncomingSell` is not in CamelCase
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

//@audit `matchIncomingAsk` is not in CamelCase
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {

//@audit `matchIncomingShort` is not in CamelCase
668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {

//@audit `matchHighestBid` is not in CamelCase
705:     function matchHighestBid(

//@audit `updateOracleAndStartingShortViaThreshold` is not in CamelCase
783:     function updateOracleAndStartingShortViaThreshold(

//@audit `updateOracleAndStartingShortViaTimeBidOnly` is not in CamelCase
803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {

//@audit `updateStartingShortIdViaShort` is not in CamelCase
810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

//@audit `findOrderHintId` is not in CamelCase
826:     function findOrderHintId(

//@audit `cancelBid` is not in CamelCase
854:     function cancelBid(address asset, uint16 id) internal {

//@audit `cancelAsk` is not in CamelCase
868:     function cancelAsk(address asset, uint16 id) internal {

//@audit `cancelShort` is not in CamelCase
882:     function cancelShort(address asset, uint16 id) internal {

//@audit `handlePriceDiscount` is not in CamelCase
955:     function handlePriceDiscount(address asset, uint80 price) internal {

//@audit `min` is not in CamelCase
985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

//@audit `max` is not in CamelCase
989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L30-L30) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L128-L128), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L153-L153), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L173-L173), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L231-L231), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L260-L260), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L289-L289), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L314-L314), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L362-L362), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L402-L402), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L440), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L474-L474), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L499-L499), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L556-L556), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L652-L652), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L668-L668), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L705-L705), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L783), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L803-L803), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L810-L810), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


```solidity

File: contracts/libraries/LibSRUtil.sol

//@audit `disburseCollateral` is not in CamelCase
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

//@audit `checkCancelShortOrder` is not in CamelCase
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

//@audit `checkShortMinErc` is not in CamelCase
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

//@audit `checkRecoveryModeViolation` is not in CamelCase
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

//@audit `transferShortRecord` is not in CamelCase
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

//@audit `updateErcDebt` is not in CamelCase
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

//@audit `getQuoteAtTick` is not in CamelCase
28:     function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)

//@audit `estimateTWAP` is not in CamelCase
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L28-L28) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47)


</details>


### [NC&#x2011;36] Assembly block creates dirty bits 
Writing data to the free memory pointer without later updating the free memory pointer will cause there to be dirty bits at that memory location. Not updating the free memory pointer will make it [harder](https://docs.soliditylang.org/en/latest/ir-breaking-changes.html#cleanup) for the optimizer to reason about whether the memory needs to be cleaned, which may lead to worse optimizations. Annotate the block with `assembly ("memory-safe") { ... }` if the memory's value can be discarded. If the memory needs to be saved, update the free memory pointer in addtion to using the annotation. See [this](https://docs.soliditylang.org/en/latest/assembly.html#memory-safety) link for other cases where the annotation can be used


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

28:             assembly {
29:                 // mload works 32 bytes at a time
30:                 let fullWord := mload(add(slate, offset))
31:                 // read 20 bytes
32:                 shorter := shr(96, fullWord) // 0x60 = 96 (256-160)
33:                 // read 8 bytes
34:                 shortId := and(0xff, shr(88, fullWord)) // 0x58 = 88 (96-8), mask of bytes1 = 0xff * 1
35:                 // read 64 bytes
36:                 CR := and(0xffffffffffffffff, shr(24, fullWord)) // 0x18 = 24 (88-64), mask of bytes8 = 0xff * 8
37: 
38:                 fullWord := mload(add(slate, add(offset, 29))) // (29 offset)
39:                 // read 88 bytes
40:                 ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
41:                 // read 88 bytes
42:                 colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
43:             }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L28-L43) 


</details>


### [NC&#x2011;37] Consider adding formal verification proofs 
Consider using formal verification to mathematically prove that your code does what is intended, and does not have any edge cases with unexpected behavior. The solidity compiler itself has this functionality [built in](https://docs.soliditylang.org/en/latest/smtchecker.html#smtchecker-and-formal-verification)


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

@audit Should implement invariant tests
1: 


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L1-L1) 


</details>


### [NC&#x2011;38] Missing zero address check in functions with address parameters 
Adding a zero address check for each address type parameter can prevent errors.


*There are 18 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

//@audit asset,  are not checked
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

//@audit asset,  are not checked
358:     function _shortDirectionHandler(
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b
363:     ) private view {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L363)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit _dusd,  are not checked
30:     constructor(address _dusd) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L30) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

//@audit _rethBridge, _stethBridge,  are not checked
29:     constructor(address _rethBridge, address _stethBridge) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L29) 


```solidity

File: contracts/facets/ExitShortFacet.sol

//@audit _dusd,  are not checked
28:     constructor(address _dusd) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L28) 


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit redeemer,  are not checked
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)

//@audit asset,  are not checked
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L347-L347) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

//@audit asset, from, to,  are not checked
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144) 


```solidity

File: contracts/libraries/LibOracle.sol

//@audit asset,  are not checked
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

//@audit asset,  are not checked
156:     function getTime(address asset) internal view returns (uint256 creationTime) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit asset,  are not checked
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

//@audit orders, asset,  are not checked
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

//@audit orders, asset,  are not checked
320:     function _reuseOrderIds(
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {

//@audit orders, asset,  are not checked
532:     function _updateOrders(
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId
537:     ) private {

//@audit asset,  are not checked
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {

//@audit orders, asset,  are not checked
826:     function findOrderHintId(
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray
830:     ) internal view returns (uint16 hintId) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L326), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L532-L537), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L652-L652), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L830)


```solidity

File: contracts/libraries/LibSRUtil.sol

//@audit asset, shorter,  are not checked
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

//@audit asset,  are not checked
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


</details>


### [NC&#x2011;39] Use a struct to encapsulate multiple function parameters 
If a function has too many parameters, replacing them with a struct can improve code readability and maintainability, increase reusability, and reduce the likelihood of errors when passing the parameters.


*There are 18 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

40:     function createBid(
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray
47:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
48:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);
49: 
50:         return _createBid(msg.sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray);
51:     }

65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
66:         external
67:         onlyDiamond
68:         returns (uint88 ethFilled, uint88 ercAmountLeft)
69:     {
70:         // @dev leave empty, don't need hint for market buys
71:         MTypes.OrderHint[] memory orderHintArray;
72: 
73:         // @dev update oracle in callers
74:         return _createBid(sender, asset, price, ercAmount, C.MARKET_ORDER, orderHintArray, shortHintArray);
75:     }

077:     function _createBid(
078:         address sender,
079:         address asset,
080:         uint80 price,
081:         uint88 ercAmount,
082:         bool isMarketOrder,
083:         MTypes.OrderHint[] memory orderHintArray,
084:         uint16[] memory shortHintArray
085:     ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
086:         uint256 eth = ercAmount.mul(price);
087:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();
088: 
089:         STypes.Asset storage Asset = s.asset[asset];
090:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();
091: 
092:         STypes.Order memory incomingBid;
093:         incomingBid.addr = sender;
094:         incomingBid.price = price;
095:         incomingBid.ercAmount = ercAmount;
096:         incomingBid.id = Asset.orderIdCounter;
097:         incomingBid.orderType = isMarketOrder ? O.MarketBid : O.LimitBid;
098:         incomingBid.creationTime = LibOrders.getOffsetTime();
099: 
100:         MTypes.BidMatchAlgo memory b;
101:         b.askId = s.asks[asset][C.HEAD].nextId;
102:         // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
103:         b.shortHintId = b.shortId = Asset.startingShortId;
104: 
105:         STypes.Order memory lowestSell = _getLowestSell(asset, b);
106:         if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
107:             // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
109:             b.shortHintId = b.shortId = Asset.startingShortId;
110:             b.oraclePrice = LibOracle.getPrice(asset);
111:             return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
112:         } else {
113:             // @dev no match, add to market if limit order
114:             LibOrders.addBid(asset, incomingBid, orderHintArray);
115:             return (0, ercAmount);
116:         }
117:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L40-L51) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L65-L75), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L117)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

35:     function createLimitShort(
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR
42:     ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43:         MTypes.CreateLimitShortParam memory p;
44:         STypes.Asset storage Asset = s.asset[asset];
45:         STypes.Order memory incomingShort;
46: 
47:         // @dev create "empty" SR. Fail early.
48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49: 
50:         uint256 cr = LibOrders.convertCR(shortOrderCR);
51:         if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52:             revert Errors.InvalidCR();
53:         }
54: 
55:         // @dev minShortErc needs to be modified (bigger) when cr < 1
56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57:         p.eth = price.mul(ercAmount);
58:         p.minAskEth = LibAsset.minAskEth(asset);
59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60: 
61:         // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63: 
64:         incomingShort.addr = msg.sender;
65:         incomingShort.price = price;
66:         incomingShort.ercAmount = ercAmount;
67:         incomingShort.id = Asset.orderIdCounter;
68:         incomingShort.orderType = O.LimitShort;
69:         incomingShort.creationTime = LibOrders.getOffsetTime();
70:         incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71: 
72:         p.startingId = s.bids[asset][C.HEAD].nextId;
73:         STypes.Order storage highestBid = s.bids[asset][p.startingId];
74:         // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75:         if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77:         }
78: 
79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81:             revert Errors.BelowRecoveryModeCR();
82:         }
83: 
84:         // @dev reading spot oracle price
85:         if (incomingShort.price < p.oraclePrice) {
86:             LibOrders.addShort(asset, incomingShort, orderHintArray);
87:         } else {
88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89:         }
90:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L35-L90) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)
53:     {
54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
55:         // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
56:         if (shortHintArray.length > 10) revert Errors.TooManyHints();
57: 
58:         // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile
59:         LibSRUtil.checkCancelShortOrder({
60:             asset: asset,
61:             initialStatus: s.shortRecords[asset][shorter][id].status,
62:             shortOrderId: shortOrderId,
63:             shortRecordId: id,
64:             shorter: shorter
65:         });
66: 
67:         // @dev liquidate requires more up-to-date oraclePrice
68:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);
69: 
70:         MTypes.PrimaryLiquidation memory m = _setLiquidationStruct(asset, shorter, id, shortOrderId);
71: 
72:         // @dev Can liquidate as long as CR is low enough
73:         if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {
74:             // If CR is too high, check for recovery mode and violation to continue liquidation
75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();
76:         }
77: 
78:         // revert if no asks, or price too high
79:         _checklowestSell(m);
80: 
81:         _performForcedBid(m, shortHintArray);
82: 
83:         _liquidationFeeHandler(m);
84: 
85:         _fullorPartialLiquidation(m);
86: 
87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
88: 
89:         return (m.gasFee, m.ethFilled);
90:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L47-L90) 


```solidity

File: contracts/facets/ExitShortFacet.sol

142:     function exitShort(
143:         address asset,
144:         uint8 id,
145:         uint88 buybackAmount,
146:         uint80 price,
147:         uint16[] memory shortHintArray,
148:         uint16 shortOrderId
149:     ) external isNotFrozen(asset) nonReentrant onlyValidShortRecord(asset, msg.sender, id) {
150:         MTypes.ExitShort memory e;
151:         e.asset = asset;
152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray);
153: 
154:         STypes.Asset storage Asset = s.asset[e.asset];
155:         STypes.ShortRecord storage short = s.shortRecords[e.asset][msg.sender][id];
156: 
157:         // @dev Must prevent forcedBid from exitShort() matching with original shortOrder
158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({
159:             asset: asset,
160:             initialStatus: short.status,
161:             shortOrderId: shortOrderId,
162:             shortRecordId: id,
163:             shorter: msg.sender
164:         });
165: 
166:         short.updateErcDebt(e.asset);
167: 
168:         // @dev if short order was cancelled, fully exit
169:         e.buybackAmount = e.shortOrderIsCancelled ? short.ercDebt : buybackAmount;
170:         e.beforeExitCR = getCollateralRatioNonPrice(short);
171:         e.ercDebt = short.ercDebt;
172:         e.collateral = short.collateral;
173: 
174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();
175: 
176:         {
177:             uint256 ethAmount = price.mul(e.buybackAmount);
178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();
179:         }
180: 
181:         // Temporary accounting to enable bid
182:         STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
183:         VaultUser.ethEscrowed += e.collateral;
184: 
185:         // Create bid with current msg.sender
186:         (e.ethFilled, e.ercAmountLeft) =
187:             IDiamond(payable(address(this))).createForcedBid(msg.sender, e.asset, price, e.buybackAmount, shortHintArray);
188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();
189:         e.ercFilled = e.buybackAmount - e.ercAmountLeft;
190:         Asset.ercDebt -= e.ercFilled;
191:         s.assetUser[e.asset][msg.sender].ercEscrowed -= e.ercFilled;
192: 
193:         // Refund the rest of the collateral if ercDebt is fully paid back
194:         if (e.ercDebt == e.ercFilled) {
195:             // Full Exit
196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt);
197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy
198:         } else {
199:             short.collateral -= e.ethFilled;
200:             short.ercDebt -= e.ercFilled;
201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();
202: 
203:             // @dev Only allow partial exit if the CR is same or better than before
204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();
205: 
206:             // @dev collateral already subtracted in exitShort()
207:             VaultUser.ethEscrowed -= e.collateral - e.ethFilled;
208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt);
209:         }
210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);
211:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L142-L211) 


```solidity

File: contracts/facets/RedemptionFacet.sol

224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225:         external
226:         isNotFrozen(asset)
227:         nonReentrant
228:     {
229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230:         MTypes.DisputeRedemption memory d;
231:         d.asset = asset;
232:         d.redeemer = redeemer;
233: 
234:         STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236: 
237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238: 
239:         MTypes.ProposalData[] memory decodedProposalData =
240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241: 
242:         for (uint256 i = 0; i < decodedProposalData.length; i++) {
243:             if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244:                 revert Errors.CannotDisputeWithRedeemerProposal();
245:             }
246:         }
247: 
248:         STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249:         // Match continue (skip) conditions in proposeRedemption()
250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);
251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252: 
253:         MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254:         MTypes.ProposalData memory currentProposal;
255:         STypes.Asset storage Asset = s.asset[d.asset];
256: 
257:         uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258: 
259:         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260:         {
261:             // @dev All proposals from the incorrectIndex onward will be removed
262:             // @dev Thus the proposer can only redeem a portion of their original slate
263:             for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264:                 currentProposal = decodedProposalData[i];
265: 
266:                 STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267:                 currentSR.collateral += currentProposal.colRedeemed;
268:                 currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269: 
270:                 d.incorrectCollateral += currentProposal.colRedeemed;
271:                 d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272:             }
273: 
274:             s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275:             Asset.dethCollateral += d.incorrectCollateral;
276:             Asset.ercDebt += d.incorrectErcDebt;
277: 
278:             // @dev Update the redeemer's SSTORE2Pointer
279:             if (incorrectIndex > 0) {
280:                 redeemerAssetUser.slateLength = incorrectIndex;
281:             } else {
282:                 // @dev this implies everything in the redeemer's proposal was incorrect
283:                 delete redeemerAssetUser.SSTORE2Pointer;
284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);
285:             }
286: 
287:             // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288:             // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289:             uint256 penaltyPct = LibOrders.min(
290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291:             );
292: 
293:             uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294: 
295:             // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296:             redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297:             s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298:         } else {
299:             revert Errors.InvalidRedemptionDispute();
300:         }
301:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L301) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

039:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
040:         internal
041:         returns (uint88)
042:     {
043:         AppStorage storage s = appStorage();
044:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];
045: 
046:         uint88 creditReth;
047:         uint88 creditSteth;
048:         if (bridgePointer == VAULT.BRIDGE_RETH) {
049:             // Withdraw RETH
050:             creditReth = VaultUser.bridgeCreditReth;
051:             if (creditReth >= amount) {
052:                 VaultUser.bridgeCreditReth -= amount;
053:                 return 0;
054:             }
055: 
056:             VaultUser.bridgeCreditReth = 0;
057:             amount -= creditReth;
058:             creditSteth = VaultUser.bridgeCreditSteth;
059:             if (creditSteth < C.ROUNDING_ZERO) {
060:                 // Valid withdraw when no STETH credits
061:                 return amount;
062:             } else {
063:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
064:                     // Can withdraw RETH using STETH credit when STETH bridge is empty
065:                     if (creditSteth >= amount) {
066:                         VaultUser.bridgeCreditSteth -= amount;
067:                         return 0;
068:                     } else {
069:                         VaultUser.bridgeCreditSteth = 0;
070:                         return amount - creditSteth;
071:                     }
072:                 } else {
073:                     // Must use available bridge credits on withdrawal
074:                     // @dev Prevents abusing bridge for arbitrage
075:                     revert Errors.MustUseExistingBridgeCredit();
076:                 }
077:             }
078:         } else {
079:             // Withdraw STETH
080:             creditSteth = VaultUser.bridgeCreditSteth;
081:             if (creditSteth >= amount) {
082:                 VaultUser.bridgeCreditSteth -= amount;
083:                 return 0;
084:             }
085: 
086:             VaultUser.bridgeCreditSteth = 0;
087:             amount -= creditSteth;
088:             creditReth = VaultUser.bridgeCreditReth;
089:             if (creditReth < C.ROUNDING_ZERO) {
090:                 // Valid withdraw when no RETH credits
091:                 return amount;
092:             } else {
093:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
094:                     // Can withdraw STETH using RETH credit when RETH bridge is empty
095:                     if (creditReth >= amount) {
096:                         VaultUser.bridgeCreditReth -= amount;
097:                         return 0;
098:                     } else {
099:                         VaultUser.bridgeCreditReth = 0;
100:                         return amount - creditReth;
101:                     }
102:                 } else {
103:                     // Must use available bridge credits on withdrawal
104:                     // @dev Prevents abusing bridge for arbitrage
105:                     revert Errors.MustUseExistingBridgeCredit();
106:                 }
107:             }
108:         }
109:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L109) 


```solidity

File: contracts/libraries/LibOracle.sol

069:     function baseOracleCircuitBreaker(
070:         uint256 protocolPrice,
071:         uint80 roundId,
072:         int256 chainlinkPrice,
073:         uint256 timeStamp,
074:         uint256 chainlinkPriceInEth
075:     ) private view returns (uint256 _protocolPrice) {
076:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
077:             || block.timestamp > 2 hours + timeStamp;
078:         uint256 chainlinkDiff =
079:             chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
080:         bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;
081: 
082:         // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
083:         if (invalidFetchData) {
084:             return twapCircuitBreaker();
085:         } else if (priceDeviation) {
086:             // Check valid twap price
087:             try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
088:             {
089:                 if (twapPrice == 0) {
090:                     return chainlinkPriceInEth;
091:                 }
092: 
093:                 uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
094:                 uint256 twapPriceInEth = twapPriceNormalized.inv();
095:                 uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
096: 
097:                 // Save the price that is closest to saved oracle price
098:                 if (chainlinkDiff <= twapDiff) {
099:                     return chainlinkPriceInEth;
100:                 } else {
101:                     // Check valid twap liquidity
102:                     IERC20 weth = IERC20(C.WETH);
103:                     uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104:                     if (wethBal < 100 ether) {
105:                         return chainlinkPriceInEth;
106:                     }
107:                     return twapPriceInEth;
108:                 }
109:             } catch {
110:                 return chainlinkPriceInEth;
111:             }
112:         } else {
113:             return chainlinkPriceInEth;
114:         }
115:     }

117:     function oracleCircuitBreaker(
118:         uint80 roundId,
119:         uint80 baseRoundId,
120:         int256 chainlinkPrice,
121:         int256 baseChainlinkPrice,
122:         uint256 timeStamp,
123:         uint256 baseTimeStamp
124:     ) private view {
125:         bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
126:             || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;
127: 
128:         if (invalidFetchData) revert Errors.InvalidPrice();
129:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L115) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L129)


```solidity

File: contracts/libraries/LibOrders.sol

260:     function verifySellId(
261:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262:         address asset,
263:         uint16 _prevId,
264:         uint256 _newPrice,
265:         uint16 _nextId
266:     ) private view returns (int256 direction) {
267:         // @dev: TAIL can't be prevId because it will always be last item in list
268:         bool check1 = orders[asset][_prevId].price <= _newPrice || _prevId == C.HEAD;
269: 
270:         bool check2 = _newPrice < orders[asset][_nextId].price || _nextId == C.TAIL;
271: 
272:         if (check1 && check2) {
273:             return C.EXACT;
274:         } else if (!check1) {
275:             return C.PREV;
276:         } else if (!check2) {
277:             return C.NEXT;
278:         }
279:     }

320:     function _reuseOrderIds(
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched
326:     ) private {
327:         // matching ID1 and ID2
328:         // BEFORE: HEAD <- <---------------- HEAD <-> (ID1) <-> (ID2) <-> (ID3) <-> NEXT
329:         // AFTER1: HEAD <- [ID1] <---------- HEAD <-----------> (ID2) <-> (ID3) <-> NEXT
330:         // AFTER2: HEAD <- [ID1] <- [ID2] <- HEAD <---------------------> (ID3) <-> NEXT
331: 
332:         // @dev mark as cancelled instead of deleting the order itself
333:         orders[asset][id].orderType = cancelledOrMatched;
334:         orders[asset][C.HEAD].prevId = id;
335:         // Move the cancelled ID behind HEAD to re-use it
336:         // note: C_IDs (cancelled ids) only need to point back (set prevId, can retain nextId)
337:         // BEFORE: .. C_ID2 <- C_ID1 <--------- HEAD <-> ... [ID]
338:         // AFTER1: .. C_ID2 <- C_ID1 <- [ID] <- HEAD <-> ...
339:         if (prevHEAD != C.HEAD) {
340:             orders[asset][id].prevId = prevHEAD;
341:         } else {
342:             // if this is the first ID cancelled
343:             // HEAD.prevId needs to be HEAD
344:             // and one of the cancelled id.prevID should point to HEAD
345:             // BEFORE: HEAD <--------- HEAD <-> ... [ID]
346:             // AFTER1: HEAD <- [ID] <- HEAD <-> ...
347:             orders[asset][id].prevId = C.HEAD;
348:         }
349:     }

402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {
410:         orderType = normalizeOrderType(orderType);
411: 
412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413:             return verifySellId(orders, asset, prevId, newPrice, nextId);
414:         } else if (orderType == O.LimitBid) {
415:             return verifyBidId(asset, prevId, newPrice, nextId);
416:         }
417:     }

440:     function getOrderId(
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {
448:         while (true) {
449:             uint16 nextId = orders[asset][hintId].nextId;
450: 
451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
452:                 return hintId;
453:             }
454: 
455:             if (direction == C.PREV) {
456:                 uint16 prevId = orders[asset][hintId].prevId;
457:                 hintId = prevId;
458:             } else {
459:                 hintId = nextId;
460:             }
461:         }
462:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L260-L279) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L349), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L402-L417), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L462)


```solidity

File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23:         internal
24:     {
25:         AppStorage storage s = appStorage();
26: 
27:         STypes.Asset storage Asset = s.asset[asset];
28:         uint256 vault = Asset.vault;
29:         STypes.Vault storage Vault = s.vault[vault];
30: 
31:         Vault.dethCollateral -= collateral;
32:         Asset.dethCollateral -= collateral;
33:         // Distribute yield
34:         uint88 yield = collateral.mulU88(Vault.dethYieldRate - dethYieldRate);
35:         if (yield > 0) {
36:             /*
37:             @dev If somebody exits a short, gets liquidated, decreases their collateral before YIELD_DELAY_SECONDS duration is up,
38:             they lose their yield to the TAPP
39:             */
40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;
41:             if (isNotRecentlyModified) {
42:                 s.vaultUser[vault][shorter].ethEscrowed += yield;
43:             } else {
44:                 s.vaultUser[vault][address(this)].ethEscrowed += yield;
45:             }
46:         }
47:     }

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
50:         internal
51:         returns (bool isCancelled)
52:     {
53:         AppStorage storage s = appStorage();
54:         if (initialStatus == SR.PartialFill) {
55:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
56:             STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
58: 
59:             if (shorter == msg.sender) {
60:                 // If call comes from exitShort() or combineShorts() then always cancel
61:                 LibOrders.cancelShort(asset, shortOrderId);
62:                 assert(shortRecord.status != SR.PartialFill);
63:                 return true;
64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
65:                 // If call comes from liquidate() and SR ercDebt under minShortErc
66:                 LibOrders.cancelShort(asset, shortOrderId);
67:                 return true;
68:             }
69:         }
70:     }

072:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
073:         internal
074:         returns (bool isCancelled)
075:     {
076:         AppStorage storage s = appStorage();
077: 
078:         STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
079:         uint256 minShortErc = LibAsset.minShortErc(asset);
080: 
081:         if (initialStatus == SR.PartialFill) {
082:             // Verify shortOrder
083:             STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
084:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();
085: 
086:             if (shortRecord.status == SR.Closed) {
087:                 // Check remaining shortOrder
088:                 if (shortOrder.ercAmount < minShortErc) {
089:                     // @dev The resulting SR will not have PartialFill status after cancel
090:                     LibOrders.cancelShort(asset, shortOrderId);
091:                     isCancelled = true;
092:                 }
093:             } else {
094:                 // Check remaining shortOrder and remaining shortRecord
095:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
096:             }
097:         } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) {
098:             revert Errors.CannotLeaveDustAmount();
099:         }
100:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L47) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L70), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L100)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
48:         internal
49:         view
50:         returns (uint256 amountOut)
51:     {
52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();
53: 
54:         uint32[] memory secondsAgos = new uint32[](2);
55:         secondsAgos[0] = secondsAgo;
56:         secondsAgos[1] = 0;
57: 
58:         // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp
59:         (int56[] memory tickCumulatives,) = IUniswapV3Pool(pool).observe(secondsAgos);
60: 
61:         int56 tickCumulativesDelta = tickCumulatives[1] - tickCumulatives[0];
62:         int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));
63: 
64:         // Always round to negative infinity
65:         if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {
66:             tick--;
67:         }
68: 
69:         // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick
70:         amountOut = getQuoteAtTick(tick, amountIn, baseToken, quoteToken);
71:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L71) 


</details>


### [NC&#x2011;40] Use custom errors rather than `revert()`/`require()` strings for better readability 
Custom errors are available from solidity version 0.8.4. Custom errors are more easily processed in try-catch blocks, and are easier to re-use and maintain.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

14:         require(slate.length % 51 == 0, "Invalid data length");


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L14-L14) 


</details>


### [NC&#x2011;41] constructor should emit an event 
Use events to signal significant changes to off-chain monitoring tools.


*There are 3 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

30:     constructor(address _dusd) {
31:         dusd = _dusd;
32:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L32) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

29:     constructor(address _rethBridge, address _stethBridge) {
30:         rethBridge = _rethBridge;
31:         stethBridge = _stethBridge;
32:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L32) 


```solidity

File: contracts/facets/ExitShortFacet.sol

28:     constructor(address _dusd) {
29:         dusd = _dusd;
30:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L30) 


</details>


### [NC&#x2011;42] Complex functions should include comments 
Large and/or complex functions should include comments to make them easier to understand and reduce margin for error.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BridgeRouterFacet.sol

101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L101-L101) 


```solidity

File: contracts/facets/RedemptionFacet.sol

310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L310-L310) 


```solidity

File: contracts/libraries/LibOrders.sol

440:     function getOrderId(

668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L440) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L668-L668)


</details>


### [NC&#x2011;43] Make use of Solidiy's `using` keyword 
The directive `using A for B` can be used to attach functions (`A`) as operators to user-defined value types or as member functions to any type (`B`). The member functions receive the object they are called on as their first parameter (like the `self` variable in Python). The operator functions receive operands as parameters.  Doing so improves readability, makes debugging easier, and promotes modularity and reusability in the code.


*There are 193 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

48:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);

136:         uint256 minBidEth = LibAsset.minBidEth(asset);

288:         LibOrders.updateSellOrdersOnMatch(asset, b);

332:         emit Events.MatchOrder(asset, bidder, incomingBid.orderType, incomingBid.id, matchTotal.fillEth, matchTotal.fillErc);

335:         LibOrders.handlePriceDiscount(asset, matchTotal.lastMatchPrice);

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();

87:         if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();

90:         if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();

98:         incomingBid.creationTime = LibOrders.getOffsetTime();

114:             LibOrders.addBid(asset, incomingBid, orderHintArray);

108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);

227:             LibOrders.increaseSharesOnMatch(asset, lowestSell, matchTotal, colUsed);

243:             LibShortRecord.fillShortRecord(

108:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);

110:             b.oraclePrice = LibOracle.getPrice(asset);

226:             uint88 colUsed = fillEth.mulU88(LibOrders.convertCR(lowestSell.shortOrderCR));

143:                     LibOrders.addBid(asset, incomingBid, orderHintArray);

199:                     LibOrders.addBid(asset, incomingBid, orderHintArray);

166:                         LibOrders.matchOrder(s.asks, asset, lowestSell.id);

162:                         LibOrders.matchOrder(s.shorts, asset, lowestSell.id);

177:                             LibOrders.matchOrder(s.asks, asset, lowestSell.id);

174:                             LibOrders.matchOrder(s.shorts, asset, lowestSell.id);

190:                         if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L48-L48) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L136-L136), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L288-L288), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L332-L332), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L335-L335), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L87-L87), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L87-L87), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L90-L90), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L98-L98), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L114-L114), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L108-L108), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L227-L227), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L243-L243), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L108-L108), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L110-L110), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L226-L226), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L143-L143), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L199-L199), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L166-L166), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L177-L177), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L174-L174), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L190-L190)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

50:         uint256 cr = LibOrders.convertCR(shortOrderCR);

80:         if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {

48:         incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

58:         p.minAskEth = LibAsset.minAskEth(asset);

59:         if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();

62:         if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();

69:         incomingShort.creationTime = LibOrders.getOffsetTime();

79:         p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);

52:             revert Errors.InvalidCR();

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);

76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);

81:             revert Errors.BelowRecoveryModeCR();

88:             LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);

86:             LibOrders.addShort(asset, incomingShort, orderHintArray);

76:             LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);

56:         p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L50-L50) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L80-L80), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L48-L48), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L58-L58), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L59-L59), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L62-L62), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L79-L79), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L52-L52), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L56-L56), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L76-L76), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L81-L81), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L88-L88), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L86-L86), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L76-L76), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L56-L56)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

59:         LibSRUtil.checkCancelShortOrder({

68:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);

87:         emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);

126:         LibShortRecord.updateErcDebt(asset, shorter, id);

54:         if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();

56:         if (shortHintArray.length > 10) revert Errors.TooManyHints();

73:         if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {

230:         if (a > type(uint88).max) revert Errors.InvalidAmount();

109:             revert Errors.NoSells();

134:             m.penaltyCR = LibAsset.penaltyCR(asset);

135:             m.oraclePrice = LibOracle.getPrice(asset);

137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);

138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);

139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);

260:             LibSRUtil.disburseCollateral(m.asset, m.shorter, decreaseCol, m.short.dethYieldRate, m.short.updatedAt);

246:             LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt);

247:             LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);

282:             LibSRUtil.checkShortMinErc({

75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();

75:             if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();

174:                 revert Errors.CannotSocializeDebt();

265:                 LibShortRecord.deleteShortRecord(m.asset, m.shorter, m.short.id);

267:                 LibShortRecord.fillShortRecord(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L59-L59) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L68-L68), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L87-L87), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L126-L126), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L54-L54), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L56-L56), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L73-L73), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L230-L230), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L109-L109), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L134-L134), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L135-L135), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L137-L137), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L138-L138), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L139-L139), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L260-L260), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L246-L246), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L247-L247), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L282-L282), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L75-L75), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L75-L75), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L174-L174), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L265-L265), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L267-L267)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

72:         emit Events.Deposit(bridge, msg.sender, dethAmount);

90:         emit Events.DepositEth(bridge, msg.sender, dethAmount);

122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);

143:         emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);

64:         if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

83:         if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

102:         if (dethAmount == 0) revert Errors.ParameterIsZero();

134:         if (dethAmount == 0) revert Errors.ParameterIsZero();

110:                 uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);

164:             if (vault == 0) revert Errors.InvalidBridge();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L72-L72) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L90-L90), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L122-L122), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L143-L143), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L64-L64), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L83-L83), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L134-L134), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L110-L110), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L164-L164)


```solidity

File: contracts/facets/ExitShortFacet.sol

67:         LibSRUtil.checkShortMinErc({

75:         emit Events.ExitShortWallet(asset, msg.sender, id, buybackAmount);

120:         LibSRUtil.checkShortMinErc({

128:         emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);

152:         LibOrders.updateOracleAndStartingShortViaTimeBidOnly(e.asset, shortHintArray);

210:         emit Events.ExitShort(asset, msg.sender, id, e.ercFilled);

53:         if (buybackAmount > ercDebt || buybackAmount == 0) revert Errors.InvalidBuyback();

99:         if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();

158:         e.shortOrderIsCancelled = LibSRUtil.checkCancelShortOrder({

174:         if (e.buybackAmount == 0 || e.buybackAmount > e.ercDebt) revert Errors.InvalidBuyback();

188:         if (e.ethFilled == 0) revert Errors.ExitShortPriceTooLow();

61:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

62:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);

103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();

113:             LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

115:             LibShortRecord.deleteShortRecord(asset, msg.sender, id);

178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();

208:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.ethFilled, short.dethYieldRate, short.updatedAt);

196:             LibSRUtil.disburseCollateral(e.asset, msg.sender, e.collateral, short.dethYieldRate, short.updatedAt);

197:             LibShortRecord.deleteShortRecord(e.asset, msg.sender, id); // prevent reentrancy

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();

201:             if (short.ercDebt < LibAsset.minShortErc(asset)) revert Errors.CannotLeaveDustAmount();

204:             if (getCollateralRatioNonPrice(short) < e.beforeExitCR) revert Errors.PostExitCRLtPreExitCR();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L67-L67) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L75-L75), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L120-L120), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L128-L128), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L152-L152), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L210-L210), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L53-L53), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L99-L99), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L158-L158), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L174-L174), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L188-L188), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L61-L61), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L62-L62), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L115-L115), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L178-L178), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L208-L208), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L196-L196), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L197-L197), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L201-L201), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L201-L201), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L204-L204)


```solidity

File: contracts/facets/RedemptionFacet.sol

66:         uint256 minShortErc = LibAsset.minShortErc(p.asset);

154:         uint32 protocolTime = LibOrders.getOffsetTime();

210:         emit Events.ProposeRedemption(p.asset, msg.sender);

240:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

250:         uint256 minShortErc = LibAsset.minShortErc(d.asset);

318:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

333:         emit Events.ClaimRedemption(asset, msg.sender);

358:             LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);

387:         uint32 protocolTime = LibOrders.getOffsetTime();

401:         uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);

62:         if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();

68:         if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();

70:         if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();

73:         if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();

75:         p.oraclePrice = LibOracle.getPrice(p.asset);

143:         if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();

146:         redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);

202:         redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();

205:         if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();

208:         if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();

229:         if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();

235:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();

237:         if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();

251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();

314:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

315:         if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

353:         if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();

354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

354:         if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();

361:         if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();

396:         newBaseRate = LibOrders.min(newBaseRate, 1 ether); // cap baseRate at a maximum of 100%

138:             LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);

299:             revert Errors.InvalidRedemptionDispute();

289:             uint256 penaltyPct = LibOrders.min(

376:             LibSRUtil.disburseCollateral(asset, shorter, collateral, shortRecord.dethYieldRate, shortRecord.updatedAt);

377:             LibShortRecord.deleteShortRecord(asset, shorter, shortId);

290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

113:                 LibOrders.cancelShort(asset, p.shortOrderId);

244:                 revert Errors.CannotDisputeWithRedeemerProposal();

284:                 emit Events.DisputeRedemptionAll(d.asset, redeemer);

290:                 LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

112:                 if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L66-L66) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L154-L154), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L210-L210), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L240-L240), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L250-L250), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L318-L318), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L333-L333), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L358-L358), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L387-L387), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L401-L401), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L62-L62), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L68-L68), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L70-L70), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L73-L73), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L75-L75), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L143-L143), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L146-L146), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L202-L202), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L205-L205), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L208-L208), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L229-L229), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L235-L235), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L237-L237), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L237-L237), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L251-L251), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L314-L314), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L315-L315), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L315-L315), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L353-L353), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L354-L354), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L354-L354), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L361-L361), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L396-L396), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L138-L138), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L299-L299), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L289-L289), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L376-L376), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L377-L377), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L290-L290), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L244-L244), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L284-L284), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L290-L290), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L112-L112)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

118:         uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);

122:         uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);

105:                     revert Errors.MustUseExistingBridgeCredit();

75:                     revert Errors.MustUseExistingBridgeCredit();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L118-L118) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L122-L122), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L105-L105), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L75-L75)


```solidity

File: contracts/libraries/LibBytes.sol

12:         bytes memory slate = SSTORE2.read(SSTORE2Pointer);

45:             data[i] = MTypes.ProposalData({


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L12-L12) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L45-L45)


```solidity

File: contracts/libraries/LibOracle.sol

25:         if (address(oracle) == address(0)) revert Errors.InvalidAsset();

128:         if (invalidFetchData) revert Errors.InvalidPrice();

134:         if (twapPrice == 0) revert Errors.InvalidTwapPrice();

139:         if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();

169:         if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {

60:                 if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L25-L25) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L128-L128), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L134-L134), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L139-L139), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L169-L169), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L60-L60)


```solidity

File: contracts/libraries/LibOrders.sol

218:         emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount);

301:         emit Events.CancelOrder(asset, id, orders[asset][id].orderType);

631:         emit Events.MatchOrder(

679:         LibShortRecord.fillShortRecord(

730:         uint256 oraclePrice = LibOracle.getOraclePrice(asset);

813:         uint256 savedPrice = LibOracle.getPrice(asset);

850:         revert Errors.BadHintIdArray();

959:         uint256 savedPrice = LibOracle.getPrice(asset);

804:         uint256 timeDiff = getOffsetTime() - LibOracle.getTime(asset);

859:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();

887:         if (orderType == O.Cancelled || orderType == O.Matched) revert Errors.NotActiveOrder();

778:             revert Errors.BadShortHint();

874:             revert Errors.NotActiveOrder();

901:             LibShortRecord.deleteShortRecord(asset, shorter, shortRecordId);

942:             uint256 savedPrice = LibOracle.getPrice(asset);

903:             uint88 minShortErc = uint88(LibAsset.minShortErc(asset));

913:                     LibShortRecord.fillShortRecord(

608:                         if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L218-L218) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L301-L301), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L631-L631), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L679-L679), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L730-L730), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L813-L813), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L850-L850), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L959-L959), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L804-L804), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L859-L859), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L887-L887), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L778-L778), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L874-L874), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L901-L901), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L942-L942), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L903-L903), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L913-L913), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L608-L608)


```solidity

File: contracts/libraries/LibSRUtil.sol

79:         uint256 minShortErc = LibAsset.minShortErc(asset);

109:         uint256 recoveryCR = LibAsset.recoveryCR(asset);

139:         LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId);

140:         LibBridgeRouter.transferBridgeCredit(asset, from, to, short.collateral);

142:         uint8 id = LibShortRecord.createShortRecord(

130:         if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled();

131:         if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

135:             LibOrders.cancelShort(asset, nft.shortOrderId);

57:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

98:             revert Errors.CannotLeaveDustAmount();

84:             if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

40:             bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;

64:             } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {

61:                 LibOrders.cancelShort(asset, shortOrderId);

66:                 LibOrders.cancelShort(asset, shortOrderId);

95:                 if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();

90:                     LibOrders.cancelShort(asset, shortOrderId);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L79-L79) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L109-L109), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L139-L139), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L140-L140), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L142-L142), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L130-L130), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L135-L135), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L57-L57), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L98-L98), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L84-L84), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L64-L64), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L61-L61), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L66-L66), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L95-L95), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L90-L90)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

33:         uint160 sqrtRatioX96 = TickMath.getSqrtRatioAtTick(tick);

52:         if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();

41:             uint256 ratioX128 = U256.mulDiv(sqrtRatioX96, sqrtRatioX96, 1 << 64);

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L33-L33) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L52-L52), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L41-L41), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L43-L43), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L43-L43), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L39-L39)


</details>


### [NC&#x2011;44] [Solidity]: All `verbatim` blocks are considered identical by deduplicator and can incorrectly be unified 
The block deduplicator is a step of the opcode-based optimizer which identifies equivalent assembly blocks and merges them into a single one. However, when blocks contained `verbatim`, their comparison was performed incorrectly, leading to the collapse of assembly blocks which are identical except for the contents of the ``verbatim`` items. Since `verbatim` is only available in Yul, compilation of Solidity sources is not affected. For more details check the following [link](https://blog.soliditylang.org/2023/11/08/verbatim-invalid-deduplication-bug/)


*There are 12 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L2-L2) 


```solidity

File: contracts/facets/ShortOrdersFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L2-L2) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L2-L2) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L2-L2) 


```solidity

File: contracts/facets/ExitShortFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L2-L2) 


```solidity

File: contracts/facets/RedemptionFacet.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L2-L2) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L2-L2) 


```solidity

File: contracts/libraries/LibBytes.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L2-L2) 


```solidity

File: contracts/libraries/LibOracle.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L2-L2) 


```solidity

File: contracts/libraries/LibOrders.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L2-L2) 


```solidity

File: contracts/libraries/LibSRUtil.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L2-L2) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L2-L2) 


</details>


### [NC&#x2011;45] [NatSpec] Natspec `@param` is missing from `error` 



*There are 56 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

77:     function _createBid(

340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

358:     function _shortDirectionHandler(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L77) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L358)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

30:     constructor(address _dusd) {

96:     function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L30-L30) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L96-L96), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

29:     constructor(address _rethBridge, address _stethBridge) {

148:     function maybeUpdateYield(uint256 vault, uint88 amount) private {

156:     function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L29-L29) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L169-L169)


```solidity

File: contracts/facets/ExitShortFacet.sol

28:     constructor(address _dusd) {

213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L28-L28) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213)


```solidity

File: contracts/facets/RedemptionFacet.sol

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {

382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L31) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L368-L368), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

21:     function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)

113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {

198:     function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L21-L21) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L39), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L198-L198)


```solidity

File: contracts/libraries/LibBytes.sol

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11) 


```solidity

File: contracts/libraries/LibOracle.sol

19:     function getOraclePrice(address asset) internal view returns (uint256) {

69:     function baseOracleCircuitBreaker(

117:     function oracleCircuitBreaker(

149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

156:     function getTime(address asset) internal view returns (uint256 creationTime) {

162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L117-L117), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

82:     function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

103:     function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {

320:     function _reuseOrderIds(

420:     function normalizeOrderType(O o) private pure returns (O newO) {

628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

728:     function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {

783:     function updateOracleAndStartingShortViaThreshold(

803:     function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {

810:     function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {

826:     function findOrderHintId(

854:     function cancelBid(address asset, uint16 id) internal {

868:     function cancelAsk(address asset, uint16 id) internal {

882:     function cancelShort(address asset, uint16 id) internal {

955:     function handlePriceDiscount(address asset, uint80 price) internal {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L103-L103), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L320), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L728-L728), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L783), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L803-L803), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L810-L810), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


```solidity

File: contracts/libraries/LibSRUtil.sol

22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

11:     function observe(uint32[] calldata secondsAgos)

47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L11-L11) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47)


</details>


### [NC&#x2011;46] [NatSpec] Natspec comment is missing from scope `block` 



*There are 5 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

127:         {
128:             MTypes.PrimaryLiquidation memory m;
129:             m.asset = asset;
130:             m.short = s.shortRecords[asset][shorter][id];
131:             m.shortOrderId = shortOrderId;
132:             m.vault = s.asset[asset].vault;
133:             m.shorter = shorter;
134:             m.penaltyCR = LibAsset.penaltyCR(asset);
135:             m.oraclePrice = LibOracle.getPrice(asset);
136:             m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
137:             m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);
138:             m.callerFeePct = LibAsset.callerFeePct(m.asset);
139:             m.tappFeePct = LibAsset.tappFeePct(m.asset);
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
141:             return m;
142:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L127-L142) 


```solidity

File: contracts/facets/ExitShortFacet.sol

101:         {
102:             STypes.AssetUser storage AssetUser = s.assetUser[asset][msg.sender];
103:             if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();
104: 
105:             AssetUser.ercEscrowed -= buybackAmount;
106:         }

176:         {
177:             uint256 ethAmount = price.mul(e.buybackAmount);
178:             if (ethAmount > e.collateral) revert Errors.InsufficientCollateral();
179:         }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L101-L106) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L176-L179)


```solidity

File: contracts/libraries/LibOrders.sol

750:                 {
751:                     O shortOrderType = short.orderType;
752:                     if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753:                         continue;
754:                     }
755:                 }

908:                 {
909:                     STypes.Vault storage Vault = s.vault[vault];
910: 
911:                     uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));
912: 
913:                     LibShortRecord.fillShortRecord(
914:                         asset,
915:                         shorter,
916:                         shortRecordId,
917:                         SR.FullyFilled,
918:                         collateralDiff,
919:                         debtDiff,
920:                         Asset.ercDebtRate,
921:                         Vault.dethYieldRate
922:                     );
923: 
924:                     Vault.dethCollateral += collateralDiff;
925:                     Asset.dethCollateral += collateralDiff;
926:                     Asset.ercDebt += debtDiff;
927: 
928:                     // @dev update the eth refund amount
929:                     eth -= collateralDiff;
930:                 }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L750-L755) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L908-L930)


</details>


### [NC&#x2011;47] OpenZeppelin libraries should be upgraded to a newer version 
These contracts import some OpenZeppelin libraries, but they are using an old version.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibOracle.sol

7: import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L7-L7) 


</details>


### [NC&#x2011;48] Not using the latest version of `prb-math` from dependencies 
`prb-math` is an important mathematical library The package.json configuration file says that the project is using an old version of `prb-math`.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: package.json

//@audit `prb-math` version is 
1: 


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//package.json#L1-L1) 


</details>


### [NC&#x2011;49] Establishing Best Practices for Initial Version in package.json 
Starting with 0.1.0 or 1.0.0 in package.json adheres to Semantic Versioning (SemVer) standards, implying a more stable and significant release. Initial versions like 0.0.1 or 0.0.0 suggest extreme infancy or instability, which might not accurately reflect the software's development stage, potentially misleading users or contributors about its readiness.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: package.json

//@audit package.json version is 0.0.1
1: {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//package.json#L1-L1) 


</details>


### [NC&#x2011;50] Consider making private state variables internal to increase flexibility 
In Solidity, `private` state variables are strictly confined to the contract they are defined in and can't be accessed or modified by its derived contracts. While this offers strong encapsulation, it can limit contract extensibility and modification in inheritance chains. On the other hand, `internal` variables can be accessed and potentially overridden by child contracts, granting more flexibility in contract development and upgrades. Therefore, it's recommended to use `private` only when you explicitly want to prevent child contract access. Otherwise, prefer `internal` to maintain a balance between encapsulation and the flexibility offered by inheritance patterns in Solidity.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

28:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L28-L28) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

26:     address private immutable rethBridge;

27:     address private immutable stethBridge;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L26-L26) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L27-L27)


```solidity

File: contracts/facets/ExitShortFacet.sol

26:     address private immutable dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L26-L26) 


</details>


### [NC&#x2011;51] Lack of space near the operator 
Lack of space near operators in code can lead to reduced readability, making it more challenging to distinguish between different elements and understand the logic quickly. As a resolution, always include spaces around operators to ensure a clear visual separation, which promotes better maintainability and comprehension of the code.


*There are 8 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit operator : *
199:         m.gasFee = uint88(gasUsed * block.basefee); // @dev(safe-cast)

//@audit operator : +
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees

//@audit operator : +
140:             m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees

//@audit operator : +
180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)

//@audit operator : +
180:             m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L199-L199) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L140-L140), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L140-L140), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L180-L180), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L180-L180)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit operator : -
32:         return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L32-L32) 


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

43:                 baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

39:                 baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L43-L43) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L39-L39)


</details>


### [NC&#x2011;52] Incorrect withdraw declaration 
In Solidity, it's essential for clarity and interoperability to correctly specify return types in function declarations. If the `withdraw` function is expected to return a `bool` to indicate success or failure, its omission could lead to ambiguity or unexpected behavior when interacting with or calling this function from other contracts or off-chain systems. Missing return values can mislead developers and potentially lead to contract integrations built on incorrect assumptions. To resolve this, the function declaration for `withdraw` should be modified to explicitly include the `bool` return type, ensuring clarity and correctness in contract interactions.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BridgeRouterFacet.sol

101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
102:         if (dethAmount == 0) revert Errors.ParameterIsZero();
103: 
104:         (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
105: 
106:         uint88 fee;
107:         if (vault == VAULT.ONE) {
108:             uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
109:             if (dethAssessable > 0) {
110:                 uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
111:                 if (withdrawalFeePct > 0) {
112:                     fee = dethAssessable.mulU88(withdrawalFeePct);
113:                     dethAmount -= fee;
114:                     s.vaultUser[vault][address(this)].ethEscrowed += fee;
115:                 }
116:             }
117:         }
118: 
119:         uint88 ethAmount = _ethConversion(vault, dethAmount);
120:         vault.removeDeth(dethAmount, fee);
121:         IBridge(bridge).withdraw(msg.sender, ethAmount);
122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
123:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L101-L123) 


</details>


### [NC&#x2011;53] Avoid mutating function parameters 
Function parameters in Solidity are passed by value, meaning they are essentially local copies. Mutating them can lead to confusion and errors because the changes don't persist outside the function. By keeping function parameters immutable, you ensure clarity in code behavior, preventing unintended side-effects. If you need to modify a value based on a parameter, use a local variable inside the function, leaving the original parameter unaltered. By adhering to this practice, you maintain a clear distinction between input data and the internal processing logic, improving code readability and reducing the potential for bugs.


*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BridgeRouterFacet.sol

//@audit the following parameters are mutated dethAmount,
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
102:         if (dethAmount == 0) revert Errors.ParameterIsZero();
103: 
104:         (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
105: 
106:         uint88 fee;
107:         if (vault == VAULT.ONE) {
108:             uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
109:             if (dethAssessable > 0) {
110:                 uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
111:                 if (withdrawalFeePct > 0) {
112:                     fee = dethAssessable.mulU88(withdrawalFeePct);
113:                     dethAmount -= fee;
114:                     s.vaultUser[vault][address(this)].ethEscrowed += fee;
115:                 }
116:             }
117:         }
118: 
119:         uint88 ethAmount = _ethConversion(vault, dethAmount);
120:         vault.removeDeth(dethAmount, fee);
121:         IBridge(bridge).withdraw(msg.sender, ethAmount);
122:         emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
123:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L101-L123) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

//@audit the following parameters are mutated amount,
039:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
040:         internal
041:         returns (uint88)
042:     {
043:         AppStorage storage s = appStorage();
044:         STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];
045: 
046:         uint88 creditReth;
047:         uint88 creditSteth;
048:         if (bridgePointer == VAULT.BRIDGE_RETH) {
049:             // Withdraw RETH
050:             creditReth = VaultUser.bridgeCreditReth;
051:             if (creditReth >= amount) {
052:                 VaultUser.bridgeCreditReth -= amount;
053:                 return 0;
054:             }
055: 
056:             VaultUser.bridgeCreditReth = 0;
057:             amount -= creditReth;
058:             creditSteth = VaultUser.bridgeCreditSteth;
059:             if (creditSteth < C.ROUNDING_ZERO) {
060:                 // Valid withdraw when no STETH credits
061:                 return amount;
062:             } else {
063:                 if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
064:                     // Can withdraw RETH using STETH credit when STETH bridge is empty
065:                     if (creditSteth >= amount) {
066:                         VaultUser.bridgeCreditSteth -= amount;
067:                         return 0;
068:                     } else {
069:                         VaultUser.bridgeCreditSteth = 0;
070:                         return amount - creditSteth;
071:                     }
072:                 } else {
073:                     // Must use available bridge credits on withdrawal
074:                     // @dev Prevents abusing bridge for arbitrage
075:                     revert Errors.MustUseExistingBridgeCredit();
076:                 }
077:             }
078:         } else {
079:             // Withdraw STETH
080:             creditSteth = VaultUser.bridgeCreditSteth;
081:             if (creditSteth >= amount) {
082:                 VaultUser.bridgeCreditSteth -= amount;
083:                 return 0;
084:             }
085: 
086:             VaultUser.bridgeCreditSteth = 0;
087:             amount -= creditSteth;
088:             creditReth = VaultUser.bridgeCreditReth;
089:             if (creditReth < C.ROUNDING_ZERO) {
090:                 // Valid withdraw when no RETH credits
091:                 return amount;
092:             } else {
093:                 if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
094:                     // Can withdraw STETH using RETH credit when RETH bridge is empty
095:                     if (creditReth >= amount) {
096:                         VaultUser.bridgeCreditReth -= amount;
097:                         return 0;
098:                     } else {
099:                         VaultUser.bridgeCreditReth = 0;
100:                         return amount - creditReth;
101:                     }
102:                 } else {
103:                     // Must use available bridge credits on withdrawal
104:                     // @dev Prevents abusing bridge for arbitrage
105:                     revert Errors.MustUseExistingBridgeCredit();
106:                 }
107:             }
108:         }
109:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L109) 


```solidity

File: contracts/libraries/LibOrders.sol

//@audit the following parameters are mutated orderType,
402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType
409:     ) internal view returns (int256 direction) {
410:         orderType = normalizeOrderType(orderType);
411: 
412:         if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413:             return verifySellId(orders, asset, prevId, newPrice, nextId);
414:         } else if (orderType == O.LimitBid) {
415:             return verifyBidId(asset, prevId, newPrice, nextId);
416:         }
417:     }

//@audit the following parameters are mutated hintId,
440:     function getOrderId(
441:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442:         address asset,
443:         int256 direction,
444:         uint16 hintId,
445:         uint256 _newPrice,
446:         O orderType
447:     ) internal view returns (uint16 _hintId) {
448:         while (true) {
449:             uint16 nextId = orders[asset][hintId].nextId;
450: 
451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {
452:                 return hintId;
453:             }
454: 
455:             if (direction == C.PREV) {
456:                 uint16 prevId = orders[asset][hintId].prevId;
457:                 hintId = prevId;
458:             } else {
459:                 hintId = nextId;
460:             }
461:         }
462:     }


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L402-L417) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L462)


</details>


### [NC&#x2011;54] A event should be emitted if a non immutable state variable is set in a constructor 



*There are 4 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

31:         dusd = _dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L31-L31) 


```solidity

File: contracts/facets/BridgeRouterFacet.sol

30:         rethBridge = _rethBridge;

31:         stethBridge = _stethBridge;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L30-L30) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L31-L31)


```solidity

File: contracts/facets/ExitShortFacet.sol

29:         dusd = _dusd;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L29-L29) 


</details>


### [NC&#x2011;55] Contracts use both += 1 and ++ (-- and -= 1) 
For consistency consider only using one of these incrementing methods. The instances bellow represents the less used technique.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibOrders.sol

210:             s.asset[asset].orderIdCounter += 1;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L210-L210) 


</details>


### [NC&#x2011;56] Not using the named return variables anywhere in the function is confusing 
Consider changing the variable to be an unnamed one, since the variable is never assigned, nor is it returned by name. If the optimizer is not turned on, leaving the code as it is will also waste gas for the stack variable.


*There are 22 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

// @audit ethFilled
// @audit ercAmountLeft
40:     function createBid(

// @audit ethFilled
// @audit ercAmountLeft
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)

// @audit ethFilled
// @audit ercAmountLeft
77:     function _createBid(

// @audit ethFilled
// @audit ercAmountLeft
130:     function bidMatchAlgo(

// @audit ethFilled
// @audit ercAmountLeft
275:     function matchIncomingBid(

// @audit lowestSell
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L40-L40) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L65-L65), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L77-L77), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L130-L130), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L275-L275), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340)


```solidity

File: contracts/facets/ExitShortFacet.sol

// @audit cRatio
213:     function getCollateralRatioNonPrice(STypes.ShortRecord storage short) internal view returns (uint256 cRatio) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L213-L213) 


```solidity

File: contracts/facets/RedemptionFacet.sol

// @audit redemptionFee
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

// @audit fee
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113) 


```solidity

File: contracts/libraries/LibOracle.sol

// @audit _protocolPrice
69:     function baseOracleCircuitBreaker(

// @audit twapPriceInEth
131:     function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {

// @audit creationTime
156:     function getTime(address asset) internal view returns (uint256 creationTime) {

// @audit oraclePrice
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L69-L69) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L131-L131), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162)


```solidity

File: contracts/libraries/LibOrders.sol

// @audit timeInSeconds
30:     function getOffsetTime() internal view returns (uint32 timeInSeconds) {

// @audit direction
231:     function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)

// @audit direction
260:     function verifySellId(

// @audit direction
402:     function verifyId(

// @audit newO
420:     function normalizeOrderType(O o) private pure returns (O newO) {

// @audit _hintId
440:     function getOrderId(

// @audit hintId
826:     function findOrderHintId(


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L30-L30) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L231-L231), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L260-L260), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L402-L402), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L420-L420), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L440-L440), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L826)


```solidity

File: contracts/libraries/LibSRUtil.sol

// @audit isCancelled
49:     function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

// @audit recoveryViolation
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L49-L49) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102)


</details>


### [NC&#x2011;57] Use named return values 
Using named returns makes the code more self-documenting, makes it easier to fill out NatSpec, and in some cases can save gas. The cases below are where there currently is at most one return statement, which is ideal for named returns.


*There are 17 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/PrimaryLiquidationFacet.sol

47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48:         external
49:         isNotFrozen(asset)
50:         nonReentrant
51:         onlyValidShortRecord(asset, shorter, id)
52:         returns (uint88, uint88)

122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123:         private
124:         returns (MTypes.PrimaryLiquidation memory)

229:     function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L47-L52) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L122-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L229-L229)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

40:     function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {

51:     function getBridges(uint256 vault) external view returns (address[] memory) {

169:     function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L40-L40) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L51-L51), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L169-L169)


```solidity

File: contracts/facets/RedemptionFacet.sol

31:     function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)
32:         internal
33:         view
34:         returns (bool)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L31-L34) 


```solidity

File: contracts/libraries/LibBridgeRouter.sol

39:     function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40:         internal
41:         returns (uint88)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L39-L41) 


```solidity

File: contracts/libraries/LibBytes.sol

11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11) 


```solidity

File: contracts/libraries/LibOracle.sol

19:     function getOraclePrice(address asset) internal view returns (uint256) {

168:     function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L168-L168)


```solidity

File: contracts/libraries/LibOrders.sol

35:     function convertCR(uint16 cr) internal pure returns (uint256) {

55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)
56:         internal
57:         view
58:         returns (STypes.Order[] memory)

78:     function isShort(STypes.Order memory order) internal pure returns (bool) {

362:     function findPrevOfIncomingId(
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId
367:     ) internal view returns (uint16) {

985:     function min(uint256 a, uint256 b) internal pure returns (uint256) {

989:     function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L35-L35) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L58), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L78-L78), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L362-L367), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L985-L985), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L989-L989)


</details>


### [NC&#x2011;58] Consider moving duplicated strings to constants 



*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/LibBytes.sol

14:         require(slate.length % 51 == 0, "Invalid data length");


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L14-L14) 


</details>


### [NC&#x2011;59] Consider adding validation of user inputs 



*There are 56 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

//@audit these parameters `asset`, are not checked
40:     function createBid(
41:         address asset,
42:         uint80 price,
43:         uint88 ercAmount,
44:         bool isMarketOrder,
45:         MTypes.OrderHint[] calldata orderHintArray,
46:         uint16[] calldata shortHintArray

//@audit these parameters `sender`,`asset`, are not checked
65:     function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)

//@audit these parameters `asset`, are not checked
215:     function matchlowestSell(
216:         address asset,
217:         STypes.Order memory lowestSell,
218:         STypes.Order memory incomingBid,
219:         MTypes.Match memory matchTotal

//@audit these parameters `asset`, are not checked
275:     function matchIncomingBid(
276:         address asset,
277:         STypes.Order memory incomingBid,
278:         MTypes.Match memory matchTotal,
279:         MTypes.BidMatchAlgo memory b

//@audit these parameters `asset`, are not checked
340:     function _getLowestSell(address asset, MTypes.BidMatchAlgo memory b) private view returns (STypes.Order memory lowestSell) {

//@audit these parameters `asset`, are not checked
358:     function _shortDirectionHandler(
359:         address asset,
360:         STypes.Order memory lowestSell,
361:         STypes.Order memory incomingBid,
362:         MTypes.BidMatchAlgo memory b


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L40-L46) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L65-L65), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L215-L219), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L275-L279), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L340-L340), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L358-L362)


```solidity

File: contracts/facets/ShortOrdersFacet.sol

//@audit these parameters `asset`, are not checked
35:     function createLimitShort(
36:         address asset,
37:         uint80 price,
38:         uint88 ercAmount,
39:         MTypes.OrderHint[] memory orderHintArray,
40:         uint16[] memory shortHintArray,
41:         uint16 shortOrderCR


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ShortOrdersFacet.sol#L35-L41) 


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

//@audit these parameters `asset`, are not checked
47:     function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)

//@audit these parameters `asset`,`shorter`, are not checked
122:     function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L47-L47) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L122-L122)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

//@audit these parameters `bridge`, are not checked
63:     function deposit(address bridge, uint88 amount) external nonReentrant {

//@audit these parameters `bridge`, are not checked
82:     function depositEth(address bridge) external payable nonReentrant {

//@audit these parameters `bridge`, are not checked
101:     function withdraw(address bridge, uint88 dethAmount) external nonReentrant {

//@audit these parameters `bridge`, are not checked
133:     function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L63-L63) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L82-L82), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L101-L101), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L133-L133)


```solidity

File: contracts/facets/ExitShortFacet.sol

//@audit these parameters `asset`, are not checked
41:     function exitShortWallet(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)

//@audit these parameters `asset`, are not checked
87:     function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L41-L41) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/ExitShortFacet.sol#L87-L87)


```solidity

File: contracts/facets/RedemptionFacet.sol

//@audit these parameters `asset`, are not checked
56:     function proposeRedemption(
57:         address asset,
58:         MTypes.ProposalInput[] calldata proposalInput,
59:         uint88 redemptionAmount,
60:         uint88 maxRedemptionFee

//@audit these parameters `asset`, are not checked
224:     function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)

//@audit these parameters `asset`, are not checked
310:     function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {

//@audit these parameters `asset`,`redeemer`, are not checked
347:     function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)

//@audit these parameters `asset`,`shorter`, are not checked
368:     function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {

//@audit these parameters `asset`, are not checked
382:     function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L56-L60) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L224-L224), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L310-L310), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L347-L347), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L368-L368), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L382-L382)


```solidity

File: contracts/libraries/LibBridgeRouter.sol

//@audit these parameters `rethBridge`,`stethBridge`, are not checked
113:     function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

//@audit these parameters `asset`,`from`,`to`, are not checked
144:     function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L113-L113) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBridgeRouter.sol#L144-L144)


```solidity

File: contracts/libraries/LibBytes.sol

//@audit these parameters `SSTORE2Pointer`, are not checked
11:     function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibBytes.sol#L11-L11) 


```solidity

File: contracts/libraries/LibOracle.sol

//@audit these parameters `asset`, are not checked
19:     function getOraclePrice(address asset) internal view returns (uint256) {

//@audit these parameters `asset`, are not checked
149:     function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {

//@audit these parameters `asset`, are not checked
156:     function getTime(address asset) internal view returns (uint256 creationTime) {

//@audit these parameters `asset`, are not checked
162:     function getPrice(address asset) internal view returns (uint80 oraclePrice) {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L19-L19) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L149-L149), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L162-L162)


```solidity

File: contracts/libraries/LibOrders.sol

//@audit these parameters `asset`, are not checked
40:     function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

//@audit these parameters `orders`,`asset`, are not checked
55:     function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)

//@audit these parameters `asset`, are not checked
153:     function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {

//@audit these parameters `orders`,`asset`, are not checked
173:     function addOrder(
174:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
175:         address asset,
176:         STypes.Order memory incomingOrder,
177:         uint16 hintId

//@audit these parameters `orders`,`asset`, are not checked
289:     function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

//@audit these parameters `orders`,`asset`, are not checked
314:     function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

//@audit these parameters `orders`,`asset`, are not checked
320:     function _reuseOrderIds(
321:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322:         address asset,
323:         uint16 id,
324:         uint16 prevHEAD,
325:         O cancelledOrMatched

//@audit these parameters `orders`,`asset`, are not checked
362:     function findPrevOfIncomingId(
363:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
364:         address asset,
365:         STypes.Order memory incomingOrder,
366:         uint16 hintId

//@audit these parameters `orders`,`asset`, are not checked
402:     function verifyId(
403:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404:         address asset,
405:         uint16 prevId,
406:         uint256 newPrice,
407:         uint16 nextId,
408:         O orderType

//@audit these parameters `orders`,`asset`, are not checked
474:     function updateBidOrdersOnMatch(
475:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
476:         address asset,
477:         uint16 id,
478:         bool isOrderFullyFilled

//@audit these parameters `asset`, are not checked
499:     function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {

//@audit these parameters `orders`,`asset`, are not checked
532:     function _updateOrders(
533:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
534:         address asset,
535:         uint16 headId,
536:         uint16 lastMatchedId

//@audit these parameters `asset`, are not checked
628:     function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

//@audit these parameters `asset`, are not checked
652:     function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {

//@audit these parameters `asset`, are not checked
668:     function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {

//@audit these parameters `asset`, are not checked
705:     function matchHighestBid(
706:         STypes.Order memory incomingSell,
707:         STypes.Order memory highestBid,
708:         address asset,
709:         MTypes.Match memory matchTotal

//@audit these parameters `asset`, are not checked
783:     function updateOracleAndStartingShortViaThreshold(
784:         address asset,
785:         uint256 savedPrice,
786:         STypes.Order memory incomingOrder,
787:         uint16[] memory shortHintArray

//@audit these parameters `orders`,`asset`, are not checked
826:     function findOrderHintId(
827:         mapping(address => mapping(uint16 => STypes.Order)) storage orders,
828:         address asset,
829:         MTypes.OrderHint[] memory orderHintArray

//@audit these parameters `asset`, are not checked
854:     function cancelBid(address asset, uint16 id) internal {

//@audit these parameters `asset`, are not checked
868:     function cancelAsk(address asset, uint16 id) internal {

//@audit these parameters `asset`, are not checked
882:     function cancelShort(address asset, uint16 id) internal {

//@audit these parameters `asset`, are not checked
955:     function handlePriceDiscount(address asset, uint80 price) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L40-L40) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L55-L55), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L153-L153), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L173-L177), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L289-L289), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L314-L314), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L320-L325), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L362-L366), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L402-L408), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L474-L478), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L499-L499), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L532-L536), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L628-L628), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L652-L652), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L668-L668), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L705-L709), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L783-L787), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L826-L829), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L854-L854), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L868-L868), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L882-L882), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L955-L955)


```solidity

File: contracts/libraries/LibSRUtil.sol

//@audit these parameters `asset`,`shorter`, are not checked
22:     function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

//@audit these parameters `asset`, are not checked
72:     function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

//@audit these parameters `asset`, are not checked
102:     function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)

//@audit these parameters `from`,`to`, are not checked
124:     function transferShortRecord(address from, address to, uint40 tokenId) internal {

//@audit these parameters `asset`, are not checked
151:     function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L22-L22) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L72-L72), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L102-L102), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L124-L124), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibSRUtil.sol#L151-L151)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

//@audit these parameters `pool`,`baseToken`,`quoteToken`, are not checked
47:     function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L47-L47) 


</details>


### [NC&#x2011;60] Interfaces should use floating version pragmas 
If the file contains non-interfaces as well, the interfaces should be moved to a separate file.


*There are 1 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/libraries/UniswapOracleLibrary.sol

2: pragma solidity 0.8.21;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L2-L2) 


</details>


### [NC&#x2011;61] Consider using named function calls 
Named function calls in Solidity greatly improve code readability by explicitly mapping arguments to their respective parameter names. This clarity becomes critical when dealing with functions that have numerous or complex parameters, reducing potential errors due to misordered arguments. Therefore, adopting named function calls contributes to more maintainable and less error-prone code.


*There are 74 instances of this issue:*



<details>
<summary>see instances</summary>


```solidity
File: contracts/facets/BidOrdersFacet.sol

50:         return _createBid(msg.sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray);

74:         return _createBid(sender, asset, price, ercAmount, C.MARKET_ORDER, orderHintArray, shortHintArray);

105:         STypes.Order memory lowestSell = _getLowestSell(asset, b);

111:             return bidMatchAlgo(asset, incomingBid, orderHintArray, b);

148:             STypes.Order memory lowestSell = _getLowestSell(asset, b);

145:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);

201:                 return matchIncomingBid(asset, incomingBid, matchTotal, b);

155:                 matchlowestSell(asset, lowestSell, incomingBid, matchTotal);

153:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

195:                     return matchIncomingBid(asset, incomingBid, matchTotal, b);

163:                         _shortDirectionHandler(asset, lowestSell, incomingBid, b);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L50-L50) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L74-L74), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L105-L105), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L111-L111), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L148-L148), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L145-L145), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L201-L201), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L155-L155), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L153-L153), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L195-L195), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BidOrdersFacet.sol#L163-L163)


```solidity

File: contracts/facets/PrimaryLiquidationFacet.sol

70:         MTypes.PrimaryLiquidation memory m = _setLiquidationStruct(asset, shorter, id, shortOrderId);

81:         _performForcedBid(m, shortHintArray);

242:         uint88 decreaseCol = min88(m.totalFee + m.ethFilled, m.short.collateral);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L70-L70) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L81-L81), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/PrimaryLiquidationFacet.sol#L242-L242)


```solidity

File: contracts/facets/BridgeRouterFacet.sol

71:         maybeUpdateYield(vault, dethAmount);

89:         maybeUpdateYield(vault, dethAmount);

119:         uint88 ethAmount = _ethConversion(vault, dethAmount);

137:         uint88 ethAmount = _ethConversion(vault, dethAmount);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L71-L71) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L89-L89), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L119-L119), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/BridgeRouterFacet.sol#L137-L137)


```solidity

File: contracts/facets/RedemptionFacet.sol

204:         uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);

251:         if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();

87:             if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L204-L204) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L251-L251), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/facets/RedemptionFacet.sol#L87-L87)


```solidity

File: contracts/libraries/LibOracle.sol

44:                 oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp);

31:                 basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L44-L44) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOracle.sol#L31-L31)


```solidity

File: contracts/libraries/LibOrders.sol

96:         addOrder(s.bids, asset, order, hintId);

116:         addOrder(s.asks, asset, order, hintId);

139:         addOrder(s.shorts, asset, order, hintId);

140:         updateStartingShortIdViaShort(asset, order);

182:         uint16 prevId = findPrevOfIncomingId(orders, asset, incomingOrder, hintId);

302:         _reuseOrderIds(orders, asset, id, prevHEAD, O.Cancelled);

316:         _reuseOrderIds(orders, asset, id, prevHEAD, O.Matched);

376:         int256 direction = verifyId(orders, asset, hintId, incomingOrder.price, nextId, incomingOrder.orderType);

715:         increaseSharesOnMatch(asset, highestBid, matchTotal, fillEth);

865:         cancelOrder(s.bids, asset, id);

879:         cancelOrder(s.asks, asset, id);

951:         cancelOrder(s.shorts, asset, id);

156:             addShort(asset, incomingOrder, orderHintArray);

372:             return getOrderId(orders, asset, C.NEXT, C.HEAD, incomingOrder.price, incomingOrder.orderType);

413:             return verifySellId(orders, asset, prevId, newPrice, nextId);

483:             _updateOrders(orders, asset, C.HEAD, id);

502:             _updateOrders(s.asks, asset, C.HEAD, b.matchedAskId);

636:             matchIncomingShort(asset, incomingOrder, matchTotal);

798:             _updateOracleAndStartingShort(asset, shortHintArray);

806:             _updateOracleAndStartingShort(asset, shortHintArray);

965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));

93:             hintId = findOrderHintId(s.bids, asset, orderHintArray);

114:             hintId = findOrderHintId(s.asks, asset, orderHintArray);

135:             hintId = findOrderHintId(s.shorts, asset, orderHintArray);

158:             addAsk(asset, incomingOrder, orderHintArray);

387:             return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);

384:             return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);

415:             return verifyBidId(asset, prevId, newPrice, nextId);

451:             if (verifyId(orders, asset, hintId, _newPrice, nextId, orderType) == C.EXACT) {

638:             matchIncomingAsk(asset, incomingOrder, matchTotal);

965:             uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));

509:                 _updateOrders(s.shorts, asset, b.prevShortId, b.matchedShortId);

566:                 addSellOrder(incomingAsk, asset, orderHintArray);

617:                 updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

618:                 matchIncomingSell(asset, incomingAsk, matchTotal);

582:                 matchHighestBid(incomingAsk, highestBid, asset, matchTotal);

512:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, b.matchedShortId);

515:                 _updateOrders(s.shorts, asset, b.prevShortId, b.shortHintId);

621:                     addSellOrder(incomingAsk, asset, orderHintArray);

577:                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

579:                     matchIncomingSell(asset, incomingAsk, matchTotal);

613:                     matchIncomingSell(asset, incomingAsk, matchTotal);

586:                     matchOrder(s.bids, asset, highestBid.id);

519:                 _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, id);

606:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);

601:                         matchOrder(s.bids, asset, highestBid.id);

602:                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);

591:                         matchIncomingSell(asset, incomingAsk, matchTotal);

609:                             cancelBid(asset, highestBid.id);

594:                             addSellOrder(incomingAsk, asset, orderHintArray);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L96-L96) , [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L116-L116), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L139-L139), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L140-L140), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L182-L182), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L302-L302), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L316-L316), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L376-L376), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L715-L715), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L865-L865), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L879-L879), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L951-L951), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L156-L156), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L372-L372), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L413-L413), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L483-L483), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L502-L502), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L636-L636), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L798-L798), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L806-L806), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L965-L965), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L93-L93), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L114-L114), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L135-L135), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L158-L158), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L387-L387), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L384-L384), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L415-L415), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L451-L451), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L638-L638), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L965-L965), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L509-L509), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L566-L566), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L617-L617), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L618-L618), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L582-L582), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L512-L512), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L515-L515), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L621-L621), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L577-L577), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L579-L579), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L613-L613), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L586-L586), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L519-L519), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L606-L606), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L601-L601), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L602-L602), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L591-L591), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L609-L609), [link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/LibOrders.sol#L594-L594)


```solidity

File: contracts/libraries/UniswapOracleLibrary.sol

70:         amountOut = getQuoteAtTick(tick, amountIn, baseToken, quoteToken);


```

[link](https://github.com/code-423n4/2024-03-dittoeth/blob/main//contracts/libraries/UniswapOracleLibrary.sol#L70-L70) 


</details>
