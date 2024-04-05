![Pic](https://code4rena.com/_next/image?url=https%3A%2F%2Fstorage.googleapis.com%2Fcdn-c4-uploads-v0%2Fuploads%2FXcKzZ6eSLH9.0&w=256&q=75)

# DittoETH Security Analysis Report

## Overview

DittoETH is a decentralized stable asset system focusing on the creation of a USD-pegged stablecoin, dUSD. Ditto innovatively utilizes overcollateralized liquid staked Ethereum variants, such as rETH and stETH, leveraging a gas-optimized orderbook mechanism for stablecoin issuance. This system allows users to engage in dynamic roles-bidders, shorters, and askers - each playing a crucial part in the stablecoin ecosystem.

In this ecosystem, bidders and shorters provide Ethereum as collateral. Bidders aim to acquire dUSD directly on the orderbook, whereas shorters, in accepting the bidders' collateral, initiate a debt position marked by a ShortRecord, akin to a Collateralized Debt Position (CDP). However, distinctively, in Ditto's framework, the collateral and consequently, the yield from the staked Ethereum transfers to the shorter, while the bidder receives the stablecoin dUSD. This represents a departure from traditional CDP models, where the collateral provider also obtains the asset.

Given this backdrop, the suggestions for enhancing Ditto's operational framework, particularly concerning lower collateral requirements for creating short positions and facilitating up to 10X leverage, must be contextualized within its unique ecosystem. Enhancements need to focus on ensuring system stability, user protection, and market integrity, while fostering an environment conducive to capital efficiency and innovative trading strategies.

## Scope of Audit

- contracts/facets/BidOrdersFacet.sol
- contracts/facets/ShortOrdersFacet.sol
- contracts/facets/PrimaryLiquidationFacet.sol
- contracts/facets/BridgeRouterFacet.sol
- contracts/facets/ExitShortFacet.sol
- contracts/facets/RedemptionFacet.sol
- contracts/libraries/LibBridgeRouter.sol
- contracts/libraries/LibBytes.sol
- contracts/libraries/LibOracle.sol
- contracts/libraries/LibOrders.sol
- contracts/libraries/LibSRUtil.sol
- contracts/libraries/UniswapOracleLibrary.sol

## Architecture

The architecture of Ditto, with its specialized facets and libraries, presents a modular and robust framework tailored to the needs of a decentralized stablecoin ecosystem. Each component is designed with a specific purpose in mind, from managing bids and short orders to handling liquidations and redemptions, all while interacting with external systems and protocols.

## Suggested Code Logic Improvements

### Graduated Reward Scale Based on Time

Implement a graduated reward scale where the longer an order remains on the OrderBook before being matched, the higher the reward rate it earns. This encourages liquidity provision for longer periods, further stabilizing the order book liquidity.

This approach also mitigates rapid, in-and-out strategies focused solely on harvesting rewards rather than providing genuine liquidity.

### Variable Reward Rates Based on Market Conditions

Adjust reward rates dynamically based on current liquidity needs and market conditions. For example, increase rewards during periods of low liquidity to incentivize more order placements and decrease them when the order book is sufficiently liquid.

### Incorporate Order Size Impact for Reward Ratess

Consider the size and market impact of orders when determining rewards. Larger orders that contribute more significantly to market depth could receive higher rewards, adjusted for their potential impact on market stability. This approach encourages substantial liquidity provision while recognizing the risks and benefits larger orders bring to the market.

### Lack of Anti-Gaming Measures and Anomaly Detection

Introduce mechanisms to detect and penalize gaming strategies, such as placing and quickly canceling orders to appear active or using flash loans to inflate apparent liquidity.

Employ anomaly detection algorithms to identify patterns of behavior indicative of gaming or manipulation, adjusting rewards or imposing penalties accordingly.
 
 
### Dynamic Collateral Release Based on Market Conditions
 
Implement a dynamic collateral release mechanism that adjusts the amount of collateral returned based on current market conditions and the health of the overall platform. This could help mitigate systemic risk during periods of high volatility.

### Introduce Automated Collateral Top-Ups

Implement a feature that allows users to opt-in to automatic collateral top-ups from their wallet or a designated contract when their CR approaches the liquidation threshold. This can help users maintain their positions during volatile market conditions without requiring constant monitoring.

### Implement a Liquidation Queue System

Introduce a liquidation queue system that prioritizes liquidations based on CR and time, ensuring that the most at-risk positions are liquidated first. This can help manage gas costs and prevent network congestion during periods of high liquidation volume.

### Secondary Liquidation Enhancements

While prioritizing primary liquidations is essential, providing better incentives or mechanisms for secondary liquidations can help ensure that positions are liquidated efficiently, especially in low-volume conditions. This could include partial rewards or improved mechanisms for identifying and executing secondary liquidations.

### Fine-Tuned Recovery Criteria

Refine the criteria for entering and exiting Recovery Mode to ensure that it accurately reflects systemic risk and doesn't trigger too readily, avoiding unnecessary market panic. Consider incorporating a broader set of indicators beyond the total assetCR.

### Improve Arbitrage Deterrence with a Dynamic Fee Adjustment Mechanism

Instead of a static formula, use a machine learning model or algorithmic approach that dynamically adjusts fees based on a broader range of market signals, not just the immediate premium/discount of LSTs. This could include volume trends, volatility indicators, and the velocity of bridge flows.

## Audit Findings

Below is a list of findings from the audit

| Issue ID | Issue Title |
| --- | --- |
| M-01 | Unsafe Casting in min88 function |
| M-02 | Inaccurate tappFee and callerFee calculations |
| M-03 | Lack of Finalization for Partially Filled Asks |
| M-04 | Hint Array Inaccuracy Post-Reorganization |
| M-05 | High-Frequency Trading and Front Running Risks |
| L-01 | Multiple Orders Requirement for Large Trades is Prone to Slippage Issues |
| L-01 | Inaccurate Gas Cost Calculation |
| L-02 | Potential Rounding Issues when calculating m.short.ercDebt |
| L-03 | Reduced Flexibility in Pricing |
| L-04 | Inadequate Risk Management Due to Limited Collateral Ratio Precision |
| L-05 | Precision loss due to rounding errors |
| L-06 | Short Record ID Limitation |
| L-07 | Dos Vector through Hint Mechanism |
| L-08 | Outdated Hints Due to Dynamic Oracle Price Volatility |
| L-09 | Lack of Explicit Balance Checks |
| L-10 | Check effects Violation |
| L-11 | Validation of Order Hints |
| L-12 | Check for Valid Price and Amounts in _createBid |
| L-13 | Loop Efficiency and Termination in bidMatchAlgo to prevent Out of Gas Errors |
| L-14 | Check for Asset Oracle Validity |
| L-15 | Order ID Counter Validity |
| L-16 | Precision loss due to rounding errors |
| L-17 | Short Record ID Limitation |
| L-18 | Dos Vector through Hint Mechanism |
| L-19 | Outdated Hints Due to Dynamic Oracle Price Volatility |
| L-20 | Partial Exit Strategies Can be Improved |
| L-21 | Introduce Automated Collateral Top-Ups |
| L-22 | Introduce Micro Liquidation Pools to Handle Small ShortRecords More Efficiently |
| L-23 | Optimize the Dispute Resolution Process |
| L-24 | Implement Dynamic Fee and Reward Structures |
| L-25 | Insufficient Validation in Proposal Mechanism |
| L-26 | Streamline the Partial Redemption Process |
| L-27 | Implement Automated Claim Function |
| L-28 | Add a Decentralized Verification Network for redemption proposals and disputes |
| L-29 | Locking Mechanism for Active Disputes |
| L-30 | Enhance Fee Transparency and Predictability by introducing Estimation functions for Users |
| NC-01 | Use of Magic Numbers |
| NC-02 | Variable Naming and Documentation |
| NC-03 | Unclear Comments |

## Centralization Risks

DittoETH's reliance on specific oracles for price data and liquidation triggers introduces a centralization risk. Oracles are external services that provide smart contracts with external data. If these oracles are compromised or manipulated, it could lead to incorrect valuations, unfair liquidations, or the issuance of stablecoins under improper conditions. To mitigate this risk, DittoETH could diversify its data sources, employing a decentralized network of oracles and incorporating fail-safes like multi-sig mechanisms for critical operations that rely heavily on external data.

Another aspect of centralization risk involves the governance model. If a small group of stakeholders holds a significant portion of governance tokens or decision-making power, they could influence the platform's direction, policy changes, or updates to the protocol in ways that benefit them disproportionately. Implementing a broad and inclusive governance structure, possibly with checks and balances like a DAO (Decentralized Autonomous Organization) model, could distribute decision-making power more evenly among its users.

## Systemic Risks

DittoETH's systemic risks primarily revolve around the volatility of the collateral assets (rETH and stETH) and the dynamics of the liquid staking derivatives market. Significant price fluctuations in Ethereum could trigger mass liquidations if the collateral value falls below certain thresholds, potentially destabilizing the platform. To combat this, DittoETH could enhance its risk management framework by adjusting collateral requirements based on market conditions and implementing dynamic liquidation thresholds.

Moreover, the platform's interdependencies with other protocols for staked Ethereum variants introduce systemic risks. Issues in these underlying protocols, such as smart contract vulnerabilities or governance attacks, could indirectly impact DittoETH. Diversifying the types of accepted collateral and maintaining rigorous security standards and audits for integrated protocols can help mitigate these risks.


## Conclusion

DittoETH presents an innovative approach to stablecoin issuance, leveraging staked Ethereum derivatives to offer users a flexible and potentially lucrative way to participate in the DeFi ecosystem. However, the platform faces challenges typical of complex financial systems, including centralization and systemic risks. By addressing the concerns highlighted in the audit findings and implementing the suggested improvements, DittoETH can enhance its resilience, security, and user trust, positioning itself as a leading platform in the stablecoin and wider DeFi space. Continuous vigilance, community engagement, and adaptation to the evolving DeFi landscape will be key to DittoETH's long-term success and contribution to a stable, decentralized financial system.

### Time spent:
48 hours