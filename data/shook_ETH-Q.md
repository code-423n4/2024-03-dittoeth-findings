The pragma solidity declare version is 0.8.21
but the latest version of solidity is 0.8.25

Recommendation
Change the solidity version to the latest one.

----------------------------------------------
In BridgeReth.sol

Exposing private variable(RETH_TYPEHASH) using 
external function getBaseCollateral() 
is very prone to attack. It may expose
sensitive information or make it easier
to launch further attack.

Recommendation
Don't expose private variable using
external function