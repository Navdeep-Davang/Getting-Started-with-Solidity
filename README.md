# Getting-Started-with-Solidity

This is the code Solidity contract with use case of variables, mapping, functions, if-else statements. This Solidity program is a simple "mint and burn token" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. 
1) We declare the public variables for the token name, symbol, and total supply.

2) We declare the mapping of addresses to balances, which will store the token balance of each address.

3) We define the mint function, which takes an address and a value as parameters. The function increases the total supply by the value and the balance of the recipient address by the same value.

4) We define the burn function, which works in the opposite way as the mint function. It first ensure that the sender has enough balance to burn the tokens and that the balance of the sender is greater than or equal to the value. Then it decreases the total supply and the balance of the sender by the same value. Otherwise it revert insuficient balance statment.

## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Getting-Started-with-Solidity.sol).

```javascript
pragma solidity ^0.8.4;

contract MyToken {
/* code */
}
```
First we define version of solidity we want to use(i.e. 0.8.4). After that we created a contract named Mytoken.   
```javascript
// public variables here
    string public Token_Name;
    string public Token_Abbrv;
    uint256 public Total_supply;
```

In this Mytoken contract we declared three variabels (Token_Name, Token_Abbrv, Total_supply) by their type(eg. string) and accessibility(eg. public).
```javascript
 // mapping variable here
    mapping (address=>uint256) public balances;
 ```   
After that we created mapping of account address to balance. It is similar to dictionary function in python.

```javascript
 // mint function
    function mint(address _addr, uint256 _val) public {
        Total_supply += _val;
        balances[_addr] += _val;
    }
```
After that we created mint funtion which will take account address(i.e. _addr) and increamenting value(i.e. _val) as a input parameters. It then uses them to increment the Total_supply and balances. 

```javascript
 // burn function
    function burn(address _addr, uint256 _val) public {
       if(Total_supply >= _val) 
         {
           Total_supply -= _val;
            balances[_addr] -= _val;
         }else 
            {revert("You dont have enough balance");}
    }
```    
Similarly we created mint function which can decrement the balance of corresponding account. Input paramenters and logic of decreament is similar that of mint funtion. But if-else statment is used to check that given account(i.e. _addr) has enough balance for decreasing it. If it has enough balance then the balnce amount is dcremented by input value(i.e._val) 

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile Getting-Started-with-Solidity.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Mytoken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. We can give address(i.e._addr) and tansfer value(i.e._val) to mint and burn funtion and see the value reflected under Total_supply.


License
This project is licensed under the MIT License - see the LICENSE.md file for details


