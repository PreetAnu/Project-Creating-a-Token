# Project-Creating-a-Token
This Solidity program is a simple token creation contract that demonstrates the basic functionalities and features of token management on the Ethereum blockchain. The purpose of this program is to provide a starting point for those who are new to Solidity and want to learn how to create and manage their own tokens.

## Description
This program is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract allows users to create a token with a name, abbreviation, and total supply. It includes functions for minting new tokens and burning existing tokens. This program serves as an introduction to token management in Solidity, and can be used as a foundation for more complex projects in the future.

## Requirements
* The contract has public variables that store the details about the coin (Token Name, Token Abbrv., Total Supply).
* The contract has a mapping of addresses to balances **(address => uint)**.
* A mint function that takes two parameters: an address and a value. The function increases the total supply by that number and increases the balance of the specified address by that amount.
* A burn function, which works the opposite of the mint function, as it will destroy tokens. It takes an address and value just like the mint functions. It then deducts the value from the total supply and from the balance of the specified address.
* The burn function includes conditionals to make sure the balance of the address is greater than or equal to the amount that is supposed to be burned.

## Getting Started
### Executing Program 
1. To **run this program**, I used Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).
2. **Create a New File:**
 * Click on the "+" icon in the left-hand sidebar.
 * Save the file with a .sol extension (e.g.,MyToken.sol).
3.  **Copy and Paste the Code**: Copy the following code and paste it into the newly created file:
   ```
   // SPDX-License-Identifier: MIT
pragma solidity 0.8.9;

contract MyToken {
    // Public variables here
    string public TokenName = "Ethereum";
    string public TokenAbbrv = "ETH";
    uint public TotalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balance;

    // Mint function
    function mint(address Address, uint Value) public {
        TotalSupply += Value;
        balance[Address] += Value;
    }

    // Burn function
    function burn(address Address, uint Value) public {
        if (balance[Address] >= Value) {
            TotalSupply -= Value;
            balance[Address] -= Value;
        }
    }
}
```
4. **Compile the Code**:
* Click on the "Solidity Compiler" tab in the left-hand sidebar.
* Make sure the "Compiler" option is set to "0.8.9" (or another compatible version).
* Click on the "Compile MyToken.sol" button or use short-cut key **(Ctrl+s)**.
5. **Deploy the Contract:**
* Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
* Select the "MyToken" contract from the dropdown menu.
* Click on the "Deploy" button.
6. **Interact with the Contract:**
* **Mint Tokens:** Call the ***mint*** function with the address and amount of tokens to be created. This increases the total supply and the balance of the specified address
* **Burn Tokens**: Call the ***burn*** function with the address and amount of tokens to be destroyed. This decreases the total supply and the balance of the specified address, provided the address has enough balance.

## Author
Anupreet Kaur

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.
