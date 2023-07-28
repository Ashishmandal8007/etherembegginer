
# myToken
This application is based on solidity programming language ,in which we have created our own token.The main work of this application to mint and burn token,respectively.This application basically manages the token system,for example digital asset,decentralized financial system. 

# Description
Created a contract myToken in which  i have pased 3 public variable ,after that i have created to function which are mint and burn  respectively, where Users are able to create new tokens and burn old ones. The mapping variable used by the contract to maintain the track of the token's name, tokenAbbrv, total supply, and individual token balances. The burn function reduces the total supply and balance of the sender's address while the mint function raises the total supply and balance of a given address.

# Getting Started
### Executing program
We have used online Solidity IDE Remix to run this program. Visit the Remix website at https://remix.ethereum.org to get started.

When we are on the Remix website, click the "+" icon in the left sidebar to start a new file. 
Add the.sol extension to the file, for example, Token.sol. Write the provided code into your file now.
```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
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
    string public tokenname ="Microprocessor";
    string public tokenAbbrv = "MP";
    uint public totalsupply = 0;

    // mapping variable here
    mapping(address => uint) public myamount;

    // mint function
    function mint (address _address,uint _cost) public{
        totalsupply += _cost;
        myamount[ _address] += _cost;
    } 
    // burn function
    function burn(address _address,uint _cost) public{
        if (myamount[_address] >= _cost){
            totalsupply -= _cost;
            myamount[_address] -=_cost;
        }
    }
}
```
### Expalanation
I have created a contract called "myToken" that holds  information and features of a unique token. I have created three public variables and these variables are accessible from outside the contract. They keep the token's original supply, which is zero, as well as its name and tokenabbrv (Microprocessor and MP, respectively). 
I have created a mapping variable (address => uint), this statement assigns the value _myamount to the address and states that it is mapped to an uint.

I have created a mint function that enables the contract owner to issue fresh tokens. It will requires two inputs: cost, which indicates the number of tokens to be minted, and _address, which represents the address to which the tokens will be transferred. The function adds the newly produced tokens to the balance of the supplied address and raises the overall supply by the set amount. 

I have created another function that is the reverse of mint(burn). User of tokens can burn (destroy) their tokens using the burn function. It will require two inputs: cost, which represents the number of tokens to be burned, and _address, which represents the address from which tokens will be burned. The function initially determines whether the address has enough funds to burn the required number of tokens. If so, it deducts the tokens that were burned from the available supply and lowers the balance at the specified address.

### Compilation
By Clicking  the "Solidity Compiler" tab in the left-hand sidebar to compile the code. Click the "Compile Token.sol" button after making sure the "Compiler" option is set to "0.8.18" (or another compatible version).

Using the "Deploy & Run Transactions" tab in the left-hand sidebar, you can deploy the contract after the code has been compiled. Click the "Deploy" button after choosing the "Token" contract from the drop-down menu.

Where we can start the contract deployment process after the code has been compiled. There are six buttons, two of which are orange and four of which are Steel Blue, will be present during deployment. Functions are represented by the orange buttons, and variables are represented by the steel blue buttons.

When you click "tokenName," the word "Microprocessor" will appear. When "tokenAbbrv" is clicked, "MP" appears. The "amount" is not showing any value, and the "totalSupply" is currently set to 0.

Select any random address from the accounts shown above the deploy button to continue. The address of choice is copied.
Copy the address, put it into the "mint" function, and give the context a random number, like 1000. When it is finished, check "totalSupply" once more; it should now display 1000. Use the "burn" function to perform the same steps; this time, the value will decrease rather than increase.

An analogous method can be used to check the balance.

# Licence
This project is licensed under the MIT License - see the LICENSE.md file for details


