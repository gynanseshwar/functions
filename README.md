# Token 

## Overview

This Solidity smart contract implements a basic ERC-20 token with additional functionalities such as burning tokens and minting new tokens. The contract is also Ownable, meaning that it has an owner with special privileges, such as the ability to mint new tokens.

## License

This code is licensed under the MIT License. Please refer to the SPDX-License-Identifier in the code for more details.

## Contracts

### Token.sol

This is the main contract that inherits from the OpenZeppelin ERC20, ERC20Burnable, and Ownable contracts. It represents the ERC-20 token with additional features.

#### Constructor

- **Parameters:**
  - `TKName`: The name of the token.
  - `TKcode`: The symbol or code representing the token.

- **Functionality:**
  - Initializes the token with a total supply of 50 tokens, minted to the contract deployer (presumably the owner).

#### Minting

- **Function:**
  - `mint(address account, uint256 tally) public onlyOwner`
  
- **Parameters:**
  - `account`: The address to which new tokens will be minted.
  - `tally`: The amount of tokens to mint.

- **Functionality:**
  - Allows the owner to mint new tokens and allocate them to a specific account.

#### Burning

- **Function:**
  - `burn(uint256 tally) public override`
  
- **Parameters:**
  - `tally`: The amount of tokens to burn.

- **Functionality:**
  - Allows any token holder to burn their own tokens, reducing the total supply.

#### Transfer

- **Function:**
  - `transfer(address payee, uint256 tally) public virtual override returns (bool)`
  
- **Parameters:**
  - `payee`: The address to which tokens will be transferred.
  - `tally`: The amount of tokens to transfer.

- **Functionality:**
  - Overrides the transfer function from the ERC20 contract to add custom logic.

## Usage

1. Deploy the `Token` contract, providing the desired name and code for the token.
2. The deployer becomes the owner of the token contract and receives an initial supply of 50 tokens.
3. The owner can mint new tokens using the `mint` function, providing the recipient's address and the amount to mint.
4. Token holders can burn their own tokens using the `burn` function, reducing the total supply.
5. Token holders can transfer tokens to other addresses using the standard ERC-20 `transfer` function with additional logic.
