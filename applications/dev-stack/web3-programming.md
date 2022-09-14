# Web3 Programming

Though the resources you can refer to for blockchain development is quite abundant, most seem to provide only a part of the whole picture. Here, we tryp to provide a high-level overview of the dev stack required for web3 development. After all, just as it is the case for web2 (or non-web3) development, there are several types programming languages that you can refer to depending on which part of development/engineering you are pursuing.

Here are some programming languages we introduce to you for building in web3.

- Solidity
- Vyper
- Go
- Huff
- Rust
- Move
- Cairo
- Haskell

# Types of languages for web3 developers?
There are 3 main types of relevant programming languages for web3 developers: smart contract programming languages, frontend programming languages, and blockchain engineering languages. In that regard, we can crudely term it as that the former 2 are for blockchain development and the last one is for blockchain engineering.

## 1. Smart Contract Programming Languages
Here are some distinctions between Web3 programming languages and other programming languages lie.

When a transaction is sent through a dApp, a smart contract could be executed in order to access accounts on the blockchain and process the transfer. With smart contract programming languages, developers can write contracts to access assets, transfer ownership, guarantee settlement, etc.

Languages for this area include Solidity, Vyper, Golang, Huff, Rust, Move, Cairo, and Haskell. Among these, Solidity is considered to be the go-to-language considering how EVM compatible blockchains are the most prevalent at the moment.

## 2. Frontend Programming Languages
These languages mostly include traditional ones that software developers may already be using to build apps. This part of the workload is considered to be lacking in many web3 protocols and services so it the development demand for this area is high. Web3 developers would have to seek to learn frontend programming languages with extensive UI libraries and APIs for connecting with backend services.

The selection of web3 frontend languages is largely the same as software development in other industries. Look for the same tried and true languages that support versatile UI libraries, including JavaScript, TypeScript, Dart, and C++.

## 3. Backend Programming Languages
This part is mostly dealing with the blockchain itself. This guidebook would like to refer to this part as blockchain engineering rather than development since the work load is more similar to web server work done by current/traditional backend developers. This part is mostly done by Golang at the moment and more technical understanding of how the blockchain works at a low level would be useful to pursue a career into this direction. Note that Golang can also be used as the programming language for writing smart contracts as illustrated later on in this section.


<!--
# Web3 Programming Languages for Writing Smart Contracts

Each blockchain uses a specific type of web3 programming language to write smart contracts, and these are the most popular 8 languages: Solidity, Vyper, Huff, Rust, Go, Move, Cairo, Haskell. This list is not in a specific order.


1. Solidity
Developed by an Ethereum team, Solidity is the most commonly used smart contract programming language in web3. The language is Turing complete, fairly high-level, and object-oriented. These features come as a side-effect of the language being largely influenced by C++, Python, and JavaScript. 

Solidity Use Cases
Using Solidity, developers can write smart contracts on any Ethereum Virtual Machine (EVM) compatible blockchain such as Ethereum, Polygon, Arbitrum, Optimism, and many others. Solidity developers thus have access to the largest Web3 ecosystem with extensive developer support resources.

Building on EVM-compatible blockchains, developers can use Solidity to create Ethereum-native dApps, deploy smart contracts for a myriad of uses such as voting, transaction management, and multi-signature wallets.

For new Web3 developers, Solidity is a great place to start because of their tried-and-true coding practices, terrific community support, and smart contract versatility.

Start for free and begin building on Ethereum with Alchemy for fast and secure access to Ethereum APIs.

To learn more about Solidity, visit: https://docs.soliditylang.org/en/v0.8.15/index.html

2. Vyper
Another language for building on EVM compatible blockchains, Vyper is a Pythonic version of Solidity using Python’s syntactic simplicity–language focused on building secure smart contracts. Vyper was designed to make its code as simple and readable as possible.

By removing unnecessary complexity in smart contract code, Vyper allows developers to avoid confusing, bug-laden code and quickly detect security risks in their smart contracts.

Vyper Use Cases
As another language for programming on all EVM compatible blockchains, Vyper is a great choice to write smart contracts in the Ethereum ecosystem. The Vyper developers note, however, that Vyper is not intended as a holistic alternative to Solidity. For the sake of security, Vyper forbids doing certain things with your code that can be achieved with Solidity.

If you plan on building on EVM-compatible blockchains and need simplicity and security, Vyper is a potential web3 programming language for your smart contracts. 

To learn more about Vyper, visit: https://vyper.readthedocs.io/en/stable/

