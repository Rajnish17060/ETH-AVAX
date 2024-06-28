# Smart Contract Project

This program is a simple program that demonstrates the working of require(),assert() and revert() statements.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has functions like incrementCount, decrementCount and resetCount. incrementCount function is used to increase the value, decrement function is used to decreasse the value and resetCount is used to reset the count value to zero. 
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Project.sol). Copy and paste the following code into the file:

```javascript
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

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Project.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Errorhandling" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the incrementCount, decrementCount and resetCount function. Click on the "Errorhandling" contract in the left-hand sidebar.
After that you can see "decrementCount", "incrementCount", "resetCount" and "count". Click on the incrementCount function and pass the value by which you want to increase the count and then click on transact. Now, click on count to see the increment of value. In same way you can use decrementCount function. When you click on resetCount, the value of count will be zero.

## Authors
Rajnish Kumar
