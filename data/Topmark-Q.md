### Report 1:
#### Fund Loss due to Precision Loss
The convertCR(...) function in the LibOrders contract shows how covert is done for Cr to a lower decimal which means certain amount of value would be lost during the division, the problem is that this lost value is not accounted for by protocol and would be completely lost
https://github.com/code-423n4/2024-03-dittoeth/blob/main/contracts/libraries/LibOrders.sol#L36
```solidity
  function convertCR(uint16 cr) internal pure returns (uint256) {
>>>        return (uint256(cr) * 1 ether) / C.TWO_DECIMAL_PLACES;
    }
```
###  Report 2:
