## Creation of a Token

This project is a blockchain-based digital currency providing secure and transparent minting and burning functionalities on the Ethereum network.

## Description

This is a smart contract written in Solidity that creates a token called "GALAXY" (abbreviated as "GLX"). It has functions to:

- Mint new tokens and assign them to an address
- Burn (destroy) tokens from an address

The contract also keeps track of the total token supply and each address's token balance.

The project aims to deliver an efficient means of transferring value, ensuring public accessibility to token details and balances while maintaining a secure and immutable transaction record.

## Getting Started

### Installing

* This program is written in a code named file in J-Anushka/MyToken repository on github, this can be downloaded from there

### Executing program

To run this program, I'm using Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

 // SPDX-License-Identifier: MIT
 pragma solidity ^0.8.18;
 
 contract MyToken {
 
    // public variables here
    string public myTokenName = "GALAXY";
    string public MyTokenAbbrv = "GLX";
    uint public TotalSupply = 0;

    // mapping variable here
    mapping(address => uint) public MyTokenBalance;

    // mint function
    function mint (address _address, uint _value) public {
        TotalSupply += _value;
        MyTokenBalance[_address] += _value;
    }

     // burn function
    function burn (address _address, uint _value) public {
        if (MyTokenBalance[_address] >= _value)
        TotalSupply -= _value;
        MyTokenBalance[_address] -= _value;
    }

 }

- To mompile the code:
    - Click on the "Solidity Compiler" tab in the left-hand sidebar
    - Set the "Compiler" option to "0.8.4" (or another compatible version)
    - Click on the "Compile MyToken.sol" button

- To deploy the contract:
    - Click on the "Deploy & Run Transactions" tab in the left-hand sidebar
    - Select the "MyToken" contract from the dropdown menu
    - Click on the "Deploy" button

- To interact with the contract:
    - Click on the "transact" button to execute the function

## Authors

Anushka Jaiswal

anushkajais1001@gmail.com

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
