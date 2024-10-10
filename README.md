# I Love You Token (ILY)

This Solidity program demonstrates the creation of a basic token contract on the Ethereum blockchain. It is designed to introduce beginners to the Solidity programming language by implementing simple minting and burning functionality. This contract allows users to create ("mint") and destroy ("burn") tokens.

## Description
The "I Love You" (ILY) token is a simple example of an ERC-20-like token built in Solidity. The contract includes the following features:

    Minting: Increases the total token supply and assigns tokens to a specific address.
    Burning: Decreases the total supply of tokens by removing tokens from a specific address, provided that the address has enough tokens.
    The token's name is "I Love You," and its ticker symbol is "ILY".

This contract is meant as a basic introduction to Solidity and smart contract programming, which can serve as a foundation for more advanced projects.

## Getting Started
### Executing the Program

To run this program, use Remix, an online IDE for Solidity development. Follow these steps:

    Visit Remix.
    Create a new file by clicking the "+" icon in the left-hand sidebar and name it myToken.sol.
    Copy and paste the following code into the file:

```javascript

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract myToken {
    // Public variables here
    string public tokenName = "I Love You";
    string public tokenAbbrv = "ILY";
    uint public totalSupply = 0;

    // Mapping to store balances
    mapping(address => uint) public balances;

    // Mint function to create tokens
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to destroy tokens
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
### Compiling and Deploying the Contract

    Click on the "Solidity Compiler" tab in Remix, and set the compiler version to 0.8.18.
    Compile the contract by clicking "Compile myToken.sol".
    After successful compilation, go to the "Deploy & Run Transactions" tab.
    Select the myToken contract from the dropdown menu and click "Deploy".
    Once deployed, you can use the mint and burn functions to interact with the contract.

### Interacting with the Contract

    Minting: Call the mint function by providing an address and the number of tokens you want to create for that address.
    Burning: Call the burn function by specifying an address and the number of tokens you want to destroy from that address, ensuring the address holds enough tokens to burn.

## Authors

Metacrafter Chris_Narumi

## License

This project is licensed under the MIT License. See the LICENSE.md file for details.
