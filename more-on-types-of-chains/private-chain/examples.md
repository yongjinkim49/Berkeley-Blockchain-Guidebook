# Examples


**Enterprise Ethereum (private):** Actually, Enterprise Ethereum is actually one of the recent additions. Ethereum is actually a public blockchain that got traction based on the features it introduced. But it was difficult for enterprise companies to even use up those features as it’s fully a public network. So EEA(Enterprise Ethereum Alliance) started to roll out an Ethereum private blockchain version just for the sake of commercial use. Thereby, this Ethereum private blockchain offers a new type of private network that uses public network benefits as well. More so, the Ethereum private blockchain also updates based on the public network as well. So, it can continue to grow into a vaster network.

**Hyperledger Fabric:** This is one of the popular private blockchain platforms on the list so far. In reality, Hyperledger Fabric is full of features that anyone can use in any kind of industry. Also, it comes with permissioned access, so any member has to authorize their identities before they can get in it. More so, it comes with a modular structure, which means you can plug and play any type of item in this. Furthermore, it allows you to customize to a great length. The transaction speed is fast and, in reality, excels at any other platform in the marketplace.

**Corda:** Corda has two types of versions one is open-source, and another one is for commercial usage. But Corda blockchain is more suited for financial industries such as banking sectors, insurances, real estate, and so on. Also, Corda happens to offer the best possible firewall against any online attacks. So, it’s a great option to use as a security system. Though it is still evolving, there are some talks regarding Corda being adapted into Hyperledger.

**Ripple:** Ripple is another private blockchain platform, that is solely for the financial sector. In reality, it comes with a native token of its own, and by using this you can complete transactions within seconds. Anyhow, previously many people thought that Ripple is only suited for finance industries. But slowly even governments are starting to use this platform for their own benefits. The transaction costs for this platform are relatively low, and it offers a secured consensus protocol.

**Quorum:** JP. Morgan is the one behind the success of Quorum. In reality, Quorum is actually a private version of Ethereum. But the developers tweaked the Ethereum platform to make certain moderations and make it enterprise-friendly. Enterprise Ethereum and Quorum are not the same things. So, make sure not to confuse them. They both use different methods and different protocols to reach consensus. Also, their privacy policies are different.




# More in-depth Analysis of Popular Frameworks:


We can focus on 3 key areas of functionality for these frameworks:
    1. *Data coordination:* How information and trust within a system is better distributed and allocated among stakeholders
    2. *Cryptoeconomic internal incentive layers:* How is a system architected so that different stakeholders and users are motivated based on economic incentives to ensure functionality of a system eg. Game Theory and mechanism design.
    3. *Integration into the digital commoditization of assets:* How the systems can integrate into a digital goods economy. In some nominal characterizations this is known as the token economy

An important note to recognize is that R3 Corda and Hyperledger Fabric do not have cryptoeconomic incentive layers instantiated within their software architectures. Due to the fact that the software architectures are foundationally designed based on distributed database focused paradigms, they were not originally designed for the incorporation of native cryptocurrency layers within the overall framework.

And because of this inherent difference in design of the software, they are not yet calibrated to be able to take part in multi-chain ecosystems where there is interoperability and coordination with a multitude of blockchains. Because the systems are structured with maximum throughput in mind, architectural layouts for an interoperable network topology with blockchains including the public blockchain mainnets were overlooked based on the initial construction of these systems.

As a quick summary, Corda acquires most of its use cases from the financial service industry. Hyperledger, on the other hand, offers an extendable, modular architecture in multiple industries.

## Hyperledger

In **Hyperledger**, the governing peers allow and provide permission to other nodes for any sort of transaction. This type of access control can be done on node, channel or even consortium levels. Rather than the sequential execution of transactions, multiple transactions can be executed simultaneously that enhances the performance of the system. For transactions to be executed and affirmed, Hyperledger follows the KAFKA and the RAFT algorithms to arrive at a consensus. Hyperledger uses the Chaincode as its business logic. Chaincode can be written in any standard programming language like Node.js, Go, and Java. It also facilitates the creation of native currencies as well as digital tokens using the FabToken management system.

## Corda

**Corda** has file based configurations to access nodes and their permissions. Contrary to other blockchains, in Corda, data is shared only on a need-to-know basis instead of global broadcasts. Corda was designed to specially serve banks and financial institutions and overcome challenges faced by this particular field. Hence, Corda coined the “Notaries” concept wherein the notaries validate the transactions and add blocks to the chain. Since Corda was developed for banks and financial institutes which emphasizes the need of a legal agreement between participants. Thus, Corda implements smart contracts coupled with Ricardian contracts to obtain validity and security. For Corda, the smart contract can be written using Java or Kotlin programming languages. Note that Corda also offers an SDK that allows the development of native tokens, issuance and trading of the tokens.

