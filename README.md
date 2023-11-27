# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat run scripts/deploy.js
```

## Summary
The code snippet is a Solidity smart contract called "Token" that represents a basic token with a fixed supply. It allows for the transfer of tokens between Ethereum accounts and provides a function to retrieve the token balance of an account.

## Example Usage
```solidity
Token token = new Token();
address recipient = 0x1234567890abcdef;
uint256 amount = 100;
token.transfer(recipient, amount);
uint256 balance = token.balanceOf(recipient);
```
In this example, a new instance of the Token contract is created. Then, 100 tokens are transferred from the contract deployer to the recipient address. Finally, the balance of the recipient address is retrieved.

## Code Analysis
### Inputs
- `to` (address): The Ethereum address to which tokens will be transferred.
- `amount` (uint256): The amount of tokens to be transferred.
___
### Flow
1. The contract is initialized with a fixed total supply of tokens assigned to the deployer's address.
2. The `transfer` function is called with the recipient address and the amount of tokens to be transferred.
3. The function checks if the sender has enough tokens and reverts the transaction if not.
4. If the sender has enough tokens, the transfer is executed by subtracting the amount from the sender's balance and adding it to the recipient's balance.
5. An event is emitted to notify off-chain applications about the transfer.
___
### Outputs
- None (void): The `transfer` function does not return any value.
- `balanceOf` function returns the token balance of a given account as a `uint256` value.
___
