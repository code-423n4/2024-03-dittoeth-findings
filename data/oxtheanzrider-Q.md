L-01 Unnecessary declaration of the depositETH function as payable

declaring of the function depositETH is unnecessary as payable is used when functions are expected to receive Ether directly. However, the function depositETH does not accept Ether directly as a parameter or directly from the function call itself.

    function depositEth(address bridge) external payable nonReentrant {
        if (msg.value < C.MIN_DEPOSIT) revert Errors.UnderMinimumDeposit();

        (uint256 vault, uint256 bridgePointer) = _getVault(bridge);

        uint88 dethAmount = uint88(IBridge(bridge).depositEth{value: msg.value}()); // Assumes 1 ETH = 1 DETH
        vault.addDeth(bridgePointer, dethAmount);
        maybeUpdateYield(vault, dethAmount);
        emit Events.DepositEth(bridge, msg.sender, dethAmount);
    }


L-02 Missing valid input parameters checks

checks to ensure price and Ercamount are greater than zero are not implemented.

Recommendation
use of require
require(price > 0 && ercAmount > 0, "Price and ercAmount must be greater than zero")



L-03 Missing event logging

The necessity of the emission of events for such as:
MatchOrder Event,BidCreated Event, ShortMatched Event, ShortRecordUpdated Event can be debated but of uptmost importance as it helps provide valuable insights, transparency, and monitoring capabilities for users and administrators.






 






