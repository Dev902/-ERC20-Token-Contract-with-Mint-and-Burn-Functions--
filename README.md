# -ERC20-Token-Contract-with-Mint-and-Burn-Functions--
# 🌟 MyToken - ERC20 Token Contract with Mint and Burn Functions 🌟

This repository contains a Solidity smart contract for the "MyToken" ERC20 token. It includes functionalities to mint and burn tokens, keeping track of the total supply and individual balances. This contract serves as a foundation for managing tokens on the Ethereum blockchain.

## Project Overview

This project is a Solidity smart contract for the "MyToken" ERC20 token. It enables token minting and burning operations, while tracking the total token supply and individual balances. The contract serves as a fundamental building block for managing tokens on the Ethereum blockchain.

## Process and Steps

### Contract Initialization

- The contract is initialized with the name "MyToken" and deploys an ERC20 token on the Ethereum blockchain.
- It sets the initial values for public variables, such as `tokenName`, `tokenAbbrv`, and `totalSupply`.
- Additionally, a mapping named `balances` is created to associate addresses with their token balances.

### Minting Tokens

The `mint` function is provided to create new tokens and distribute them to a specified address. When called, the function takes two parameters: `_address` (the recipient address) and `_value` (the number of tokens to be minted). Within the function, the total supply is increased by `_value`, and the `_value` is added to the balance of `_address` in the `balances` mapping.

### Burning Tokens

The `burn` function is implemented to remove tokens from circulation and decrease an address's balance. The function requires two parameters: `_address` (the owner of the tokens) and `_value` (the number of tokens to be burned). It first checks if the balance of `_address` is greater than or equal to `_value`. If the condition is met, the total supply is decreased by `_value`, and the `_value` is subtracted from the `_address` balance in the `balances` mapping.

## Code Snippets

Here are the `mint` and `burn` functions from the contract:

```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}

function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
