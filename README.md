
# Safe Wallet

## About
A wallet contract which is intended to be more secure than pure address wallets.

The contract has two different user roles: 1) the owner, and 2) the user.
Only the user is allowed to request withdrawals from the contract. In case
a withdrawal is requested, the contract fires an event, allowing a client
program to send a notification to the owner's email address. Within a specified
waiting period, the owner can cancel the withdrawal and freeze the wallet, for
example if the requested withdrawal was made by a hacker.

The idea is that one do not have to worry about keeping the private key file of
the user account in devices that are connected to the Internet, as long as the
owner address is stored securely. The owner address/account is however needed
in the following cases: when the contract is deployed, when the contract settings
are modified, when a request must be cancelled, or when the contract is killed
(in which case the remaining funds are transferred to the owner. These special
transactions can be generated offline to ensure security.

## Deployment

TODO

## Testing

This project uses [Truffle framework](http://truffleframework.com/) which 
provides Mocha + Chai libraries for testing solidity contracts through 
[web3.js](https://github.com/ethereum/web3.js/) interface.

Install Truffle:
```
npm install -g truffle
``` 

Start Truffle development engine:
```
truffle development
``` 

Run unit tests:
```
truffle(develop)> test
``` 

## Future features:
 - ability for the owner to add trusted withdrawal addresses