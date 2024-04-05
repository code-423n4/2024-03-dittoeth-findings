## [L01]
## IMPACT

Creation of SRs during order matching result in SR id collision for different users, this breaks protocol design intension (See coded POC)

## Description

According to the [documentation](https://dittoeth.com/technical/ob#shortrecord), a user’s SR position is identified by the user’s address and id. 

Contrary to that, the implementation of order matching results in a situation where the SR id for the matched order of different shorters are the same

## CODED POC

- `sender` and `extra` creates are two different shorters and create separate limit short orders
- `receiver` creates a limit bit just enough to match their short orders and create separate SR’
- two SRs are created with the same SR id

Add the test function below to the `BidOrders.t.sol` file and run 

```solidity
    function test_AddingLimitBidPriceEqualShortPriceIdCollisionLow() public {
    
        fundLimitShortOpt(DEFAULT_PRICE, DEFAULT_AMOUNT / 2, sender); // 2500

        fundLimitShortOpt(DEFAULT_PRICE, DEFAULT_AMOUNT / 2, extra); // 2500

        (, uint256 ercAmountLeft) = fundLimitBidOpt(DEFAULT_PRICE, DEFAULT_AMOUNT, receiver); // 5000

        // orders were matched no active bid or short
        checkEscrowedAndOrders({
            receiverErcEscrowed: DEFAULT_AMOUNT,
            receiverEthEscrowed: 0,
            senderErcEscrowed: 0,
            senderEthEscrowed: 0,
            bidLength: 0,
            askLength: 0,
            shortLength: 0,
            senderPrice: DEFAULT_PRICE
        });

        STypes.ShortRecord memory senderSR = getShortRecord(sender, 2);
        STypes.ShortRecord memory extraSR = getShortRecord(sender, 2);

        emit log_named_uint("sender's Sr Id", diamond.getShortRecords(asset, sender)[0].id);
        emit log_named_uint("extra's Sr Id", diamond.getShortRecords(asset, extra)[0].id);

        // @audit there is a collision id SR ids for different shorter

        assertEq(senderSR.id, 2);
        assertEq(extraSR.id, 2);

        assertEq(getShortRecordCount(extra), 1);

        assertEq(ercAmountLeft, 0);

       
    }
```

## TOOLS USED

Foundry

## RECOMMENDATION

I am not sure if this is intended design, otherwise consider implementing the SR creation logic to create unique id for each unique user. 


## [L02]
change the NATSPEC comment in [the `LibOrders.sol::updateBidOrdersOnMatch(...)`](https://github.com/code-423n4/2024-03-dittoeth/blob/91faf46078bb6fe8ce9f55bcb717e5d2d302d22e/contracts/libraries/LibOrders.sol#L469) 
from: @param orders The market that will be impacted
to: @param orders The orders mapping