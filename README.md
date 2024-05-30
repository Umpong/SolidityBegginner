# Solidity

The goal of this Solidity application is to build a smart contract that will hold information about our token. 
This program's goal is to illustrate a token's fundamental syntactic functionality, such as its mint and burn functions.

## Description

The public variables in the contract (Token Name, Token Abbrv., and Total Supply) store information about the coin, the addresses and balances are mapped in the contract (address => uint).
The mint function in the contract requires two inputs: an address and a value. The function then raises the balance and the total supply by that amount of the "sender" address by the specified sum
The contract includes a burn function that destroys tokens, operating in opposition to the mint function. 
In the same way as the mint operates, it will require an address and value. The value will then be subtracted from the entire supply and from the "sender's" equilibrium.
Lastly, the burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.

## Getting Started

Remix is an online Solidity IDE that may be used to run this software; to get started, visit the Remix website at https://remix.ethereum.org.

Click the "+" symbol in the left-hand sidebar to start a new file once you are on the Remix website. Save the file as HelloWorld.sol or another file with the.sol extension. 

### Executing program
Copy and paste the code into the file:

pragma solidity 0.8.18;

contract AbayonToken {

string public tokenName = "AEROS";
string public tokenAbbrv = "ARS";
uint public totalSupply = 10;

mapping(address => uint) public balance;

function mint (address _address, uint _value) public {
  totalSupply += _value;
  balance[_address] += _value;
}

function burn (address _address, uint _value) public {
  if (balance[_address] >= _value) {
     totalSupply -= _value;
     balance[_address] -= _value;
  }
}
}



Select the "Solidity Compiler" tab from the sidebar on the left to begin compiling the code. Click the "Compile _.sol" button after ensuring that the "Compiler" option is set to"0.8.18" (or another suitable version).

Selecting the "Deploy & Run Transactions" tab from the left-hand sidebar will allow you to deploy the contract after the code has been compiled. From the dropdown menu, choose the compiled contract, and then press the "Deploy" button.

You can communicate with the contract by using the methods once it has been deployed. Select the function by clicking on it after selecting the compiled contract in the left-hand sidebar. Lastly, to run the function and get the value, click the "transact" button.

## Authors

Don Jhonson Abayon


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
