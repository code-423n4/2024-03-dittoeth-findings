# Quality Assurance Report For DittoETH Contest
### Total Low Risk Issues : 10
### Total Non-critical Issues : 54
# Low Risk Issues

| |Issue|Instances|
|-|:-|:-:|
| [[L001](#l001---array-lengths-not-checked)] | Array lengths not checked | 1 |
| [[L002](#l002---unsafe-downcast)] | Unsafe downcast | 7 |
| [[L003](#l003---no-limits-when-setting-state-variable-amounts)] | No limits when setting state variable amounts | 4 |
| [[L004](#l004---double-type-casts-create-complexity-within-the-code)] | Double type casts create complexity within the code | 1 |
| [[L005](#l005---constructor-contains-no-validation)] | Constructor contains no validation | 2 |
| [[L006](#l006---for-loops-in-public-or-external-functions-should-be-avoided-due-to-high-gas-costs-and-possible-dos)] | For loops in `public` or `external` functions should be avoided due to high gas costs and possible DOS | 3 |
| [[L007](#l007---function-calls-within-for-loops)] | Function calls within for loops | 2 |
| [[L008](#l008---multiplication-on-the-result-of-a-division)] | Multiplication on the result of a division | 3 |
| [[L009](#l009---missing-checks-for-address0x0-in-the-constructor)] | Missing checks for address(0x0) in the constructor | 3 |
| [[L010](#l010---prefer-continue-over-revert-model-in-iteration)] | Prefer continue over revert model in iteration | 2 |


## L001 - Array lengths not checked:

If the length of the arrays are not required to be of the same length, user operations may not be fully executed due to a mismatch in the number of items iterated over, versus the number of items provided in the second array.


```solidity
File: facets/ShortOrdersFacet.sol


35          function createLimitShort(
36              address asset,
37              uint80 price,
38              uint88 ercAmount,
39              MTypes.OrderHint[] memory orderHintArray,
40              uint16[] memory shortHintArray,
41              uint16 shortOrderCR
42          ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43              MTypes.CreateLimitShortParam memory p;
44              STypes.Asset storage Asset = s.asset[asset];
45              STypes.Order memory incomingShort;
46      
47              // @dev create "empty" SR. Fail early.
48              incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49      
50              uint256 cr = LibOrders.convertCR(shortOrderCR);
51              if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52                  revert Errors.InvalidCR();
53              }
54      
55              // @dev minShortErc needs to be modified (bigger) when cr < 1
56              p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57              p.eth = price.mul(ercAmount);
58              p.minAskEth = LibAsset.minAskEth(asset);
59              if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60      
61              // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62              if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63      
64              incomingShort.addr = msg.sender;
65              incomingShort.price = price;
66              incomingShort.ercAmount = ercAmount;
67              incomingShort.id = Asset.orderIdCounter;
68              incomingShort.orderType = O.LimitShort;
69              incomingShort.creationTime = LibOrders.getOffsetTime();
70              incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71      
72              p.startingId = s.bids[asset][C.HEAD].nextId;
73              STypes.Order storage highestBid = s.bids[asset][p.startingId];
74              // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75              if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76                  LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77              }
78      
79              p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80              if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81                  revert Errors.BelowRecoveryModeCR();
82              }
83      
84              // @dev reading spot oracle price
85              if (incomingShort.price < p.oraclePrice) {
86                  LibOrders.addShort(asset, incomingShort, orderHintArray);
87              } else {
88                  LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89              }
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35:90



## L002 - Unsafe downcast:

When a type is downcast to a smaller type, the higher order bits are truncated, effectively applying a modulo to the original value. Without any other checks, this wrapping will lead to unexpected behavior and bugs.


<details>
<summary>Click to show 7 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


87              uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH


68              uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L68:68

```solidity
File: facets/PrimaryLiquidationFacet.sol


231             return a < b ? uint88(a) : b;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L231:231

```solidity
File: libraries/LibOracle.sol


151             s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);


164             return uint80(s.bids[asset][C.HEAD].ercAmount);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L164:164

```solidity
File: libraries/LibOrders.sol


903                 uint88 minShortErc = uint88(LibAsset.minShortErc(asset));


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L903:903

```solidity
File: libraries/UniswapOracleLibrary.sol


62              int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62:62

</details>


## L003 - No limits when setting state variable amounts:

It is important to ensure state variables numbers are set to a reasonable value.


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: libraries/LibOracle.sol


152             s.bids[asset][C.HEAD].creationTime = oracleTime;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L152:152

```solidity
File: libraries/LibOrders.sol


334             orders[asset][C.HEAD].prevId = id;


488                 orders[asset][C.HEAD].nextId = id;


542                 orders[asset][nextAskId].prevId = headId;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L542:542

</details>

## L004 - Double type casts create complexity within the code:

Double type casting should be avoided in Solidity contracts to prevent unintended consequences and ensure accurate data representation. Performing multiple type casts in succession can lead to unexpected truncation, rounding errors, or loss of precision, potentially compromising the contract's functionality and reliability. Furthermore, double type casting can make the code less readable and harder to maintain, increasing the likelihood of errors and misunderstandings during development and debugging. To ensure precise and consistent data handling, developers should use appropriate data types and avoid unnecessary or excessive type casting, promoting a more robust and dependable contract execution.


```solidity
File: facets/RedemptionFacet.sol


bytes8(uint64(p.currentCR)),

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L133:133

## L005 - Constructor contains no validation:

In Solidity, when values are being assigned in constructors to unsigned or integer variables, it's crucial to ensure the provided values adhere to the protocol's specific operational boundaries as laid out in the project specifications and documentation. If the constructors lack appropriate validation checks, there's a risk of setting state variables with values that could cause unexpected and potentially detrimental behavior within the contract's operations, violating the intended logic of the protocol. This can compromise the contract's security and impact the maintainability and reliability of the system. In order to avoid such issues, it is recommended to incorporate rigorous validation checks in constructors. These checks should align with the project's defined rules and constraints, making use of Solidity's built-in require function to enforce these conditions. If the validation checks fail, the require function will cause the transaction to revert, ensuring the integrity and adherence to the protocol's expected behavior.


```solidity
File: facets/BridgeRouterFacet.sol


29          constructor(address _rethBridge, address _stethBridge) {
30              rethBridge = _rethBridge;
31              stethBridge = _stethBridge;
32          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29:32

```solidity
File: facets/PrimaryLiquidationFacet.sol


30          constructor(address _dusd) {
31              dusd = _dusd;
32          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L30:32

## L006 - For loops in `public` or `external` functions should be avoided due to high gas costs and possible DOS:

In Solidity, for loops can potentially cause Denial of Service (DoS) attacks if not handled carefully. DoS attacks can occur when an attacker intentionally exploits the gas cost of a function, causing it to run out of gas or making it too expensive for other users to call. Below are some scenarios where for loops can lead to DoS attacks: Nested for loops can become exceptionally gas expensive and should be used sparingly.


```solidity
File: facets/RedemptionFacet.sol


56          function proposeRedemption(
57              address asset,
58              MTypes.ProposalInput[] calldata proposalInput,
59              uint88 redemptionAmount,
60              uint88 maxRedemptionFee
61          ) external isNotFrozen(asset) nonReentrant {
62              if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63              MTypes.ProposeRedemption memory p;
64              p.asset = asset;
65              STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66              uint256 minShortErc = LibAsset.minShortErc(p.asset);
67      
68              if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69      
70              if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71      
72              // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73              if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74      
75              p.oraclePrice = LibOracle.getPrice(p.asset);
76      
77              bytes memory slate;
78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }
142     
143             if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144     
145             // @dev SSTORE2 the entire proposalData after validating proposalInput
146             redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147             redeemerAssetUser.slateLength = p.redemptionCounter;
148             redeemerAssetUser.oraclePrice = p.oraclePrice;
149             redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150     
151             STypes.Asset storage Asset = s.asset[p.asset];
152             Asset.ercDebt -= p.totalAmountProposed;
153     
154             uint32 protocolTime = LibOrders.getOffsetTime();
155             redeemerAssetUser.timeProposed = protocolTime;
156             // @dev Calculate the dispute period
157             // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158     
159             /*
160             +-------+------------+
161             | CR(X) |  Hours(Y)  |
162             +-------+------------+
163             | 1.1   |     0      |
164             | 1.2   |    .333    |
165             | 1.3   |    .75     |
166             | 1.5   |    1.5     |
167             | 1.7   |     3      |
168             | 2.0   |     6      |
169             +-------+------------+
170     
171             Creating fixed points and interpolating between points on the graph without using exponentials
172             Using simple y = mx + b formula
173             
174             where x = currentCR - previousCR
175             m = (y2-y1)/(x2-x1)
176             b = previous fixed point (Y)
177             */
178     
179             uint256 m;
180     
181             if (p.currentCR > 1.7 ether) {
182                 m = uint256(3 ether).div(0.3 ether);
183                 redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184             } else if (p.currentCR > 1.5 ether) {
185                 m = uint256(1.5 ether).div(0.2 ether);
186                 redeemerAssetUser.timeToDispute =
187                     protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188             } else if (p.currentCR > 1.3 ether) {
189                 m = uint256(0.75 ether).div(0.2 ether);
190                 redeemerAssetUser.timeToDispute =
191                     protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192             } else if (p.currentCR > 1.2 ether) {
193                 m = uint256(0.417 ether).div(0.1 ether);
194                 redeemerAssetUser.timeToDispute =
195                     protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196             } else if (p.currentCR > 1.1 ether) {
197                 m = uint256(C.ONE_THIRD.div(0.1 ether));
198                 redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199             }
200     
201             redeemerAssetUser.oraclePrice = p.oraclePrice;
202             redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203     
204             uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205             if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206     
207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208             if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209             VaultUser.ethEscrowed -= redemptionFee;
210             emit Events.ProposeRedemption(p.asset, msg.sender);
211         }


224         function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225             external
226             isNotFrozen(asset)
227             nonReentrant
228         {
229             if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230             MTypes.DisputeRedemption memory d;
231             d.asset = asset;
232             d.redeemer = redeemer;
233     
234             STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236     
237             if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238     
239             MTypes.ProposalData[] memory decodedProposalData =
240                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241     
242             for (uint256 i = 0; i < decodedProposalData.length; i++) {
243                 if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244                     revert Errors.CannotDisputeWithRedeemerProposal();
245                 }
246             }
247     
248             STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249             // Match continue (skip) conditions in proposeRedemption()
250             uint256 minShortErc = LibAsset.minShortErc(d.asset);
251             if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252     
253             MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254             MTypes.ProposalData memory currentProposal;
255             STypes.Asset storage Asset = s.asset[d.asset];
256     
257             uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258     
259             if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260             {
261                 // @dev All proposals from the incorrectIndex onward will be removed
262                 // @dev Thus the proposer can only redeem a portion of their original slate
263                 for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264                     currentProposal = decodedProposalData[i];
265     
266                     STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267                     currentSR.collateral += currentProposal.colRedeemed;
268                     currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269     
270                     d.incorrectCollateral += currentProposal.colRedeemed;
271                     d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272                 }
273     
274                 s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275                 Asset.dethCollateral += d.incorrectCollateral;
276                 Asset.ercDebt += d.incorrectErcDebt;
277     
278                 // @dev Update the redeemer's SSTORE2Pointer
279                 if (incorrectIndex > 0) {
280                     redeemerAssetUser.slateLength = incorrectIndex;
281                 } else {
282                     // @dev this implies everything in the redeemer's proposal was incorrect
283                     delete redeemerAssetUser.SSTORE2Pointer;
284                     emit Events.DisputeRedemptionAll(d.asset, redeemer);
285                 }
286     
287                 // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288                 // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289                 uint256 penaltyPct = LibOrders.min(
290                     LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291                 );
292     
293                 uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294     
295                 // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296                 redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297                 s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298             } else {
299                 revert Errors.InvalidRedemptionDispute();
300             }
301         }


310         function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
311             uint256 vault = s.asset[asset].vault;
312             STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
313             STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
314             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
315             if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
316     
317             MTypes.ProposalData[] memory decodedProposalData =
318                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
319     
320             uint88 totalColRedeemed;
321             for (uint256 i = 0; i < decodedProposalData.length; i++) {
322                 MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323                 totalColRedeemed += currentProposal.colRedeemed;
324                 _claimRemainingCollateral({
325                     asset: asset,
326                     vault: vault,
327                     shorter: currentProposal.shorter,
328                     shortId: currentProposal.shortId
329                 });
330             }
331             redeemerVaultUser.ethEscrowed += totalColRedeemed;
332             delete redeemerAssetUser.SSTORE2Pointer;
333             emit Events.ClaimRedemption(asset, msg.sender);
334         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L310:334

## L007 - Function calls within for loops:

Making function calls within loops in Solidity can lead to inefficient gas usage, potential bottlenecks, and increased vulnerability to attacks. Each function call or external call consumes gas, and when executed within a loop, the gas cost multiplies, potentially causing the transaction to run out of gas or exceed block gas limits. This can result in transaction failure or unpredictable behavior.


```solidity
File: facets/RedemptionFacet.sol


321             for (uint256 i = 0; i < decodedProposalData.length; i++) {
322                 MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323                 totalColRedeemed += currentProposal.colRedeemed;
324                 _claimRemainingCollateral({
325                     asset: asset,
326                     vault: vault,
327                     shorter: currentProposal.shorter,
328                     shortId: currentProposal.shortId
329                 });
330             }


78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78:141


## L008 - Multiplication on the result of a division:

Dividing an integer by another integer will often result in loss of precision. When the result is multiplied by another number, the loss of precision is magnified, often to material magnitudes. (X / Z) * Y should be re-written as (X * Y) / Z.


```solidity
File: libraries/LibOracle.sol


93                      uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);


141             uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L141:141

```solidity
File: libraries/LibOrders.sol


47                  uint88 shares = eth * (timeTillMatch / 1 days);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L47:47

## L009 - Missing checks for address(0x0) in the constructor:




```solidity
File: facets/BridgeRouterFacet.sol


30              rethBridge = _rethBridge;


31              stethBridge = _stethBridge;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L31:31

```solidity
File: facets/PrimaryLiquidationFacet.sol


31              dusd = _dusd;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L31:31


## L010 - Prefer continue over revert model in iteration:

Preferably, it's better to skip operations on array indices when a condition is not met instead of reverting the entire transaction. Reverting could be exploited by malicious actors who might intentionally introduce array objects failing conditional checks, disrupting group operations. It's advisable to skip array indices rather than revert, unless there are valid security or logic reasons for doing otherwise


```solidity
File: facets/RedemptionFacet.sol


78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }


242             for (uint256 i = 0; i < decodedProposalData.length; i++) {
243                 if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244                     revert Errors.CannotDisputeWithRedeemerProposal();
245                 }
246             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L242:246


# Non-critical Issues

| |Issue|Instances|
|-|:-|:-:|
| [[NC001](#nc001---the-nonreentrant-modifier-should-occur-before-all-other-modifiers)] | The `nonReentrant` `modifier` should occur before all other modifiers | 6 |
| [[NC002](#nc002---imports-could-be-organized-more-systematically)] | Imports could be organized more systematically | 4 |
| [[NC003](#nc003---constants-in-comparisons-should-appear-on-the-left-side)] | Constants in comparisons should appear on the left side | 41 |
| [[NC004](#nc004---else-block-not-required)] | else-block not required | 32 |
| [[NC005](#nc005---if-statement-can-be-converted-to-a-ternary)] | If-statement can be converted to a ternary | 4 |
| [[NC006](#nc006---variable-names-that-consist-of-all-capital-letters-should-be-reserved-for-constantimmutable-variables)] | Variable names that consist of all capital letters should be reserved for constant/immutable variables | 4 |
| [[NC007](#nc007---consider-using-delete-rather-than-assigning-falsezero-to-clear-values)] | Consider using delete rather than assigning false/zero to clear values | 14 |
| [[NC008](#nc008---variable-names-for-immutables-should-use-constant_case)] | Variable names for `immutable`s should use CONSTANT_CASE | 3 |
| [[NC009](#nc009---lines-are-too-long)] | Lines are too long | 53 |
| [[NC010](#nc010---file-is-missing-natspec-comments)] | File is missing NatSpec comments | 4 |
| [[NC011](#nc011---function-declarations-should-have-natspec-descriptions)] | Function declarations should have NatSpec descriptions | 36 |
| [[NC012](#nc012---contract-declarations-should-have-notice-tags)] | Contract declarations should have `@notice` tags | 10 |
| [[NC013](#nc013---invalid-natspec-comment-style)] | Invalid NatSpec comment style | 93 |
| [[NC014](#nc014---inconsistent-spacing-in-comments)] | Inconsistent spacing in comments | 2 |
| [[NC015](#nc015---not-using-the-named-return-variables-anywhere-in-the-function-is-confusing)] | Not using the named return variables anywhere in the function is confusing | 15 |
| [[NC016](#nc016---contracts-should-have-full-test-coverage)] | Contracts should have full test coverage | 1 |
| [[NC017](#nc017---large-or-complicated-code-bases-should-implement-invariant-tests)] | Large or complicated code bases should implement invariant tests | 1 |
| [[NC018](#nc018---consider-using-blocknumber-instead-of-blocktimestamp)] | Consider using `block.number` instead of `block.timestamp` | 6 |
| [[NC019](#nc019---consider-bounding-input-array-length)] | Consider bounding input array length | 2 |
| [[NC020](#nc020---variables-should-be-named-in-mixedcase-style)] | Variables should be named in mixedCase style | 46 |
| [[NC021](#nc021---function-names-should-use-lowercamelcase)] | Function names should use lowerCamelCase | 3 |
| [[NC022](#nc022---consider-adding-a-deny-list)] | Consider adding a deny-list | 4 |
| [[NC023](#nc023---events-are-missing-sender-information)] | Events are missing sender information | 1 |
| [[NC024](#nc024---zero-as-a-function-argument-should-have-a-descriptive-meaning)] | Zero as a function argument should have a descriptive meaning | 23 |
| [[NC025](#nc025---it-is-standard-for-all-external-and-public-functions-to-be-override-from-an-interface)] | It is standard for all external and public functions to be override from an interface | 12 |
| [[NC026](#nc026---consider-adding-formal-verification-proofs)] | Consider adding formal verification proofs | 1 |
| [[NC027](#nc027---setters-should-prevent-re-setting-of-the-same-value)] | Setters should prevent re-setting of the same value | 1 |
| [[NC028](#nc028---consider-splitting-long-calculations)] | Consider splitting long calculations | 6 |
| [[NC029](#nc029---high-cyclomatic-complexity)] | High cyclomatic complexity | 9 |
| [[NC030](#nc030---unused-import)] | Unused import | 11 |
| [[NC031](#nc031---unsafe-conversion-from-unsigned-to-signed-values)] | Unsafe conversion from unsigned to signed values | 2 |
| [[NC032](#nc032---style-guide-state-and-local-variables-should-be-named-using-lowercamelcase)] | Style guide: State and local variables should be named using lowerCamelCase | 82 |
| [[NC033](#nc033---function-definitions-should-have-natspec-dev-annotations)] | Function definitions should have NatSpec @dev annotations | 57 |
| [[NC034](#nc034---function-definitions-should-have-natspec-notice-annotations)] | Function definitions should have NatSpec @notice annotations | 55 |
| [[NC035](#nc035---interface-declarations-should-have-natspec-title-annotations)] | Interface declarations should have NatSpec @title annotations | 1 |
| [[NC036](#nc036---interface-declarations-should-have-natspec-author-annotations)] | Interface declarations should have NatSpec @author annotations | 1 |
| [[NC037](#nc037---interface-declarations-should-have-natspec-notice-annotations)] | Interface declarations should have NatSpec @notice annotations | 1 |
| [[NC038](#nc038---interface-declarations-should-have-natspec-dev-annotations)] | Interface declarations should have NatSpec @dev annotations | 1 |
| [[NC039](#nc039---library-declarations-should-have-natspec-title-annotations)] | Library declarations should have Natspec @title annotations | 5 |
| [[NC040](#nc040---library-declarations-should-have-natspec-author-annotations)] | Library declarations should have Natspec @author annotations | 6 |
| [[NC041](#nc041---library-declarations-should-have-natspec-notice-annotations)] | Library declarations should have Natspec @notice annotations | 5 |
| [[NC042](#nc042---library-declarations-should-have-natspec-dev-annotations)] | Library declarations should have Natspec @dev annotations | 6 |
| [[NC043](#nc043---contract-definitions-should-have-natspec-title-annotations)] | Contract definitions should have Natspec @title annotations | 4 |
| [[NC044](#nc044---contract-definitions-should-have-natspec-author-annotations)] | Contract definitions should have Natspec @author annotations | 4 |
| [[NC045](#nc045---contract-definitions-should-have-natspec-notice-annotations)] | Contract definitions should have Natspec @notice annotations | 4 |
| [[NC046](#nc046---contract-definitions-should-have-natspec-dev-annotations)] | Contract definitions should have Natspec @dev annotations | 4 |
| [[NC047](#nc047---state-variable-declarations-should-have-natspec-notice-annotations)] | State variable declarations should have Natspec @notice annotations | 3 |
| [[NC048](#nc048---state-variable-declarations-should-have-natspec-dev-annotations)] | State variable declarations should have Natspec @dev annotations | 3 |
| [[NC049](#nc049---functions-should-have-natspec-return-annotations)] | Functions should have Natspec @return annotations | 31 |
| [[NC050](#nc050---functions-should-have-natspec-param-annotations)] | Functions should have Natspec @param annotations | 54 |
| [[NC051](#nc051---missing-events-in-sensitive-functions)] | Missing events in sensitive functions | 1 |
| [[NC052](#nc052---unused-file)] | Unused file | 6 |
| [[NC053](#nc053---consider-only-defining-one-libraryinterfacecontract-per-sol-file)] | Consider only defining one library/interface/contract per sol file | 1 |
| [[NC054](#nc054---use-a-struct-to-encapsulate-multiple-function-parameters)] | Use a struct to encapsulate multiple function parameters | 14 |

## NC001 - The `nonReentrant` `modifier` should occur before all other modifiers:

This is a best-practice to protect against reentrancy in other modifiers.


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


47          function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48              external
49              isNotFrozen(asset)
50              nonReentrant
51              onlyValidShortRecord(asset, shorter, id)
52              returns (uint88, uint88)
53          {
54              if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
55              // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
56              if (shortHintArray.length > 10) revert Errors.TooManyHints();
57      
58              // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile
59              LibSRUtil.checkCancelShortOrder({
60                  asset: asset,
61                  initialStatus: s.shortRecords[asset][shorter][id].status,
62                  shortOrderId: shortOrderId,
63                  shortRecordId: id,
64                  shorter: shorter
65              });
66      
67              // @dev liquidate requires more up-to-date oraclePrice
68              LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);
69      
70              MTypes.PrimaryLiquidation memory m = _setLiquidationStruct(asset, shorter, id, shortOrderId);
71      
72              // @dev Can liquidate as long as CR is low enough
73              if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {
74                  // If CR is too high, check for recovery mode and violation to continue liquidation
75                  if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();
76              }
77      
78              // revert if no asks, or price too high
79              _checklowestSell(m);
80      
81              _performForcedBid(m, shortHintArray);
82      
83              _liquidationFeeHandler(m);
84      
85              _fullorPartialLiquidation(m);
86      
87              emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
88      
89              return (m.gasFee, m.ethFilled);
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47:90

```solidity
File: facets/RedemptionFacet.sol


56          function proposeRedemption(
57              address asset,
58              MTypes.ProposalInput[] calldata proposalInput,
59              uint88 redemptionAmount,
60              uint88 maxRedemptionFee
61          ) external isNotFrozen(asset) nonReentrant {
62              if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63              MTypes.ProposeRedemption memory p;
64              p.asset = asset;
65              STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66              uint256 minShortErc = LibAsset.minShortErc(p.asset);
67      
68              if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69      
70              if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71      
72              // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73              if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74      
75              p.oraclePrice = LibOracle.getPrice(p.asset);
76      
77              bytes memory slate;
78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }
142     
143             if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144     
145             // @dev SSTORE2 the entire proposalData after validating proposalInput
146             redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147             redeemerAssetUser.slateLength = p.redemptionCounter;
148             redeemerAssetUser.oraclePrice = p.oraclePrice;
149             redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150     
151             STypes.Asset storage Asset = s.asset[p.asset];
152             Asset.ercDebt -= p.totalAmountProposed;
153     
154             uint32 protocolTime = LibOrders.getOffsetTime();
155             redeemerAssetUser.timeProposed = protocolTime;
156             // @dev Calculate the dispute period
157             // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158     
159             /*
160             +-------+------------+
161             | CR(X) |  Hours(Y)  |
162             +-------+------------+
163             | 1.1   |     0      |
164             | 1.2   |    .333    |
165             | 1.3   |    .75     |
166             | 1.5   |    1.5     |
167             | 1.7   |     3      |
168             | 2.0   |     6      |
169             +-------+------------+
170     
171             Creating fixed points and interpolating between points on the graph without using exponentials
172             Using simple y = mx + b formula
173             
174             where x = currentCR - previousCR
175             m = (y2-y1)/(x2-x1)
176             b = previous fixed point (Y)
177             */
178     
179             uint256 m;
180     
181             if (p.currentCR > 1.7 ether) {
182                 m = uint256(3 ether).div(0.3 ether);
183                 redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184             } else if (p.currentCR > 1.5 ether) {
185                 m = uint256(1.5 ether).div(0.2 ether);
186                 redeemerAssetUser.timeToDispute =
187                     protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188             } else if (p.currentCR > 1.3 ether) {
189                 m = uint256(0.75 ether).div(0.2 ether);
190                 redeemerAssetUser.timeToDispute =
191                     protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192             } else if (p.currentCR > 1.2 ether) {
193                 m = uint256(0.417 ether).div(0.1 ether);
194                 redeemerAssetUser.timeToDispute =
195                     protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196             } else if (p.currentCR > 1.1 ether) {
197                 m = uint256(C.ONE_THIRD.div(0.1 ether));
198                 redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199             }
200     
201             redeemerAssetUser.oraclePrice = p.oraclePrice;
202             redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203     
204             uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205             if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206     
207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208             if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209             VaultUser.ethEscrowed -= redemptionFee;
210             emit Events.ProposeRedemption(p.asset, msg.sender);
211         }


224         function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225             external
226             isNotFrozen(asset)
227             nonReentrant
228         {
229             if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230             MTypes.DisputeRedemption memory d;
231             d.asset = asset;
232             d.redeemer = redeemer;
233     
234             STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236     
237             if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238     
239             MTypes.ProposalData[] memory decodedProposalData =
240                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241     
242             for (uint256 i = 0; i < decodedProposalData.length; i++) {
243                 if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244                     revert Errors.CannotDisputeWithRedeemerProposal();
245                 }
246             }
247     
248             STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249             // Match continue (skip) conditions in proposeRedemption()
250             uint256 minShortErc = LibAsset.minShortErc(d.asset);
251             if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252     
253             MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254             MTypes.ProposalData memory currentProposal;
255             STypes.Asset storage Asset = s.asset[d.asset];
256     
257             uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258     
259             if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260             {
261                 // @dev All proposals from the incorrectIndex onward will be removed
262                 // @dev Thus the proposer can only redeem a portion of their original slate
263                 for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264                     currentProposal = decodedProposalData[i];
265     
266                     STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267                     currentSR.collateral += currentProposal.colRedeemed;
268                     currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269     
270                     d.incorrectCollateral += currentProposal.colRedeemed;
271                     d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272                 }
273     
274                 s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275                 Asset.dethCollateral += d.incorrectCollateral;
276                 Asset.ercDebt += d.incorrectErcDebt;
277     
278                 // @dev Update the redeemer's SSTORE2Pointer
279                 if (incorrectIndex > 0) {
280                     redeemerAssetUser.slateLength = incorrectIndex;
281                 } else {
282                     // @dev this implies everything in the redeemer's proposal was incorrect
283                     delete redeemerAssetUser.SSTORE2Pointer;
284                     emit Events.DisputeRedemptionAll(d.asset, redeemer);
285                 }
286     
287                 // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288                 // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289                 uint256 penaltyPct = LibOrders.min(
290                     LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291                 );
292     
293                 uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294     
295                 // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296                 redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297                 s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298             } else {
299                 revert Errors.InvalidRedemptionDispute();
300             }
301         }


310         function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
311             uint256 vault = s.asset[asset].vault;
312             STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
313             STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
314             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
315             if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
316     
317             MTypes.ProposalData[] memory decodedProposalData =
318                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
319     
320             uint88 totalColRedeemed;
321             for (uint256 i = 0; i < decodedProposalData.length; i++) {
322                 MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323                 totalColRedeemed += currentProposal.colRedeemed;
324                 _claimRemainingCollateral({
325                     asset: asset,
326                     vault: vault,
327                     shorter: currentProposal.shorter,
328                     shortId: currentProposal.shortId
329                 });
330             }
331             redeemerVaultUser.ethEscrowed += totalColRedeemed;
332             delete redeemerAssetUser.SSTORE2Pointer;
333             emit Events.ClaimRedemption(asset, msg.sender);
334         }


347         function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
348             external
349             isNotFrozen(asset)
350             nonReentrant
351         {
352             STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];
353             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
354             if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();
355     
356             // @dev Only need to read up to the position of the SR to be claimed
357             MTypes.ProposalData[] memory decodedProposalData =
358                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
359             MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];
360     
361             if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
362     
363             STypes.Asset storage Asset = s.asset[asset];
364             _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
365         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347:365

```solidity
File: facets/ShortOrdersFacet.sol


35          function createLimitShort(
36              address asset,
37              uint80 price,
38              uint88 ercAmount,
39              MTypes.OrderHint[] memory orderHintArray,
40              uint16[] memory shortHintArray,
41              uint16 shortOrderCR
42          ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43              MTypes.CreateLimitShortParam memory p;
44              STypes.Asset storage Asset = s.asset[asset];
45              STypes.Order memory incomingShort;
46      
47              // @dev create "empty" SR. Fail early.
48              incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49      
50              uint256 cr = LibOrders.convertCR(shortOrderCR);
51              if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52                  revert Errors.InvalidCR();
53              }
54      
55              // @dev minShortErc needs to be modified (bigger) when cr < 1
56              p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57              p.eth = price.mul(ercAmount);
58              p.minAskEth = LibAsset.minAskEth(asset);
59              if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60      
61              // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62              if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63      
64              incomingShort.addr = msg.sender;
65              incomingShort.price = price;
66              incomingShort.ercAmount = ercAmount;
67              incomingShort.id = Asset.orderIdCounter;
68              incomingShort.orderType = O.LimitShort;
69              incomingShort.creationTime = LibOrders.getOffsetTime();
70              incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71      
72              p.startingId = s.bids[asset][C.HEAD].nextId;
73              STypes.Order storage highestBid = s.bids[asset][p.startingId];
74              // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75              if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76                  LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77              }
78      
79              p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80              if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81                  revert Errors.BelowRecoveryModeCR();
82              }
83      
84              // @dev reading spot oracle price
85              if (incomingShort.price < p.oraclePrice) {
86                  LibOrders.addShort(asset, incomingShort, orderHintArray);
87              } else {
88                  LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89              }
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35:90

</details>


## NC002 - Imports could be organized more systematically:

This issue arises when the contract's interface is not imported first, followed by each of the interfaces it uses, followed by all other files.


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


6       import {IBridge} from "contracts/interfaces/IBridge.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L6:6

```solidity
File: facets/PrimaryLiquidationFacet.sol


6       import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L6:6

```solidity
File: libraries/LibOracle.sol


8       import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L8:8

```solidity
File: libraries/LibOrders.sol


6       import {IDiamond} from "interfaces/IDiamond.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L6:6

</details>

## NC003 - Constants in comparisons should appear on the left side:

This issue arises when constants in comparisons appear on the right side, which can lead to typo bugs.


<details>
<summary>Click to show 41 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


102             if (dethAmount == 0) revert Errors.ParameterIsZero();


109                 if (dethAssessable > 0) {


111                     if (withdrawalFeePct > 0) {


134             if (dethAmount == 0) revert Errors.ParameterIsZero();


164                 if (vault == 0) revert Errors.InvalidBridge();


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L164:164

```solidity
File: facets/PrimaryLiquidationFacet.sol


56              if (shortHintArray.length > 10) revert Errors.TooManyHints();


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L56:56

```solidity
File: facets/RedemptionFacet.sol


181             if (p.currentCR > 1.7 ether) {


184             } else if (p.currentCR > 1.5 ether) {


188             } else if (p.currentCR > 1.3 ether) {


192             } else if (p.currentCR > 1.2 ether) {


196             } else if (p.currentCR > 1.1 ether) {


279                 if (incorrectIndex > 0) {


371             if (shortRecord.ercDebt == 0 && shortRecord.status == SR.FullyFilled) {


397             assert(newBaseRate > 0); // Base rate is always non-zero after redemption


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L397:397

```solidity
File: facets/ShortOrdersFacet.sol


56              p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L56:56

```solidity
File: libraries/LibBytes.sol


14              require(slate.length % 51 == 0, "Invalid data length");


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L14:14

```solidity
File: libraries/LibOracle.sol


30                      uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;


60                      if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();


76              bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0


80              bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;


89                      if (twapPrice == 0) {


104                         if (wethBal < 100 ether) {


125             bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0


126                 || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;


134             if (twapPrice == 0) revert Errors.InvalidTwapPrice();


139             if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();


169             if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169:169

```solidity
File: libraries/LibOrders.sol


371             if (hintId == 0 || nextId == 0) {


501             if (b.matchedAskId != 0) {


505             if (b.matchedShortId != 0) {


576                     if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {


677             SR status = incomingShort.ercAmount == 0 ? SR.FullyFilled : SR.PartialFill;


792                 orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;


794                 orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;


805             if (timeDiff >= 15 minutes) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L805:805

```solidity
File: libraries/LibSRUtil.sol


35              if (yield > 0) {


113                 if (Asset.ercDebt > 0) {


131             if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();


158             if (ercDebt > 0) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L158:158

```solidity
File: libraries/UniswapOracleLibrary.sol


52              if (secondsAgo <= 0) revert Errors.InvalidTWAPSecondsAgo();


65              if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L65:65

</details>

## NC004 - else-block not required:

One level of nesting can be removed by not having an else block when the if-block returns


<details>
<summary>Click to show 32 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


173             if (dethTotalNew >= dethTotal) {
174                 // when yield is positive 1 deth = 1 eth
175                 return amount;
176             } else {
177                 // negative yield means 1 deth < 1 eth
178                 // @dev don't use mulU88 in rare case of overflow
179                 return amount.mul(dethTotalNew).divU88(dethTotal);
180             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L173:180

```solidity
File: facets/RedemptionFacet.sol


38              if (shortRecord.status == SR.Closed || shortRecord.ercDebt < minShortErc || proposer == shorter) {
39                  return false;
40              } else {
41                  return true;
42              }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L38:42

```solidity
File: libraries/LibBridgeRouter.sol


48              if (bridgePointer == VAULT.BRIDGE_RETH) {
49                  // Withdraw RETH
50                  creditReth = VaultUser.bridgeCreditReth;
51                  if (creditReth >= amount) {
52                      VaultUser.bridgeCreditReth -= amount;
53                      return 0;
54                  }
55      
56                  VaultUser.bridgeCreditReth = 0;
57                  amount -= creditReth;
58                  creditSteth = VaultUser.bridgeCreditSteth;
59                  if (creditSteth < C.ROUNDING_ZERO) {
60                      // Valid withdraw when no STETH credits
61                      return amount;
62                  } else {
63                      if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64                          // Can withdraw RETH using STETH credit when STETH bridge is empty
65                          if (creditSteth >= amount) {
66                              VaultUser.bridgeCreditSteth -= amount;
67                              return 0;
68                          } else {
69                              VaultUser.bridgeCreditSteth = 0;
70                              return amount - creditSteth;
71                          }
72                      } else {
73                          // Must use available bridge credits on withdrawal
74                          // @dev Prevents abusing bridge for arbitrage
75                          revert Errors.MustUseExistingBridgeCredit();
76                      }
77                  }
78              } else {
79                  // Withdraw STETH
80                  creditSteth = VaultUser.bridgeCreditSteth;
81                  if (creditSteth >= amount) {
82                      VaultUser.bridgeCreditSteth -= amount;
83                      return 0;
84                  }
85      
86                  VaultUser.bridgeCreditSteth = 0;
87                  amount -= creditSteth;
88                  creditReth = VaultUser.bridgeCreditReth;
89                  if (creditReth < C.ROUNDING_ZERO) {
90                      // Valid withdraw when no RETH credits
91                      return amount;
92                  } else {
93                      if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94                          // Can withdraw STETH using RETH credit when RETH bridge is empty
95                          if (creditReth >= amount) {
96                              VaultUser.bridgeCreditReth -= amount;
97                              return 0;
98                          } else {
99                              VaultUser.bridgeCreditReth = 0;
100                             return amount - creditReth;
101                         }
102                     } else {
103                         // Must use available bridge credits on withdrawal
104                         // @dev Prevents abusing bridge for arbitrage
105                         revert Errors.MustUseExistingBridgeCredit();
106                     }
107                 }
108             }


59                  if (creditSteth < C.ROUNDING_ZERO) {
60                      // Valid withdraw when no STETH credits
61                      return amount;
62                  } else {
63                      if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64                          // Can withdraw RETH using STETH credit when STETH bridge is empty
65                          if (creditSteth >= amount) {
66                              VaultUser.bridgeCreditSteth -= amount;
67                              return 0;
68                          } else {
69                              VaultUser.bridgeCreditSteth = 0;
70                              return amount - creditSteth;
71                          }
72                      } else {
73                          // Must use available bridge credits on withdrawal
74                          // @dev Prevents abusing bridge for arbitrage
75                          revert Errors.MustUseExistingBridgeCredit();
76                      }
77                  }


63                      if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64                          // Can withdraw RETH using STETH credit when STETH bridge is empty
65                          if (creditSteth >= amount) {
66                              VaultUser.bridgeCreditSteth -= amount;
67                              return 0;
68                          } else {
69                              VaultUser.bridgeCreditSteth = 0;
70                              return amount - creditSteth;
71                          }
72                      } else {
73                          // Must use available bridge credits on withdrawal
74                          // @dev Prevents abusing bridge for arbitrage
75                          revert Errors.MustUseExistingBridgeCredit();
76                      }


65                          if (creditSteth >= amount) {
66                              VaultUser.bridgeCreditSteth -= amount;
67                              return 0;
68                          } else {
69                              VaultUser.bridgeCreditSteth = 0;
70                              return amount - creditSteth;
71                          }


89                  if (creditReth < C.ROUNDING_ZERO) {
90                      // Valid withdraw when no RETH credits
91                      return amount;
92                  } else {
93                      if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94                          // Can withdraw STETH using RETH credit when RETH bridge is empty
95                          if (creditReth >= amount) {
96                              VaultUser.bridgeCreditReth -= amount;
97                              return 0;
98                          } else {
99                              VaultUser.bridgeCreditReth = 0;
100                             return amount - creditReth;
101                         }
102                     } else {
103                         // Must use available bridge credits on withdrawal
104                         // @dev Prevents abusing bridge for arbitrage
105                         revert Errors.MustUseExistingBridgeCredit();
106                     }
107                 }


93                      if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94                          // Can withdraw STETH using RETH credit when RETH bridge is empty
95                          if (creditReth >= amount) {
96                              VaultUser.bridgeCreditReth -= amount;
97                              return 0;
98                          } else {
99                              VaultUser.bridgeCreditReth = 0;
100                             return amount - creditReth;
101                         }
102                     } else {
103                         // Must use available bridge credits on withdrawal
104                         // @dev Prevents abusing bridge for arbitrage
105                         revert Errors.MustUseExistingBridgeCredit();
106                     }


95                          if (creditReth >= amount) {
96                              VaultUser.bridgeCreditReth -= amount;
97                              return 0;
98                          } else {
99                              VaultUser.bridgeCreditReth = 0;
100                             return amount - creditReth;
101                         }


125             if (factorReth > factorSteth) {
126                 // rETH market premium relative to stETH
127                 if (bridgePointer == VAULT.BRIDGE_RETH) {
128                     // Only charge fee if withdrawing rETH
129                     return factorReth.div(factorSteth) - 1 ether;
130                 }
131             } else if (factorSteth > factorReth) {
132                 // stETH market premium relative to rETH
133                 if (bridgePointer == VAULT.BRIDGE_STETH) {
134                     // Only charge fee if withdrawing stETH
135                     return factorSteth.div(factorReth) - 1 ether;
136                 }
137             } else {
138                 // Withdrawing less premium LST or premiums are equivalent
139                 return 0;
140             }


131             } else if (factorSteth > factorReth) {
132                 // stETH market premium relative to rETH
133                 if (bridgePointer == VAULT.BRIDGE_STETH) {
134                     // Only charge fee if withdrawing stETH
135                     return factorSteth.div(factorReth) - 1 ether;
136                 }
137             } else {
138                 // Withdrawing less premium LST or premiums are equivalent
139                 return 0;
140             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L131:140

```solidity
File: libraries/LibOracle.sol


28                  if (oracle == baseOracle) {
29                      // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
30                      uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;
31                      basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
32                      return basePriceInEth;
33                  } else {
34                      // prettier-ignore
35                      (
36                          uint80 roundID,
37                          int256 price,
38                          /*uint256 startedAt*/
39                          ,
40                          uint256 timeStamp,
41                          /*uint80 answeredInRound*/
42                      ) = oracle.latestRoundData();
43                      uint256 priceInEth = uint256(price).div(uint256(basePrice));
44                      oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp);
45                      return priceInEth;
46                  }


48                  if (oracle == baseOracle) {
49                      return twapCircuitBreaker();
50                  } else {
51                      // prettier-ignore
52                      (
53                          uint80 roundID,
54                          int256 price,
55                          /*uint256 startedAt*/
56                          ,
57                          uint256 timeStamp,
58                          /*uint80 answeredInRound*/
59                      ) = oracle.latestRoundData();
60                      if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();
61      
62                      uint256 twapInv = twapCircuitBreaker();
63                      uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv);
64                      return priceInEth;
65                  }


83              if (invalidFetchData) {
84                  return twapCircuitBreaker();
85              } else if (priceDeviation) {
86                  // Check valid twap price
87                  try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
88                  {
89                      if (twapPrice == 0) {
90                          return chainlinkPriceInEth;
91                      }
92      
93                      uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
94                      uint256 twapPriceInEth = twapPriceNormalized.inv();
95                      uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
96      
97                      // Save the price that is closest to saved oracle price
98                      if (chainlinkDiff <= twapDiff) {
99                          return chainlinkPriceInEth;
100                     } else {
101                         // Check valid twap liquidity
102                         IERC20 weth = IERC20(C.WETH);
103                         uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104                         if (wethBal < 100 ether) {
105                             return chainlinkPriceInEth;
106                         }
107                         return twapPriceInEth;
108                     }
109                 } catch {
110                     return chainlinkPriceInEth;
111                 }
112             } else {
113                 return chainlinkPriceInEth;
114             }


85              } else if (priceDeviation) {
86                  // Check valid twap price
87                  try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
88                  {
89                      if (twapPrice == 0) {
90                          return chainlinkPriceInEth;
91                      }
92      
93                      uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
94                      uint256 twapPriceInEth = twapPriceNormalized.inv();
95                      uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
96      
97                      // Save the price that is closest to saved oracle price
98                      if (chainlinkDiff <= twapDiff) {
99                          return chainlinkPriceInEth;
100                     } else {
101                         // Check valid twap liquidity
102                         IERC20 weth = IERC20(C.WETH);
103                         uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104                         if (wethBal < 100 ether) {
105                             return chainlinkPriceInEth;
106                         }
107                         return twapPriceInEth;
108                     }
109                 } catch {
110                     return chainlinkPriceInEth;
111                 }
112             } else {
113                 return chainlinkPriceInEth;
114             }


98                      if (chainlinkDiff <= twapDiff) {
99                          return chainlinkPriceInEth;
100                     } else {
101                         // Check valid twap liquidity
102                         IERC20 weth = IERC20(C.WETH);
103                         uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104                         if (wethBal < 100 ether) {
105                             return chainlinkPriceInEth;
106                         }
107                         return twapPriceInEth;
108                     }


169             if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
170                 return getPrice(asset);
171             } else {
172                 return getOraclePrice(asset);
173             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L169:173

```solidity
File: libraries/LibOrders.sol


241             if (check1 && check2) {
242                 return C.EXACT;
243             } else if (!check1) {
244                 return C.PREV;
245             } else if (!check2) {
246                 return C.NEXT;
247             }


243             } else if (!check1) {
244                 return C.PREV;
245             } else if (!check2) {
246                 return C.NEXT;
247             }


272             if (check1 && check2) {
273                 return C.EXACT;
274             } else if (!check1) {
275                 return C.PREV;
276             } else if (!check2) {
277                 return C.NEXT;
278             }


274             } else if (!check1) {
275                 return C.PREV;
276             } else if (!check2) {
277                 return C.NEXT;
278             }


381             if (direction == C.EXACT) {
382                 return hintId;
383             } else if (direction == C.NEXT) {
384                 return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
385             } else {
386                 uint16 prevId = orders[asset][hintId].prevId;
387                 return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);
388             }


383             } else if (direction == C.NEXT) {
384                 return getOrderId(orders, asset, C.NEXT, nextId, incomingOrder.price, incomingOrder.orderType);
385             } else {
386                 uint16 prevId = orders[asset][hintId].prevId;
387                 return getOrderId(orders, asset, C.PREV, prevId, incomingOrder.price, incomingOrder.orderType);
388             }


412             if (orderType == O.LimitAsk || orderType == O.LimitShort) {
413                 return verifySellId(orders, asset, prevId, newPrice, nextId);
414             } else if (orderType == O.LimitBid) {
415                 return verifyBidId(asset, prevId, newPrice, nextId);
416             }


421             if (o == O.LimitBid || o == O.MarketBid) {
422                 return O.LimitBid;
423             } else if (o == O.LimitAsk || o == O.MarketAsk) {
424                 return O.LimitAsk;
425             } else if (o == O.LimitShort) {
426                 return O.LimitShort;
427             }


423             } else if (o == O.LimitAsk || o == O.MarketAsk) {
424                 return O.LimitAsk;
425             } else if (o == O.LimitShort) {
426                 return O.LimitShort;
427             }


574                 if (incomingAsk.price <= highestBid.price) {
575                     // Consider ask filled if only dust amount left
576                     if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578                         incomingAsk.ercAmount = 0;
579                         matchIncomingSell(asset, incomingAsk, matchTotal);
580                         return;
581                     }
582                     matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
583                     if (incomingAsk.ercAmount > highestBid.ercAmount) {
584                         incomingAsk.ercAmount -= highestBid.ercAmount;
585                         highestBid.ercAmount = 0;
586                         matchOrder(s.bids, asset, highestBid.id);
587     
588                         // loop
589                         startingId = highestBid.nextId;
590                         if (startingId == C.TAIL) {
591                             matchIncomingSell(asset, incomingAsk, matchTotal);
592     
593                             if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594                                 addSellOrder(incomingAsk, asset, orderHintArray);
595                             }
596                             s.bids[asset][C.HEAD].nextId = C.TAIL;
597                             return;
598                         }
599                     } else {
600                         if (incomingAsk.ercAmount == highestBid.ercAmount) {
601                             matchOrder(s.bids, asset, highestBid.id);
602                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603                         } else {
604                             highestBid.ercAmount -= incomingAsk.ercAmount;
605                             s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607                             // Check reduced dust threshold for existing limit orders
608                             if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609                                 cancelBid(asset, highestBid.id);
610                             }
611                         }
612                         incomingAsk.ercAmount = 0;
613                         matchIncomingSell(asset, incomingAsk, matchTotal);
614                         return;
615                     }
616                 } else {
617                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
618                     matchIncomingSell(asset, incomingAsk, matchTotal);
619     
620                     if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621                         addSellOrder(incomingAsk, asset, orderHintArray);
622                     }
623                     return;
624                 }


583                     if (incomingAsk.ercAmount > highestBid.ercAmount) {
584                         incomingAsk.ercAmount -= highestBid.ercAmount;
585                         highestBid.ercAmount = 0;
586                         matchOrder(s.bids, asset, highestBid.id);
587     
588                         // loop
589                         startingId = highestBid.nextId;
590                         if (startingId == C.TAIL) {
591                             matchIncomingSell(asset, incomingAsk, matchTotal);
592     
593                             if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594                                 addSellOrder(incomingAsk, asset, orderHintArray);
595                             }
596                             s.bids[asset][C.HEAD].nextId = C.TAIL;
597                             return;
598                         }
599                     } else {
600                         if (incomingAsk.ercAmount == highestBid.ercAmount) {
601                             matchOrder(s.bids, asset, highestBid.id);
602                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603                         } else {
604                             highestBid.ercAmount -= incomingAsk.ercAmount;
605                             s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607                             // Check reduced dust threshold for existing limit orders
608                             if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609                                 cancelBid(asset, highestBid.id);
610                             }
611                         }
612                         incomingAsk.ercAmount = 0;
613                         matchIncomingSell(asset, incomingAsk, matchTotal);
614                         return;
615                     }


765                     if (isExactStartingShort) {
766                         Asset.startingShortId = shortHintId;
767                         return;
768                     } else if (startingShortWithinOracleRange) {
769                         // @dev prevShortPrice >= oraclePrice
770                         Asset.startingShortId = prevId;
771                         return;
772                     } else if (allShortUnderOraclePrice) {
773                         Asset.startingShortId = C.HEAD;
774                         return;
775                     }


768                     } else if (startingShortWithinOracleRange) {
769                         // @dev prevShortPrice >= oraclePrice
770                         Asset.startingShortId = prevId;
771                         return;
772                     } else if (allShortUnderOraclePrice) {
773                         Asset.startingShortId = C.HEAD;
774                         return;
775                     }


838                 } else if (order.creationTime == orderHint.creationTime) {
839                     return orderHint.hintId;
840                 } else if (!anyOrderHintPrevMatched && order.prevOrderType == O.Matched) {
841                     anyOrderHintPrevMatched = true;
842                 }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L838:842

```solidity
File: libraries/LibSRUtil.sol


59                  if (shorter == msg.sender) {
60                      // If call comes from exitShort() or combineShorts() then always cancel
61                      LibOrders.cancelShort(asset, shortOrderId);
62                      assert(shortRecord.status != SR.PartialFill);
63                      return true;
64                  } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
65                      // If call comes from liquidate() and SR ercDebt under minShortErc
66                      LibOrders.cancelShort(asset, shortOrderId);
67                      return true;
68                  }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L59:68

</details>

## NC005 - If-statement can be converted to a ternary:

The code can be made more compact while also increasing readability by converting the following if-statements to ternaries (e.g. foo += (x > y) ? a : b)


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: libraries/LibOrders.sol


90              if (order.price > s.bids[asset][nextId].price || nextId == C.TAIL) {
91                  hintId = C.HEAD;
92              } else {
93                  hintId = findOrderHintId(s.bids, asset, orderHintArray);
94              }


111             if (order.price < s.asks[asset][nextId].price || nextId == C.TAIL) {
112                 hintId = C.HEAD;
113             } else {
114                 hintId = findOrderHintId(s.asks, asset, orderHintArray);
115             }


132             if (order.price < s.shorts[asset][nextId].price || nextId == C.TAIL) {
133                 hintId = C.HEAD;
134             } else {
135                 hintId = findOrderHintId(s.shorts, asset, orderHintArray);
136             }


791             if (incomingOrder.price >= savedPrice) {
792                 orderPriceGtThreshold = (incomingOrder.price - savedPrice).div(savedPrice) > 0.005 ether;
793             } else {
794                 orderPriceGtThreshold = (savedPrice - incomingOrder.price).div(savedPrice) > 0.005 ether;
795             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L791:795

</details>


## NC006 - Variable names that consist of all capital letters should be reserved for constant/immutable variables:

If the variable needs to be different based on which class it comes from, a view/pure function should be used instead.


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


165             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


211             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


241             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241:241

```solidity
File: libraries/LibBytes.sol


24                  uint64 CR; // bytes8


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24:24

</details>

## NC007 - Consider using delete rather than assigning false/zero to clear values:

The `delete` keyword more closely matches the semantics of what is being done, and draws more attention to the changing of state, which may lead to a more thorough audit of its associated logic.


<details>
<summary>Click to show 14 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


56                  VaultUser.bridgeCreditReth = 0;


69                              VaultUser.bridgeCreditSteth = 0;


86                  VaultUser.bridgeCreditSteth = 0;


99                              VaultUser.bridgeCreditReth = 0;


167                         VaultUserFrom.bridgeCreditReth = 0;


176                         VaultUserFrom.bridgeCreditSteth = 0;


188                         VaultUserFrom.bridgeCreditReth = 0;


189                         VaultUserFrom.bridgeCreditSteth = 0;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L189:189

```solidity
File: libraries/LibOrders.sol


578                         incomingAsk.ercAmount = 0;


585                         highestBid.ercAmount = 0;


612                         incomingAsk.ercAmount = 0;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L612:612

```solidity
File: libraries/LibSRUtil.sol


138             short.tokenId = 0;


148             nft.shortOrderId = 0;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L148:148

```solidity
File: libraries/UniswapOracleLibrary.sol


56              secondsAgos[1] = 0;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L56:56

</details>

## NC008 - Variable names for `immutable`s should use CONSTANT_CASE:

For `immutable` variable names, each word should use all capital letters, with underscores separating each word (CONSTANT_CASE).


```solidity
File: facets/BridgeRouterFacet.sol


26          address private immutable rethBridge;


27          address private immutable stethBridge;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27:27

```solidity
File: facets/PrimaryLiquidationFacet.sol


28          address private immutable dusd;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28:28

## NC009 - Lines are too long:

Usually lines in source code are limited to 80 characters. Today's screens are much larger so it's reasonable to stretch this in some cases. The solidity style guide recommends a maximumum line length of 120 characters, so the lines below should be split when they reach that length.

Note: these are missed from bots
<details>
<summary>Click to show 53 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


// @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L147:147

```solidity
File: facets/PrimaryLiquidationFacet.sol

IDiamond(payable(address(this))).createForcedBid(address(this), m.asset, _bidPrice, m.short.ercDebt, shortHintArray);

LibSRUtil.disburseCollateral(m.asset, m.shorter, m.short.collateral, m.short.dethYieldRate, m.short.updatedAt);

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L246:246

```solidity
File: facets/RedemptionFacet.sol


function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)

// @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount

if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();

LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);

redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);

function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)

if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)

STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];

LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L290:290

```solidity
File: facets/ShortOrdersFacet.sol


p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);

LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L76:76

```solidity
File: libraries/LibBridgeRouter.sol


function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {

uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122:122

```solidity
File: libraries/LibBytes.sol


function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {

colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L42:42

```solidity
File: libraries/LibOracle.sol


try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {

basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);

chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;

try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)

uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L95:95

```solidity
File: libraries/LibOrders.sol


function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {

function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {

emit Events.CreateOrder(asset, incomingOrder.addr, incomingOrder.orderType, incomingOrder.id, incomingOrder.ercAmount);

function cancelOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

function matchOrder(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset, uint16 id) internal {

* @dev Instead of canceling each one, just wait till the last match and only swap prevId/nextId there, since the rest are gone

function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {

function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {

matchTotal.colUsed += incomingSell.price.mulU88(fillErc).mulU88(LibOrders.convertCR(incomingSell.shortOrderCR));

if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {

bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;

// @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)

// @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough

uint88 collateralDiff = shortOrder.price.mulU88(debtDiff).mulU88(LibOrders.convertCR(shortOrder.shortOrderCR));

// Approximates the match price compared to the oracle price and accounts for any discount by increasing dethTithePercent

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L954:954

```solidity
File: libraries/LibSRUtil.sol


function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)

@dev If somebody exits a short, gets liquidated, decreases their collateral before YIELD_DELAY_SECONDS duration is up,

function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)

if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L84:84

```solidity
File: libraries/UniswapOracleLibrary.sol


// https://github.com/Uniswap/v3-periphery/blob/b325bb0905d922ae61fcc7df85ee802e8df5e96c/contracts/libraries/OracleLibrary.sol

baseToken < quoteToken ? U256.mulDiv(ratioX192, baseAmount, 1 << 192) : U256.mulDiv(1 << 192, baseAmount, ratioX192);

baseToken < quoteToken ? U256.mulDiv(ratioX128, baseAmount, 1 << 128) : U256.mulDiv(1 << 128, baseAmount, ratioX128);

// @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp

```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L58:58

</details>

## NC010 - File is missing NatSpec comments:

The file does not contain any of the NatSpec comments (@inheritdoc, @param, @return, @notice), which are important for documentation and user confirmation.


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


// SPDX-License-Identifier: GPL-3.0-only
pragma solidity 0.8.21;

import {IBridge} from "contracts/interfaces/IBridge.sol";

import {STypes} from "contracts/libraries/DataTypes.sol";
import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
import {OracleLibrary} from "contracts/libraries/UniswapOracleLibrary.sol";
import {C, VAULT} from "contracts/libraries/Constants.sol";
import {Errors} from "contracts/libraries/Errors.sol";

import {U256, U88} from "contracts/libraries/PRBMathHelper.sol";

// import {console} from "contracts/libraries/console.sol";

library LibBridgeRouter {
    using U256 for uint256;
    using U88 for uint88;

    // Credit user account with dETH and bridge credit if applicable
    function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {
        AppStorage storage s = appStorage();
        STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];

        if (vault == VAULT.ONE) {
            // Only VAULT.ONE has mixed LST
            if (bridgePointer == VAULT.BRIDGE_RETH) {
                VaultUser.bridgeCreditReth += amount;
            } else {
                VaultUser.bridgeCreditSteth += amount;
            }
        }

        VaultUser.ethEscrowed += amount;
        s.vault[vault].dethTotal += amount;
    }

    // Determine how much dETH is NOT covered by bridge credits during withdrawal
    function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
        internal
        returns (uint88)
    {
        AppStorage storage s = appStorage();
        STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];

        uint88 creditReth;
        uint88 creditSteth;
        if (bridgePointer == VAULT.BRIDGE_RETH) {
            // Withdraw RETH
            creditReth = VaultUser.bridgeCreditReth;
            if (creditReth >= amount) {
                VaultUser.bridgeCreditReth -= amount;
                return 0;
            }

            VaultUser.bridgeCreditReth = 0;
            amount -= creditReth;
            creditSteth = VaultUser.bridgeCreditSteth;
            if (creditSteth < C.ROUNDING_ZERO) {
                // Valid withdraw when no STETH credits
                return amount;
            } else {
                if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    // Can withdraw RETH using STETH credit when STETH bridge is empty
                    if (creditSteth >= amount) {
                        VaultUser.bridgeCreditSteth -= amount;
                        return 0;
                    } else {
                        VaultUser.bridgeCreditSteth = 0;
                        return amount - creditSteth;
                    }
                } else {
                    // Must use available bridge credits on withdrawal
                    // @dev Prevents abusing bridge for arbitrage
                    revert Errors.MustUseExistingBridgeCredit();
                }
            }
        } else {
            // Withdraw STETH
            creditSteth = VaultUser.bridgeCreditSteth;
            if (creditSteth >= amount) {
                VaultUser.bridgeCreditSteth -= amount;
                return 0;
            }

            VaultUser.bridgeCreditSteth = 0;
            amount -= creditSteth;
            creditReth = VaultUser.bridgeCreditReth;
            if (creditReth < C.ROUNDING_ZERO) {
                // Valid withdraw when no RETH credits
                return amount;
            } else {
                if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
                    // Can withdraw STETH using RETH credit when RETH bridge is empty
                    if (creditReth >= amount) {
                        VaultUser.bridgeCreditReth -= amount;
                        return 0;
                    } else {
                        VaultUser.bridgeCreditReth = 0;
                        return amount - creditReth;
                    }
                } else {
                    // Must use available bridge credits on withdrawal
                    // @dev Prevents abusing bridge for arbitrage
                    revert Errors.MustUseExistingBridgeCredit();
                }
            }
        }
    }

    // Bridge fees exist only to prevent free arbitrage, fee charged is the premium/discount differential
    // @dev Only applicable to VAULT.ONE which has mixed LST
    function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {
        IBridge bridgeReth = IBridge(rethBridge);
        IBridge bridgeSteth = IBridge(stethBridge);

        // Calculate rETH market premium/discount (factor)
        uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);
        uint256 unitRethOracle = bridgeReth.getUnitDethValue();
        uint256 factorReth = unitRethTWAP.div(unitRethOracle);
        // Calculate stETH market premium/discount (factor)
        uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);
        uint256 unitWstethOracle = bridgeSteth.getUnitDethValue();
        uint256 factorSteth = unitWstethTWAP.div(unitWstethOracle);
        if (factorReth > factorSteth) {
            // rETH market premium relative to stETH
            if (bridgePointer == VAULT.BRIDGE_RETH) {
                // Only charge fee if withdrawing rETH
                return factorReth.div(factorSteth) - 1 ether;
            }
        } else if (factorSteth > factorReth) {
            // stETH market premium relative to rETH
            if (bridgePointer == VAULT.BRIDGE_STETH) {
                // Only charge fee if withdrawing stETH
                return factorSteth.div(factorReth) - 1 ether;
            }
        } else {
            // Withdrawing less premium LST or premiums are equivalent
            return 0;
        }
    }

    // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system
    function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
        AppStorage storage s = appStorage();

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;

        if (vault == VAULT.ONE) {
            STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
            uint88 creditReth = VaultUserFrom.bridgeCreditReth;
            uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
            STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];

            if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                // No bridge credits
                return;
            }

            if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
                // Only creditReth
                if (creditReth > collateral) {
                    VaultUserFrom.bridgeCreditReth -= collateral;
                    VaultUserTo.bridgeCreditReth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserTo.bridgeCreditReth += creditReth;
                }
            } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
                // Only creditSteth
                if (creditSteth > collateral) {
                    VaultUserFrom.bridgeCreditSteth -= collateral;
                    VaultUserTo.bridgeCreditSteth += collateral;
                } else {
                    VaultUserFrom.bridgeCreditSteth = 0;
                    VaultUserTo.bridgeCreditSteth += creditSteth;
                }
            } else {
                // Both creditReth and creditSteth
                uint88 creditTotal = creditReth + creditSteth;
                if (creditTotal > collateral) {
                    creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
                    creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
                    VaultUserFrom.bridgeCreditReth -= creditReth;
                    VaultUserFrom.bridgeCreditSteth -= creditSteth;
                } else {
                    VaultUserFrom.bridgeCreditReth = 0;
                    VaultUserFrom.bridgeCreditSteth = 0;
                }
                VaultUserTo.bridgeCreditReth += creditReth;
                VaultUserTo.bridgeCreditSteth += creditSteth;
            }
        }
    }

    // Update user account upon dETH withdrawal
    function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {
        AppStorage storage s = appStorage();
        s.vaultUser[vault][msg.sender].ethEscrowed -= (amount + fee);
        s.vault[vault].dethTotal -= amount;
    }
}


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L1:1

```solidity
File: libraries/LibBytes.sol


// SPDX-License-Identifier: GPL-3.0-only
pragma solidity 0.8.21;

import {MTypes} from "contracts/libraries/DataTypes.sol";
import {SSTORE2} from "solmate/utils/SSTORE2.sol";

// import {console} from "contracts/libraries/console.sol";

library LibBytes {
    // Custom decode since SSTORE.write was written directly in proposeRedemption
    function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {
        bytes memory slate = SSTORE2.read(SSTORE2Pointer);
        // ProposalData is 51 bytes
        require(slate.length % 51 == 0, "Invalid data length");

        MTypes.ProposalData[] memory data = new MTypes.ProposalData[](slateLength);

        for (uint256 i = 0; i < slateLength; i++) {
            // 32 offset for array length, mulitply by each ProposalData
            uint256 offset = i * 51 + 32;

            address shorter; // bytes20
            uint8 shortId; // bytes1
            uint64 CR; // bytes8
            uint88 ercDebtRedeemed; // bytes11
            uint88 colRedeemed; // bytes11

            assembly {
                // mload works 32 bytes at a time
                let fullWord := mload(add(slate, offset))
                // read 20 bytes
                shorter := shr(96, fullWord) // 0x60 = 96 (256-160)
                // read 8 bytes
                shortId := and(0xff, shr(88, fullWord)) // 0x58 = 88 (96-8), mask of bytes1 = 0xff * 1
                // read 64 bytes
                CR := and(0xffffffffffffffff, shr(24, fullWord)) // 0x18 = 24 (88-64), mask of bytes8 = 0xff * 8

                fullWord := mload(add(slate, add(offset, 29))) // (29 offset)
                // read 88 bytes
                ercDebtRedeemed := shr(168, fullWord) // (256-88 = 168)
                // read 88 bytes
                colRedeemed := add(0xffffffffffffffffffffff, shr(80, fullWord)) // (256-88-88 = 80), mask of bytes11 = 0xff * 11
            }

            data[i] = MTypes.ProposalData({
                shorter: shorter,
                shortId: shortId,
                CR: CR,
                ercDebtRedeemed: ercDebtRedeemed,
                colRedeemed: colRedeemed
            });
        }

        return data;
    }
}


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1:1

```solidity
File: libraries/LibOracle.sol


// SPDX-License-Identifier: GPL-3.0-only
pragma solidity 0.8.21;

import {U256} from "contracts/libraries/PRBMathHelper.sol";

import {AggregatorV3Interface} from "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
import {IERC20} from "@openzeppelin/contracts/token/ERC20/IERC20.sol";
import {IDiamond} from "interfaces/IDiamond.sol";
import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
import {C} from "contracts/libraries/Constants.sol";
import {LibOrders} from "contracts/libraries/LibOrders.sol";
import {Errors} from "contracts/libraries/Errors.sol";

// import {console} from "contracts/libraries/console.sol";

library LibOracle {
    using U256 for uint256;

    function getOraclePrice(address asset) internal view returns (uint256) {
        AppStorage storage s = appStorage();
        AggregatorV3Interface baseOracle = AggregatorV3Interface(s.baseOracle);
        uint256 protocolPrice = getPrice(asset);

        AggregatorV3Interface oracle = AggregatorV3Interface(s.asset[asset].oracle);
        if (address(oracle) == address(0)) revert Errors.InvalidAsset();

        try baseOracle.latestRoundData() returns (uint80 baseRoundID, int256 basePrice, uint256, uint256 baseTimeStamp, uint80) {
            if (oracle == baseOracle) {
                // @dev multiply base oracle by 10**10 to give it 18 decimals of precision
                uint256 basePriceInEth = basePrice > 0 ? uint256(basePrice * C.BASE_ORACLE_DECIMALS).inv() : 0;
                basePriceInEth = baseOracleCircuitBreaker(protocolPrice, baseRoundID, basePrice, baseTimeStamp, basePriceInEth);
                return basePriceInEth;
            } else {
                // prettier-ignore
                (
                    uint80 roundID,
                    int256 price,
                    /*uint256 startedAt*/
                    ,
                    uint256 timeStamp,
                    /*uint80 answeredInRound*/
                ) = oracle.latestRoundData();
                uint256 priceInEth = uint256(price).div(uint256(basePrice));
                oracleCircuitBreaker(roundID, baseRoundID, price, basePrice, timeStamp, baseTimeStamp);
                return priceInEth;
            }
        } catch {
            if (oracle == baseOracle) {
                return twapCircuitBreaker();
            } else {
                // prettier-ignore
                (
                    uint80 roundID,
                    int256 price,
                    /*uint256 startedAt*/
                    ,
                    uint256 timeStamp,
                    /*uint80 answeredInRound*/
                ) = oracle.latestRoundData();
                if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();

                uint256 twapInv = twapCircuitBreaker();
                uint256 priceInEth = uint256(price * C.BASE_ORACLE_DECIMALS).mul(twapInv);
                return priceInEth;
            }
        }
    }

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
            try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
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

    function oracleCircuitBreaker(
        uint80 roundId,
        uint80 baseRoundId,
        int256 chainlinkPrice,
        int256 baseChainlinkPrice,
        uint256 timeStamp,
        uint256 baseTimeStamp
    ) private view {
        bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
            || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;

        if (invalidFetchData) revert Errors.InvalidPrice();
    }

    function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {
        // Check valid price
        uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes);
        if (twapPrice == 0) revert Errors.InvalidTwapPrice();

        // Check valid liquidity
        IERC20 weth = IERC20(C.WETH);
        uint256 wethBal = weth.balanceOf(C.USDC_WETH);
        if (wethBal < 100 ether) revert Errors.InsufficientEthInLiquidityPool();

        uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
        return twapPriceNormalized.inv();
    }

    /* 
    @dev C.HEAD to marks the start/end of the linked list, so the only properties needed are id/nextId/prevId.
    Helper methods are used to set the values of oraclePrice and oracleTime since they are set to different properties
    */
    function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {
        AppStorage storage s = appStorage();
        s.bids[asset][C.HEAD].ercAmount = uint80(oraclePrice);
        s.bids[asset][C.HEAD].creationTime = oracleTime;
    }

    // @dev Intentionally using creationTime for oracleTime.
    function getTime(address asset) internal view returns (uint256 creationTime) {
        AppStorage storage s = appStorage();
        return s.bids[asset][C.HEAD].creationTime;
    }

    // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.
    function getPrice(address asset) internal view returns (uint80 oraclePrice) {
        AppStorage storage s = appStorage();
        return uint80(s.bids[asset][C.HEAD].ercAmount);
    }

    // @dev Allows caller to save gas since reading spot price costs ~16K
    function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {
        if (LibOrders.getOffsetTime() - getTime(asset) < 15 minutes) {
            return getPrice(asset);
        } else {
            return getOraclePrice(asset);
        }
    }
}


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L1:1

```solidity
File: libraries/LibSRUtil.sol


// SPDX-License-Identifier: GPL-3.0-only
pragma solidity 0.8.21;

import {U88, U256} from "contracts/libraries/PRBMathHelper.sol";

import {STypes, SR} from "contracts/libraries/DataTypes.sol";
import {AppStorage, appStorage} from "contracts/libraries/AppStorage.sol";
import {C} from "contracts/libraries/Constants.sol";
import {LibOrders} from "contracts/libraries/LibOrders.sol";
import {LibShortRecord} from "contracts/libraries/LibShortRecord.sol";
import {LibAsset} from "contracts/libraries/LibAsset.sol";
import {Errors} from "contracts/libraries/Errors.sol";
import {LibBridgeRouter} from "contracts/libraries/LibBridgeRouter.sol";

// import {console} from "contracts/libraries/console.sol";

// extra ShortRecord helpers, similar to LibShortRecord
library LibSRUtil {
    using U88 for uint88;
    using U256 for uint256;

    function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
        internal
    {
        AppStorage storage s = appStorage();

        STypes.Asset storage Asset = s.asset[asset];
        uint256 vault = Asset.vault;
        STypes.Vault storage Vault = s.vault[vault];

        Vault.dethCollateral -= collateral;
        Asset.dethCollateral -= collateral;
        // Distribute yield
        uint88 yield = collateral.mulU88(Vault.dethYieldRate - dethYieldRate);
        if (yield > 0) {
            /*
            @dev If somebody exits a short, gets liquidated, decreases their collateral before YIELD_DELAY_SECONDS duration is up,
            they lose their yield to the TAPP
            */
            bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;
            if (isNotRecentlyModified) {
                s.vaultUser[vault][shorter].ethEscrowed += yield;
            } else {
                s.vaultUser[vault][address(this)].ethEscrowed += yield;
            }
        }
    }

    function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
        AppStorage storage s = appStorage();
        if (initialStatus == SR.PartialFill) {
            STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
            STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
            if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

            if (shorter == msg.sender) {
                // If call comes from exitShort() or combineShorts() then always cancel
                LibOrders.cancelShort(asset, shortOrderId);
                assert(shortRecord.status != SR.PartialFill);
                return true;
            } else if (shortRecord.ercDebt < LibAsset.minShortErc(asset)) {
                // If call comes from liquidate() and SR ercDebt under minShortErc
                LibOrders.cancelShort(asset, shortOrderId);
                return true;
            }
        }
    }

    function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
        internal
        returns (bool isCancelled)
    {
        AppStorage storage s = appStorage();

        STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortRecordId];
        uint256 minShortErc = LibAsset.minShortErc(asset);

        if (initialStatus == SR.PartialFill) {
            // Verify shortOrder
            STypes.Order storage shortOrder = s.shorts[asset][shortOrderId];
            if (shortOrder.shortRecordId != shortRecordId || shortOrder.addr != shorter) revert Errors.InvalidShortOrder();

            if (shortRecord.status == SR.Closed) {
                // Check remaining shortOrder
                if (shortOrder.ercAmount < minShortErc) {
                    // @dev The resulting SR will not have PartialFill status after cancel
                    LibOrders.cancelShort(asset, shortOrderId);
                    isCancelled = true;
                }
            } else {
                // Check remaining shortOrder and remaining shortRecord
                if (shortOrder.ercAmount + shortRecord.ercDebt < minShortErc) revert Errors.CannotLeaveDustAmount();
            }
        } else if (shortRecord.status != SR.Closed && shortRecord.ercDebt < minShortErc) {
            revert Errors.CannotLeaveDustAmount();
        }
    }

    function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)
        internal
        view
        returns (bool recoveryViolation)
    {
        AppStorage storage s = appStorage();

        uint256 recoveryCR = LibAsset.recoveryCR(asset);
        if (shortRecordCR < recoveryCR) {
            // Only check asset CR if low enough
            STypes.Asset storage Asset = s.asset[asset];
            if (Asset.ercDebt > 0) {
                // If Asset.ercDebt == 0 then assetCR is NA
                uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt));
                if (assetCR < recoveryCR) {
                    // Market is in recovery mode and shortRecord CR too low
                    return true;
                }
            }
        }
    }

    function transferShortRecord(address from, address to, uint40 tokenId) internal {
        AppStorage storage s = appStorage();

        STypes.NFT storage nft = s.nftMapping[tokenId];
        address asset = s.assetMapping[nft.assetId];
        STypes.ShortRecord storage short = s.shortRecords[asset][from][nft.shortRecordId];
        if (short.status == SR.Closed) revert Errors.OriginalShortRecordCancelled();
        if (short.ercDebt == 0) revert Errors.OriginalShortRecordRedeemed();

        // @dev shortOrderId is already validated in mintNFT
        if (short.status == SR.PartialFill) {
            LibOrders.cancelShort(asset, nft.shortOrderId);
        }

        short.tokenId = 0;
        LibShortRecord.deleteShortRecord(asset, from, nft.shortRecordId);
        LibBridgeRouter.transferBridgeCredit(asset, from, to, short.collateral);

        uint8 id = LibShortRecord.createShortRecord(
            asset, to, SR.FullyFilled, short.collateral, short.ercDebt, short.ercDebtRate, short.dethYieldRate, tokenId
        );

        nft.owner = to;
        nft.shortRecordId = id;
        nft.shortOrderId = 0;
    }

    function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
        AppStorage storage s = appStorage();

        // Distribute ercDebt
        uint64 ercDebtRate = s.asset[asset].ercDebtRate;
        uint88 ercDebt = short.ercDebt.mulU88(ercDebtRate - short.ercDebtRate);

        if (ercDebt > 0) {
            short.ercDebt += ercDebt;
            short.ercDebtRate = ercDebtRate;
        }
    }
}


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L1:1

</details>

## NC011 - Function declarations should have NatSpec descriptions:

Function declarations should be preceded by a NatSpec comment.


<details>
<summary>Click to show 36 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


29          constructor(address _rethBridge, address _stethBridge) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L29:29

```solidity
File: facets/PrimaryLiquidationFacet.sol


30          constructor(address _dusd) {


229         function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229:229

```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31:31

```solidity
File: libraries/LibBridgeRouter.sol


21          function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)


198         function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198:198

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


19          function getOraclePrice(address asset) internal view returns (uint256) {


69          function baseOracleCircuitBreaker(


117         function oracleCircuitBreaker(


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


149         function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149:149

```solidity
File: libraries/LibOrders.sol


35          function convertCR(uint16 cr) internal pure returns (uint256) {


40          function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {


55          function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)


78          function isShort(STypes.Order memory order) internal pure returns (bool) {


82          function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


103         function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


628         function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {


810         function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {


826         function findOrderHintId(


854         function cancelBid(address asset, uint16 id) internal {


868         function cancelAsk(address asset, uint16 id) internal {


882         function cancelShort(address asset, uint16 id) internal {


955         function handlePriceDiscount(address asset, uint80 price) internal {


985         function min(uint256 a, uint256 b) internal pure returns (uint256) {


989         function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989:989

```solidity
File: libraries/LibSRUtil.sol


22          function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


124         function transferShortRecord(address from, address to, uint40 tokenId) internal {


151         function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151:151

```solidity
File: libraries/UniswapOracleLibrary.sol


11          function observe(uint32[] calldata secondsAgos)


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

</details>

## NC012 - Contract declarations should have `@notice` tags:

`@notice` is used to explain to end users what the contract does, and the compiler interprets `///` or `/**` comments as this tag if one wasn't explicitly provided.


<details>
<summary>Click to show 10 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

```solidity
File: libraries/LibBridgeRouter.sol


16      library LibBridgeRouter {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16:16

```solidity
File: libraries/LibBytes.sol


9       library LibBytes {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9:9

```solidity
File: libraries/LibOracle.sol


16      library LibOracle {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16:16

```solidity
File: libraries/LibOrders.sol


20      library LibOrders {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20:20

```solidity
File: libraries/LibSRUtil.sol


18      library LibSRUtil {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18:18

```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:10

</details>

## NC013 - Invalid NatSpec comment style:

NatSpec must begin with `///`, or use `/* ... */` syntax. 


<details>
<summary>Click to show 93 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


67              // @dev amount after deposit might be less, if bridge takes a fee


147         // @dev Deters attempts to take advantage of long delays between updates to the yield rate, by creating large temporary positions


178                 // @dev don't use mulU88 in rare case of overflow


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L178:178

```solidity
File: facets/PrimaryLiquidationFacet.sol


55              // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost


58              // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile


67              // @dev liquidate requires more up-to-date oraclePrice


72              // @dev Can liquidate as long as CR is low enough


95          // @dev startingShortId is updated via updateOracleAndStartingShortViaTimeBidOnly() prior to call


158             // @dev Provide higher price to better ensure it can fully fill the liquidation


164             // @dev Increase ethEscrowed by shorter's full collateral for forced bid


177                 // @dev Max ethDebt can only be the ethEscrowed in the TAPP


186             // @dev Liquidation contract will be the caller. Virtual accounting done later for shorter or TAPP


192             // @dev virtually burning the repurchased debt


197             // @dev manually setting basefee to 1,000,000 in foundry.toml;


198             // @dev By basing gasFee off of baseFee instead of priority, adversaries are prevent from draining the TAPP


217             // @dev TAPP already received the gasFee for being the forcedBid caller. tappFee nets out.


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L217:217

```solidity
File: facets/RedemptionFacet.sol


36              // @dev Matches check in onlyValidShortRecord but with a more restrictive ercDebt condition


37              // @dev Proposer can't redeem on self


72              // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption


82                  // @dev Setting this above _onlyValidShortRecord to allow skipping


92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold


95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount


100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate


108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR


109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()


127                 // @dev directly write the properties of MTypes.ProposalData into bytes


145             // @dev SSTORE2 the entire proposalData after validating proposalInput


156             // @dev Calculate the dispute period


157             // @dev timeToDispute is immediate for shorts with CR <= 1.1x


261                 // @dev All proposals from the incorrectIndex onward will be removed


262                 // @dev Thus the proposer can only redeem a portion of their original slate


278                 // @dev Update the redeemer's SSTORE2Pointer


282                     // @dev this implies everything in the redeemer's proposal was incorrect


287                 // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)


288                 // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees


295                 // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)


356             // @dev Only need to read up to the position of the SR to be claimed


372                 // @dev Refund shorter the remaining collateral only if fully redeemed and not claimed already


375                 // @dev Shorter shouldn't lose any unclaimed yield because dispute time > YIELD_DELAY_SECONDS


381         // @dev inspired by https://docs.liquity.org/faq/lusd-redemptions#how-is-the-redemption-fee-calculated


391             // @dev Calculate Asset.ercDebt prior to proposal


393             // @dev Derived via this forumula: baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L393:393

```solidity
File: facets/ShortOrdersFacet.sol


47              // @dev create "empty" SR. Fail early.


55              // @dev minShortErc needs to be modified (bigger) when cr < 1


74              // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId


84              // @dev reading spot oracle price


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L84:84

```solidity
File: libraries/LibBridgeRouter.sol


74                          // @dev Prevents abusing bridge for arbitrage


104                         // @dev Prevents abusing bridge for arbitrage


112         // @dev Only applicable to VAULT.ONE which has mixed LST


143         // @dev Only relevant to NFT SR that is being transferred, used to deter workarounds to the bridge credit system


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L143:143

```solidity
File: libraries/LibOracle.sol


29                      // @dev multiply base oracle by 10**10 to give it 18 decimals of precision


82              // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink


155         // @dev Intentionally using creationTime for oracleTime.


161         // @dev Intentionally using ercAmount for oraclePrice. Storing as price may lead to bugs in the match algos.


167         // @dev Allows caller to save gas since reading spot price costs ~16K


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L167:167

```solidity
File: libraries/LibOrders.sol


29          // @dev in seconds


43              // @dev use the diff to get more time (2159), to prevent overflow at year 2106


138             // @dev: Only need to set this when placing incomingShort onto market


172         // @dev partial addOrder


188             // @dev (ID) is exiting, [ID] is inserted


237             // @dev: TAIL can't be prevId because it will always be last item in list


267             // @dev: TAIL can't be prevId because it will always be last item in list


294             // @dev (ID) is exiting, [ID] is inserted


332             // @dev mark as cancelled instead of deleting the order itself


419         // @dev not used to change state, just which methods to call


507                     // @dev Handles only matching one thing


508                     // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block


511                     // @dev Handles moving forward only


518                     // @dev Handle going backward and forward


641             // @dev match price is based on the order that was already on orderbook


724             // @dev this happens at the end so fillErc isn't affected in previous calculations


760                     // @dev force hint to be within 0.5% of oraclePrice


769                         // @dev prevShortPrice >= oraclePrice


782         // @dev Update on match if order matches and price diff between order price and oracle > chainlink threshold (i.e. eth .5%)


790             // @dev handle .5% deviations in either directions


802         // @dev Possible for this function to never get called if updateOracleAndStartingShortViaThreshold() gets called often enough


846                 // @dev If hint was prev matched, assume that hint was close to HEAD and therefore is reasonable to use HEAD


899                 // @dev creating shortOrder automatically creates a closed shortRecord which also sets a shortRecordId


900                 // @dev cancelling an unmatched order needs to also handle/recycle the shortRecordId


905                     // @dev prevents leaving behind a partially filled SR is under minShortErc


906                     // @dev if the corresponding short is cancelled, then the partially filled SR's debt will == minShortErc


928                         // @dev update the eth refund amount


931                     // @dev virtually mint the increased debt


962             // @dev tithe is increased only if discount is greater than 1%


964                 // @dev bound the new tithe amount between 25% and 100%


967                 // @dev Vault.dethTitheMod is added onto Vault.dethTithePercent to get tithe amount


970                 // @dev dethTitheMod is only set when setTithe is called.


974                     // @dev change back to original tithe percent


981             // @dev exists because of ShortOrderFacet contract size


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L981:981

```solidity
File: libraries/LibSRUtil.sol


89                          // @dev The resulting SR will not have PartialFill status after cancel


133             // @dev shortOrderId is already validated in mintNFT


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L133:133

```solidity
File: libraries/UniswapOracleLibrary.sol


58              // @dev Returns the cumulative tick and liquidity as of each timestamp secondsAgo from the current block timestamp


69              // @dev Gets price using this formula: p(i) = 1.0001**i, where i is the tick


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L69:69

</details>

## NC014 - Inconsistent spacing in comments:

Some lines use // x and some use //x. The instances below point out the usages that don't follow the majority, within each file.


```solidity
File: facets/PrimaryLiquidationFacet.sol


92          //PRIVATE FUNCTIONS


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L92:92

```solidity
File: libraries/LibOrders.sol


514                     //@handles moving backwards only.


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L514:514



## NC015 - Not using the named return variables anywhere in the function is confusing:

Consider changing the return variable to be an unnamed one, since the variable is never assigned, nor is it returned by name


<details>
<summary>Click to show 15 findings</summary>

```solidity
File: facets/RedemptionFacet.sol


384             returns (uint88 redemptionFee)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L384:384

```solidity
File: libraries/LibBridgeRouter.sol


113         function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113:113

```solidity
File: libraries/LibOracle.sol


75          ) private view returns (uint256 _protocolPrice) {


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


156         function getTime(address asset) internal view returns (uint256 creationTime) {


162         function getPrice(address asset) internal view returns (uint80 oraclePrice) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L162:162

```solidity
File: libraries/LibOrders.sol


30          function getOffsetTime() internal view returns (uint32 timeInSeconds) {


234             returns (int256 direction)


266         ) private view returns (int256 direction) {


409         ) internal view returns (int256 direction) {


420         function normalizeOrderType(O o) private pure returns (O newO) {


447         ) internal view returns (uint16 _hintId) {


830         ) internal view returns (uint16 hintId) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L830:830

```solidity
File: libraries/LibSRUtil.sol


51              returns (bool isCancelled)


105             returns (bool recoveryViolation)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L105:105

</details>

## NC016 - Contracts should have full test coverage:

While 100% code coverage does not guarantee that there are no bugs, it often will catch easy-to-find bugs, and will ensure that there are fewer regressions when the code invariably has to be modified. Furthermore, in order to get full coverage, code authors will often have to re-organize their code so that it is more modular, so that each component can be tested separately, which reduces interdependencies between modules and layers, and makes for code that is easier to reason about and audit.


```solidity
File: Various Files


None

```

## NC017 - Large or complicated code bases should implement invariant tests:

Large code bases, or code with lots of inline-assembly, complicated math, or complicated interactions between multiple contracts, should implement invariant fuzzing tests. Invariant fuzzers such as Echidna require the test writer to come up with invariants which should not be violated under any circumstances, and the fuzzer tests various inputs and function calls to ensure that the invariants always hold. Even code with 100% code coverage can still have bugs due to the order of the operations a user performs, and invariant fuzzers, with properly and extensively-written invariants, can close this testing gap significantly.


```solidity
File: Various Files


None

```

## NC018 - Consider using `block.number` instead of `block.timestamp`:

`block.timestamp` is vulnerable to miner manipulation and creates a potential front-running vulnerability. Consider using `block.number` instead.


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: libraries/LibOracle.sol


60                      if (roundID == 0 || price == 0 || timeStamp > block.timestamp) revert Errors.InvalidPrice();


76              bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0


77                  || block.timestamp > 2 hours + timeStamp;


125             bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0


126                 || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L126:126

```solidity
File: libraries/LibOrders.sol


32              return uint32(block.timestamp - C.STARTING_TIME); // @dev(safe-cast)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L32:32

</details>

## NC019 - Consider bounding input array length:

The functions below take in an unbounded array, and make function calls for entries in the array. While the function will revert if it eventually runs out of gas, it may be a nicer user experience to `require()` that the length of the array is below some reasonable maximum, so that the user doesn't have to use up a full transaction's gas only to see that the transaction reverts.


```solidity
File: facets/RedemptionFacet.sol


78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L78:141

```solidity
File: libraries/LibOrders.sol


743                 for (uint256 i = 0; i < shortHintArray.length;) {
744                     shortHintId = shortHintArray[i];
745                     unchecked {
746                         ++i;
747                     }
748     
749                     STypes.Order storage short = s.shorts[asset][shortHintId];
750                     {
751                         O shortOrderType = short.orderType;
752                         if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753                             continue;
754                         }
755                     }
756     
757                     uint80 shortPrice = short.price;
758                     uint16 prevId = short.prevId;
759                     uint80 prevShortPrice = s.shorts[asset][prevId].price;
760                     // @dev force hint to be within 0.5% of oraclePrice
761                     bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762                     bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763                     bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764     
765                     if (isExactStartingShort) {
766                         Asset.startingShortId = shortHintId;
767                         return;
768                     } else if (startingShortWithinOracleRange) {
769                         // @dev prevShortPrice >= oraclePrice
770                         Asset.startingShortId = prevId;
771                         return;
772                     } else if (allShortUnderOraclePrice) {
773                         Asset.startingShortId = C.HEAD;
774                         return;
775                     }
776                 }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L743:776

## NC020 - Variables should be named in mixedCase style:

As the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html#naming-styles) suggests: arguments, local variables and mutable state variables should be named in mixedCase style.


<details>
<summary>Click to show 46 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


210             STypes.VaultUser storage VaultUser = s.vaultUser[m.vault][msg.sender];


241             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


170                 STypes.Asset storage Asset = s.asset[m.asset];


211             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


165             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L165:165

```solidity
File: facets/RedemptionFacet.sol


207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];


248             STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];


386             STypes.Asset storage Asset = s.asset[asset];


363             STypes.Asset storage Asset = s.asset[asset];


83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];


151             STypes.Asset storage Asset = s.asset[p.asset];


266                     STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];


257             uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);


255             STypes.Asset storage Asset = s.asset[d.asset];


394             uint256 redeemedDUSDFraction = ercDebtRedeemed.div(totalAssetErcDebt);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L394:394

```solidity
File: facets/ShortOrdersFacet.sol


41              uint16 shortOrderCR


44              STypes.Asset storage Asset = s.asset[asset];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L44:44

```solidity
File: libraries/LibBridgeRouter.sol


23              STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];


44              STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];


154                 STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];


151                 STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];


147             STypes.Asset storage Asset = s.asset[asset];


118             uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);


122             uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122:122

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


24                  uint64 CR; // bytes8


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L24:24

```solidity
File: libraries/LibOracle.sol


36                          uint80 roundID,
37                          int256 price,
38                          /*uint256 startedAt*/
39                          ,
40                          uint256 timeStamp,


53                          uint80 roundID,
54                          int256 price,
55                          /*uint256 startedAt*/
56                          ,
57                          uint256 timeStamp,


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L53:57

```solidity
File: libraries/LibOrders.sol


737             STypes.Asset storage Asset = s.asset[asset];


187             uint16 canceledID = orders[asset][C.HEAD].prevId;


891             STypes.Asset storage Asset = s.asset[asset];


909                         STypes.Vault storage Vault = s.vault[vault];


315             uint16 prevHEAD = orders[asset][C.HEAD].prevId;


958             STypes.Vault storage Vault = s.vault[vault];


324             uint16 prevHEAD,


812             STypes.Asset storage Asset = s.asset[asset];


291             uint16 prevHEAD = orders[asset][C.HEAD].prevId;


195                 uint16 prevCanceledID = orders[asset][canceledID].prevId;


670             STypes.Asset storage Asset = s.asset[asset];


672             STypes.Vault storage Vault = s.vault[vault];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L672:672

```solidity
File: libraries/LibSRUtil.sol


27              STypes.Asset storage Asset = s.asset[asset];


109             uint256 recoveryCR = LibAsset.recoveryCR(asset);


29              STypes.Vault storage Vault = s.vault[vault];


115                     uint256 assetCR = Asset.dethCollateral.div(oraclePrice.mul(Asset.ercDebt));


112                 STypes.Asset storage Asset = s.asset[asset];


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102:102

</details>

## NC021 - Function names should use lowerCamelCase:

According to the Solidity [style guide](https://docs.soliditylang.org/en/latest/style-guide.html#function-names) function names should be in `mixedCase` (lowerCamelCase).


```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L31:31

```solidity
File: libraries/LibOrders.sol


35          function convertCR(uint16 cr) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L35:35

```solidity
File: libraries/UniswapOracleLibrary.sol


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

## NC022 - Consider adding a deny-list:

Doing so will significantly increase centralization, but will help to prevent hackers from using stolen tokens.


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

</details>

## NC023 - Events are missing sender information:

When an action is triggered based on a user's action, not being able to filter based on who triggered the action makes event processing a lot more cumbersome. Including the msg.sender the events of these types of action will make events much more useful to end users. Include `msg.sender` in the event output.


```solidity
File: facets/RedemptionFacet.sol


284                     emit Events.DisputeRedemptionAll(d.asset, redeemer);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L284:284

## NC024 - Zero as a function argument should have a descriptive meaning:

Consider using descriptive constants or an enum instead of passing zero directly on function calls, as that might be error-prone, to fully describe the caller's intention.


<details>
<summary>Click to show 23 findings</summary>

```solidity
File: facets/RedemptionFacet.sol


182                 m = uint256(3 ether).div(0.3 ether);


182                 m = uint256(3 ether).div(0.3 ether);


185                 m = uint256(1.5 ether).div(0.2 ether);


185                 m = uint256(1.5 ether).div(0.2 ether);


189                 m = uint256(0.75 ether).div(0.2 ether);


189                 m = uint256(0.75 ether).div(0.2 ether);


193                 m = uint256(0.417 ether).div(0.1 ether);


193                 m = uint256(0.417 ether).div(0.1 ether);


197                 m = uint256(C.ONE_THIRD.div(0.1 ether));


289                 uint256 penaltyPct = LibOrders.min(
290                     LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291                 );


396             newBaseRate = LibOrders.min(newBaseRate, 1 ether); // cap baseRate at a maximum of 100%


401             uint256 redemptionRate = LibOrders.min((Asset.baseRate + 0.005 ether), 1 ether);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L401:401

```solidity
File: facets/ShortOrdersFacet.sol


48              incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L48:48

```solidity
File: libraries/LibBridgeRouter.sol


118             uint256 unitRethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.RETH_WETH, VAULT.RETH, C.WETH);


122             uint256 unitWstethTWAP = OracleLibrary.estimateTWAP(1 ether, 30 minutes, VAULT.WSTETH_WETH, VAULT.WSTETH, C.WETH);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L122:122

```solidity
File: libraries/LibOracle.sol


87                  try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)


133             uint256 twapPrice = IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L133:133

```solidity
File: libraries/LibOrders.sol


761                     bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;


960             bool isDiscounted = savedPrice > price.mul(1.01 ether);


965                 uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));


965                 uint256 discountPct = max(0.01 ether, min(((savedPrice - price).div(savedPrice)), 0.04 ether));


968                 Vault.dethTitheMod = (C.MAX_TITHE - Vault.dethTithePercent).mulU16(discountPct.div(0.04 ether));


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L968:968

```solidity
File: libraries/UniswapOracleLibrary.sol


54              uint32[] memory secondsAgos = new uint32[](2);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L54:54

</details>

## NC025 - It is standard for all external and public functions to be override from an interface:

This is to ensure the whole API is extracted in an interface


<details>
<summary>Click to show 12 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


40          function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {
41              return vault.getDethTotal();
42          }


51          function getBridges(uint256 vault) external view returns (address[] memory) {
52              return s.vaultBridges[vault];
53          }


63          function deposit(address bridge, uint88 amount) external nonReentrant {
64              if (amount < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();
65      
66              (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
67              // @dev amount after deposit might be less, if bridge takes a fee
68              uint88 dethAmount = uint88(IBridge(bridge).deposit(msg.sender, amount)); // @dev(safe-cast)
69      
70              vault.addDeth(bridgePointer, dethAmount);
71              maybeUpdateYield(vault, dethAmount);
72              emit Events.Deposit(bridge, msg.sender, dethAmount);
73          }


82          function depositEth(address bridge) external payable nonReentrant {
83              if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();
84      
85              (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
86      
87              uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
88              vault.addDeth(bridgePointer, dethAmount);
89              maybeUpdateYield(vault, dethAmount);
90              emit Events.DepositEth(bridge, msg.sender, dethAmount);
91          }


101         function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
102             if (dethAmount == 0) revert Errors.ParameterIsZero();
103     
104             (uint256 vault, uint256 bridgePointer) = _getVault(bridge);
105     
106             uint88 fee;
107             if (vault == VAULT.ONE) {
108                 uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
109                 if (dethAssessable > 0) {
110                     uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
111                     if (withdrawalFeePct > 0) {
112                         fee = dethAssessable.mulU88(withdrawalFeePct);
113                         dethAmount -= fee;
114                         s.vaultUser[vault][address(this)].ethEscrowed += fee;
115                     }
116                 }
117             }
118     
119             uint88 ethAmount = _ethConversion(vault, dethAmount);
120             vault.removeDeth(dethAmount, fee);
121             IBridge(bridge).withdraw(msg.sender, ethAmount);
122             emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
123         }


133         function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
134             if (dethAmount == 0) revert Errors.ParameterIsZero();
135     
136             (uint256 vault,) = _getVault(bridge);
137             uint88 ethAmount = _ethConversion(vault, dethAmount);
138     
139             s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
140             s.vault[vault].dethTotal -= dethAmount;
141     
142             IBridge(bridge).withdraw(msg.sender, ethAmount);
143             emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
144         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L133:144

```solidity
File: facets/PrimaryLiquidationFacet.sol


47          function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48              external
49              isNotFrozen(asset)
50              nonReentrant
51              onlyValidShortRecord(asset, shorter, id)
52              returns (uint88, uint88)
53          {
54              if (msg.sender == shorter) revert Errors.CannotLiquidateSelf();
55              // @dev TAPP partially reimburses gas fees, capped at 10 to limit arbitrary high cost
56              if (shortHintArray.length > 10) revert Errors.TooManyHints();
57      
58              // @dev Ensures SR has enough ercDebt/collateral to make caller fee worthwhile
59              LibSRUtil.checkCancelShortOrder({
60                  asset: asset,
61                  initialStatus: s.shortRecords[asset][shorter][id].status,
62                  shortOrderId: shortOrderId,
63                  shortRecordId: id,
64                  shorter: shorter
65              });
66      
67              // @dev liquidate requires more up-to-date oraclePrice
68              LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);
69      
70              MTypes.PrimaryLiquidation memory m = _setLiquidationStruct(asset, shorter, id, shortOrderId);
71      
72              // @dev Can liquidate as long as CR is low enough
73              if (m.cRatio >= LibAsset.liquidationCR(m.asset)) {
74                  // If CR is too high, check for recovery mode and violation to continue liquidation
75                  if (!LibSRUtil.checkRecoveryModeViolation(m.asset, m.cRatio, m.oraclePrice)) revert Errors.SufficientCollateral();
76              }
77      
78              // revert if no asks, or price too high
79              _checklowestSell(m);
80      
81              _performForcedBid(m, shortHintArray);
82      
83              _liquidationFeeHandler(m);
84      
85              _fullorPartialLiquidation(m);
86      
87              emit Events.Liquidate(asset, shorter, id, msg.sender, m.ercDebtMatched);
88      
89              return (m.gasFee, m.ethFilled);
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47:90

```solidity
File: facets/RedemptionFacet.sol


56          function proposeRedemption(
57              address asset,
58              MTypes.ProposalInput[] calldata proposalInput,
59              uint88 redemptionAmount,
60              uint88 maxRedemptionFee
61          ) external isNotFrozen(asset) nonReentrant {
62              if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63              MTypes.ProposeRedemption memory p;
64              p.asset = asset;
65              STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66              uint256 minShortErc = LibAsset.minShortErc(p.asset);
67      
68              if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69      
70              if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71      
72              // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73              if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74      
75              p.oraclePrice = LibOracle.getPrice(p.asset);
76      
77              bytes memory slate;
78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }
142     
143             if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144     
145             // @dev SSTORE2 the entire proposalData after validating proposalInput
146             redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147             redeemerAssetUser.slateLength = p.redemptionCounter;
148             redeemerAssetUser.oraclePrice = p.oraclePrice;
149             redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150     
151             STypes.Asset storage Asset = s.asset[p.asset];
152             Asset.ercDebt -= p.totalAmountProposed;
153     
154             uint32 protocolTime = LibOrders.getOffsetTime();
155             redeemerAssetUser.timeProposed = protocolTime;
156             // @dev Calculate the dispute period
157             // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158     
159             /*
160             +-------+------------+
161             | CR(X) |  Hours(Y)  |
162             +-------+------------+
163             | 1.1   |     0      |
164             | 1.2   |    .333    |
165             | 1.3   |    .75     |
166             | 1.5   |    1.5     |
167             | 1.7   |     3      |
168             | 2.0   |     6      |
169             +-------+------------+
170     
171             Creating fixed points and interpolating between points on the graph without using exponentials
172             Using simple y = mx + b formula
173             
174             where x = currentCR - previousCR
175             m = (y2-y1)/(x2-x1)
176             b = previous fixed point (Y)
177             */
178     
179             uint256 m;
180     
181             if (p.currentCR > 1.7 ether) {
182                 m = uint256(3 ether).div(0.3 ether);
183                 redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184             } else if (p.currentCR > 1.5 ether) {
185                 m = uint256(1.5 ether).div(0.2 ether);
186                 redeemerAssetUser.timeToDispute =
187                     protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188             } else if (p.currentCR > 1.3 ether) {
189                 m = uint256(0.75 ether).div(0.2 ether);
190                 redeemerAssetUser.timeToDispute =
191                     protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192             } else if (p.currentCR > 1.2 ether) {
193                 m = uint256(0.417 ether).div(0.1 ether);
194                 redeemerAssetUser.timeToDispute =
195                     protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196             } else if (p.currentCR > 1.1 ether) {
197                 m = uint256(C.ONE_THIRD.div(0.1 ether));
198                 redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199             }
200     
201             redeemerAssetUser.oraclePrice = p.oraclePrice;
202             redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203     
204             uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205             if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206     
207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208             if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209             VaultUser.ethEscrowed -= redemptionFee;
210             emit Events.ProposeRedemption(p.asset, msg.sender);
211         }


224         function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225             external
226             isNotFrozen(asset)
227             nonReentrant
228         {
229             if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230             MTypes.DisputeRedemption memory d;
231             d.asset = asset;
232             d.redeemer = redeemer;
233     
234             STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236     
237             if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238     
239             MTypes.ProposalData[] memory decodedProposalData =
240                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241     
242             for (uint256 i = 0; i < decodedProposalData.length; i++) {
243                 if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244                     revert Errors.CannotDisputeWithRedeemerProposal();
245                 }
246             }
247     
248             STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249             // Match continue (skip) conditions in proposeRedemption()
250             uint256 minShortErc = LibAsset.minShortErc(d.asset);
251             if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252     
253             MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254             MTypes.ProposalData memory currentProposal;
255             STypes.Asset storage Asset = s.asset[d.asset];
256     
257             uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258     
259             if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260             {
261                 // @dev All proposals from the incorrectIndex onward will be removed
262                 // @dev Thus the proposer can only redeem a portion of their original slate
263                 for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264                     currentProposal = decodedProposalData[i];
265     
266                     STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267                     currentSR.collateral += currentProposal.colRedeemed;
268                     currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269     
270                     d.incorrectCollateral += currentProposal.colRedeemed;
271                     d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272                 }
273     
274                 s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275                 Asset.dethCollateral += d.incorrectCollateral;
276                 Asset.ercDebt += d.incorrectErcDebt;
277     
278                 // @dev Update the redeemer's SSTORE2Pointer
279                 if (incorrectIndex > 0) {
280                     redeemerAssetUser.slateLength = incorrectIndex;
281                 } else {
282                     // @dev this implies everything in the redeemer's proposal was incorrect
283                     delete redeemerAssetUser.SSTORE2Pointer;
284                     emit Events.DisputeRedemptionAll(d.asset, redeemer);
285                 }
286     
287                 // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288                 // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289                 uint256 penaltyPct = LibOrders.min(
290                     LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291                 );
292     
293                 uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294     
295                 // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296                 redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297                 s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298             } else {
299                 revert Errors.InvalidRedemptionDispute();
300             }
301         }


310         function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
311             uint256 vault = s.asset[asset].vault;
312             STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
313             STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
314             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
315             if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();
316     
317             MTypes.ProposalData[] memory decodedProposalData =
318                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
319     
320             uint88 totalColRedeemed;
321             for (uint256 i = 0; i < decodedProposalData.length; i++) {
322                 MTypes.ProposalData memory currentProposal = decodedProposalData[i];
323                 totalColRedeemed += currentProposal.colRedeemed;
324                 _claimRemainingCollateral({
325                     asset: asset,
326                     vault: vault,
327                     shorter: currentProposal.shorter,
328                     shortId: currentProposal.shortId
329                 });
330             }
331             redeemerVaultUser.ethEscrowed += totalColRedeemed;
332             delete redeemerAssetUser.SSTORE2Pointer;
333             emit Events.ClaimRedemption(asset, msg.sender);
334         }


347         function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)
348             external
349             isNotFrozen(asset)
350             nonReentrant
351         {
352             STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];
353             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
354             if (redeemerAssetUser.timeToDispute > LibOrders.getOffsetTime()) revert Errors.TimeToDisputeHasNotElapsed();
355     
356             // @dev Only need to read up to the position of the SR to be claimed
357             MTypes.ProposalData[] memory decodedProposalData =
358                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, claimIndex + 1);
359             MTypes.ProposalData memory claimProposal = decodedProposalData[claimIndex];
360     
361             if (claimProposal.shorter != msg.sender && claimProposal.shortId != id) revert Errors.CanOnlyClaimYourShort();
362     
363             STypes.Asset storage Asset = s.asset[asset];
364             _claimRemainingCollateral({asset: asset, vault: Asset.vault, shorter: msg.sender, shortId: id});
365         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L347:365

```solidity
File: facets/ShortOrdersFacet.sol


35          function createLimitShort(
36              address asset,
37              uint80 price,
38              uint88 ercAmount,
39              MTypes.OrderHint[] memory orderHintArray,
40              uint16[] memory shortHintArray,
41              uint16 shortOrderCR
42          ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43              MTypes.CreateLimitShortParam memory p;
44              STypes.Asset storage Asset = s.asset[asset];
45              STypes.Order memory incomingShort;
46      
47              // @dev create "empty" SR. Fail early.
48              incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49      
50              uint256 cr = LibOrders.convertCR(shortOrderCR);
51              if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52                  revert Errors.InvalidCR();
53              }
54      
55              // @dev minShortErc needs to be modified (bigger) when cr < 1
56              p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57              p.eth = price.mul(ercAmount);
58              p.minAskEth = LibAsset.minAskEth(asset);
59              if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60      
61              // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62              if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63      
64              incomingShort.addr = msg.sender;
65              incomingShort.price = price;
66              incomingShort.ercAmount = ercAmount;
67              incomingShort.id = Asset.orderIdCounter;
68              incomingShort.orderType = O.LimitShort;
69              incomingShort.creationTime = LibOrders.getOffsetTime();
70              incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71      
72              p.startingId = s.bids[asset][C.HEAD].nextId;
73              STypes.Order storage highestBid = s.bids[asset][p.startingId];
74              // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75              if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76                  LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77              }
78      
79              p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80              if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81                  revert Errors.BelowRecoveryModeCR();
82              }
83      
84              // @dev reading spot oracle price
85              if (incomingShort.price < p.oraclePrice) {
86                  LibOrders.addShort(asset, incomingShort, orderHintArray);
87              } else {
88                  LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89              }
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35:90

</details>

## NC026 - Consider adding formal verification proofs:

Consider using formal verification to mathematically prove that your code does what is intended, and does not have any edge cases with unexpected behavior. The solidity compiler itself has this functionality [built in based off of SMTChecker](https://docs.soliditylang.org/en/latest/smtchecker.html#smtchecker-and-formal-verification).


```solidity
File: Various Files


None

```

## NC027 - Setters should prevent re-setting of the same value:

This especially problematic when the setter also emits the same value, which may be confusing to offline parsers.


```solidity
File: facets/PrimaryLiquidationFacet.sol


122         function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123             private
124             returns (MTypes.PrimaryLiquidation memory)
125         {
126             LibShortRecord.updateErcDebt(asset, shorter, id);
127             {
128                 MTypes.PrimaryLiquidation memory m;
129                 m.asset = asset;
130                 m.short = s.shortRecords[asset][shorter][id];
131                 m.shortOrderId = shortOrderId;
132                 m.vault = s.asset[asset].vault;
133                 m.shorter = shorter;
134                 m.penaltyCR = LibAsset.penaltyCR(asset);
135                 m.oraclePrice = LibOracle.getPrice(asset);
136                 m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
137                 m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);
138                 m.callerFeePct = LibAsset.callerFeePct(m.asset);
139                 m.tappFeePct = LibAsset.tappFeePct(m.asset);
140                 m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
141                 return m;
142             }
143         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122:143

## NC028 - Consider splitting long calculations:

The longer a string of operations is, the harder it is to understand it. Consider splitting the full calculation into more steps, with more descriptive temporary variable names, and add extensive comments.


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: facets/RedemptionFacet.sol


186                 redeemerAssetUser.timeToDispute =
187                     protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);


190                 redeemerAssetUser.timeToDispute =
191                     protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);


183                 redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);


194                 redeemerAssetUser.timeToDispute =
195                     protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L194:195

```solidity
File: libraries/LibOracle.sol


125             bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
126                 || baseRoundId == 0 || baseTimeStamp == 0 || baseTimeStamp > block.timestamp || baseChainlinkPrice <= 0;


76              bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
77                  || block.timestamp > 2 hours + timeStamp;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L76:77

</details>

## NC029 - High cyclomatic complexity:

Consider breaking down these blocks into more manageable units, by splitting things into utility functions, by reducing nesting, and by using early returns.


<details>
<summary>Click to show 9 findings</summary>

```solidity
File: facets/RedemptionFacet.sol


224         function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225             external
226             isNotFrozen(asset)
227             nonReentrant
228         {
229             if (redeemer == msg.sender) revert Errors.CannotDisputeYourself();
230             MTypes.DisputeRedemption memory d;
231             d.asset = asset;
232             d.redeemer = redeemer;
233     
234             STypes.AssetUser storage redeemerAssetUser = s.assetUser[d.asset][d.redeemer];
235             if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
236     
237             if (LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasElapsed();
238     
239             MTypes.ProposalData[] memory decodedProposalData =
240                 LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);
241     
242             for (uint256 i = 0; i < decodedProposalData.length; i++) {
243                 if (decodedProposalData[i].shorter == disputeShorter && decodedProposalData[i].shortId == disputeShortId) {
244                     revert Errors.CannotDisputeWithRedeemerProposal();
245                 }
246             }
247     
248             STypes.ShortRecord storage disputeSR = s.shortRecords[d.asset][disputeShorter][disputeShortId];
249             // Match continue (skip) conditions in proposeRedemption()
250             uint256 minShortErc = LibAsset.minShortErc(d.asset);
251             if (!validRedemptionSR(disputeSR, d.redeemer, disputeShorter, minShortErc)) revert Errors.InvalidRedemption();
252     
253             MTypes.ProposalData memory incorrectProposal = decodedProposalData[incorrectIndex];
254             MTypes.ProposalData memory currentProposal;
255             STypes.Asset storage Asset = s.asset[d.asset];
256     
257             uint256 disputeCR = disputeSR.getCollateralRatio(redeemerAssetUser.oraclePrice);
258     
259             if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed)
260             {
261                 // @dev All proposals from the incorrectIndex onward will be removed
262                 // @dev Thus the proposer can only redeem a portion of their original slate
263                 for (uint256 i = incorrectIndex; i < decodedProposalData.length; i++) {
264                     currentProposal = decodedProposalData[i];
265     
266                     STypes.ShortRecord storage currentSR = s.shortRecords[d.asset][currentProposal.shorter][currentProposal.shortId];
267                     currentSR.collateral += currentProposal.colRedeemed;
268                     currentSR.ercDebt += currentProposal.ercDebtRedeemed;
269     
270                     d.incorrectCollateral += currentProposal.colRedeemed;
271                     d.incorrectErcDebt += currentProposal.ercDebtRedeemed;
272                 }
273     
274                 s.vault[Asset.vault].dethCollateral += d.incorrectCollateral;
275                 Asset.dethCollateral += d.incorrectCollateral;
276                 Asset.ercDebt += d.incorrectErcDebt;
277     
278                 // @dev Update the redeemer's SSTORE2Pointer
279                 if (incorrectIndex > 0) {
280                     redeemerAssetUser.slateLength = incorrectIndex;
281                 } else {
282                     // @dev this implies everything in the redeemer's proposal was incorrect
283                     delete redeemerAssetUser.SSTORE2Pointer;
284                     emit Events.DisputeRedemptionAll(d.asset, redeemer);
285                 }
286     
287                 // @dev Penalty is based on the proposal with highest CR (decodedProposalData is sorted)
288                 // @dev PenaltyPct is bound between CallerFeePct and 33% to prevent exploiting primaryLiquidation fees
289                 uint256 penaltyPct = LibOrders.min(
290                     LibOrders.max(LibAsset.callerFeePct(d.asset), (currentProposal.CR - disputeCR).div(currentProposal.CR)), 0.33 ether
291                 );
292     
293                 uint88 penaltyAmt = d.incorrectErcDebt.mulU88(penaltyPct);
294     
295                 // @dev Give redeemer back ercEscrowed that is no longer used to redeem (penalty applied)
296                 redeemerAssetUser.ercEscrowed += (d.incorrectErcDebt - penaltyAmt);
297                 s.assetUser[d.asset][msg.sender].ercEscrowed += penaltyAmt;
298             } else {
299                 revert Errors.InvalidRedemptionDispute();
300             }
301         }


56          function proposeRedemption(
57              address asset,
58              MTypes.ProposalInput[] calldata proposalInput,
59              uint88 redemptionAmount,
60              uint88 maxRedemptionFee
61          ) external isNotFrozen(asset) nonReentrant {
62              if (proposalInput.length > type(uint8).max) revert Errors.TooManyProposals();
63              MTypes.ProposeRedemption memory p;
64              p.asset = asset;
65              STypes.AssetUser storage redeemerAssetUser = s.assetUser[p.asset][msg.sender];
66              uint256 minShortErc = LibAsset.minShortErc(p.asset);
67      
68              if (redemptionAmount < minShortErc) revert Errors.RedemptionUnderMinShortErc();
69      
70              if (redeemerAssetUser.ercEscrowed < redemptionAmount) revert Errors.InsufficientERCEscrowed();
71      
72              // @dev redeemerAssetUser.SSTORE2Pointer gets reset to address(0) after actual redemption
73              if (redeemerAssetUser.SSTORE2Pointer != address(0)) revert Errors.ExistingProposedRedemptions();
74      
75              p.oraclePrice = LibOracle.getPrice(p.asset);
76      
77              bytes memory slate;
78              for (uint8 i = 0; i < proposalInput.length; i++) {
79                  p.shorter = proposalInput[i].shorter;
80                  p.shortId = proposalInput[i].shortId;
81                  p.shortOrderId = proposalInput[i].shortOrderId;
82                  // @dev Setting this above _onlyValidShortRecord to allow skipping
83                  STypes.ShortRecord storage currentSR = s.shortRecords[p.asset][p.shorter][p.shortId];
84      
85                  /// Evaluate proposed shortRecord
86      
87                  if (!validRedemptionSR(currentSR, msg.sender, p.shorter, minShortErc)) continue;
88      
89                  currentSR.updateErcDebt(p.asset);
90                  p.currentCR = currentSR.getCollateralRatio(p.oraclePrice);
91      
92                  // @dev Skip if proposal is not sorted correctly or if above redemption threshold
93                  if (p.previousCR > p.currentCR || p.currentCR >= C.MAX_REDEMPTION_CR) continue;
94      
95                  // @dev totalAmountProposed tracks the actual amount that can be redeemed. totalAmountProposed <= redemptionAmount
96                  if (p.totalAmountProposed + currentSR.ercDebt <= redemptionAmount) {
97                      p.amountProposed = currentSR.ercDebt;
98                  } else {
99                      p.amountProposed = redemptionAmount - p.totalAmountProposed;
100                     // @dev Exit when proposal would leave less than minShortErc, proxy for nearing end of slate
101                     if (currentSR.ercDebt - p.amountProposed < minShortErc) break;
102                 }
103     
104                 /// At this point, the shortRecord passes all checks and will be included in the slate
105     
106                 p.previousCR = p.currentCR;
107     
108                 // @dev Cancel attached shortOrder if below minShortErc, regardless of ercDebt in SR
109                 // @dev All verified SR have ercDebt >= minShortErc so CR does not change in cancelShort()
110                 STypes.Order storage shortOrder = s.shorts[asset][p.shortOrderId];
111                 if (currentSR.status == SR.PartialFill && shortOrder.ercAmount < minShortErc) {
112                     if (shortOrder.shortRecordId != p.shortId || shortOrder.addr != p.shorter) revert Errors.InvalidShortOrder();
113                     LibOrders.cancelShort(asset, p.shortOrderId);
114                 }
115     
116                 p.colRedeemed = p.oraclePrice.mulU88(p.amountProposed);
117                 if (p.colRedeemed > currentSR.collateral) {
118                     p.colRedeemed = currentSR.collateral;
119                 }
120     
121                 currentSR.collateral -= p.colRedeemed;
122                 currentSR.ercDebt -= p.amountProposed;
123     
124                 p.totalAmountProposed += p.amountProposed;
125                 p.totalColRedeemed += p.colRedeemed;
126     
127                 // @dev directly write the properties of MTypes.ProposalData into bytes
128                 // instead of usual abi.encode to save on extra zeros being written
129                 slate = bytes.concat(
130                     slate,
131                     bytes20(p.shorter),
132                     bytes1(p.shortId),
133                     bytes8(uint64(p.currentCR)),
134                     bytes11(p.amountProposed),
135                     bytes11(p.colRedeemed)
136                 );
137     
138                 LibSRUtil.disburseCollateral(p.asset, p.shorter, p.colRedeemed, currentSR.dethYieldRate, currentSR.updatedAt);
139                 p.redemptionCounter++;
140                 if (redemptionAmount - p.totalAmountProposed < minShortErc) break;
141             }
142     
143             if (p.totalAmountProposed < minShortErc) revert Errors.RedemptionUnderMinShortErc();
144     
145             // @dev SSTORE2 the entire proposalData after validating proposalInput
146             redeemerAssetUser.SSTORE2Pointer = SSTORE2.write(slate);
147             redeemerAssetUser.slateLength = p.redemptionCounter;
148             redeemerAssetUser.oraclePrice = p.oraclePrice;
149             redeemerAssetUser.ercEscrowed -= p.totalAmountProposed;
150     
151             STypes.Asset storage Asset = s.asset[p.asset];
152             Asset.ercDebt -= p.totalAmountProposed;
153     
154             uint32 protocolTime = LibOrders.getOffsetTime();
155             redeemerAssetUser.timeProposed = protocolTime;
156             // @dev Calculate the dispute period
157             // @dev timeToDispute is immediate for shorts with CR <= 1.1x
158     
159             /*
160             +-------+------------+
161             | CR(X) |  Hours(Y)  |
162             +-------+------------+
163             | 1.1   |     0      |
164             | 1.2   |    .333    |
165             | 1.3   |    .75     |
166             | 1.5   |    1.5     |
167             | 1.7   |     3      |
168             | 2.0   |     6      |
169             +-------+------------+
170     
171             Creating fixed points and interpolating between points on the graph without using exponentials
172             Using simple y = mx + b formula
173             
174             where x = currentCR - previousCR
175             m = (y2-y1)/(x2-x1)
176             b = previous fixed point (Y)
177             */
178     
179             uint256 m;
180     
181             if (p.currentCR > 1.7 ether) {
182                 m = uint256(3 ether).div(0.3 ether);
183                 redeemerAssetUser.timeToDispute = protocolTime + uint32((m.mul(p.currentCR - 1.7 ether) + 3 ether) * 1 hours / 1 ether);
184             } else if (p.currentCR > 1.5 ether) {
185                 m = uint256(1.5 ether).div(0.2 ether);
186                 redeemerAssetUser.timeToDispute =
187                     protocolTime + uint32((m.mul(p.currentCR - 1.5 ether) + 1.5 ether) * 1 hours / 1 ether);
188             } else if (p.currentCR > 1.3 ether) {
189                 m = uint256(0.75 ether).div(0.2 ether);
190                 redeemerAssetUser.timeToDispute =
191                     protocolTime + uint32((m.mul(p.currentCR - 1.3 ether) + 0.75 ether) * 1 hours / 1 ether);
192             } else if (p.currentCR > 1.2 ether) {
193                 m = uint256(0.417 ether).div(0.1 ether);
194                 redeemerAssetUser.timeToDispute =
195                     protocolTime + uint32((m.mul(p.currentCR - 1.2 ether) + C.ONE_THIRD) * 1 hours / 1 ether);
196             } else if (p.currentCR > 1.1 ether) {
197                 m = uint256(C.ONE_THIRD.div(0.1 ether));
198                 redeemerAssetUser.timeToDispute = protocolTime + uint32(m.mul(p.currentCR - 1.1 ether) * 1 hours / 1 ether);
199             }
200     
201             redeemerAssetUser.oraclePrice = p.oraclePrice;
202             redeemerAssetUser.timeProposed = LibOrders.getOffsetTime();
203     
204             uint88 redemptionFee = calculateRedemptionFee(asset, p.totalColRedeemed, p.totalAmountProposed);
205             if (redemptionFee > maxRedemptionFee) revert Errors.RedemptionFeeTooHigh();
206     
207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];
208             if (VaultUser.ethEscrowed < redemptionFee) revert Errors.InsufficientETHEscrowed();
209             VaultUser.ethEscrowed -= redemptionFee;
210             emit Events.ProposeRedemption(p.asset, msg.sender);
211         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56:211

```solidity
File: facets/ShortOrdersFacet.sol


35          function createLimitShort(
36              address asset,
37              uint80 price,
38              uint88 ercAmount,
39              MTypes.OrderHint[] memory orderHintArray,
40              uint16[] memory shortHintArray,
41              uint16 shortOrderCR
42          ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
43              MTypes.CreateLimitShortParam memory p;
44              STypes.Asset storage Asset = s.asset[asset];
45              STypes.Order memory incomingShort;
46      
47              // @dev create "empty" SR. Fail early.
48              incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);
49      
50              uint256 cr = LibOrders.convertCR(shortOrderCR);
51              if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
52                  revert Errors.InvalidCR();
53              }
54      
55              // @dev minShortErc needs to be modified (bigger) when cr < 1
56              p.minShortErc = cr < 1 ether ? LibAsset.minShortErc(asset).mul(1 ether + cr.inv()) : LibAsset.minShortErc(asset);
57              p.eth = price.mul(ercAmount);
58              p.minAskEth = LibAsset.minAskEth(asset);
59              if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
60      
61              // For a short, need enough collateral to cover minting ERC (calculated using initialCR)
62              if (s.vaultUser[Asset.vault][msg.sender].ethEscrowed < p.eth.mul(cr)) revert Errors.InsufficientETHEscrowed();
63      
64              incomingShort.addr = msg.sender;
65              incomingShort.price = price;
66              incomingShort.ercAmount = ercAmount;
67              incomingShort.id = Asset.orderIdCounter;
68              incomingShort.orderType = O.LimitShort;
69              incomingShort.creationTime = LibOrders.getOffsetTime();
70              incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x
71      
72              p.startingId = s.bids[asset][C.HEAD].nextId;
73              STypes.Order storage highestBid = s.bids[asset][p.startingId];
74              // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
75              if (highestBid.price >= incomingShort.price && highestBid.orderType == O.LimitBid) {
76                  LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingShort, shortHintArray);
77              }
78      
79              p.oraclePrice = LibOracle.getSavedOrSpotOraclePrice(asset);
80              if (LibSRUtil.checkRecoveryModeViolation(asset, cr, p.oraclePrice)) {
81                  revert Errors.BelowRecoveryModeCR();
82              }
83      
84              // @dev reading spot oracle price
85              if (incomingShort.price < p.oraclePrice) {
86                  LibOrders.addShort(asset, incomingShort, orderHintArray);
87              } else {
88                  LibOrders.sellMatchAlgo(asset, incomingShort, orderHintArray, p.minAskEth);
89              }
90          }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35:90

```solidity
File: libraries/LibBridgeRouter.sol


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40              internal
41              returns (uint88)
42          {
43              AppStorage storage s = appStorage();
44              STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];
45      
46              uint88 creditReth;
47              uint88 creditSteth;
48              if (bridgePointer == VAULT.BRIDGE_RETH) {
49                  // Withdraw RETH
50                  creditReth = VaultUser.bridgeCreditReth;
51                  if (creditReth >= amount) {
52                      VaultUser.bridgeCreditReth -= amount;
53                      return 0;
54                  }
55      
56                  VaultUser.bridgeCreditReth = 0;
57                  amount -= creditReth;
58                  creditSteth = VaultUser.bridgeCreditSteth;
59                  if (creditSteth < C.ROUNDING_ZERO) {
60                      // Valid withdraw when no STETH credits
61                      return amount;
62                  } else {
63                      if (IBridge(stethBridge).getDethValue() < C.ROUNDING_ZERO) {
64                          // Can withdraw RETH using STETH credit when STETH bridge is empty
65                          if (creditSteth >= amount) {
66                              VaultUser.bridgeCreditSteth -= amount;
67                              return 0;
68                          } else {
69                              VaultUser.bridgeCreditSteth = 0;
70                              return amount - creditSteth;
71                          }
72                      } else {
73                          // Must use available bridge credits on withdrawal
74                          // @dev Prevents abusing bridge for arbitrage
75                          revert Errors.MustUseExistingBridgeCredit();
76                      }
77                  }
78              } else {
79                  // Withdraw STETH
80                  creditSteth = VaultUser.bridgeCreditSteth;
81                  if (creditSteth >= amount) {
82                      VaultUser.bridgeCreditSteth -= amount;
83                      return 0;
84                  }
85      
86                  VaultUser.bridgeCreditSteth = 0;
87                  amount -= creditSteth;
88                  creditReth = VaultUser.bridgeCreditReth;
89                  if (creditReth < C.ROUNDING_ZERO) {
90                      // Valid withdraw when no RETH credits
91                      return amount;
92                  } else {
93                      if (IBridge(rethBridge).getDethValue() < C.ROUNDING_ZERO) {
94                          // Can withdraw STETH using RETH credit when RETH bridge is empty
95                          if (creditReth >= amount) {
96                              VaultUser.bridgeCreditReth -= amount;
97                              return 0;
98                          } else {
99                              VaultUser.bridgeCreditReth = 0;
100                             return amount - creditReth;
101                         }
102                     } else {
103                         // Must use available bridge credits on withdrawal
104                         // @dev Prevents abusing bridge for arbitrage
105                         revert Errors.MustUseExistingBridgeCredit();
106                     }
107                 }
108             }
109         }


144         function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {
145             AppStorage storage s = appStorage();
146     
147             STypes.Asset storage Asset = s.asset[asset];
148             uint256 vault = Asset.vault;
149     
150             if (vault == VAULT.ONE) {
151                 STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];
152                 uint88 creditReth = VaultUserFrom.bridgeCreditReth;
153                 uint88 creditSteth = VaultUserFrom.bridgeCreditSteth;
154                 STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];
155     
156                 if (creditReth < C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
157                     // No bridge credits
158                     return;
159                 }
160     
161                 if (creditReth > C.ROUNDING_ZERO && creditSteth < C.ROUNDING_ZERO) {
162                     // Only creditReth
163                     if (creditReth > collateral) {
164                         VaultUserFrom.bridgeCreditReth -= collateral;
165                         VaultUserTo.bridgeCreditReth += collateral;
166                     } else {
167                         VaultUserFrom.bridgeCreditReth = 0;
168                         VaultUserTo.bridgeCreditReth += creditReth;
169                     }
170                 } else if (creditReth < C.ROUNDING_ZERO && creditSteth > C.ROUNDING_ZERO) {
171                     // Only creditSteth
172                     if (creditSteth > collateral) {
173                         VaultUserFrom.bridgeCreditSteth -= collateral;
174                         VaultUserTo.bridgeCreditSteth += collateral;
175                     } else {
176                         VaultUserFrom.bridgeCreditSteth = 0;
177                         VaultUserTo.bridgeCreditSteth += creditSteth;
178                     }
179                 } else {
180                     // Both creditReth and creditSteth
181                     uint88 creditTotal = creditReth + creditSteth;
182                     if (creditTotal > collateral) {
183                         creditReth = creditReth.divU88(creditTotal).mulU88(collateral);
184                         creditSteth = creditSteth.divU88(creditTotal).mulU88(collateral);
185                         VaultUserFrom.bridgeCreditReth -= creditReth;
186                         VaultUserFrom.bridgeCreditSteth -= creditSteth;
187                     } else {
188                         VaultUserFrom.bridgeCreditReth = 0;
189                         VaultUserFrom.bridgeCreditSteth = 0;
190                     }
191                     VaultUserTo.bridgeCreditReth += creditReth;
192                     VaultUserTo.bridgeCreditSteth += creditSteth;
193                 }
194             }
195         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L144:195

```solidity
File: libraries/LibOracle.sol


69          function baseOracleCircuitBreaker(
70              uint256 protocolPrice,
71              uint80 roundId,
72              int256 chainlinkPrice,
73              uint256 timeStamp,
74              uint256 chainlinkPriceInEth
75          ) private view returns (uint256 _protocolPrice) {
76              bool invalidFetchData = roundId == 0 || timeStamp == 0 || timeStamp > block.timestamp || chainlinkPrice <= 0
77                  || block.timestamp > 2 hours + timeStamp;
78              uint256 chainlinkDiff =
79                  chainlinkPriceInEth > protocolPrice ? chainlinkPriceInEth - protocolPrice : protocolPrice - chainlinkPriceInEth;
80              bool priceDeviation = protocolPrice > 0 && chainlinkDiff.div(protocolPrice) > 0.5 ether;
81      
82              // @dev if there is issue with chainlink, get twap price. Verify twap and compare with chainlink
83              if (invalidFetchData) {
84                  return twapCircuitBreaker();
85              } else if (priceDeviation) {
86                  // Check valid twap price
87                  try IDiamond(payable(address(this))).estimateWETHInUSDC(C.UNISWAP_WETH_BASE_AMT, 30 minutes) returns (uint256 twapPrice)
88                  {
89                      if (twapPrice == 0) {
90                          return chainlinkPriceInEth;
91                      }
92      
93                      uint256 twapPriceNormalized = twapPrice * (1 ether / C.DECIMAL_USDC);
94                      uint256 twapPriceInEth = twapPriceNormalized.inv();
95                      uint256 twapDiff = twapPriceInEth > protocolPrice ? twapPriceInEth - protocolPrice : protocolPrice - twapPriceInEth;
96      
97                      // Save the price that is closest to saved oracle price
98                      if (chainlinkDiff <= twapDiff) {
99                          return chainlinkPriceInEth;
100                     } else {
101                         // Check valid twap liquidity
102                         IERC20 weth = IERC20(C.WETH);
103                         uint256 wethBal = weth.balanceOf(C.USDC_WETH);
104                         if (wethBal < 100 ether) {
105                             return chainlinkPriceInEth;
106                         }
107                         return twapPriceInEth;
108                     }
109                 } catch {
110                     return chainlinkPriceInEth;
111                 }
112             } else {
113                 return chainlinkPriceInEth;
114             }
115         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L69:115

```solidity
File: libraries/LibOrders.sol


556         function sellMatchAlgo(
557             address asset,
558             STypes.Order memory incomingAsk,
559             MTypes.OrderHint[] memory orderHintArray,
560             uint256 minAskEth
561         ) internal {
562             AppStorage storage s = appStorage();
563             uint16 startingId = s.bids[asset][C.HEAD].nextId;
564             if (incomingAsk.price > s.bids[asset][startingId].price) {
565                 if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
566                     addSellOrder(incomingAsk, asset, orderHintArray);
567                 }
568                 return;
569             }
570             // matching loop starts
571             MTypes.Match memory matchTotal;
572             while (true) {
573                 STypes.Order memory highestBid = s.bids[asset][startingId];
574                 if (incomingAsk.price <= highestBid.price) {
575                     // Consider ask filled if only dust amount left
576                     if (incomingAsk.ercAmount.mul(highestBid.price) == 0) {
577                         updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
578                         incomingAsk.ercAmount = 0;
579                         matchIncomingSell(asset, incomingAsk, matchTotal);
580                         return;
581                     }
582                     matchHighestBid(incomingAsk, highestBid, asset, matchTotal);
583                     if (incomingAsk.ercAmount > highestBid.ercAmount) {
584                         incomingAsk.ercAmount -= highestBid.ercAmount;
585                         highestBid.ercAmount = 0;
586                         matchOrder(s.bids, asset, highestBid.id);
587     
588                         // loop
589                         startingId = highestBid.nextId;
590                         if (startingId == C.TAIL) {
591                             matchIncomingSell(asset, incomingAsk, matchTotal);
592     
593                             if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
594                                 addSellOrder(incomingAsk, asset, orderHintArray);
595                             }
596                             s.bids[asset][C.HEAD].nextId = C.TAIL;
597                             return;
598                         }
599                     } else {
600                         if (incomingAsk.ercAmount == highestBid.ercAmount) {
601                             matchOrder(s.bids, asset, highestBid.id);
602                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, true);
603                         } else {
604                             highestBid.ercAmount -= incomingAsk.ercAmount;
605                             s.bids[asset][highestBid.id].ercAmount = highestBid.ercAmount;
606                             updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
607                             // Check reduced dust threshold for existing limit orders
608                             if (highestBid.ercAmount.mul(highestBid.price) < LibAsset.minBidEth(asset).mul(C.DUST_FACTOR)) {
609                                 cancelBid(asset, highestBid.id);
610                             }
611                         }
612                         incomingAsk.ercAmount = 0;
613                         matchIncomingSell(asset, incomingAsk, matchTotal);
614                         return;
615                     }
616                 } else {
617                     updateBidOrdersOnMatch(s.bids, asset, highestBid.id, false);
618                     matchIncomingSell(asset, incomingAsk, matchTotal);
619     
620                     if (incomingAsk.ercAmount.mul(incomingAsk.price) >= minAskEth) {
621                         addSellOrder(incomingAsk, asset, orderHintArray);
622                     }
623                     return;
624                 }
625             }
626         }


499         function updateSellOrdersOnMatch(address asset, MTypes.BidMatchAlgo memory b) internal {
500             AppStorage storage s = appStorage();
501             if (b.matchedAskId != 0) {
502                 _updateOrders(s.asks, asset, C.HEAD, b.matchedAskId);
503             }
504     
505             if (b.matchedShortId != 0) {
506                 if (!b.isMovingBack && !b.isMovingFwd) {
507                     // @dev Handles only matching one thing
508                     // @dev If does not get fully matched, b.matchedShortId == 0 and therefore not hit this block
509                     _updateOrders(s.shorts, asset, b.prevShortId, b.matchedShortId);
510                 } else if (!b.isMovingBack && b.isMovingFwd) {
511                     // @dev Handles moving forward only
512                     _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, b.matchedShortId);
513                 } else if (b.isMovingBack && !b.isMovingFwd) {
514                     //@handles moving backwards only.
515                     _updateOrders(s.shorts, asset, b.prevShortId, b.shortHintId);
516                 } else if (b.isMovingBack && b.isMovingFwd) {
517                     uint16 id = b.prevShortId == b.firstShortIdBelowOracle ? b.shortHintId : b.matchedShortId;
518                     // @dev Handle going backward and forward
519                     _updateOrders(s.shorts, asset, b.firstShortIdBelowOracle, id);
520                 }
521             }
522         }


728         function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {
729             AppStorage storage s = appStorage();
730             uint256 oraclePrice = LibOracle.getOraclePrice(asset);
731             uint256 savedPrice = asset.getPrice();
732             asset.setPriceAndTime(oraclePrice, getOffsetTime());
733             if (oraclePrice == savedPrice) {
734                 return; // no need to update startingShortId
735             }
736     
737             STypes.Asset storage Asset = s.asset[asset];
738             bool shortOrdersIsEmpty = s.shorts[asset][C.HEAD].nextId == C.TAIL;
739             if (shortOrdersIsEmpty) {
740                 Asset.startingShortId = C.HEAD;
741             } else {
742                 uint16 shortHintId;
743                 for (uint256 i = 0; i < shortHintArray.length;) {
744                     shortHintId = shortHintArray[i];
745                     unchecked {
746                         ++i;
747                     }
748     
749                     STypes.Order storage short = s.shorts[asset][shortHintId];
750                     {
751                         O shortOrderType = short.orderType;
752                         if (shortOrderType == O.Cancelled || shortOrderType == O.Matched || shortOrderType == O.Uninitialized) {
753                             continue;
754                         }
755                     }
756     
757                     uint80 shortPrice = short.price;
758                     uint16 prevId = short.prevId;
759                     uint80 prevShortPrice = s.shorts[asset][prevId].price;
760                     // @dev force hint to be within 0.5% of oraclePrice
761                     bool startingShortWithinOracleRange = shortPrice <= oraclePrice.mul(1.005 ether) && prevShortPrice >= oraclePrice;
762                     bool isExactStartingShort = shortPrice >= oraclePrice && prevShortPrice < oraclePrice;
763                     bool allShortUnderOraclePrice = shortPrice < oraclePrice && short.nextId == C.TAIL;
764     
765                     if (isExactStartingShort) {
766                         Asset.startingShortId = shortHintId;
767                         return;
768                     } else if (startingShortWithinOracleRange) {
769                         // @dev prevShortPrice >= oraclePrice
770                         Asset.startingShortId = prevId;
771                         return;
772                     } else if (allShortUnderOraclePrice) {
773                         Asset.startingShortId = C.HEAD;
774                         return;
775                     }
776                 }
777     
778                 revert Errors.BadShortHint();
779             }
780         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L728:780

</details>


## NC030 - Unused import:

The identifier is imported but never used within the file


<details>
<summary>Click to show 11 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


10      import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";


10      import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L10:10

```solidity
File: facets/RedemptionFacet.sol


9       import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";


9       import {STypes, MTypes, SR} from "contracts/libraries/DataTypes.sol";


19      import {console} from "contracts/libraries/console.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L19:19

```solidity
File: facets/ShortOrdersFacet.sol


7       import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";


7       import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L7:7

```solidity
File: libraries/LibBridgeRouter.sol


6       import {STypes} from "contracts/libraries/DataTypes.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L6:6

```solidity
File: libraries/LibOrders.sol


9       import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";


9       import {STypes, MTypes, O, SR} from "contracts/libraries/DataTypes.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L9:9

```solidity
File: libraries/LibSRUtil.sol


6       import {STypes, SR} from "contracts/libraries/DataTypes.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L6:6

</details>

## NC031 - Unsafe conversion from unsigned to signed values:

Solidity follows [two's complement](https://en.wikipedia.org/wiki/Two%27s_complement) rules for its integers, meaning that the most significant bit for signed integers is used to denote the sign, and converting between the two requires inverting all of the bits and adding one. Because of this, casting an unsigned integer to a signed one may result in a change of the sign and or magnitude of the value. For example, `int8(type(uint8).max)` is not equal to `type(int8).max`, but is equal to `-1`. `type(uint8).max` in binary is `11111111`, which if cast to a signed value, means the first binary `1` indicates a negative value, and the binary `1`s, invert to all zeroes, and when one is added, it becomes one, but negative, and therefore the decimal value of binary `11111111` is `-1`.


```solidity
File: libraries/UniswapOracleLibrary.sol


65              if (tickCumulativesDelta < 0 && (tickCumulativesDelta % int32(secondsAgo) != 0)) {


62              int24 tick = int24(tickCumulativesDelta / int32(secondsAgo));


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L62:62

## NC032 - Style guide: State and local variables should be named using lowerCamelCase:

The Solidity style guide says to use mixedCase for local and state variable names. Note that while OpenZeppelin may not follow this advice, it still is the recommended way of naming variables.


<details>
<summary>Click to show 82 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


165             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


170                 STypes.Asset storage Asset = s.asset[m.asset];


210             STypes.VaultUser storage VaultUser = s.vaultUser[m.vault][msg.sender];


211             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


241             STypes.VaultUser storage TAPP = s.vaultUser[m.vault][address(this)];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L241:241

```solidity
File: facets/RedemptionFacet.sol


151             STypes.Asset storage Asset = s.asset[p.asset];


207             STypes.VaultUser storage VaultUser = s.vaultUser[Asset.vault][msg.sender];


255             STypes.Asset storage Asset = s.asset[d.asset];


363             STypes.Asset storage Asset = s.asset[asset];


386             STypes.Asset storage Asset = s.asset[asset];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L386:386

```solidity
File: facets/ShortOrdersFacet.sol


44              STypes.Asset storage Asset = s.asset[asset];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L44:44

```solidity
File: libraries/LibBridgeRouter.sol


23              STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];


44              STypes.VaultUser storage VaultUser = s.vaultUser[vault][msg.sender];


147             STypes.Asset storage Asset = s.asset[asset];


151                 STypes.VaultUser storage VaultUserFrom = s.vaultUser[vault][from];


154                 STypes.VaultUser storage VaultUserTo = s.vaultUser[vault][to];


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L154:154

```solidity
File: libraries/LibBytes.sol


24                  uint64 CR; // bytes8


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


11      import {LibOrders} from "contracts/libraries/LibOrders.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L11:11

```solidity
File: libraries/LibOrders.sol


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


670             STypes.Asset storage Asset = s.asset[asset];


672             STypes.Vault storage Vault = s.vault[vault];


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


737             STypes.Asset storage Asset = s.asset[asset];


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


812             STypes.Asset storage Asset = s.asset[asset];


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


891             STypes.Asset storage Asset = s.asset[asset];


909                         STypes.Vault storage Vault = s.vault[vault];


11      import {Events} from "contracts/libraries/Events.sol";


958             STypes.Vault storage Vault = s.vault[vault];


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


11      import {Events} from "contracts/libraries/Events.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L11:11

```solidity
File: libraries/LibSRUtil.sol


27              STypes.Asset storage Asset = s.asset[asset];


29              STypes.Vault storage Vault = s.vault[vault];


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


112                 STypes.Asset storage Asset = s.asset[asset];


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


11      import {LibAsset} from "contracts/libraries/LibAsset.sol";


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L11:11

```solidity
File: libraries/UniswapOracleLibrary.sol


11          function observe(uint32[] calldata secondsAgos)


11          function observe(uint32[] calldata secondsAgos)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L11:11

</details>

## NC033 - Function definitions should have NatSpec @dev annotations:

Explain to a developer any extra details


<details>
<summary>Click to show 57 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


29          constructor(address _rethBridge, address _stethBridge) {


40          function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {


156         function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {


169         function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169:169

```solidity
File: facets/PrimaryLiquidationFacet.sol


30          constructor(address _dusd) {


122         function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)


229         function min88(uint256 a, uint88 b) private pure returns (uint88) {


240         function _fullorPartialLiquidation(MTypes.PrimaryLiquidation memory m) private {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L240:240

```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


347         function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)


368         function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L368:368

```solidity
File: libraries/LibBridgeRouter.sol


21          function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)


198         function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198:198

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


19          function getOraclePrice(address asset) internal view returns (uint256) {


69          function baseOracleCircuitBreaker(


117         function oracleCircuitBreaker(


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


149         function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L149:149

```solidity
File: libraries/LibOrders.sol


35          function convertCR(uint16 cr) internal pure returns (uint256) {


40          function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {


55          function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)


78          function isShort(STypes.Order memory order) internal pure returns (bool) {


82          function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


103         function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


128         function addShort(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


153         function addSellOrder(STypes.Order memory incomingOrder, address asset, MTypes.OrderHint[] memory orderHintArray) private {


231         function verifyBidId(address asset, uint16 _prevId, uint256 _newPrice, uint16 _nextId)


260         function verifySellId(


320         function _reuseOrderIds(


362         function findPrevOfIncomingId(


402         function verifyId(


440         function getOrderId(


532         function _updateOrders(


556         function sellMatchAlgo(


628         function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {


652         function matchIncomingAsk(address asset, STypes.Order memory incomingAsk, MTypes.Match memory matchTotal) private {


668         function matchIncomingShort(address asset, STypes.Order memory incomingShort, MTypes.Match memory matchTotal) private {


728         function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {


810         function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {


826         function findOrderHintId(


854         function cancelBid(address asset, uint16 id) internal {


868         function cancelAsk(address asset, uint16 id) internal {


882         function cancelShort(address asset, uint16 id) internal {


955         function handlePriceDiscount(address asset, uint80 price) internal {


985         function min(uint256 a, uint256 b) internal pure returns (uint256) {


989         function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989:989

```solidity
File: libraries/LibSRUtil.sol


22          function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


124         function transferShortRecord(address from, address to, uint40 tokenId) internal {


151         function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151:151

```solidity
File: libraries/UniswapOracleLibrary.sol


11          function observe(uint32[] calldata secondsAgos)


28          function getQuoteAtTick(int24 tick, uint128 baseAmount, address baseToken, address quoteToken)


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

</details>

## NC034 - Function definitions should have NatSpec @notice annotations:

Explain to an end user what this does


<details>
<summary>Click to show 55 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


29          constructor(address _rethBridge, address _stethBridge) {


148         function maybeUpdateYield(uint256 vault, uint88 amount) private {


156         function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {


169         function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169:169

```solidity
File: facets/PrimaryLiquidationFacet.sol


30          constructor(address _dusd) {


96          function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {


229         function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229:229

```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


347         function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)


368         function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {


382         function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382:382

```solidity
File: libraries/LibBridgeRouter.sol


21          function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)


113         function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


144         function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {


198         function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198:198

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


19          function getOraclePrice(address asset) internal view returns (uint256) {


69          function baseOracleCircuitBreaker(


117         function oracleCircuitBreaker(


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


149         function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


156         function getTime(address asset) internal view returns (uint256 creationTime) {


162         function getPrice(address asset) internal view returns (uint80 oraclePrice) {


168         function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168:168

```solidity
File: libraries/LibOrders.sol


30          function getOffsetTime() internal view returns (uint32 timeInSeconds) {


35          function convertCR(uint16 cr) internal pure returns (uint256) {


40          function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {


55          function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)


78          function isShort(STypes.Order memory order) internal pure returns (bool) {


82          function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


103         function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


173         function addOrder(


320         function _reuseOrderIds(


420         function normalizeOrderType(O o) private pure returns (O newO) {


628         function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {


728         function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {


783         function updateOracleAndStartingShortViaThreshold(


803         function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {


810         function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {


826         function findOrderHintId(


854         function cancelBid(address asset, uint16 id) internal {


868         function cancelAsk(address asset, uint16 id) internal {


882         function cancelShort(address asset, uint16 id) internal {


955         function handlePriceDiscount(address asset, uint80 price) internal {


985         function min(uint256 a, uint256 b) internal pure returns (uint256) {


989         function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989:989

```solidity
File: libraries/LibSRUtil.sol


22          function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


124         function transferShortRecord(address from, address to, uint40 tokenId) internal {


151         function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151:151

```solidity
File: libraries/UniswapOracleLibrary.sol


11          function observe(uint32[] calldata secondsAgos)


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

</details>

## NC035 - Interface declarations should have NatSpec @title annotations:

A title that should describe the contract/interface


```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:10

## NC036 - Interface declarations should have NatSpec @author annotations:

The name of the author


```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:10

## NC037 - Interface declarations should have NatSpec @notice annotations:

Explain to an end user what this does


```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:10

## NC038 - Interface declarations should have NatSpec @dev annotations:

Explain to a developer any extra details


```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:10

## NC039 - Library declarations should have Natspec @title annotations:

A title that should describe the contract/interface


<details>
<summary>Click to show 5 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


16      library LibBridgeRouter {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16:16

```solidity
File: libraries/LibBytes.sol


9       library LibBytes {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9:9

```solidity
File: libraries/LibOracle.sol


16      library LibOracle {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16:16

```solidity
File: libraries/LibOrders.sol


20      library LibOrders {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20:20

```solidity
File: libraries/LibSRUtil.sol


18      library LibSRUtil {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18:18

</details>

## NC040 - Library declarations should have Natspec @author annotations:

The name of the author


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


16      library LibBridgeRouter {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16:16

```solidity
File: libraries/LibBytes.sol


9       library LibBytes {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9:9

```solidity
File: libraries/LibOracle.sol


16      library LibOracle {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16:16

```solidity
File: libraries/LibOrders.sol


20      library LibOrders {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20:20

```solidity
File: libraries/LibSRUtil.sol


18      library LibSRUtil {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18:18

```solidity
File: libraries/UniswapOracleLibrary.sol


21      library OracleLibrary {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21:21

</details>

## NC041 - Library declarations should have Natspec @notice annotations:

Explain to an end user what this does


<details>
<summary>Click to show 5 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


16      library LibBridgeRouter {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16:16

```solidity
File: libraries/LibBytes.sol


9       library LibBytes {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9:9

```solidity
File: libraries/LibOracle.sol


16      library LibOracle {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16:16

```solidity
File: libraries/LibOrders.sol


20      library LibOrders {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20:20

```solidity
File: libraries/LibSRUtil.sol


18      library LibSRUtil {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18:18

</details>

## NC042 - Library declarations should have Natspec @dev annotations:

Explain to a developer any extra details


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


16      library LibBridgeRouter {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L16:16

```solidity
File: libraries/LibBytes.sol


9       library LibBytes {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L9:9

```solidity
File: libraries/LibOracle.sol


16      library LibOracle {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L16:16

```solidity
File: libraries/LibOrders.sol


20      library LibOrders {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L20:20

```solidity
File: libraries/LibSRUtil.sol


18      library LibSRUtil {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L18:18

```solidity
File: libraries/UniswapOracleLibrary.sol


21      library OracleLibrary {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L21:21

</details>

## NC043 - Contract definitions should have Natspec @title annotations:

 title that should describe the contract


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

</details>

## NC044 - Contract definitions should have Natspec @author annotations:

The name of the author


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

</details>

## NC045 - Contract definitions should have Natspec @notice annotations:

Explain to an end user what this does


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

</details>

## NC046 - Contract definitions should have Natspec @dev annotations:

Explain to a developer any extra details


<details>
<summary>Click to show 4 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


18      contract BridgeRouterFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L18:18

```solidity
File: facets/PrimaryLiquidationFacet.sol


21      contract PrimaryLiquidationFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L21:21

```solidity
File: facets/RedemptionFacet.sol


21      contract RedemptionFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L21:21

```solidity
File: facets/ShortOrdersFacet.sol


18      contract ShortOrdersFacet is Modifiers {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L18:18

</details>

## NC047 - State variable declarations should have Natspec @notice annotations:

Explain to an end user what this does


```solidity
File: facets/BridgeRouterFacet.sol


26          address private immutable rethBridge;


27          address private immutable stethBridge;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27:27

```solidity
File: facets/PrimaryLiquidationFacet.sol


28          address private immutable dusd;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28:28

## NC048 - State variable declarations should have Natspec @dev annotations:

Explain to a developer any extra details


```solidity
File: facets/BridgeRouterFacet.sol


26          address private immutable rethBridge;


27          address private immutable stethBridge;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L27:27

```solidity
File: facets/PrimaryLiquidationFacet.sol


28          address private immutable dusd;


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L28:28

## NC049 - Functions should have Natspec @return annotations:

Documents the return variables of a contract’s function


<details>
<summary>Click to show 31 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


40          function getDethTotal(uint256 vault) external view nonReentrantView returns (uint256) {


51          function getBridges(uint256 vault) external view returns (address[] memory) {


156         function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {


169         function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169:169

```solidity
File: facets/PrimaryLiquidationFacet.sol


229         function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229:229

```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


382         function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382:382

```solidity
File: libraries/LibBridgeRouter.sol


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)


113         function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L113:113

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


19          function getOraclePrice(address asset) internal view returns (uint256) {


69          function baseOracleCircuitBreaker(


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


156         function getTime(address asset) internal view returns (uint256 creationTime) {


162         function getPrice(address asset) internal view returns (uint80 oraclePrice) {


168         function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168:168

```solidity
File: libraries/LibOrders.sol


30          function getOffsetTime() internal view returns (uint32 timeInSeconds) {


35          function convertCR(uint16 cr) internal pure returns (uint256) {


55          function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)


78          function isShort(STypes.Order memory order) internal pure returns (bool) {


362         function findPrevOfIncomingId(


420         function normalizeOrderType(O o) private pure returns (O newO) {


440         function getOrderId(


826         function findOrderHintId(


985         function min(uint256 a, uint256 b) internal pure returns (uint256) {


989         function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989:989

```solidity
File: libraries/LibSRUtil.sol


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L102:102

```solidity
File: libraries/UniswapOracleLibrary.sol


11          function observe(uint32[] calldata secondsAgos)


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

</details>

## NC050 - Functions should have Natspec @param annotations:

Documents a parameter just like in Doxygen (must be followed by parameter name)


<details>
<summary>Click to show 54 findings</summary>

```solidity
File: facets/BridgeRouterFacet.sol


29          constructor(address _rethBridge, address _stethBridge) {


148         function maybeUpdateYield(uint256 vault, uint88 amount) private {


156         function _getVault(address bridge) private view returns (uint256 vault, uint256 bridgePointer) {


169         function _ethConversion(uint256 vault, uint88 amount) private view returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L169:169

```solidity
File: facets/PrimaryLiquidationFacet.sol


30          constructor(address _dusd) {


96          function _checklowestSell(MTypes.PrimaryLiquidation memory m) private view {


229         function min88(uint256 a, uint88 b) private pure returns (uint88) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L229:229

```solidity
File: facets/RedemptionFacet.sol


31          function validRedemptionSR(STypes.ShortRecord storage shortRecord, address proposer, address shorter, uint256 minShortErc)


347         function claimRemainingCollateral(address asset, address redeemer, uint8 claimIndex, uint8 id)


368         function _claimRemainingCollateral(address asset, uint256 vault, address shorter, uint8 shortId) private {


382         function calculateRedemptionFee(address asset, uint88 colRedeemed, uint88 ercDebtRedeemed)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L382:382

```solidity
File: libraries/LibBridgeRouter.sol


21          function addDeth(uint256 vault, uint256 bridgePointer, uint88 amount) internal {


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)


113         function withdrawalFeePct(uint256 bridgePointer, address rethBridge, address stethBridge) internal view returns (uint256 fee) {


144         function transferBridgeCredit(address asset, address from, address to, uint88 collateral) internal {


198         function removeDeth(uint256 vault, uint88 amount, uint88 fee) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L198:198

```solidity
File: libraries/LibBytes.sol


11          function readProposalData(address SSTORE2Pointer, uint8 slateLength) internal view returns (MTypes.ProposalData[] memory) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L11:11

```solidity
File: libraries/LibOracle.sol


19          function getOraclePrice(address asset) internal view returns (uint256) {


69          function baseOracleCircuitBreaker(


117         function oracleCircuitBreaker(


131         function twapCircuitBreaker() private view returns (uint256 twapPriceInEth) {


149         function setPriceAndTime(address asset, uint256 oraclePrice, uint32 oracleTime) internal {


156         function getTime(address asset) internal view returns (uint256 creationTime) {


162         function getPrice(address asset) internal view returns (uint80 oraclePrice) {


168         function getSavedOrSpotOraclePrice(address asset) internal view returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L168:168

```solidity
File: libraries/LibOrders.sol


30          function getOffsetTime() internal view returns (uint32 timeInSeconds) {


35          function convertCR(uint16 cr) internal pure returns (uint256) {


40          function increaseSharesOnMatch(address asset, STypes.Order memory order, MTypes.Match memory matchTotal, uint88 eth) internal {


55          function currentOrders(mapping(address => mapping(uint16 => STypes.Order)) storage orders, address asset)


78          function isShort(STypes.Order memory order) internal pure returns (bool) {


82          function addBid(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


103         function addAsk(address asset, STypes.Order memory order, MTypes.OrderHint[] memory orderHintArray) internal {


173         function addOrder(


320         function _reuseOrderIds(


420         function normalizeOrderType(O o) private pure returns (O newO) {


628         function matchIncomingSell(address asset, STypes.Order memory incomingOrder, MTypes.Match memory matchTotal) private {


728         function _updateOracleAndStartingShort(address asset, uint16[] memory shortHintArray) private {


783         function updateOracleAndStartingShortViaThreshold(


803         function updateOracleAndStartingShortViaTimeBidOnly(address asset, uint16[] memory shortHintArray) internal {


810         function updateStartingShortIdViaShort(address asset, STypes.Order memory incomingShort) internal {


826         function findOrderHintId(


854         function cancelBid(address asset, uint16 id) internal {


868         function cancelAsk(address asset, uint16 id) internal {


882         function cancelShort(address asset, uint16 id) internal {


955         function handlePriceDiscount(address asset, uint80 price) internal {


985         function min(uint256 a, uint256 b) internal pure returns (uint256) {


989         function max(uint256 a, uint256 b) internal pure returns (uint256) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L989:989

```solidity
File: libraries/LibSRUtil.sol


22          function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)


102         function checkRecoveryModeViolation(address asset, uint256 shortRecordCR, uint256 oraclePrice)


124         function transferShortRecord(address from, address to, uint40 tokenId) internal {


151         function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L151:151

```solidity
File: libraries/UniswapOracleLibrary.sol


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:47

</details>

## NC051 - Missing events in sensitive functions:

Sensitive setter functions in smart contracts often alter critical state variables. Without events emitted in these functions, external observers or dApps cannot easily track or react to these state changes. Missing events can obscure contract activity, hampering transparency and making integration more challenging. To resolve this, incorporate appropriate event emissions within these functions. Events offer an efficient way to log crucial changes, aiding in real-time tracking and post-transaction verification..


```solidity
File: facets/PrimaryLiquidationFacet.sol


122         function _setLiquidationStruct(address asset, address shorter, uint8 id, uint16 shortOrderId)
123             private
124             returns (MTypes.PrimaryLiquidation memory)
125         {
126             LibShortRecord.updateErcDebt(asset, shorter, id);
127             {
128                 MTypes.PrimaryLiquidation memory m;
129                 m.asset = asset;
130                 m.short = s.shortRecords[asset][shorter][id];
131                 m.shortOrderId = shortOrderId;
132                 m.vault = s.asset[asset].vault;
133                 m.shorter = shorter;
134                 m.penaltyCR = LibAsset.penaltyCR(asset);
135                 m.oraclePrice = LibOracle.getPrice(asset);
136                 m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
137                 m.forcedBidPriceBuffer = LibAsset.forcedBidPriceBuffer(asset);
138                 m.callerFeePct = LibAsset.callerFeePct(m.asset);
139                 m.tappFeePct = LibAsset.tappFeePct(m.asset);
140                 m.ethDebt = m.short.ercDebt.mul(m.oraclePrice).mul(m.forcedBidPriceBuffer).mul(1 ether + m.tappFeePct + m.callerFeePct); // ethDebt accounts for forcedBidPriceBuffer and potential fees
141                 return m;
142             }
143         }


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L122:143


## NC052 - Unused file:

The file is never imported by any other source file. If the file is needed for tests, it should be moved to a test directory


<details>
<summary>Click to show 6 findings</summary>

```solidity
File: libraries/LibBridgeRouter.sol


/// @auditbase `gitio/libraries/LibBridgeRouter.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L1:1

```solidity
File: libraries/LibBytes.sol


/// @auditbase `gitio/libraries/LibBytes.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBytes.sol#L1:1

```solidity
File: libraries/LibOracle.sol


/// @auditbase `gitio/libraries/LibOracle.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L1:1

```solidity
File: libraries/LibOrders.sol


/// @auditbase `gitio/libraries/LibOrders.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L1:1

```solidity
File: libraries/LibSRUtil.sol


/// @auditbase `gitio/libraries/LibSRUtil.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L1:1

```solidity
File: libraries/UniswapOracleLibrary.sol


/// @auditbase `gitio/libraries/UniswapOracleLibrary.sol` not used in any contracts


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L1:1

</details>

## NC053 - Consider only defining one library/interface/contract per sol file:

Combining multiple libraries, interfaces, or contracts in a single  file can lead to clutter, reduced readability, and versioning issues. **Resolution**: Adopt the best practice of defining only one library, interface, or contract per Solidity file. This modular approach enhances clarity, simplifies unit testing, and streamlines code review. Furthermore, segregating components makes version management easier, as updates to one component won't necessitate changes to a file housing multiple unrelated components. Structured file management can further assist in avoiding naming collisions and ensure smoother integration into larger systems or DApps.


```solidity
File: libraries/UniswapOracleLibrary.sol


10      interface IUniswapV3Pool {
11          function observe(uint32[] calldata secondsAgos)
12              external
13              view
14              returns (int56[] memory tickCumulatives, uint160[] memory secondsPerLiquidityCumulativeX128s);
15      }
16      
17      /* solhint-disable */
18      
19      /// @title Oracle library
20      /// @notice Provides functions to integrate with V3 pool oracle
21      library OracleLibrary {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L10:21

## NC054 - Use a struct to encapsulate multiple function parameters:

Using a struct to encapsulate multiple parameters in Solidity functions can significantly enhance code readability and maintainability. Instead of passing a long list of arguments, which can be error-prone and hard to manage, a struct allows grouping related data into a single, coherent entity. This approach simplifies function signatures and makes the code more organized. It also enhances code clarity, as developers can easily understand the relationship between the parameters. Moreover, it aids in future code modifications and expansions, as adding or modifying a parameter only requires changes in the struct definition, rather than in every function that uses these parameters.


<details>
<summary>Click to show 14 findings</summary>

```solidity
File: facets/PrimaryLiquidationFacet.sol


47          function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray, uint16 shortOrderId)
48              external
49              isNotFrozen(asset)
50              nonReentrant
51              onlyValidShortRecord(asset, shorter, id)
52              returns (uint88, uint88)
53          {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L47:53

```solidity
File: facets/RedemptionFacet.sol


224         function disputeRedemption(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId)
225             external
226             isNotFrozen(asset)
227             nonReentrant
228         {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224:228

```solidity
File: facets/ShortOrdersFacet.sol


35          function createLimitShort(
36              address asset,
37              uint80 price,
38              uint88 ercAmount,
39              MTypes.OrderHint[] memory orderHintArray,
40              uint16[] memory shortHintArray,
41              uint16 shortOrderCR
42          ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35:42

```solidity
File: libraries/LibBridgeRouter.sol


39          function assessDeth(uint256 vault, uint256 bridgePointer, uint88 amount, address rethBridge, address stethBridge)
40              internal
41              returns (uint88)
42          {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibBridgeRouter.sol#L39:42

```solidity
File: libraries/LibOracle.sol


69          function baseOracleCircuitBreaker(
70              uint256 protocolPrice,
71              uint80 roundId,
72              int256 chainlinkPrice,
73              uint256 timeStamp,
74              uint256 chainlinkPriceInEth
75          ) private view returns (uint256 _protocolPrice) {


117         function oracleCircuitBreaker(
118             uint80 roundId,
119             uint80 baseRoundId,
120             int256 chainlinkPrice,
121             int256 baseChainlinkPrice,
122             uint256 timeStamp,
123             uint256 baseTimeStamp
124         ) private view {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol#L117:124

```solidity
File: libraries/LibOrders.sol


260         function verifySellId(
261             mapping(address => mapping(uint16 => STypes.Order)) storage orders,
262             address asset,
263             uint16 _prevId,
264             uint256 _newPrice,
265             uint16 _nextId
266         ) private view returns (int256 direction) {


320         function _reuseOrderIds(
321             mapping(address => mapping(uint16 => STypes.Order)) storage orders,
322             address asset,
323             uint16 id,
324             uint16 prevHEAD,
325             O cancelledOrMatched
326         ) private {


402         function verifyId(
403             mapping(address => mapping(uint16 => STypes.Order)) storage orders,
404             address asset,
405             uint16 prevId,
406             uint256 newPrice,
407             uint16 nextId,
408             O orderType
409         ) internal view returns (int256 direction) {


440         function getOrderId(
441             mapping(address => mapping(uint16 => STypes.Order)) storage orders,
442             address asset,
443             int256 direction,
444             uint16 hintId,
445             uint256 _newPrice,
446             O orderType
447         ) internal view returns (uint16 _hintId) {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol#L440:447

```solidity
File: libraries/LibSRUtil.sol


22          function disburseCollateral(address asset, address shorter, uint88 collateral, uint256 dethYieldRate, uint32 updatedAt)
23              internal
24          {


49          function checkCancelShortOrder(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
50              internal
51              returns (bool isCancelled)
52          {


72          function checkShortMinErc(address asset, SR initialStatus, uint16 shortOrderId, uint8 shortRecordId, address shorter)
73              internal
74              returns (bool isCancelled)
75          {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibSRUtil.sol#L72:75

```solidity
File: libraries/UniswapOracleLibrary.sol


47          function estimateTWAP(uint128 amountIn, uint32 secondsAgo, address pool, address baseToken, address quoteToken)
48              internal
49              view
50              returns (uint256 amountOut)
51          {


```

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/UniswapOracleLibrary.sol#L47:51

</details>