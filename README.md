# Error Handling

This Solidity program is a simple "Error Handling" program that demonstrates the use of three main error handling function in Solidity.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has 3 functions:-
1. revert():- Explicitly halts execution and reverts any state changes made so far in the current transaction.
2. require():- Used to validate inputs, conditions, or contract state before executing the rest of the function.
3. assert():- Used to check for internal errors and invariants that should never occur if the contract’s logic is correct.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ErrorHandling.sol). Copy and paste the following code into the file:

```javascript
pragma solidity ^0.8.13;
contract ErrorHandling {


    function requireUse(uint some) public pure{
        require(some==10,"the input must be 10");
    }


    function revertUse(uint some) public pure{
        if(some!=10){
            revert("Input must be 10");
        }
    }

    uint temp=0;
    function assertUse() public view{
        assert(temp==0);
    }
    


}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile ErrorHandling.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.

## Authors

Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
