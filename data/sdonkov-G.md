```solidity
function createForcedBid(address sender, address asset, uint80 price, uint88 ercAmount, uint16[] calldata shortHintArray)
        external
        onlyDiamond
        returns (uint88 ethFilled, uint88 ercAmountLeft)
    {
        // @dev leave empty, don't need hint for market buys
        MTypes.OrderHint[] memory orderHintArray;

        // @dev update oracle in callers
        return _createBid(sender, asset, price, ercAmount, C.MARKET_ORDER, orderHintArray, shortHintArray);
    }
```


The `createForcedBid` function is marked as external and includes the `onlyDiamond` modifier, which restricts its invocation to the contract itself. Since this function is exclusively intended for internal contract use, it can be more gas efficient to declare it as private instead of external.