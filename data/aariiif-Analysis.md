# DittoETH Security Analysis Report

## Table of Contents
1. [Introduction](#introduction)
2. [Approach](#approach)
3. [Architecture Overview](#architecture-overview)
4. [Codebase Quality Analysis](#codebase-quality-analysis)
5. [Centralization Risks and Admin Control Abuse](#centralization-risks-and-admin-control-abuse)
6. [Mechanism Review](#mechanism-review)
7. [Systemic Risks](#systemic-risks)
8. [Recommendations](#recommendations)
9. [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>

DittoETH is a decentralized stablecoin protocol that utilizes an order book design to provide supercharged staking yield. My security analysis report aims to thoroughly examine the DittoETH codebase, focusing on identifying potential bugs, vulnerabilities, edge cases, centralization risks, and admin/owner abuse. In the report, I provide actionable insights, improvement points, and a comprehensive analysis of the protocol's architecture and mechanisms.

## Approach <a name="approach"></a>

The evaluation of the DittoETH codebase involved a multi-step approach:

1. A thorough manual examination of the smart contract code was conducted to identify potential vulnerabilities, logic flaws, and coding best practices.

2. Static analysis tools and security scanners were employed to detect common vulnerabilities and coding issues.

3. The protocol's architecture was analyzed to identify potential design flaws, centralization risks, and scalability concerns.

4. The core mechanisms of the protocol, such as the order book, liquidations, and redemptions, were tested to ensure their correctness and robustness.

## Architecture Overview <a name="architecture-overview"></a>

1. Order Book: The protocol utilizes an order book mechanism to match bids and asks for the stablecoin. The order book is implemented using a linked list data structure and supports limit orders and market orders.

2. Liquidations: DittoETH incorporates a liquidation mechanism to ensure the stability of the stablecoin. Both primary and secondary liquidations are supported to handle undercollateralized positions.

3. Redemptions: Users can redeem their stablecoins for the underlying collateral through the redemption mechanism. The redemption process involves a two-step proposal and dispute system to ensure fairness.

4. Collateral Management: The protocol manages the collateral assets, including ETH and various Liquid Staking Tokens (LSTs), to back the stablecoin.

5. Oracles: DittoETH relies on price oracles, such as Chainlink and Uniswap, to obtain accurate price data for the collateral assets and ensure proper functioning of the liquidation and redemption mechanisms.

![DittoETH Architecture Diagram](https://i.imgur.com/architecture.png)

> The DittoETH protocol follows a modular and composable architecture, leveraging the Diamond Standard (EIP-2535) for contract upgradability and separation of concerns. The protocol consists of several key components that interact with each other to facilitate the creation and management of stablecoins backed by staked ETH.

Here's my overview of the main architectural components:

**1. Diamond Proxy:**
   - The Diamond Proxy is the central entry point for interacting with the DittoETH protocol.
   - It follows the EIP-2535 standard, allowing for contract upgradability and the addition of new functionality through facets.
   - The Diamond Proxy delegates calls to the appropriate facet contracts based on the function selectors.

**2. Facet Contracts:**
   - Facet contracts contain the actual implementation logic of the DittoETH protocol.
   - Each facet focuses on a specific aspect of the protocol, such as order management, liquidations, redemptions, and collateral management.
   - The facet contracts include [`OrdersFacet`](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/BidOrdersFacet.sol), [`RedemptionFacet`](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/facets/RedemptionFacet.sol),

**3. Library Contracts:**
   - Library contracts provide reusable and modular functionality that can be accessed by multiple facets.
   - They encapsulate common logic, data structures, and utilities used throughout the protocol.
   - The library contracts include [`LibOrders`](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOrders.sol), `LibShortRecord`, `LibAsset`, and [`LibOracle`](https://github.com/code-423n4/2024-03-dittoeth//blob/main/contracts/libraries/LibOracle.sol).

**4. Bridge Contracts:**
   - Bridge contracts facilitate the integration of external staking protocols, such as Lido and Rocket Pool, into the DittoETH ecosystem.
   - They handle the deposit and withdrawal of staked ETH (stETH, rETH) and manage the conversion between staked ETH and the protocol's internal dETH representation.
   - The bridge contracts include `BridgeReth` and `BridgeSteth`.

**5. Governance Contracts:**
   - Governance contracts enable decentralized decision-making and protocol upgrades.
   - They allow stakeholders to propose, vote on, and execute changes to the protocol's parameters and functionality.
   - The governance contracts include `DittoTimelockController`.

**6. External Dependencies:**
   - The DittoETH protocol integrates with external systems and contracts to enhance its functionality and security.
   - It relies on price oracles, such as Chainlink and Uniswap, to obtain accurate price data for collateral assets and enable liquidations and redemptions.
   - It may also interact with other DeFi protocols, such as lending platforms or decentralized exchanges, to provide additional services to users.

**Architectural diagram illustrating the components and their interactions:**

```
       ┌──────────────────────────────────────────────────────────────────────────────────┐
       │                                  Diamond Proxy                                   │
       └───────────────────────────────────▲────────────────────────────────────────────┬─┘
                                           │                                            │
                                           │                                            │
                                           │                                            │
                            ┌──────────────┴───────────────┐                            │
                            │                               │                            │
                            ▼                               ▼                            ▼
                    ┌───────────────┐               ┌───────────────┐            ┌───────────────┐
                    │   Facets      │               │  Governance   │            │    Bridges    │
                    ├───────────────┤               ├───────────────┤            ├───────────────┤
                    │ - OrdersFacet │               │ - DittoDAO    │            │ - BridgeReth  │
                    │ - MarginCall  │               │ - Timelock    │            │ - BridgeSteth │
                    │   PrimaryFacet│               │   Controller  │            └───────────────┘
                    │ - Redemption  │               └───────────────┘
                    │   Facet       │
                    │ - VaultFacet  │
                    └───────────────┘
                            │
                            │
                            ▼
                    ┌───────────────┐                              ┌───────────────────┐
                    │   Libraries   │                              │     External      │
                    ├───────────────┤                              │    Dependencies   │
                    │ - LibOrders   │                              ├───────────────────┤
                    │ - LibShort    │                              │ - Price Oracles   │
                    │   Record      │                              │   (Chainlink,     │
                    │ - LibAsset    │                              │    Uniswap)       │
                    │ - LibOracle   │                              │ - DeFi Protocols  │
                    └───────────────┘                              └───────────────────┘
```

The architectural design allows for flexibility, upgradability, and modularity within the DittoETH protocol. The separation of concerns through facets and libraries enables easier maintenance, testing, and integration of new features. The use of the Diamond Standard ensures that the protocol can evolve over time without the need for complex migrations.

## Codebase Quality Analysis <a name="codebase-quality-analysis"></a>

> DittoETH codebase demonstrates a modular and well-structured design, adhering to Solidity coding best practices. The use of libraries, such as `LibOrders`, `LibShortRecord`, and `LibAsset`, promotes code reusability and maintainability.

**However, there are a few areas that could be improved**
1. While the codebase includes some comments and documentation, there are areas where the documentation is lacking or unclear. Comprehensive code documentation is crucial for understanding the purpose and behavior of each component.

   Recommendation: Enhance the code documentation by providing clear and concise comments for all critical functions, data structures, and mechanisms. Use NatSpec format to document function parameters, return values, and expected behavior.

3. The codebase includes a set of test cases, but the test coverage could be improved to ensure that all critical functionalities and edge cases are thoroughly tested.

   Recommendation: Expand the test suite to cover all core mechanisms, including order matching, liquidations, redemptions, and collateral management. Utilize property-based testing techniques to generate a wide range of test scenarios and identify potential edge cases.

## Centralization Risks and Admin Control Abuse <a name="centralization-risks-and-admin-control-abuse"></a>

DittoETH protocol incorporates a governance model that grants certain privileges to admin roles. While this is necessary for protocol upgrades and parameter adjustments, it introduces centralization risks and the potential for admin control abuse.

1. Admin privileges: The protocol defines admin roles, such as [`owner`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L146), which have the ability to perform critical actions, including freezing markets, adjusting protocol parameters, and managing collateral types.

**Recommendation**: Implement a robust governance mechanism that involves community participation and decentralized decision-making. Consider using time-locked multisig contracts or a decentralized autonomous organization (DAO) structure to distribute control and mitigate centralization risks.

2. Upgradability: The protocol utilizes a proxy-based upgradability pattern, allowing the contract logic to be upgraded by the admin roles. While upgradability is essential for fixing bugs and introducing new features, it also poses risks if the upgrade process is not properly controlled.

   **Recommendation**: Establish strict upgrade policies and procedures, including thorough testing, auditing, and community approval, before deploying any contract upgrades. Consider implementing a time-delay mechanism for upgrades to allow users to review and opt-out if necessary.

3. Collateral management: The admin roles have the ability to add or remove collateral types and adjust collateral parameters. Malicious or erroneous modifications to the collateral settings could potentially destabilize the protocol.

   **Recommendation**: Implement a multi-signature mechanism for critical collateral management actions, requiring multiple authorized parties to approve any changes. Conduct thorough risk assessments and simulations before modifying collateral parameters.

## Mechanism Review <a name="mechanism-review"></a>

**1. Order Book:**
   - The order book mechanism utilizes a linked list data structure to maintain a sorted list of bids and asks. While this approach is gas-efficient, it may lead to potential front-running risks and scalability issues as the number of orders increases.
   - The order matching algorithm relies on a hint system to optimize gas costs. However, if the hints are not properly validated or if they are manipulated by malicious actors, it could lead to incorrect order matching or potential exploits.

[BidOrdersFacet.sol#createBid](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/BidOrdersFacet.sol#L40-L51)
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

**Recommendation**: Implement additional safeguards and validations for the hint system, such as checking the validity of hints against the current order book state and imposing limits on the number of hints allowed per transaction. Consider exploring alternative order book designs, such as a tree-based structure, to improve scalability and reduce front-running risks.

**2. Liquidations:**
   - The liquidation mechanism relies on accurate price oracles to determine the collateral ratios and trigger liquidations. If the oracle prices are manipulated or become stale, it could lead to incorrect liquidations or allow undercollateralized positions to remain open.

[PrimaryLiquidationFacet.sol#liquidate](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L90), [PrimaryLiquidationFacet.sol#L135-L136](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L135-L136)
```solidity
     function liquidate(...) external {
         // ...
         m.oraclePrice = LibOracle.getPrice(asset);
         m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
         // ...
     }
```
Recommendation: Implement a robust oracle system that incorporates multiple price sources and includes safety mechanisms, such as price deviation checks and fallback oracles, to ensure the integrity of the price data. 

**3. Redemptions:**
   - The redemption mechanism allows users to redeem their stablecoins for the underlying collateral. The current implementation relies on a two-step process with a dispute period to ensure fairness. However, the dispute process may be vulnerable to front-running attacks or collusion among disputants.

[RedemptionFacet.sol#disputeRedemption](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L224-L301)
```solidity
     function disputeRedemption(...) external {
         // ...
         if (disputeCR < incorrectProposal.CR && disputeSR.updatedAt + C.DISPUTE_REDEMPTION_BUFFER <= redeemerAssetUser.timeProposed) {
             // ...
         } else {
             revert Errors.InvalidRedemptionDispute();
         }
     }
```

Recommendation: Explore alternative redemption mechanisms that minimize the reliance on a dispute process, such as using a continuous redemption model or incorporating a random selection process for redemption proposals. Implement strict time limits and incentives for disputants to prevent front-running and collusion.

## Systemic Risks <a name="systemic-risks"></a>

1. Liquidity Risk: The stability of the DittoETH stablecoin depends on the liquidity of the underlying collateral assets. If there is insufficient liquidity in the markets for the collateral assets, it could lead to difficulties in liquidating positions and maintaining the stablecoin peg.

_Recommendation: Continuously monitor the liquidity of the collateral assets and establish partnerships with market makers and liquidity providers to ensure adequate liquidity. Implement contingency plans, such as emergency liquidity facilities or backstop mechanisms, to handle liquidity shortages._

2. Oracle Dependency: The DittoETH protocol heavily relies on price oracles for critical functions, such as liquidations and redemptions. If the oracle prices are manipulated or become unreliable, it could compromise the integrity of the protocol and lead to financial losses for users.

_Recommendation: Diversify the oracle sources and implement a multi-oracle approach to reduce the dependency on a single oracle provider. Establish a robust oracle governance framework that includes regular audits, price feed monitoring, and emergency response procedures._

3. Governance Risks: The centralized governance model of DittoETH poses risks related to admin control abuse and centralized decision-making. If the admin roles are compromised or act maliciously, it could have severe consequences for the protocol and its users.

_Recommendation: Transition towards a more decentralized governance model that incorporates community participation, such as a DAO structure or a token-based voting system. Implement strict access controls and multi-signature requirements for critical governance actions._

## Recommendations <a name="recommendations"></a>

Based on my analysis of the DittoETH codebase and the identified risks, the following recommendations are highly security and robustness of the protocol:

1. Enhance the code documentation to provide clear and concise explanations of the protocol's components, mechanisms, and expected behavior. Use NatSpec format to document function parameters, return values, and error conditions.

2. Increase the test coverage of the DittoETH codebase to ensure that all critical functionalities and edge cases are thoroughly tested. Utilize property-based testing techniques to generate a wide range of test scenarios and identify potential weaknesses.

3. Transition towards a more decentralized governance model that involves community participation and reduces the reliance on centralized admin roles. Implement strict access controls, multi-signature requirements, and time-locks for critical governance actions.

4. Diversify the oracle sources and implement a multi-oracle approach to reduce the dependency on a single oracle provider. Establish a robust oracle governance framework that includes regular audits, price feed monitoring, and emergency response procedures.

5. Strengthen governance mechanisms: Transition towards a more decentralized governance model that involves community participation and reduces the reliance on centralized admin roles. Implement strict access controls, multi-signature requirements, and time-locks for critical governance actions.

6. Continuously monitor the liquidity of the collateral assets and establish partnerships with market makers and liquidity providers to ensure adequate liquidity. Implement contingency plans, such as emergency liquidity facilities or backstop mechanisms, to handle liquidity shortages.

7. Actively engage with the DittoETH community and stakeholders to gather feedback, discuss potential improvements, and address concerns. Maintain transparency and open communication channels to build trust and foster a collaborative environment.

### Potential security vulnerabilities in the key areas mentioned earlier: liquidation parameter validation, dust amount handling, reentrancy vulnerabilities, and collateral ratio calculations.

1. Liquidation Parameter Validation:
   - The `liquidate` function in the `PrimaryLiquidationFacet.sol` contract lacks proper validation of the `shortHintArray` parameter.
   - An attacker could potentially provide a large `shortHintArray` to consume excessive gas and cause a denial-of-service attack.

**Improvement points:**
- Implement a maximum limit on the size of the `shortHintArray` to prevent gas exhaustion attacks.
- Validate each element of the `shortHintArray` to ensure they are within valid ranges and correspond to existing short records.
- Consider charging the liquidator for the gas cost associated with processing the `shortHintArray` to discourage excessive gas consumption.

[PrimaryLiquidationFacet.sol#liquidate](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L77)

2. Dust Amount Handling:
   - The `updateErcDebt` function in the `LibShortRecord` library calculates the `ercDebt` based on the difference between the global `ercDebtRate` and the short record's individual `ercDebtRate`.
   - If the `ercDebtRate` calculation introduces precision loss or rounding errors, it could lead to a situation where a short record's debt falls slightly below the `minShortErc` threshold, making it unliquidatable.

[LibSRUtil.sol#updateErcDebt](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L151-L163)

**Improvement points:**
- Use a high-precision arithmetic library, such as SafeMath or PRBMath, to perform the `ercDebt` calculation and avoid precision loss.
- Implement additional checks to ensure that the calculated `ercDebt` does not result in a debt below the `minShortErc` threshold.
- Consider adjusting the `minShortErc` threshold or introducing a grace period for liquidations to account for potential rounding errors.
```solidity
function updateErcDebt(STypes.ShortRecord storage short, address asset) internal {
    // Distribute ercDebt
    uint64 ercDebtRate = s.asset[asset].ercDebtRate;
    uint88 ercDebt = PRBMathUD60x18.mul(short.ercDebt, PRBMathUD60x18.sub(ercDebtRate, short.ercDebtRate));

    if (ercDebt > 0) {
        uint88 newErcDebt = PRBMathUD60x18.add(short.ercDebt, ercDebt);
        require(newErcDebt >= minShortErc(asset), "Debt below minimum threshold");
        short.ercDebt = newErcDebt;
        short.ercDebtRate = ercDebtRate;
    }
}
```

3. Reentrancy Vulnerabilities:
   - The `liquidate` function in the `PrimaryLiquidationFacet.sol` contract calls the `_performForcedBid` function, which interacts with external contracts.
   - If the external contracts are malicious and perform a reentrant call back to the `liquidate` function, it could lead to unexpected behavior and potential fund theft.

[PrimaryLiquidationFacet.sol#liquidate](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L77)

**Improvement points:**
- Ensure that all state changes, including updating the short record's collateral and debt, are performed before any external calls.
- Use a reentrancy guard, such as the `nonReentrant` modifier from OpenZeppelin, to prevent reentrant calls to the `liquidate` function.
- Implement a "checks-effects-interactions" pattern, where all necessary checks and state updates are performed before interacting with external contracts.

```solidity
function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray)
    external
    isNotFrozen(asset)
    nonReentrant
    onlyValidShortRecord(asset, shorter, id)
    returns (uint88, uint88)
{
    // ...
    
    // Perform all state updates and checks before external calls
    _updateShortRecord(asset, shorter, id);
    _checkLiquidationConditions(asset, shorter, id);
    
    // Interact with external contracts
    _performForcedBid(m, shortHintArray);
    
    // ...
}
```

4. Collateral Ratio Calculations:
   - The `_setLiquidationStruct` function in the `PrimaryLiquidationFacet.sol` contract retrieves the oracle price using `LibOracle.getPrice(asset)` and calculates the collateral ratio.
   - If the oracle price is manipulated, stale, or inaccurate, it could lead to incorrect collateral ratio calculations and improper liquidations.

[PrimaryLiquidationFacet.sol#_setLiquidationStruct](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L122-L143)

**Improvement points:**
- Implement a price feed aggregation mechanism to obtain more reliable and tamper-resistant price data.
- Use multiple price oracles and compare their values to detect and mitigate potential price manipulation.
- Introduce a price deviation threshold and a fallback mechanism to handle cases where the oracle price significantly deviates from the expected range.
- Consider incorporating a time-weighted average price (TWAP) or a volume-weighted average price (VWAP) to smooth out price fluctuations and reduce the impact of short-term price spikes.

```solidity
function _setLiquidationStruct(address asset, address shorter, uint8 id)
    private
    returns (MTypes.PrimaryLiquidation memory)
{
    // ...
    
    // Retrieve price from multiple oracles
    uint256 oracle1Price = LibOracle1.getPrice(asset);
    uint256 oracle2Price = LibOracle2.getPrice(asset);
    uint256 oracle3Price = LibOracle3.getPrice(asset);
    
    // Compare oracle prices and check for deviation
    require(isPriceWithinThreshold(oracle1Price, oracle2Price, oracle3Price), "Price deviation too high");
    
    // Calculate the average price or use a TWAP/VWAP
    uint256 averagePrice = (oracle1Price + oracle2Price + oracle3Price) / 3;
    
    m.oraclePrice = averagePrice;
    m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
    
    // ...
}
```

I tried as much to provide actionable insights to enhance the security and robustness of the liquidation mechanisms in the DittoETH protocol. However, I must recommend thoroughly testing and validating the implemented changes to ensure they effectively mitigate the identified vulnerabilities.

### Potential weaknesses and entry points in the DittoETH protocol's liquidation mechanisms.

1. Insufficient validation of liquidation parameters:
   - The `liquidate` function in the `PrimaryLiquidationFacet.sol` contract takes the `asset`, `shorter`, `id`, and `shortHintArray` as parameters.
   - If these parameters are not properly validated or if there are missing checks, an attacker could potentially manipulate the liquidation process.
   - For example, if the `shortHintArray` is not sanitized or if there are no limits on its size, an attacker could provide a large array to cause gas exhaustion or perform a denial-of-service attack.

[Entry point](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L90)
```solidity
function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray)
    external
    isNotFrozen(asset)
    nonReentrant
    onlyValidShortRecord(asset, shorter, id)
    returns (uint88, uint88)
{
    // ...
}
```

2. Improper handling of dust amounts:
   - The liquidation functions check for dust amounts and compare the remaining debt against the `minShortErc` value.
   - If the dust amount calculations are incorrect or if there are rounding errors, it could lead to a situation where a short record becomes unliquidatable.
   - For instance, if the `ercDebtRate` calculation in the `updateErcDebt` function of the `LibShortRecord` library introduces precision loss, it could result in a short record having a debt slightly below the `minShortErc` threshold.

[Entry point](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibSRUtil.sol#L151-L163)
```solidity
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
```

3. Race conditions and reentrancy vulnerabilities:
   - The liquidation functions modify state variables and transfer funds, which could be susceptible to race conditions or reentrancy attacks if not properly protected.
   - If an attacker can exploit these vulnerabilities, they could potentially manipulate the liquidation process or steal funds.
   - It's crucial to ensure that all state changes are performed before any external calls and that reentrancy guards are in place.

[Entry point](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L47-L90)
```solidity
function liquidate(address asset, address shorter, uint8 id, uint16[] memory shortHintArray)
    external
    isNotFrozen(asset)
    nonReentrant
    onlyValidShortRecord(asset, shorter, id)
    returns (uint88, uint88)
{
    // ...
    _performForcedBid(m, shortHintArray);
    // ...
}
```

4. Incorrect collateral ratio calculations:
   - The liquidation functions rely on accurate collateral ratio calculations to determine if a short record is undercollateralized.
   - If there are any flaws or inaccuracies in the collateral ratio calculations, it could lead to premature or delayed liquidations.
   - For example, if the oracle price used in the calculation is manipulated or stale, it could result in incorrect collateral ratios.

[Entry point](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/PrimaryLiquidationFacet.sol#L122-L143)
```solidity
function _setLiquidationStruct(address asset, address shorter, uint8 id)
    private
    returns (MTypes.PrimaryLiquidation memory)
{
    // ...
    m.oraclePrice = LibOracle.getPrice(asset);
    m.cRatio = m.short.getCollateralRatio(m.oraclePrice);
    // ...
}
```

_To mitigate these potential weaknesses and entry points, consider the following:_

1. Implement thorough validation and sanitization of liquidation parameters, including the `shortHintArray`, to prevent gas exhaustion and ensure the integrity of the liquidation process.

2. Review and test the `ercDebtRate` calculation and dust amount handling to ensure precision and avoid scenarios where short records become unliquidatable due to rounding errors.

3. Utilize reentrancy guards and perform all state changes before any external calls to mitigate the risk of race conditions and reentrancy attacks.

4. Ensure the accuracy and reliability of the oracle price used in collateral ratio calculations, and consider implementing safety checks and fallback mechanisms to handle stale or manipulated prices.


### Review of the [`claimRedemption` function](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/facets/RedemptionFacet.sol#L310-L334) in the RedemptionFacet.sol contract

```solidity
function claimRedemption(address asset) external isNotFrozen(asset) nonReentrant {
    uint256 vault = s.asset[asset].vault;
    STypes.AssetUser storage redeemerAssetUser = s.assetUser[asset][msg.sender];
    STypes.VaultUser storage redeemerVaultUser = s.vaultUser[vault][msg.sender];
    
    if (redeemerAssetUser.SSTORE2Pointer == address(0)) revert Errors.InvalidRedemption();
    if (LibOrders.getOffsetTime() < redeemerAssetUser.timeToDispute) revert Errors.TimeToDisputeHasNotElapsed();

    MTypes.ProposalData[] memory decodedProposalData =
        LibBytes.readProposalData(redeemerAssetUser.SSTORE2Pointer, redeemerAssetUser.slateLength);

    uint88 totalColRedeemed;
    for (uint256 i = 0; i < decodedProposalData.length; i++) {
        MTypes.ProposalData memory currentProposal = decodedProposalData[i];
        totalColRedeemed += currentProposal.colRedeemed;
        _claimRemainingCollateral({
            asset: asset,
            vault: vault,
            shorter: currentProposal.shorter,
            shortId: currentProposal.shortId
        });
    }
    
    redeemerVaultUser.ethEscrowed += totalColRedeemed;
    delete redeemerAssetUser.SSTORE2Pointer;
    emit Events.ClaimRedemption(asset, msg.sender);
}
```

My Analysis of the function step by step:

1. The function first checks that the caller (`msg.sender`) has a valid redemption proposal by checking that their `SSTORE2Pointer` is not zero. This ensures that only the original proposer can claim the redemption.

2. It then checks that the current time is after the `timeToDispute` for this proposal. This ensures that the dispute window has passed.

3. It reads the proposal data from SSTORE2 using `LibBytes.readProposalData`. This returns an array of `ProposalData` structs, each representing a ShortRecord that was part of the proposal.

4. It then iterates over these `ProposalData` structs. For each one:
   - It adds the `colRedeemed` (the amount of collateral that was redeemed from this ShortRecord) to the `totalColRedeemed` variable.
   - It calls the internal `_claimRemainingCollateral` function, which checks if the ShortRecord has been fully redeemed and if so, transfers any remaining collateral back to the shorter and deletes the ShortRecord.

5. After the loop, it transfers the `totalColRedeemed` amount to the redeemer's `ethEscrowed` balance in the `VaultUser` struct. This effectively transfers the redeemed collateral to the redeemer.

6. It then deletes the `SSTORE2Pointer`, which marks this proposal as claimed and prevents it from being claimed again.

**Checks**
- The function does only allow the original proposer to claim the funds, as it checks the `AssetUser` storage for `msg.sender`.
- The claimed amount (`totalColRedeemed`) is calculated by summing the `colRedeemed` amounts from the original proposal data. This ensures that the claimed amount matches the agreed upon proposal.
- The function does not directly check the global collateralization ratio. However, the `colRedeemed` amounts were calculated in `proposeRedemption` based on the actual collateral in each ShortRecord. As long as `proposeRedemption` and `disputeRedemption` are functioning correctly, the total redeemed amount should not exceed the actual collateral.
- The function does update the global `ethEscrowed` balance for the redeemer, effectively transferring the redeemed collateral to them. However, it does not directly update the global `dethCollateral` or `ercDebt` variables. These should have been updated in `proposeRedemption` when the proposal was created.

**To further verify the correctness and security of the function, we should:**

1. We should ensure that `proposeRedemption` correctly calculates `colRedeemed` based on the actual collateral in each ShortRecord and updates the global `dethCollateral` and `ercDebt` accordingly.

2. Ensure that `disputeRedemption` correctly removes invalid proposals and reverses any changes made by `proposeRedemption`.

3. Test scenarios where a redeemer tries to claim a proposal before the dispute window has elapsed, or tries to claim a proposal that doesn't exist.

4. Test scenarios where a redeemer tries to claim the same proposal multiple times.

5. Verify that after a redemption is claimed, the global collateralization ratio is still above the required minimum (taking into account the reduction in both collateral and debt).

> Based on my analysis of the `claimRedemption` function, there are a few potential points of entry for an attacker that I highly suggest looking into.

1. Incorrect calculation of `colRedeemed` in `proposeRedemption`: 
   If the `proposeRedemption` function incorrectly calculates the `colRedeemed` amount for each ShortRecord, it could allow a redeemer to claim more collateral than they should. _For example, if `proposeRedemption` uses the wrong price oracle or doesn't properly account for partial redemptions, it could inflate the `colRedeemed` amounts._

2. Incorrect updating of global variables in `proposeRedemption`: 
   If `proposeRedemption` doesn't correctly update the global `dethCollateral` and `ercDebt` variables when a proposal is created, it could lead to the protocol having an incorrect view of its overall collateralization. _This could potentially allow a redeemer to claim a redemption that brings the protocol's collateralization below the required minimum._

3. Incorrect dispute handling in `disputeRedemption`: 
   If the `disputeRedemption` function doesn't properly remove invalid proposals or doesn't correctly reverse the changes made by `proposeRedemption`, it could allow an attacker to bypass the dispute process. _For example, if `disputeRedemption` only removes the disputed ShortRecord but doesn't adjust the global `dethCollateral` and `ercDebt`, it could leave the protocol in an inconsistent state._

4. Reentrancy in `claimRedemption`: 
   While the function does have the `nonReentrant` modifier, it's worth double-checking that there are no potential reentrancy vectors, particularly in the `_claimRemainingCollateral` function that it calls. _If an attacker could somehow reenter the function and claim the same proposal multiple times, they could drain more funds than intended._

5. Oracle manipulation: 
   The redemption process relies on price oracles to calculate collateral ratios and redemption amounts. If an attacker could manipulate these oracles, they could potentially create a redemption proposal that appears valid but actually redeems more collateral than it should.

6. Timestamp manipulation: 
   The `claimRedemption` function checks that the current time is after the `timeToDispute` timestamp. If the protocol is running on a blockchain where miners have some control over the block timestamp, an attacker could potentially manipulate the timestamp to bypass this check and claim a redemption before the dispute window has actually elapsed.

Recommended Mitigation to mitigate these risks, it's crucial to:
---------------------------------------------

1. The `proposeRedemption` and `disputeRedemption` functions to ensure they are calculating amounts correctly and updating global state properly.

2. Ensure that the price oracles used are robust and resistant to manipulation.

3. Consider using a more secure source of time than block.timestamp if the protocol is deployed on a blockchain where timestamp manipulation is a concern.


These checks appear to be consistently enforced across the relevant functions. However, there are a few more things to consider:
--------------------------------------------------------------------

1. In `SecondaryLiquidationFacet.sol`, the `liquidateSecondaryTappShortRecord` function doesn't appear to check the minimum size of the TAPP's short record. This could potentially allow the creation of a TAPP short record below the minimum size.

2. While the checks prevent the creation of individual orders or shorts below the minimum size, they don't directly prevent the creation of a large number of minimum-sized orders. An attacker could still potentially create many small orders at the minimum size, which could lead to gas griefing when these orders are matched or liquidated.

**To mitigate this, consider:**

1. Adding a minimum size check in `liquidateSecondaryTappShortRecord`.

2. Implementing a maximum number of open orders or shorts per user. This would limit the total number of minimum-sized orders a single user could create.

3. Monitoring for abnormal patterns of order creation and liquidation in off-chain systems, and potentially restricting access for users who appear to be attempting to grief the system.

4. Adjusting gas costs for order creation and liquidation to make griefing attacks more expensive.

## Conclusion <a name="conclusion"></a>

The DittoETH protocol offers a novel approach to creating a decentralized stablecoin with supercharged staking yield through its order book design. However, the codebase analysis reveals several areas that require attention to enhance the protocol's security and robustness.

The codebase demonstrates a modular and well-structured design, but improvements can be made in areas such as error handling, code documentation, and test coverage. The centralized governance model poses risks related to admin control abuse and centralized decision-making, necessitating a transition towards a more decentralized governance structure.

The core mechanisms of the protocol, including the order book, liquidations, and redemptions, have been reviewed, and potential vulnerabilities and risks have been identified. Recommendations have been provided to address these concerns, such as implementing additional safeguards, diversifying oracle sources, and improving liquidity management.

### Time spent:
45 hours