3. Go (Golang)
Golang (Go) is a programming language designed by Google, and it is known for its built-in concurrency features. Using Go, developers can write fast, concurrent programs with ease. In the blockchain industry, Golang is used in the Geth node client, one of the original Ethereum node client implementations alongside C++ and Python. With the Go implementation, developers can program scalable dApps in Golang.

Go Use Cases
Go is a quick language for developers to learn and has a tremendous support community. In contrast to building dApps in an interpreted language like Python, Go runs much faster programs. Developers looking to build Ethereum-based dApps with tremendously scalable backend processing should consider Go for its robust concurrency abilities.

To learn more about Go, visit: https://go.dev/doc/

4. Huff Language
An assembly-level language, Huff enables developers to manually manipulate the EVM programming stack and create highly optimized EVM-based smart contracts. Rather than hiding the structure of the EVM under easier-to-use layers of abstraction, Huff intentionally exposes the EVMs inner-workings to the developer.

When the Aztec Protocol needed to power a new on-chain Ethereum program, Weierstrudel, they realized Solidity and Vyper were unable to provide the computational power their dApp needed. To solve this problem, they created the Huff programming language.

To learn more about Huff, visit: https://github.com/huff-language/huff-rs

Huff Use Cases
For developers who find their programs limited by the speed Solidity or Vyper, Huff is an EVM-compatible language for optimizing smart contracts for performance. Additionally, even for developers who do not necessarily need the speed, learning Huff is a great way to build a much deeper understanding of how the EVM works.

5. Rust
Rust is a programming language used by Solana, NEAR, and other blockchains because it enables developers to write low-level code, implement systems-level controls, manage memory, and leverage parallelism.

Simultaneously, Rust is designed to remain ergonomic when developing at a high-level, allowing a natural coding experience in nearly all settings.

Because of Rust's ability to influence low-level code, it is extremely performant, and has inspired the development of Move, an emerging web3 programming language used by new layer 1 blockchains like Aptos and Sui.

Rust was created in 2010, originally designed for general programming, with a goal to empower developers through its comfortability in a wide range of applications.

The unique Rust compiler guarantees developers only create safe, secure code. Reviewing your code after refactors and feature adds, the compiler keeps your program stable so you can keep coding. Rust is cited as the most-loved programming language in Stack Overflow’s Developer Survey six years in a row!

Rust Use Cases
Blockchains including Solana, Polkadot, Elrond, NEAR, and ZCash all support smart contract development with Rust. Due to Rust’s safety and low-level versatility, developers can write extremely fast smart contracts without making any compromises on security. 

Solana, a chain whose concurrent smart contract execution enables extremely high transaction throughput and quick block creation. Using Rust to create smart contracts, Web3 developers can take advantage of Solana’s speed without risking their users’ assets. Try building on Solana for free now with Alchemy’s RPC nodes.

To learn more about Rust, visit: https://doc.rust-lang.org/book/

6. Move
Originally developed by the Diem Association for developing on Diem blockchains, Move is a web3 programming language based on Rust that is designed to write safe smart contracts. When designing the language, the Move developers noticed a confusing hole in existing smart contract languages. Smart contracts are used to control assets on the blockchain, yet the programming languages lacked any explicit type-representations for assets and access control.

Accordingly, Move was designed with these necessary smart contract features designed directly into the language. Developers can more confidently deploy safe smart contracts, using all of Move’s built-in capabilities.

At the beginning of 2022, all of the Diem Association’s assets were acquired by an external party, so Move is no longer used for Diem blockchains. However, members of the original Diem team, and Move development team have continued to create their own projects such as Aptos and Sui.

Move Use Cases
Move is currently being used in the creation of two different chains, Aptos and Sui. Aptos is a new layer 1 blockchain looking to better solve security and scalability issues encountered by other L1s. Sui is a permissionless Layer 1 designed specifically for speed, security, and the support of dynamic on-chain assets–everything from financial products to gaming. 

While Move underlies both Aptos and Sui, each blockchain implementation also has its own overlay of unique blockchain features such as accounts, transactions, etc. Thus, developing with Move will require both learning the foundations of the language as well as the unique tooling used in Aptos and Sui. Developers looking to get into either of these chains poised for tremendous growth should consider learning Move. 

To learn more about Move, visit: https://move-language.github.io/move/

7. Cairo
Cairo is a language developed by StarkWare, a layer 2 scaling solution for Ethereum that uses zero-knowledge rollups. StarkWare uses Cairo to power StarkEx, the toolbox of scalability solutions powering Ethereum dApps including, dYdX, Sorare, and Immutable. 

Underlying Cairo is what StarkWare considers a Generic Proving Service (GPS). With their GPS, a single ZK proof can be used to prove the validity of multiple computations. For example, minted Immutable NFTs, a batch of dYdX trades, and a Rhino.fi trade can all be proven by the same STARK.