## Quorum

Whereas in **Quorum**, node permissioning is specified in smart contracts. Technically speaking, a json file containing a permission flag is maintained for it. Quorum uses a protocol called the QuorumChain to reach consensus. A simple voting process that confirms transactions using majority coupled with BFT and RAFT algorithms are used by this blockchain. It is also noteable that Quorum supports both public and private contracts which are written in Solidity programming language. In case of Quorum, the JPM coin is its digital currency.

Hyperledger, Corda and Quorum all offer privacy, robust mechanism, scalability and enhance the blockchain performance. While Corda and Quorum have simple architecture, Hyperledger is more modular. Hence, it is upto organizations to decide which blockchain is more suitable and can be altered to their business needs.

# Summarized Comparison of Major Enterprise Blockchains:

| Protocols/Parameters | Ethereum | XDC | Cardano | Polkadot | Solana | Stellar | Cosmos | Ripple | Avalanche | NEAR |
|---|---|---|---|---|---|---|---|---|---|---|
| TPS | 30 approx. | 2000+ approx. | 250 approx. | 166.6 approx. | 1954 approx. | 2500+ approx. | 1000 approx. | 1500 approx. | 10.29 approx. | up to 1,000,000 |
| Smart Contracts | Yes <br>(EVM) | Yes | Yes <br>(KEVM) | Parachains <br>(EVM, Wasm) | Yes <br>(Solana BPF) | Yes | Yes <br>(JS, CosmWasm, <br>EVM) | No | Yes <br>(C-Chain EVM based) | Yes |
| Scalability | No | Yes <br>(Sharding) | No | Parachains | Yes <br>(Horizontal PoH) | Yes | Unlimited zones <br>(Horizontal and <br>vertical) | No <br>(Only by channels) | Yes <br>(Unlimited subnets, <br>shards like) | Yes |
| On-Chain Governance | No | Yes | No | Yes | No <br>(Only for programs) | Yes | Yes | Yes | No | Yes |
| Level of Decentralization | High | High | High | High | Low | High | High | Medium | Medium | High |
| Interoperability | No | Yes | No | Yes | No | No | Yes | No | No | Yes |
| Human Readable Address | Yes | Yes | No | No | Yes | Yes | Yes | No | No | Yes |
| Gas Fee | $3 ~ $15 | Near 0 | Near 0 | Near 0 | Near 0 | Near 0 | Near 0 | Near 0 | Near 0 | Near 0 |
| Digital Identity Management | Yes | Yes | No | No | No | Yes | Yes | No | No | Yes |
| Deposit Time | 5 min | Near instant | Near instant | 2 min | Near instant | Near instant | Near instant | Near instant | 1 min | Near instant |
| Decentralized Exchange | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes <br>(In Codebase) | Yes | Yes |
| DeFi | Yes | Yes | Yes | Yes | Yes | Yes | Yes | No | Yes | Yes |
| Data Privacy | No | Yes | No | No | No | Yes | Yes | No | No | No |
| dApp | Yes | Yes | Yes | Yes | Yes | Yes | Yes | No | Yes | Yes |
| Currency | ETH | XDC | ADA | DOT | SOL | XLM | ATOM | XRP | AVAX | NEAR |
| Consensus Mechanism | Proof-of-Work | Delegated <br>Proof-of-Stake | Proof-of-Stake | Proof-of-Stake | Proof-of-Stake <br>based on BFT | Proof-of-Stake <br>based on <br>federated voting | Proof-of-Stake <br>based on BFT | Ripple Protocol <br>Consensus Algorithm <br>(RPCA) | Delegated <br>Proof-of-Stake <br>based on <br>Directed Acyclic Graph | Doomslug, <br>Threshold <br>Proof-of-Stake |
| Chain Generation | 2nd Gen | 3rd Gen | 3rd Gen | 3rd Gen | 2nd Gen | 3rd Gen | 3rd Gen | 1st Gen | 2nd Gen | 3rd Gen |
| Block Time | 14 secs | 2 secs | 20 secs | 6 secs | 0.8 secs | 3 ~ 5 secs | 7 secs | 4 secs | 3 secs | 1.3 secs |

