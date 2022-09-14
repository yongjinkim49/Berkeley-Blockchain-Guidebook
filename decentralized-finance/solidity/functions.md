---
description: 'Source: https://docs.soliditylang.org/en/v0.8.16/contracts.html#functions'
---

# Functions

Functions can be defined inside and outside of contracts.

Functions outside of a contract, also called “free functions”, always have implicit `internal` [visibility](https://docs.soliditylang.org/en/v0.8.16/contracts.html#visibility-and-getters). Their code is included in all contracts that call them, similar to internal library functions.



```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;

function sum(uint[] memory arr) pure returns (uint s) {
    for (uint i = 0; i < arr.length; i++)
        s += arr[i];
}

contract ArrayExample {
    bool found;
    function f(uint[] memory arr) public {
        // This calls the free function internally.
        // The compiler will add its code to the contract.
        uint s = sum(arr);
        require(s >= 10);
        found = true;
    }
}
```