Cairo Use Cases
Cairo was designed for writing any provable programs. Developers can use it to easily prove computational correctness of any computation to any other party. Building with Cairo is a fantastic opportunity to bolster your Web3 project with trustless, zero-knowledge powered scalability.

Beyond its use in StarkEx, Cairo is the native language for writing smart contracts on StarkNet. StarkNet is a permissionless and decentralized Ethereum-based ZK-rollup. For developers looking to be a part of Ethereum’s massive dApp ecosystem, start building with Cairo and sign up for a free StarkNet account on Alchemy.

To learn more about Cairo, visit: https://www.cairo-lang.org/

8. Haskell
Leading the industry in functional programming, Haskell is a programming language used by Cardano’s Plutus for dApp development. Functional programming languages like Haskell differ from other imperative languages (such as C, JavaScript, Rust, and Solidity). 

In an imperative programming language, developers write instructions to specify how to accomplish a certain task. In Haskell, functions are used to declare what the desired outcome is, and the language handles the specifics of the underlying implementation. 

Haskell Use Cases
The Plutus platform is the native smart contract platform on the Cardano blockchain. All of Plutus’s on and off-chain technical architecture is written in Haskell. Learning Haskell will allow developers to start building in the Cardano ecosystem. Because the underlying implementation of programs is entirely handled by the language, developers building with Haskell can confidently rely on the safe high-level functionality of their smart contracts. 

Frontend Programming Languages Helpful for Web3 Developer
Connecting the best web3 dApps to its users is a simple and intuitive user interface (UI). Frontend development for blockchain applications relies on essentially the same languages as web2. Look for languages with flexible features and support for dynamic UI frameworks.

There are many languages available for frontend development. Below we will just go over some of the most popular and essential programming languages for getting started with building a frontend. Feel free to explore other frontend programming languages, but with the tools below, you are on your way to becoming a strong web3 developer.

1. HyperText Markup Language (HTML)
HTML (Hypertext Markup Language) is the standard programming language for displaying formatted documents as part of applications. Using their standardized set of tags, developers can easily build different types of application elements. There is support for inherited attributes, element-specific parameters, URLs, and more. Think of HTML as the content manager of your program.

2. Cascading Style Sheets (CSS)
Behind an HTML-based UI is the stylesheet programming language, CSS (Cascading Style Sheets). CSS allows developers to create consolidated style rules for each of their page’s elements. With your UI elements and parameters arranged by HTML, adding CSS can put the final touch of style formatting on each element.

CSS supports grouping of elements, font and color changes, item justification, and more. Without CSS to style a dApp, developers are left without control over the specific look of their programs. Use CSS to build a recognizable brand and attractive web3 design. 

3. JavaScript
JavaScript is one of the most popularly used languages for frontend development, and is used to handle the behavior of your dApp alongside HTML and CSS which handle the content and design.

JavaScript is a programming language designed to deploy lightweight programs, called “scripts,” over your web page. Use JavaScript to make your page’s elements interactive, manage the data requested from your dApp, and ultimately complete an interactive user experience.

Aside from its robust and flexible utility, JavaScript has a multitude of libraries and frameworks that are terrific for building UIs. Integrated with JavaScript, some of the most popular libraries include React, Angular, and Grommet. Explore a UI library to make your JavaScript app development even smoother!

4. TypeScript
TypeScript is a programming language built on top of JavaScript. Bringing the same high-level functionality and syntax as JavaScript, TypeScript differs with addition of syntax extensions that promote safer, strongly-typed code.

TypeScript catches many JavaScript errors before compiling. With the need to write concise code to manage a dApp's data, developers can better guarantee security of each of their frontend functions to keep their user-data safe. TypeScript supports all of the same libraries and frameworks as JavaScript, so consider using it as your web3 programming language to code safer dApp frontends!

Which Web3 programming language should I learn?
Choosing the best web3 programming language to learn depends on the blockchain ecosystem where you want your application to launch, and your goals as a web3 startup. If you're interested in Ethereum and EVM-compatible blockchains, start with Solidity and Vyper. If you're interested in next generation blockchains like Solana, NEAR, and Move, start learning Rust.

If you're still undecided, ask questions about what the architecture of the chain itself will do for you:

Do you need interoperability? Scalability? Speed?
Are there languages that are similar to anything you have experience with?
Is the documentation thorough and approachable?
Can developers write scalable smart contracts that are resilient to malicious actors?
Is the developer community helpful and growing on a yearly basis?
Where is the web3 space moving?

-->
