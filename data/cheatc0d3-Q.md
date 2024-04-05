# QA Report: DittoEth

## L-01 Inaccurate Gas Cost Calculation

The gas cost calculation uint256 gasUsed = startGas - gasleft(); assumes that the gasleft() function returns an accurate value. However, there is a known issue with the gasleft() function in certain Ethereum virtual machine (EVM) implementations, where it might return an inaccurate value.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L196

```solidity
uint256 gasUsed = startGas - gasleft();
```

[Source: https://github.com/foundry-rs/foundry/issues/5621](https://github.com/foundry-rs/foundry/issues/5621)

## L-02 Potential Rounding Issues when calculating m.short.ercDebt

The calculation of m.short.ercDebt involves division operations, which might lead to rounding errors if the divisor is not a power of 2. It might be worth considering using a dedicated fixed-point or decimal math library to handle these calculations more precisely.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/PrimaryLiquidationFacet.sol#L180

```solidity
m.short.ercDebt = uint88(m.ethDebt.div(_bidPrice.mul(1 ether + m.callerFeePct + m.tappFeePct))); // @dev(safe-cast)

```

## L-03 Reduced Flexibility in Pricing

The uint80 type limits the maximum representable price, potentially restricting the system's ability to accurately price assets during periods of extreme volatility or when the underlying asset's value significantly increases.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol#L40

```solidity
function createBid(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray,
        uint16[] calldata shortHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant returns (uint88 ethFilled, uint88 ercAmountLeft) {
        LibOrders.updateOracleAndStartingShortViaTimeBidOnly(asset, shortHintArray);

        return _createBid(msg.sender, asset, price, ercAmount, isMarketOrder, orderHintArray, shortHintArray);
    }
```
Consider using uint256 for price representation. This data type not only eliminates the issues related to the upper limit but also provides ample room for precision. The trade-off in increased gas costs for operations involving uint256 should be evaluated against the benefits of added flexibility and precision.

## L-04 Inadequate Risk Management Due to Limited Collateral Ratio Precision

Inadequate precision in collateral ratios can lead to imprecise risk assessments, potentially exposing the platform to higher risks of defaults or liquidations in volatile market conditions.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35

```solidity
function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
 >>     uint16 shortOrderCR
    )
```
Consider upgrading the data type for collateral ratios from uint16 to a higher precision type like uint256. While this increases gas costs, the trade-off for precision and safety might be justified, especially for operations critical to financial stability.

## L-05 Precision loss due to rounding errors

The `_ethConversion` function has the potential for a rounding error when dealing with the conversion between deth (decimal ether) and ether.

In the case where `dethTotalNew < dethTotal` (negative yield), the function calculates the conversion rate using the following line:

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L179

```solidity
return amount.mul(dethTotalNew).divU88(dethTotal);
```

This line performs the following operations:

1. `amount.mul(dethTotalNew)`: Multiplies the `amount` by the new total deth value (`dethTotalNew`).
2. `divU88(dethTotal)`: Divides the result of the previous multiplication by the old total deth value (`dethTotal`).

The issue arises from the fact that integer division in Solidity truncates the result towards zero, potentially leading to a rounding error. This rounding error could result in a loss of precision, especially when dealing with small values or fractions.

### Mitigation

1. Convert `dethTotalNew` and `dethTotal` to a higher precision data type (e.g., `uint256`) before performing the calculation.
2. Use a library function or custom logic that handles rounding more accurately, such as rounding up or down based on specific rules.


## L-06 Short Record ID Limitation

The uint8 type for shortRecordId inherently limits the number of short positions to 256. Active traders who wish to take multiple short positions may be restricted by the maximum number of positions available, leading to a poor user experience and potentially driving users to competing platforms.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35

```solidity
function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
        MTypes.CreateLimitShortParam memory p;
        STypes.Asset storage Asset = s.asset[asset];
        STypes.Order memory incomingShort;

        // @dev create "empty" SR. Fail early.
  >>     incomingShort.shortRecordId = LibShortRecord.createShortRecord(asset, msg.sender, SR.Closed, 0, 0, 0, 0, 0);

        uint256 cr = LibOrders.convertCR(shortOrderCR);
        if ((shortOrderCR + C.BID_CR) < Asset.initialCR || cr >= C.CRATIO_MAX_INITIAL) {
            revert Errors.InvalidCR();
        }
```

### Mitigation

Upgrade the shortRecordId from uint8 to a larger data type, such as uint256. This change significantly increases the number of available IDs, virtually eliminating the limitation.

## L-07 Dos Vector through Hint Mechanism

A flood of near-identical orders could overwhelm the system, leading to increased computational and storage costs, slower transaction processing times, and a degraded user experience. Users could exploit the hint system to place multiple orders with minimal differences, potentially manipulating market prices or order book depth to their advantage.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35

```solidity
function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    )
```

Introduce rate limiting for order submissions per account to prevent users from flooding the system with orders. This would limit the number of orders an account can create within a certain timeframe, reducing the potential for abuse.


## L-08 Outdated Hints Due to Dynamic Oracle Price Volatility

Given the volatile nature of oracle prices, even a hint that is accurate at the time of submission could quickly become outdated, leading to failed transactions if the price moves outside of the allowed 0.5% range before the transaction is mined. Users intending to execute shorts based on specific price points can incur financial losses if their transactions fail after the price moves unfavorably.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/ShortOrdersFacet.sol#L35

```solidity
function createLimitShort(
        address asset,
        uint80 price,
        uint88 ercAmount,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray,
        uint16 shortOrderCR
    )
```

Introduce smart contract mechanisms such as commit-reveal schemes or sub-second transaction batching to mitigate the risk of frontrunning.


## L-09 Lack of Explicit Balance Checks

The potential issue in the provided function `withdrawTapp` is the lack of a check to ensure that the contract's balance of the token being withdrawn (LST or dETH) is sufficient to cover the requested withdrawal amount (`dethAmount`).

The function calculates the Ethereum amount (`ethAmount`) to be withdrawn from the bridge based on the provided `dethAmount`. However, before calling the `withdraw` function on the bridge contract, it should verify that the contract's balance of dETH (`s.vaultUser[vault][address(this)].ethEscrowed`) is greater than or equal to `dethAmount`. Otherwise, it may attempt to withdraw more dETH than it holds, potentially causing a revert or other undesired behavior.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L133

```solidity
function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
        if (dethAmount == 0) revert Errors.ParameterIsZero();

        (uint256 vault,) = _getVault(bridge);
        uint88 ethAmount = _ethConversion(vault, dethAmount);

        s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
        s.vault[vault].dethTotal -= dethAmount;

        IBridge(bridge).withdraw(msg.sender, ethAmount);
        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
    }
```

### Mitigation

Add a check for the contract's dETH balance before updating the state variables and calling the bridge's `withdraw` function. Here's an example of how you could modify the function:


```solidity
function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
    if (dethAmount == 0) revert Errors.ParameterIsZero();

    (uint256 vault, ) = _getVault(bridge);
    uint88 ethAmount = _ethConversion(vault, dethAmount);

    // Check if the contract has sufficient dETH balance
    if (s.vaultUser[vault][address(this)].ethEscrowed < dethAmount) {
        revert Errors.InsufficientBalance();
    }

    s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
    s.vault[vault].dethTotal -= dethAmount;

    IBridge(bridge).withdraw(msg.sender, ethAmount);

    emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
}
```



## L-10 Check effects Violation

The function is updating the `s.vaultUser[vault][address(this)].ethEscrowed` and `s.vault[vault].dethTotal` state variables before calling the `IBridge(bridge).withdraw(msg.sender, ethAmount)` function. This could lead to potential issues if the `withdraw` function on the bridge contract reverts or fails for any reason.

If the `withdraw` function reverts, the state variables would have already been updated, leading to an inconsistent state. The contract's dETH balance would have been deducted, but the withdrawal might not have been successful.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L133

```solidity
function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
        if (dethAmount == 0) revert Errors.ParameterIsZero();

        (uint256 vault,) = _getVault(bridge);
        uint88 ethAmount = _ethConversion(vault, dethAmount);

        s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
        s.vault[vault].dethTotal -= dethAmount;

        IBridge(bridge).withdraw(msg.sender, ethAmount);
        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
    }
```

### Mitigation

Follow the "Checks-Effects-Interactions" pattern:

```solidity
function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
    if (dethAmount == 0) revert Errors.ParameterIsZero();

    (uint256 vault, ) = _getVault(bridge);
    uint88 ethAmount = _ethConversion(vault, dethAmount);

    // Check if the contract has sufficient dETH balance
    if (s.vaultUser[vault][address(this)].ethEscrowed < dethAmount) {
        revert Errors.InsufficientBalance();
    }

    // Call the withdraw function on the bridge contract
    bool success = IBridge(bridge).withdraw(msg.sender, ethAmount);

    // Update state variables only if the withdraw was successful
    if (success) {
        s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
        s.vault[vault].dethTotal -= dethAmount;
        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
    } else {
        // Handle failure case, e.g., revert or emit an event
        revert Errors.WithdrawFailed();
    }
}
```

Here the `IBridge(bridge).withdraw(msg.sender, ethAmount)` function call is made first, and its return value is stored in the `success` variable. The state variables are updated only if the `withdraw` function call was successful (`success` is true).

If the `withdraw` function reverts or fails, the state variables remain unchanged, and the function can handle the failure case appropriately.


## L-11 Validation of Order Hints

Before utilizing orderHintArray and shortHintArray, validate their accuracy to ensure they reflect the current order book state.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L77

```solidity
function _createBid(
        address sender,
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] memory orderHintArray,
        uint16[] memory shortHintArray
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
        uint256 eth = ercAmount.mul(price);
        if (eth < LibAsset.minBidEth(asset)) revert Errors.OrderUnderMinimumSize();

        STypes.Asset storage Asset = s.asset[asset];
        if (s.vaultUser[Asset.vault][sender].ethEscrowed < eth) revert Errors.InsufficientETHEscrowed();

        STypes.Order memory incomingBid;
        incomingBid.addr = sender;
        incomingBid.price = price;
        incomingBid.ercAmount = ercAmount;
        incomingBid.id = Asset.orderIdCounter;
        incomingBid.orderType = isMarketOrder ? O.MarketBid : O.LimitBid;
        incomingBid.creationTime = LibOrders.getOffsetTime();

        MTypes.BidMatchAlgo memory b;
        b.askId = s.asks[asset][C.HEAD].nextId;
        // @dev setting initial shortId to match "backwards" (See _shortDirectionHandler() below)
        b.shortHintId = b.shortId = Asset.startingShortId;

        STypes.Order memory lowestSell = _getLowestSell(asset, b);
        if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
            // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
            b.shortHintId = b.shortId = Asset.startingShortId;
            b.oraclePrice = LibOracle.getPrice(asset);
            return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
        } else {
            // @dev no match, add to market if limit order
            LibOrders.addBid(asset, incomingBid, orderHintArray);
            return (0, ercAmount);
        }
    }
```

### Mitigation
Ensure that the lengths of orderHintArray and shortHintArray match.

```solidity
if (orderHintArray.length != shortHintArray.length) {
        revert Errors.InvalidHintArrays();
    }
```

## L-12 Check for Valid Price and Amounts in _createBid

Ensure price and ercAmount are within reasonable ranges to avoid impractical orders.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L77

### Mitigation

Add a check to ensure that both the price and the amount are greater than zero. If either of them is zero, it implies an invalid price or amount, and the function reverts with an error indicating this.

```solidity
if (price == 0 || ercAmount == 0) {
        revert Errors.InvalidPriceOrAmount();
    }
```

## L-13 Loop Efficiency and Termination in bidMatchAlgo to prevent Out of Gas Errorss

Instead of an infinite loop, you can set a maximum number of iterations or a condition that guarantees the loop will terminate. This prevents the function from running indefinitely.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L130

```solidity
function bidMatchAlgo(
        address asset,
        STypes.Order memory incomingBid,
        MTypes.OrderHint[] memory orderHintArray,
        MTypes.BidMatchAlgo memory b
    ) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
        uint256 minBidEth = LibAsset.minBidEth(asset);
        MTypes.Match memory matchTotal;

        while (true) {
            // @dev Handles scenario when no sells left after partial fill
            if (b.askId == C.TAIL && b.shortId == C.TAIL) {
                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
                    LibOrders.addBid(asset, incomingBid, orderHintArray);
                }
                return matchIncomingBid(asset, incomingBid, matchTotal, b);
            }

            STypes.Order memory lowestSell = _getLowestSell(asset, b);

            if (incomingBid.price >= lowestSell.price) {
                // Consider bid filled if only dust amount left
                if (incomingBid.ercAmount.mul(lowestSell.price) == 0) {
                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
                }
                matchlowestSell(asset, lowestSell, incomingBid, matchTotal);
                if (incomingBid.ercAmount > lowestSell.ercAmount) {
                    incomingBid.ercAmount -= lowestSell.ercAmount;
                    lowestSell.ercAmount = 0;
                    if (lowestSell.isShort()) {
                        b.matchedShortId = lowestSell.id;
                        b.prevShortId = lowestSell.prevId;
                        LibOrders.matchOrder(s.shorts, asset, lowestSell.id);
                        _shortDirectionHandler(asset, lowestSell, incomingBid, b);
                    } else {
                        b.matchedAskId = lowestSell.id;
                        LibOrders.matchOrder(s.asks, asset, lowestSell.id);
                        b.askId = lowestSell.nextId;
                    }
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
                    } else {
                        lowestSell.ercAmount -= incomingBid.ercAmount;
                        if (lowestSell.isShort()) {
                            b.dustShortId = lowestSell.id;
                            STypes.Order storage lowestShort = s.shorts[asset][lowestSell.id];
                            lowestShort.ercAmount = lowestSell.ercAmount;
                        } else {
                            b.dustAskId = lowestSell.id;
                            s.asks[asset][lowestSell.id].ercAmount = lowestSell.ercAmount;
                        }
                        // Check reduced dust threshold for existing limit orders
                        if (lowestSell.ercAmount.mul(lowestSell.price) >= LibAsset.minAskEth(asset).mul(C.DUST_FACTOR)) {
                            b.dustShortId = b.dustAskId = 0;
                        }
                    }
                    incomingBid.ercAmount = 0;
                    return matchIncomingBid(asset, incomingBid, matchTotal, b);
                }
            } else {
                if (incomingBid.ercAmount.mul(incomingBid.price) >= minBidEth) {
                    LibOrders.addBid(asset, incomingBid, orderHintArray);
                }
                return matchIncomingBid(asset, incomingBid, matchTotal, b);
            }
        }
    }
```

### Mitigation
Set a maximum number of loop iterations.

```solidity
function bidMatchAlgo(
    address asset,
    STypes.Order memory incomingBid,
    MTypes.OrderHint[] memory orderHintArray,
    MTypes.BidMatchAlgo memory b
) private returns (uint88 ethFilled, uint88 ercAmountLeft) {
    uint256 minBidEth = LibAsset.minBidEth(asset);
    MTypes.Match memory matchTotal;
    uint256 loopCount = 0;

    while (loopCount < MAX_LOOP_ITERATIONS) { 
        loopCount++;
```
## L-14 Check for Asset Oracle Validity

Given that asset prices is tied to oracles, ensuring the oracle is reporting and is within expected bounds can be crucial.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L106C9-L117C6

```solidity
if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
            // @dev if match and match price is gt .5% to saved oracle in either direction, update startingShortId
            LibOrders.updateOracleAndStartingShortViaThreshold(asset, LibOracle.getPrice(asset), incomingBid, shortHintArray);
            b.shortHintId = b.shortId = Asset.startingShortId;
            b.oraclePrice = LibOracle.getPrice(asset);
            return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
        } else {
            // @dev no match, add to market if limit order
            LibOrders.addBid(asset, incomingBid, orderHintArray);
            return (0, ercAmount);
        }
    }
```

### Mitigation

After retrieving the oracle price (oraclePrice), calculate the acceptable price threshold (priceThreshold) as 0.5% deviation from the oracle price. Then, before proceeding with the match, check if the incoming bid price deviates significantly from the oracle price. If it does, the transaction is reverted with an appropriate error message.

```solidity
// Get the oracle price for the asset
uint256 oraclePrice = LibOracle.getPrice(asset);

// Define the acceptable price threshold as 0.5% deviation from the oracle price
uint256 priceThreshold = oraclePrice * 5 / 1000; // 0.5% of oracle price

if (incomingBid.price >= lowestSell.price && (lowestSell.orderType == O.LimitAsk || lowestSell.orderType == O.LimitShort)) {
    // Check if the match price is within the acceptable range (+/- 0.5%)
    if (incomingBid.price > oraclePrice + priceThreshold || incomingBid.price < oraclePrice - priceThreshold) {
        revert("Match price deviates significantly from the oracle price");
    }

    // Update the startingShortId if match and match price is within the threshold
    LibOrders.updateOracleAndStartingShortViaThreshold(asset, oraclePrice, incomingBid, shortHintArray);
    b.shortHintId = b.shortId = Asset.startingShortId;
    b.oraclePrice = oraclePrice;
    
    // Call bid matching algorithm
    return bidMatchAlgo(asset, incomingBid, orderHintArray, b);
} else {
    // No match, add to market if it's a limit order
    LibOrders.addBid(asset, incomingBid, orderHintArray);
    return (0, ercAmount);
}

```

## L-15 Order ID Counter Validity

Lack of check to ensure that the orderIdCounter has not reached its maximum value before assigning incomingShort.id

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/DataTypes.sol#L99

```solidity
uint16 orderIdCounter; // max is uint16 but need to throw/handle that?
```

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L64C9-L70C67

```solidity
incomingShort.addr = msg.sender;
        incomingShort.price = price;
        incomingShort.ercAmount = ercAmount;
        incomingShort.id = Asset.orderIdCounter;
        incomingShort.orderType = O.LimitShort;
        incomingShort.creationTime = LibOrders.getOffsetTime();
        incomingShort.shortOrderCR = shortOrderCR; // 170 -> 1.70x

```

Verify that the orderIdCounter has not reached an invalid state, which could occur due to unchecked increments.

```solidity
if (s.asset[asset].orderIdCounter >= type(uint16).max) {
    revert("Order ID counter at max value");
}
```

## L-16 Clustering of Orders at Thresholds

The +1.0% rule might inadvertently create artificial clusters of orders around certain price points as traders attempt to position their orders within the threshold for matching. This clustering could distort the natural distribution of orders and prices in the market.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L941C8-L949C10

```solidity
 // Approximating the startingShortId, rather than expecting exact match
        if (id == Asset.startingShortId) {
            uint256 savedPrice = LibOracle.getPrice(asset);
            uint256 prevPrice = s.shorts[asset][shortOrder.prevId].price;
            if (prevPrice >= savedPrice) {
                Asset.startingShortId = shortOrder.prevId;
            } else {
                Asset.startingShortId = shortOrder.nextId;
            }
        }

        cancelOrder(s.shorts, asset, id);
    }
```


## L-17 Manually canceling orders might not be efficient way to manage order ids

The manual process for the DAO or admin to decide on canceling orders could be slow, especially if it requires consensus or voting. During this time, the spam orders might already have achieved their disruptive effect.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/OrdersFacet.sol#L66

```solidity
function cancelOrderFarFromOracle(address asset, O orderType, uint16 lastOrderId, uint16 numOrdersToCancel)
        external
        onlyAdminOrDAO
        onlyValidAsset(asset)
        nonReentrant
    {
        if (s.asset[asset].orderIdCounter < 65000) revert Errors.OrderIdCountTooLow();

        if (numOrdersToCancel > 1000) revert Errors.CannotCancelMoreThan1000Orders();

        if (orderType == O.LimitBid && s.bids[asset][lastOrderId].nextId == C.TAIL) {
            cancelManyBids(asset, lastOrderId, numOrdersToCancel);
        } else if (orderType == O.LimitAsk && s.asks[asset][lastOrderId].nextId == C.TAIL) {
            cancelManyAsks(asset, lastOrderId, numOrdersToCancel);
        } else if (orderType == O.LimitShort && s.shorts[asset][lastOrderId].nextId == C.TAIL) {
            cancelManyShorts(asset, lastOrderId, numOrdersToCancel);
        } else {
            revert Errors.NotLastOrder();
        }
    }
```


## L-18 minimum ETH amount Spam order Protection should be dynamic

The economics of a spam attack could change over time, particularly as the value of ETH fluctuates. What might be uneconomical at one point could become viable if the costs associated with making orders are reduced relative to the potential impact of the attack.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/AskOrdersFacet.sol#L37

```solidity
function createAsk(
        address asset,
        uint80 price,
        uint88 ercAmount,
        bool isMarketOrder,
        MTypes.OrderHint[] calldata orderHintArray
    ) external isNotFrozen(asset) onlyValidAsset(asset) nonReentrant {
        uint256 eth = price.mul(ercAmount);
        uint256 minAskEth = LibAsset.minAskEth(asset);
        if (eth < minAskEth) revert Errors.OrderUnderMinimumSize();

        if (s.assetUser[asset][msg.sender].ercEscrowed < ercAmount) revert Errors.InsufficientERCEscrowed();

```
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L59

```solidity
if (ercAmount < p.minShortErc || p.eth < p.minAskEth) revert Errors.OrderUnderMinimumSize();
```

## L-19 Implement batch processing of yield distributions

The system lacks a mechanism that allows for batch processing of yield distribution to multiple assets or shortRecords in a single transaction.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L148

```solidity
function maybeUpdateYield(uint256 vault, uint88 amount) private {
        uint88 dethTotal = s.vault[vault].dethTotal;
        if (dethTotal > C.BRIDGE_YIELD_UPDATE_THRESHOLD && amount.div(dethTotal) > C.BRIDGE_YIELD_PERCENT_THRESHOLD) {
            vault.updateYield();
        }
    }
```

### Mitigation

Introduce a new function or extend the current maybeUpdateYield function to handle batch processing. This function should accept arrays of vault identifiers and corresponding amounts, allowing the system to update yield for multiple assets or shortRecords in a single transaction. This approach significantly reduces gas costs and improves operational efficiency, especially during periods of high activity.

```solidity
function batchUpdateYield(uint256[] calldata vaults, uint88[] calldata amounts) external onlyDAO {
    require(vaults.length == amounts.length, "Mismatched inputs");

    for (uint256 i = 0; i < vaults.length; i++) {
        uint256 vault = vaults[i];
        uint88 amount = amounts[i];

        // Implement yield update logic here
        // For example:
        vault.updateYield(); 
    }

    // Emit an event or perform additional logic as needed
}

```

## L-20 Partial Exit Strategies Can be Improved

Enhance the flexibility of the partial exit strategy by allowing users to specify the exact amount of ercDebt they wish to exit, rather than being constrained by a binary choice between full exit and minimal reduction. This could help users manage their risk more granularly.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L87

```solidity
function exitShortErcEscrowed(address asset, uint8 id, uint88 buybackAmount, uint16 shortOrderId)
        external
        isNotFrozen(asset)
        nonReentrant
        onlyValidShortRecord(asset, msg.sender, id)
    {
        STypes.Asset storage Asset = s.asset[asset];
        STypes.ShortRecord storage short = s.shortRecords[asset][msg.sender][id];
        SR initialStatus = short.status;

        short.updateErcDebt(asset);
        uint256 ercDebt = short.ercDebt;
        if (buybackAmount == 0 || buybackAmount > ercDebt) revert Errors.InvalidBuyback();

        {
            STypes.AssetUser storage AssetUser = s.assetUser[asset][msg.sender];
            if (AssetUser.ercEscrowed < buybackAmount) revert Errors.InsufficientERCEscrowed();

            AssetUser.ercEscrowed -= buybackAmount;
        }

        Asset.ercDebt -= buybackAmount;
        // refund the rest of the collateral if ercDebt is fully paid back
        if (ercDebt == buybackAmount) {
            uint88 collateral = short.collateral;
            s.vaultUser[Asset.vault][msg.sender].ethEscrowed += collateral;
            LibSRUtil.disburseCollateral(asset, msg.sender, collateral, short.dethYieldRate, short.updatedAt);

            LibShortRecord.deleteShortRecord(asset, msg.sender, id);
        } else {
            short.ercDebt -= buybackAmount;
        }

        LibSRUtil.checkShortMinErc({
            asset: asset,
            initialStatus: initialStatus,
            shortOrderId: shortOrderId,
            shortRecordId: id,
            shorter: msg.sender
        });

        emit Events.ExitShortErcEscrowed(asset, msg.sender, id, buybackAmount);
    }
```

## L-21 Introduce Automated Collateral Top-Ups

Implement a feature that allows users to opt-in to automatic collateral top-ups from their wallet or a designated contract when their CR approaches the liquidation threshold. This can help users maintain their positions during volatile market conditions without requiring constant monitoring.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56

### Mitigation

Example of implementation

```solidity
uint256 public constant AUTO_TOP_UP_THRESHOLD = 1.2 ether; // Collateral ratio threshold for auto top-up

// Add a new flag to track if the user has opted-in to auto top-up
mapping(address => mapping(address => bool)) public userAutoTopUpEnabled;

function optInToAutoTopUp(address asset, bool enabled) external {
    userAutoTopUpEnabled[asset][msg.sender] = enabled;
}
```
The `AUTO_TOP_UP_THRESHOLD` constant defines the collateral ratio threshold at which the auto top-up feature will be triggered. In this example, it's set to 1.2x.

The `userAutoTopUpEnabled` mapping tracks whether a user has opted-in to the auto top-up feature for a specific asset. The `optInToAutoTopUp()` function allows users to enable or disable the feature.

```solidity
function proposeRedemption(
    address asset,
    MTypes.ProposalInput[] calldata proposalInput,
    uint88 redemptionAmount,
    uint88 maxRedemptionFee
) external isNotFrozen(asset) nonReentrant {
    // ... existing proposeRedemption logic

    // Check if the user has opted-in to auto top-up
    if (userAutoTopUpEnabled[asset][msg.sender]) {
        // Calculate the user's current collateral ratio
        uint256 currentCR = _getCurrentCollateralRatio(asset, msg.sender);

        // Trigger auto top-up if the CR is below the threshold
        if (currentCR < AUTO_TOP_UP_THRESHOLD) {
            _autoTopUpCollateral(asset, msg.sender, currentCR);
        }
    }

    // ... continue with existing proposeRedemption logic
}
```
In the `proposeRedemption()` function, we first check if the user has opted-in to the auto top-up feature. If so, we calculate the user's current collateral ratio using the `_getCurrentCollateralRatio()` helper function. If the collateral ratio is below the `AUTO_TOP_UP_THRESHOLD`, we call the `_autoTopUpCollateral()` function to trigger the collateral top-up process.

```solidity
function _autoTopUpCollateral(address asset, address shorter, uint256 currentCR) private {
    // Calculate the additional collateral required to reach the safe CR threshold
    uint256 safeCollateralRatio = 1.5 ether;
    uint88 additionalCollateral = _calculateAdditionalCollateral(asset, shorter, currentCR, safeCollateralRatio);

    // Call the designated contract to perform the collateral top-up
    _userTopUpCollateral(asset, shorter, additionalCollateral);
}

function _calculateAdditionalCollateral(
    address asset,
    address shorter,
    uint256 currentCR,
    uint256 safeCollateralRatio
) private view returns (uint88) {
    STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter];
    uint256 oraclePrice = LibOracle.getPrice(asset);
    uint256 currentCollateral = shortRecord.collateral;
    uint256 ercDebt = shortRecord.ercDebt;

    // Calculate the additional collateral required to reach the safe CR threshold
    uint256 targetCollateral = ercDebt.mulU256(safeCollateralRatio) / 1 ether;
    uint256 additionalCollateral = targetCollateral > currentCollateral ? targetCollateral - currentCollateral : 0;

    return uint88(additionalCollateral);
}

function _userTopUpCollateral(address asset, address shorter, uint88 additionalCollateral) private {
    // Allow the designated contract to call this function to add collateral to the user's short position
    STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter];
    shortRecord.collateral += additionalCollateral;

    // Emit an event to notify the user of the top-up
    emit Events.AutoCollateralTopUp(asset, shorter, additionalCollateral);
}
```
The `_autoTopUpCollateral()` function calculates the additional collateral required to bring the user's collateral ratio back to a safe level (e.g., 1.5x) using the `_calculateAdditionalCollateral()` helper function. It then calls the `_userTopUpCollateral()` function, which allows a designated contract to add the additional collateral to the user's short position. This function also emits an `AutoCollateralTopUp` event to notify the user of the top-up.

The `_calculateAdditionalCollateral()` function takes the current collateral ratio, the target safe collateral ratio, and the user's short position details to determine the amount of additional collateral required.

The `_userTopUpCollateral()` function updates the user's short record with the additional collateral and emits an event to notify the user.

This implementation provides a way for users to opt-in to an automated collateral top-up feature, which can help them maintain their positions during volatile market conditions without requiring constant monitoring.

## L-22 Introduce Micro Liquidation Pools to Handle Small ShortRecords More Efficiently

For small shortRecords that may not be attractive for individual liquidators, create micro liquidation pools where multiple small positions can be bundled and liquidated collectively. This could make it more economically viable to clear these positions from the system.

For small shortRecords that may not be attractive for individual liquidators, create micro liquidation pools where multiple small positions can be bundled and liquidated collectively. This could make it more economically viable to clear these positions from the system.

### Mitigation

Example of introducing Micro Liquidation Pools:

```solidity
// New contract to manage the micro liquidation pools
contract MicroLiquidationPool {
    struct PooledShortRecord {
        address shorter;
        uint8 shortId;
        uint88 collateral;
        uint88 ercDebt;
    }

    PooledShortRecord[] public pooledShorts;

    function addToPool(address asset, uint8 shortId, uint88 collateral, uint88 ercDebt) external {
        // Add a new pooled short record to the pool
        pooledShorts.push(PooledShortRecord({
            shorter: msg.sender,
            shortId: shortId,
            collateral: collateral,
            ercDebt: ercDebt
        }));
    }

    function liquidatePool() external {
        // Liquidate all the short positions in the pool
        // Distribute the collateral and debt proportionally among the pool participants
    }
}
```
The `MicroLiquidationPool` contract manages the pooled short positions. The `PooledShortRecord` struct represents the individual short positions within the pool. The `addToPool()` function allows users to add their small short positions to the pool, and the `liquidatePool()` function handles the collective liquidation of all the short positions in the pool.

```solidity
contract RedemptionFacet is Modifiers {
    function liquidateShort(address asset, address shorter, uint8 shortId) external isNotFrozen(asset) nonReentrant {
        STypes.ShortRecord storage shortRecord = s.shortRecords[asset][shorter][shortId];

        // Check if the short position is part of a micro liquidation pool
        if (shortRecord.poolId != 0) {
            // Trigger the liquidation of the entire pool
            MicroLiquidationPool(shortRecord.poolAddress).liquidatePool();
        } else {
            // Liquidate the individual short position
            // Existing liquidateShort() logic
        }
    }
}
```
In the `liquidateShort()` function, we check if the short position being liquidated is part of a micro liquidation pool. If so, we trigger the `liquidatePool()` function in the `MicroLiquidationPool` contract to handle the collective liquidation of the pooled short positions. If the short position is not part of a pool, we proceed with the existing liquidation logic.


## L-23 Optimize the Dispute Resolution Process

Integrate an automated system that leverages oracles or a set of predefined rules to identify and resolve disputes over redemption proposals. This can reduce reliance on user-initiated disputes and speed up the resolution process, making the system more efficient and less susceptible to manipulation.

### Mitigation

Here's how you can optimize the dispute resolution process using an automated system:

```solidity
import {LibOracle} from "contracts/libraries/LibOracle.sol";
import {LibDisputeResolver} from "contracts/libraries/LibDisputeResolver.sol";

contract RedemptionFacet is Modifiers {
    /**
     * @notice Automatically resolve disputes over redemption proposals
     * @dev This function is called periodically (e.g., by a keeper) to identify and resolve disputes
     * @param asset The market that will be impacted
     */
    function resolveRedemptionDisputes(address asset) external isNotFrozen(asset) nonReentrant {
        STypes.Asset storage Asset = s.asset[asset];
        STypes.AssetUser[] memory assetUsers = s.getAssetUsers(asset);

        for (uint256 i = 0; i < assetUsers.length; i++) {
            address redeemer = assetUsers[i].addr;
            STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][redeemer];

            if (redeemerAssetUser.SSTORE2Pointer != address(0) && LibOrders.getOffsetTime() >= redeemerAssetUser.timeToDispute) {
                MTypes.ProposalData[] memory decodedProposalData = LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

                for (uint256 j = 0; j < decodedProposalData.length; j++) {
                    MTypes.ProposalData memory currentProposal = decodedProposalData[j];
                    STypes.ShortRecord storage currentSR = s.shortRecords[asset][currentProposal.shorter][currentProposal.shortId];

                    // Automatically resolve the dispute based on predefined rules
                    if (!LibDisputeResolver.isProposalValid(asset, currentSR, redeemerAssetUser.oraclePrice, currentProposal)) {
                        _resolveInvalidProposal(asset, redeemer, j, currentProposal.shorter, currentProposal.shortId);
                    }
                }
            }
        }
    }

    function _resolveInvalidProposal(address asset, address redeemer, uint8 incorrectIndex, address disputeShorter, uint8 disputeShortId) private {
        // Revert the redemption proposal and update the state accordingly
        MTypes.DisputeRedemption memory d = LibDisputeResolver.disputeRedemption(asset, redeemer, incorrectIndex, disputeShorter, disputeShortId);

        // Emit events and update user balances
        emit Events.DisputeRedemption(asset, redeemer, incorrectIndex, disputeShorter, disputeShortId);
    }
}
```

In this implementation, the `resolveRedemptionDisputes()` function is called periodically (e.g., by a keeper) to automatically identify and resolve disputes over redemption proposals.

The key components are:

1. **Automated Dispute Resolution**:
   - The function iterates through all the redemption proposals that have reached the dispute period.
   - For each proposal, it checks the validity of the proposed short records using the `LibDisputeResolver.isProposalValid()` function.
   - If a proposal is found to be invalid, the `_resolveInvalidProposal()` function is called to revert the proposal and update the state accordingly.

2. **LibDisputeResolver**:
   - This library encapsulates the logic for automatically resolving disputes based on predefined rules.
   - The `isProposalValid()` function checks the proposal against the current state of the short record and the oracle price to determine if the proposal is valid.
   - The `disputeRedemption()` function updates the state of the short records and the user balances when an invalid proposal is identified.

By introducing this automated dispute resolution process, the system can proactively identify and resolve disputes, reducing the need for users to manually initiate disputes.


## L-24 Implement Dynamic Fee and Reward Structures

Implement a dynamic fee and reward structure for proposers and disputers that adjusts based on system conditions such as the volume of redemptions, the accuracy of past proposals, and overall market volatility. This could encourage participation when needed most and discourage frivolous or incorrect proposals.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224

## L-25 Insufficient Validation in Proposal Mechanism

Introduce a mechanism for pre-validating redemption proposals before they are officially submitted, using a combination of off-chain computation and on-chain verification. This could involve a "soft check" on the proposed shortRecords against the current state to catch obvious errors, reducing the likelihood of disputes.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56


## L-26 Streamline the Partial Redemption Process

For partial redemptions, simplify the process by allowing a more flexible approach to how much of a shortRecord can be redeemed, removing the restriction to only the first and last proposal in the slate. This could make the system more accessible and user-friendly.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56


## L-27 Implement Automated Claim Function

Implement an automated process for claiming redeemed ETH and remaining collateral that triggers after the dispute period ends, with safeguards to prevent abuse. This can improve user experience by reducing manual actions required and ensuring timely access to assets.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224


## L-28 Add a Decentralized Verification Network for redemption proposals and disputes

Consider establishing a decentralized network of validators to independently verify redemption proposals and disputes. This network could operate on a stake-based system, where validators are incentivized to act honestly through rewards for correct verifications and penalties for incorrect actions.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L56

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224


## L-29 Locking Mechanism for Active Disputes

Introduce a locking mechanism that temporarily restricts the transfer of the NFT if the underlying shortRecord is involved in an active dispute or redemption process. This could prevent attempts to evade liquidation or redemption by transferring the NFT under dispute.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol#L224

## L-30 Enhance Fee Transparency and Predictability by introducing Estimation functions for Users

Offer users a feature to calculate potential withdrawal fees based on hypothetical market conditions. This could help users understand how different scenarios might affect their costs, improving transparency and enabling more informed decision-making.

https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BridgeRouterFacet.sol#L101

```solidity
function withdraw(address bridge, uint88 dethAmount) external nonReentrant {
        if (dethAmount == 0) revert Errors.ParameterIsZero();

        (uint256 vault, uint256 bridgePointer) = _getVault(bridge);

        uint88 fee;
        if (vault == VAULT.ONE) {
            uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
            if (dethAssessable > 0) {
                uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
                if (withdrawalFeePct > 0) {
                    fee = dethAssessable.mulU88(withdrawalFeePct);
                    dethAmount -= fee;
                    s.vaultUser[vault][address(this)].ethEscrowed += fee;
                }
            }
        }

        uint88 ethAmount = _ethConversion(vault, dethAmount);
        vault.removeDeth(dethAmount, fee);
        IBridge(bridge).withdraw(msg.sender, ethAmount);
        emit Events.Withdraw(bridge, msg.sender, dethAmount, fee);
    }

    /**
     * @notice Withdraw LST out of the protocol
     * @dev Only callable by DAO, takes from TAPP balance
     *
     * @param bridge The address of the bridge corresponding to the LST being withdrawn
     * @param dethAmount The quantity of dETH to withdraw
     *
     */
    function withdrawTapp(address bridge, uint88 dethAmount) external onlyDAO {
        if (dethAmount == 0) revert Errors.ParameterIsZero();

        (uint256 vault,) = _getVault(bridge);
        uint88 ethAmount = _ethConversion(vault, dethAmount);

        s.vaultUser[vault][address(this)].ethEscrowed -= dethAmount;
        s.vault[vault].dethTotal -= dethAmount;

        IBridge(bridge).withdraw(msg.sender, ethAmount);
        emit Events.WithdrawTapp(bridge, msg.sender, dethAmount);
    }

```

### Mitigation

1. Implement a new function in the `BridgeRouterFacet` contract that allows users to estimate withdrawal fees based on specified parameters.

2. Within the estimation function, calculate the hypothetical withdrawal fees based on the provided market conditions. This could involve using historical data or simulated scenarios to estimate the fees.

3. Return the calculated withdrawal fees to the user, providing transparency and predictability.

Here's how you can modify the `BridgeRouterFacet` contract to include the estimation function:

```solidity
pragma solidity 0.8.21;

// Import necessary libraries and interfaces

contract BridgeRouterFacet is Modifiers {
    // Existing contract code...

    /**
     * @notice Estimate withdrawal fees based on hypothetical market conditions
     * @param bridge The address of the bridge corresponding to the LST being withdrawn
     * @param dethAmount The quantity of dETH to withdraw
     * @return Estimated withdrawal fee
     */
    function estimateWithdrawalFee(address bridge, uint88 dethAmount) external view returns (uint88) {
        (uint256 vault, uint256 bridgePointer) = _getVault(bridge);

        if (vault == VAULT.ONE) {
            uint88 dethAssessable = vault.assessDeth(bridgePointer, dethAmount, rethBridge, stethBridge);
            if (dethAssessable > 0) {
                uint256 withdrawalFeePct = LibBridgeRouter.withdrawalFeePct(bridgePointer, rethBridge, stethBridge);
                if (withdrawalFeePct > 0) {
                    return dethAssessable.mulU88(withdrawalFeePct);
                }
            }
        }

        // If no fee applicable, return 0
        return 0;
    }
}
```

The `estimateWithdrawalFee` function allows users to estimate withdrawal fees based on the specified parameters.

Users can call this function before making a withdrawal to understand the potential fees they might incur under different scenarios, thereby improving transparency and enabling more informed decision-making.


## NC-01 Use of Magic Numbers 

The constant 1 ether is used in the calculation of m.short.ercDebt. It might be better to define this constant with a more descriptive name or use a comment to explain its purpose.

## NC-02 Variable Naming and Documentation 

While the function and its parameters are well-documented using NatSpec comments, some of the variable names could be more descriptive (e.g., m, cRatio, ercDebtMatched). Clear and descriptive variable names can improve code readability and maintainability.

## NC-03 Unclear Comments

`// @dev don't use mulU88 in rare case of overflow` is a bit cryptic. It would be better to explain the reasoning behind this comment more clearly.