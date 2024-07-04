// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract Bank {
    uint256 public balance;

    constructor(uint256 initialBalance){
        balance = initialBalance;
    }

    function deposit(uint256 amount) public {
        balance += amount;
    }

    function withdraw(uint256 amount) public {
        //a function that will withdraw or pull out money from the bank
        //will throw an error exception if the condition will not be met
        require(amount <= balance, "Insufficient funds");
        assert(amount > 0);

        balance -= amount;
    }

    function withdrawEverything() public {
        // Just an additional function but not allowed to be transacted
        revert("This function is not allowed");
    }
}
