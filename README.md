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
        // Use the `require` statement to ensure that the specified condition is met
        // before executing any further code. If the condition is not met, the contract
        // will throw an exception and the transaction will be reverted.
        require(amount <= balance, "Insufficient funds");

        // Use the `assert` statement to ensure that the specified condition is met
        // during contract execution. If the condition is not met, the contract will
        // throw an exception and the transaction will be reverted.
        assert(amount > 0);

        balance -= amount;
    }

    function withdrawAll() public {
        // Use the `revert` statement to revert the current transaction and
        // revert any state changes made by the transaction.
        revert("This function is not allowed");
    }
}
