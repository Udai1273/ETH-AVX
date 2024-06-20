# Error Handling

This Solidity program is a simple "Error Handling" program that demonstrates the use of three main error handling function in Solidity .

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
pragma solidity ^0.8.0;

contract Modifier {
    uint public balance=0;
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    modifier ownerOnly() {
        require(msg.sender == owner, "Only the owner can call this function");
        _;
    }

    function deposit(uint val) public payable {
        require(val > 0, "amount must be greater than zero");
        balance += val;
    }

    function withdraw(uint256 amount) public ownerOnly {
        require(amount <= balance, "Insufficient balance to withdraw");

        uint256 oldBalance = balance;
        balance -= amount;

        assert(balance == oldBalance - amount);

    }

    function triggerRevert() public pure {
        revert("This function always reverts");
    }


}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile ErrorHandling.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "ErrorHandling" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with all three of functions.

## Authors

Udai Raj Singh Negi
udai.negi135@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
