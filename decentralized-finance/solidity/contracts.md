---
description: 'Source: https://docs.soliditylang.org/en/v0.8.16/contracts.html'
---

# Contracts

Contracts in Solidity are similar to classes in object-oriented languages. They contain persistent data in state variables, and functions that can modify these variables. Calling a function on a different contract (instance) will perform an EVM function call and thus switch the context such that state variables in the calling contract are inaccessible. A contract and its functions need to be called for anything to happen. There is no “cron” concept in Ethereum to call a function at a particular event automatically.

Contracts can be created “from outside” via Ethereum transactions or from within Solidity contracts.

IDEs, such as [Remix](https://remix.ethereum.org/), make the creation process seamless using UI elements.

One way to create contracts programmatically on Ethereum is via the JavaScript API [web3.js](https://github.com/ethereum/web3.js). It has a function called [web3.eth.Contract](https://web3js.readthedocs.io/en/1.0/web3-eth-contract.html#new-contract) to facilitate contract creation.

When a contract is created, its [constructor](https://docs.soliditylang.org/en/v0.8.16/contracts.html#constructor) (a function declared with the `constructor` keyword) is executed once.

A constructor is optional. Only one constructor is allowed, which means overloading is not supported.

After the constructor has executed, the final code of the contract is stored on the blockchain. This code includes all public and external functions and all functions that are reachable from there through function calls. The deployed code does not include the constructor code or internal functions only called from the constructor.

Internally, constructor arguments are passed [ABI encoded](https://docs.soliditylang.org/en/v0.8.16/abi-spec.html#abi) after the code of the contract itself, but you do not have to care about this if you use `web3.js`.

If a contract wants to create another contract, the source code (and the binary) of the created contract has to be known to the creator. This means that cyclic creation dependencies are impossible.

