# MyToken Contract

This Solidity contract, named MyToken, is a basic implementation of a token contract on the Ethereum blockchain.

## Overview

MyToken is a simple ERC20-compliant token with functionalities to mint new tokens and burn existing ones.

## Getting Started

### Token Details

- **Token Name:** lakhan
- **Token Abbreviation:** svm
- **Total Supply:** 0 (initially)

## Executing Program
1. Open Remix (https://remix.ethereum.org/) in your web browser.
2. Create a new Solidity file or import the MyToken.sol contract.
3. Compile the contract by selecting the appropriate compiler version (0.8.18) and clicking "Compile".
4. Deploy the contract by selecting the "Deploy & Run Transactions" tab.

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;



contract MyToken {

    // Public variables to store token details
    string public tokenName = "lakhan";
    string public tokenAbbrs = "svm";
    uint public totalSupply = 0;

    // Mapping to store balances of addresses
    mapping(address => uint) public balance;

    // Function to mint new tokens
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balance[_address] += _value;
    }

    // Function to burn tokens
    function burn(address _address, uint _value) public {
        require(balance[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balance[_address] -= _value;
    }
}


## Authors
Lakhan Singh

## License
This contract is licensed under the MIT License. See the LICENSE.md file for details.
