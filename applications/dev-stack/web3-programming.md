# Web3 Programming

## Web3 Programming

Though the resources you can refer to for blockchain development is quite abundant, most seem to provide only a part of the whole picture. Here, we try to provide a high-level overview of the dev stack required for web3 development. After all, just as it is the case for web2 (or non-web3) development, there are several types programming languages that you can refer to depending on which part of development/engineering you are pursuing.

Here are some programming languages we introduce to you for building in web3.



* Solidity
* Clarity
* Vyper
* Go
* Huff
* Rust
* Move
* Cairo
* Haskell

|                Fields               |                                     Solidity                                     |                                                          Vyper                                                         |                            Rust                            |                                                Clarity                                                |                                            Move                                            |          Go          |                   Huff                   |
| :---------------------------------: | :------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------: | :------------------: | :--------------------------------------: |
|              Blockchain             |                                     Ethereum                                     |                                                        Ethereum                                                        |               Polkadot, NEAR Protocol, Solana              |                                   Stacks (Programming layer for BTC)                                  |                                                                                            |                      |                                          |
|                 Year                |                                       2014                                       |                                                          2017                                                          |                            2010                            |                                                  2020                                                 |                                                                                            |                      |                                          |
|               Compiled              |                                        Yes                                       |                                                           Yes                                                          |                             Yes                            |                                                   No                                                  |                                             Yes                                            |                      |                                          |
|         Turing Completeness         |                                  Turing complete                                 |                                                    Turing Incomplete                                                   |                       Turing complete                      |                                     Decidable (Turing Incomplete)                                     |                                      Turing Incomplete                                     |                      |                                          |
|           Supported Types           |          Signed and unsigned integers, Booleans, Addresses, Enums, Bytes         | Boolean. Values. Operators. Unsigned Integer (N bit) Values. Operators. Decimals. Values. Operators. Address. Values.B | integers, floating-point numbers, Booleans, and characters |                 Booleans, Buffer, Integers, List, Optional, Principal, Response, Tuple                | Booleans, 256-bit addresses, References, UNsigned 64-bit integers, Fixed Size byte arrays, |                      |                                          |
|            Gas Estimation           | Fundamentally an estimation, given undecidable nature of the function call graph |                                                                                                                        |                                                            | Precise gas estimation; complete static analysis of the call graph so get exact cost before execution |                                                                                            |                      |                                          |
|      Language Design Philosophy     |            Imperative programming style, like C++, JavaScript, Python            |                                                         Python                                                         |                            C/C++                           |                           Functional programming style, like LISP and Scala                           |                                            Rust                                            |                      |                                          |
|       Development Environment       |                              Remix, Truffle, Hardhat                             |                                       Command-Line Compiler Tools, Remix, Truffle                                      |         Cargo, VS Code, Atom, Sublime Text, Eclips         |                                     VS Code, Clrinet, ClarityTools                                    |                                                                                            |                      |                                          |
| Vulnerability to Reentrancy Attacks |                                        Yes                                       |                                                                                                                        |                                                            |                                                No signs                                               |                                          No signs                                          |                      |                                          |
|              Community              |                                     Extensive                                    |                                                    Newly developing                                                    |                          Extensive                         |                                                 Small                                                 |                                          Extensive                                         |       Extensive      |                                          |
|              Use Cases              |                             Ethereum Virtual Machine                             |                                                Ethereum Virtual Machine                                                |          Solana, Polkadot, Elrond, NEAR, and ZCash         |                                                                                                       |                                         Aptos, Sui                                         | Ethereum-based dApps | on-chain Ethereum program,  Weierstrudel |

{% embed url="https://pontem.network/posts/comparison-of-the-top-10-smart-contract-programming-languages-in-2021" %}

{% embed url="https://www.hiro.so/blog/web3-programming-languages-clarity-vs-solidity" %}

{% embed url="https://101blockchains.com/vyper-vs-solidity/" %}

## Types of languages for web3 developers?

There are 3 main types of relevant programming languages for web3 developers: smart contract programming languages, frontend programming languages, and blockchain engineering languages. In that regard, we can crudely term it as that the former 2 are for blockchain development and the last one is for blockchain engineering.

### 1. Smart Contract Programming Languages

Here are some distinctions between Web3 programming languages and other programming languages lie.

When a transaction is sent through a dApp, a smart contract could be executed in order to access accounts on the blockchain and process the transfer. With smart contract programming languages, developers can write contracts to access assets, transfer ownership, guarantee settlement, etc.

Languages for this area include Solidity, Vyper, Golang, Huff, Rust, Move, Cairo, and Haskell. Among these, Solidity is considered to be the go-to-language considering how EVM compatible blockchains are the most prevalent at the moment.

### 2. Frontend Programming Languages

These languages mostly include traditional ones that software developers may already be using to build apps. This part of the workload is considered to be lacking in many web3 protocols and services so it the development demand for this area is high. Web3 developers would have to seek to learn frontend programming languages with extensive UI libraries and APIs for connecting with backend services.

The selection of web3 frontend languages is largely the same as software development in other industries. Look for the same tried and true languages that support versatile UI libraries, including JavaScript, TypeScript, Dart, and C++.

### 3. Backend Programming Languages

This part is mostly dealing with the blockchain itself. This guidebook would like to refer to this part as blockchain engineering rather than development since the work load is more similar to web server work done by current/traditional backend developers. This part is mostly done by Golang at the moment and more technical understanding of how the blockchain works at a low level would be useful to pursue a career into this direction. Note that Golang can also be used as the programming language for writing smart contracts as illustrated later on in this section.
