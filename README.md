#example
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Errorhandling {
    uint256 public count;

    function incrementCount(uint256 value) public {
        require(value > 0, "Value must be greater than zero");
        count += value;
        assert(count >= value);
    }

    function decrementCount(uint256 value) public {
        require(value > 0, "Value must be greater than zero");
        require(value <= count, "Value exceeds the current count");
        count -= value;
        assert(count <= count + value);
    }

    function resetCount() public {
        if (count == 0) {
            revert("Count is already zero");
        }
        count = 0;
    }
}
