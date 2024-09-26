/ SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

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

    mapping(address => uint) public balance;

    // mint function
    function mint(address Address, uint Value) public{
        totalSupply +=Value;
        balance[Address] += Value;
    }

    // burn function
    function burn (address Address, uint Value) public{
        if(balance[Address] >= Value){
            totalSupply -= Value;
            balance[Address] -= Value; 
        }
    }
}
/

# Functions Description
# mint
function mint(address Address, uint Value) public
# Parameters:
Address: The address to which the minted tokens will be added.
Value: The amount of tokens to be minted.
Description: This function increases the totalSupply by the Value specified and updates the balance of Address by the same amount.
burn
function burn(address Address, uint Value) public
# Parameters:
Address: The address from which the tokens will be burned.
Value: The amount of tokens to be burned.
Description: This function decreases the totalSupply by the _value specified and updates the balance of _address by the same amount. It includes a check to ensure that the Address has enough tokens to burn; otherwise, it will revert the transaction with an error.
# How to Use
Deploy the Contract: Use Remix or any other Ethereum development environment to deploy the contract on the Ethereum blockchain.

Mint Tokens: Call the mint function with the recipient's address and the amount of tokens to mint.

Burn Tokens: Call the burn function with the sender's address and the amount of tokens to burn. Ensure the sender has enough tokens to burn, otherwise, the transaction will fail.

# License
This project is licensed under the MIT License - see the LICENSE file for details.

# Acknowledgments
Solidity Documentation
OpenZeppelin Contracts Library
Ethereum Community
