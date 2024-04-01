# [L1]  Lack of Documentation Accuracy in Oracle Contract

***In the contract code being audited, there is an inconsistency between the inline comment and the actual behavior of the code regarding the return values of a function. The inline comment states that the function should return both the cumulative ticks and liquidity for each timestamp secondsAgo from the current time. However, upon inspection of the function implementation, it was found that the function only returns the cumulative ticks and does not include the liquidity information as described in the comment.***

https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L58C8-L58C123

### Impact
***This inconsistency between the documented behavior and the actual implementation could lead to misunderstandings or misinterpretations by developers who rely on the inline comments for understanding the contract functionality. If developers assume that the function returns both cumulative ticks and liquidity.***

#### Recommendation
Either you make an edit of the inline [comment](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/UniswapOracleLibrary.sol#L58C8-L58C123) if you know you don't want to use the secondsPerLiquidityCumulativeX128s;
>This information provides insights into how liquidity has been added or removed from the pool over time. It helps in understanding liquidity trends and analyzing liquidity provider behavior.