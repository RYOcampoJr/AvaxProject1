# AvaxProject1
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract FunctionalityContract {
    address public owner;
    uint256 public value;

    constructor() {
        owner = msg.sender;
    }

    function setValue(uint256 _newValue) external {
        require(msg.sender == owner, "Only the owner can set the value");
        value = _newValue;
    }

    function asserts(uint256 a, uint256 b) external pure returns (uint256) {
        assert(a != b);
        return a + b;
    }

    function reverts(uint256 _valueToCheck) external pure returns (bool) {
        if (_valueToCheck < 10) {
            revert("Value must be greater than or equal to 10");
        }
        return true;
    }
}
