## QA Summary<a name="QA Summary">

### Low Risk Issues

|                | Issue                                                        |
| -------------- | :----------------------------------------------------------- |
| [LOW-1](#LOW1) | Embedding Modifier in Private Function Reduces Contract Size |
| [LOW-2](#LOW2) | Activate the Optimizer                                       |
| [LOW-3](#LOW3) | Inconsistent Minimum Deposit Requirement                     |
|                |

### Non-critical Issues

|              | Issue                                        |
| ------------ | :------------------------------------------- |
| [NC-1](#NC1) | Unused imports across files                  |
| [NC-2](#NC2) | No events for important state changes        |
| [NC-3](#NC3) | Unused state variable                        |
| [NC-4](#NC4) | Missing documentation for function parameter |
| [NC-4](#NC5) | Confusing constant name                      |

## Low Risk Issues

### [LOW-1] Embedding Modifier in Private Function Reduces Contract Size

Consider consolidating the logic of a modifier within a private function to optimize contract size. Employing a private visibility, which is more efficient for function calls compared to internal visibility, is advisable since the modifier will exclusively invoke this function internally within the contract.

For example, the modifier referenced below could be refactored as demonstrated:
https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/bridges/BridgeReth.sol#L29-L32

```diff
-    modifier onlyDiamond() {
+    function _onlyDiamond() private view {
         if (msg.sender != diamond) revert NotDiamond();
+    }
+    modifier onlyDiamond() {
+        _onlyDiamond();
         _;
     }

```

### [LOW-2] Activate the Optimizer

Before deploying your contract, activate the optimizer when compiling using the following command:

```bash
solc --optimize --bin sourceFile.sol
```

By default, the optimizer will optimize the contract assuming it is called 200 times across its lifetime. If you want the initial contract deployment to be cheaper and the later function executions to be more expensive, set it to --optimize-runs=1. Conversely, if you expect many transactions and do not care for higher deployment cost and output size, set --optimize-runs to a high number.

```javascript
module.exports = {
  solidity: {
    version: "0.8.21",
    settings: {
      optimizer: {
        enabled: true,
        runs: 1000,
      },
    },
  },
};
```

For further information, please visit [this site](https://docs.soliditylang.org/en/v0.5.4/using-the-compiler.html#using-the-commandline-compiler).

### [LOW-3] Inconsistent Minimum Deposit Requirement

#### Summary:

The `BridgeRouterFacet.deposit()` function has a minimum deposit check (`if (amount < C.MIN_DEPOSIT)`) that may not align with the documented requirements in the `Constant.sol` file. This inconsistency could lead to confusion among users and impact the clarity of the project's requirements.

#### Description:

The documentation in `Constant.sol` specifies a 0.01 ether minimum deposit for RocketPool and 100 wei for Lido. However, the function enforces a minimum deposit of 0.01 ether for all cases. This inconsistency could lead Lido users to expect a lower deposit, causing dissatisfaction.

#### Recommendation:

To address this issue:

1. Introduce a separate constant for the minimum Lido deposit (`MIN_LIDO_DEPOSIT`), or
2. Align the Lido minimum deposit with RocketPool to be 0.01 ether.

#### Code:

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L63-L64

### Non-critical Issues

### [NC-1] Unused imports across files

During the audit, multiple unused imports were identified across files. Consider removing them.

<details><summary>Links</summary>

- [BidOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L18)
- [BridgeRouterFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BridgeRouterFacet.sol#L16)
- [ShortOrdersFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ShortOrdersFacet.sol#L16)
- [PrimaryLiquidationFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L19)
- [ExitShortFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L17)
- [LibBridgeRouter.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBridgeRouter.sol#L14)
- [LibBytes.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibBytes.sol#L7)
- [LibOracle.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOracle.sol#L14)
- [LibOrders.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L18)
- [LibSRUtil.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L15)

</details>

### [NC-2] No events for important state changes</a>

### Summary:

The `BidOrdersFacet.sol` contract lacks an event to log bid creation.

### Description:

Events are vital for Ethereum smart contracts to notify external systems about crucial state changes. However, `BidOrdersFacet.sol` fails to emit an event upon bid creation. This omission prevents external systems from efficiently monitoring bid-related activities, reducing transparency.

### Recommendation:

Add an event in `BidOrdersFacet.sol` to log bid creation events, including relevant details like the bidder's address, bid ID, etc.

### [NC-3] Unused state variables

During the audit, unused state variables were identified in the codebase. Consider removing them.

<details><summary>Links</summary>

[ExitShortFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/ExitShortFacet.sol#L26-L30)

[PrimaryLiquidationFacet.sol](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L28-L32)

</details>

### [NC-4] Missing documentation for function parameter

In the PrimariLiquidationFacet.sol file, documentation is missing for the `shortOrderId` parameter in the `liquidate()` function. It is recommended to add documentation for this parameter, similar to the documentation provided for the other parameters.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L34-L47

### [NC-5] Confusing constant name</a>

In the `Constants.sol` file, the constant name `USDC_WETH` is confusing as it suggests that the pool would be the USDC/WETH pool, while the address actually represents the WETH/USDC pool. This naming inconsistency may lead to potential mistakes by developers in the future. It is recommended to rename the constant to `WETH_USDC` to accurately reflect the pool name.

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/Constants.sol#L71
