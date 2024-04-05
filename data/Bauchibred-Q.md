## QA-01 The check in disburseCollateral() should be inclusive

### Proof of Concept

Take a look at https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L22-L47

```solidity
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
            //@audit
            bool isNotRecentlyModified = LibOrders.getOffsetTime() - updatedAt > C.YIELD_DELAY_SECONDS;
            if (isNotRecentlyModified) {
                s.vaultUser[vault][shorter].ethEscrowed += yield;
            } else {
                s.vaultUser[vault][address(this)].ethEscrowed += yield;
            }
        }
    }
```

Acceptable delay is `C.YIELD_DELAY_SECONDS` and as such the check should be inclusive and not unfairly ause the user to lose their yield to the TAPP in the edge case.

## QA-02 The try-catches are not correctly implemented

Take a look at https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L19-L67

```solidity
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
                //@audit
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
```

The main update of the LibOracle is to now handle reverts in queries to Chainlink's latestroundData, but as shown aboev this is not rightly done as only one query to `latestRoundData()` is protected, consider wrapping the second query too
## QA-03 There are currnetly no min/max checkers while integrating Chainlink prices 

In mulyiple instace a call to chainlink to query price is made for example take a look at https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L19-L67

```solidity
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
                //@audit
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
```


All these instances however never check to ensure that the price returned by chainlink in these instances is higher than the inbuilt chainlink min/max circuit breakers

## QA-04 Although the liquidation function checks shorter == msg.sender, the user can still buy time for liquidation

Take a look at https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L54

Although while liquidating there is a check for `shorter == msg.sender`, the user can still buy time for liquidation. Because msg.sender may be another account of the shorter


Where as this is probably  a design issue, maybe a whitelist of liquidators can be designed to only allow specific users to liquidate