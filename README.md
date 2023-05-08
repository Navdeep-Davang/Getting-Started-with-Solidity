# Getting-Started-with-Solidity
This is the code Solidity contract with use case of variables, mapping, functions, if-else statements 

Let me explain each part of the code.

1) We declare the public variables for the token name, symbol, and total supply.

2) We declare the mapping of addresses to balances, which will store the token balance of each address.

3) We define the mint function, which takes an address and a value as parameters. The function increases the total supply by the value and the balance of the recipient address by the same value.

4) We define the burn function, which works in the opposite way as the mint function. It first ensure that the sender has enough balance to burn the tokens and that the balance of the sender is greater than or equal to the value. Then it decreases the total supply and the balance of the sender by the same value. Otherwise it revert insuficient balance statment.


