# etherembegginer
# Token contract
Solidity-based token contract application created in the Ethereum programming language. A token contract's fundamental implementation is provided by this code. Its function is to make it possible to mint and burn tokens, respectively. This code is used to manage a basic token system that may be applied to many other things, such as developing digital assets, incentive programs, or decentralized financial protocols.

# Description
A token implementation is represented by this Solidity contract. Users are able to create new tokens and burn old ones. The mapping used by the contract serves to maintain track of the token's name, acronym, total supply, and individual token balances. Subject to certain restrictions, the burn function reduces the total supply and balance of the sender's address while the mint function raises the total supply and balance of a given address.

# Getting Started
### Executing program
Use the online Solidity IDE Remix to run this program. Visit the Remix website at https://remix.ethereum.org to get started.

When you are on the Remix website, click the "+" icon in the left sidebar to start a new file. 
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
I created a contract called "Token" that will house the information and features of a unique token. Three variables were made by myself. These variables are accessible from outside the contract since they are declared as public. They keep the token's original supply, which is zero, as well as its name and acronym (Microprocessor and MP, respectively). 

I made a mapping variable (address => uint) in the following section. This statement assigns the value _myamount to the address and states that it is mapped to an uint. 

Following that, I developed a function that enables the contract owner to issue fresh tokens. It requires two inputs: cost, which indicates the number of tokens to be minted, and _address, which represents the address to which the tokens will be transferred. The function adds the newly produced tokens to the balance of the supplied address and raises the overall supply by the set amount. 

I developed a different burn function that is the reverse of mint. Holders of tokens can burn (destroy) their tokens using the burn function. It requires two inputs: cost, which represents the number of tokens to be burned, and _address, which represents the address from which tokens will be burned. The function initially determines whether the address has enough funds to burn the required number of tokens. If so, it deducts the tokens that were burned from the available supply and lowers the balance at the specified address.

### Compilation
Click the "Solidity Compiler" tab in the left-hand sidebar to compile the code. Click the "Compile Token.sol" button after making sure the "Compiler" option is set to "0.8.18" (or another compatible version).

Using the "Deploy & Run Transactions" tab in the left-hand sidebar, you can deploy the contract after the code has been compiled. Click the "Deploy" button after choosing the "Token" contract from the drop-down menu.

You can start the contract deployment process after the code has been compiled. Six buttons, two of which are orange and four of which are Steel Blue, will be present during deployment. Functions are represented by the orange buttons, and variables are represented by the steel blue buttons.

When you click "totenName," the word "Microprocessor" will appear. When "tokenAbbrv" is clicked, "MP" appears. The "amount" is not showing any value, and the "totalSupply" is currently set to 0.

Select any random address from the accounts shown above the deploy button to continue. The address of choice is copied to the clipboard.
Copy the address, put it into the "mint" function, and give the context a random number, like 4000. When finished, check "totalSupply" once more; it should now display 4000. Use the "bur" function to perform the same steps; this time, the value will decrease rather than increase.

An analogous method can be used to check the balance.

# Licence
This project is licensed under the MIT License - see the LICENSE.md file for details


