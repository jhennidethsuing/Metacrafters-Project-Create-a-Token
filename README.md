Project: Token Creation

This Solidity smart contract aims to facilitate the creation, management, and utilization of a basic token system named "Meta (MTA)". It enables functionalities for minting to create or add tokens and burning to remove tokens.

Getting Started

Running the Program
I've utilized Remix, accessible at https://remix.ethereum.org/, to develop this program.

// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

- `SPDX-License-Identifier: MIT`: Denotes the license.
- `pragma solidity 0.8.25;`: Specifies the version.

The contract is named "MyToken", empowering users to mint and burn tokens. It incorporates public variables, a mapping, and functions for minting and burning tokens.

Public Variables

contract MyToken {

    // Public variables
    string public tokenName = "Meta";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

The public variables represent:
- `tokenName`: The token's name, set to "Meta".
- `tokenAbbrv`: The token's abbreviation, set to "MTA".
- `totalSupply`: The total supply of tokens, initially set to 0.

Mapping Variable

    // Mapping variable
    mapping(address => uint) public balances;

This variable maps Ethereum addresses to their corresponding token balances.

Functions

Mint Function 

    // Mint function
    function mint(address _address, uint _value) public  {
        totalSupply += _value;
        balances[_address] += _value;
}

This mint function enables the contract owner to mint or add a specified amount of tokens and assign them to a specific address.

Burn Function 

    // Burn function
    function burn(address _address, uint _value) public  {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    } 

The burn function allows the contract owner to burn or remove tokens from a specific address.

Author
Jhennideth Suing 422001869@ntc.edu.ph
