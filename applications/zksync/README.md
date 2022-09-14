# zkSync

## Introduction

[zkSync](https://zksync.io/) is a trustless, scalable and low-cost solution on Ethereum. It uses zero-knowledge proofs and zkRollup technology to protect the privacy of on-chain information. It can provide cheaper and faster transactions than the Ethereum main chain (layer 1). As a layer 2 solution, it removed most of the activity from layer 1 while still maintaining its security and consistency.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption><p><a href="https://docs.zksync.io/userdocs/roadmap/">Sync2.0 Releasing Roadmap</a></p></figcaption></figure>

## Key benefits of zkSync:

* Gas fee: The maximum transaction fee is only 1/100 of L1
* High speed: 2000+ transactions per second (tps) vs around 30 tps for L1
* Security: information is encrypted and secure as on the mainnet&#x20;
* Hassle-free transfer: Move cryptocurrencies easily between L1 and L2 without lag

## Zero-knowledge Proof

Detailed zero-knowledge proof background can be found at this[ link](https://ethereum.org/en/zero-knowledge-proofs/).

## zk-Rollup

zkRollup is a scaling solution to solve the blockchain trilemma (performance, security, scalability). We know that on-chain computation is very costly. If the computation can be moved off-chain while ensuring that the computation results are correct, then the transaction cost will be much lower.&#x20;

As one of the options for Layer 2 build development to improve the scalability of Ethereum. All funds for ZK Rollups are held by smart contracts on the main chain, while computing and storage are performed off-chain. The main idea is that instead of verifying each transaction individually, the transactions are **** batched to a single summary block and then validated all transactions at the same time. Each batch also includes a zkProof, which takes advantage of the low complexity of on-chain verification to prove the results of computations while securing the overall performance.

At the same time, the bundled information is transmitted in batches, which can amortize the cost of pushing data to Ethereum. This makes the cost per user significantly lower. More importantly, it will be faster, as well as lead to a better user experience.

## zkSync 1.0 VS zkSync 2.0

Launched in 2020, zkSync 1.0 is capable of around 300 TPS of transaction throughput. It can be used in simple payment scenarios, but lacks support for zkEVM and cannot handle more complex smart contracts.

zkSync 2.0 enables arbitrary smart contract functionality by supporting Solidity (via zkEVM) and Zinc (rollup's internal programming language); secondly, through zkPorter (a protocol that combines zkRollups and sharding), the throughput increases exponentially to around 20,000 + TPS.



## Tokens and Gas Fees

In zkSync, the cost of each transaction has two components.

**off-chain (storage + prover's cost) :**

Cost of state storage and SNARK (zero knowledge proof) generation. This part depends on the use of hardware resources and is therefore invariant. Our baseline estimate is about $0.001 per transfer.

**on-chain (gas fee cost):**

For each zkSync block, the verifier must pay Ethereum Gas to verify the SNARK, plus about 0.4k Gas per transaction to publish the status. The on-chain part is a variable that depends on the current gas price in the Ethereum network. However, this is much cheaper than the cost of a regular ETH/ERC20 transfer due to the batching strategy it implemented.

****

## **More information**

official website: [\[link\]](https://zksync.io/)

official tutorial: [\[link\]](https://docs.zksync.io/userdocs/tutorials/#add-funds-to-zksync-with-metamask)

zkSync Monthly Community Update: [\[link\]](https://www.reddit.com/r/zkSync/comments/wadnat/zksync\_community\_update\_july\_2022/)

roadmap: [\[link\]](https://docs.zksync.io/userdocs/roadmap/)

official bucket list: [\[link\]](https://blog.matter-labs.io/introducing-zk-sync-the-missing-link-to-mass-adoption-of-ethereum-14c9cea83f58)

ZkSync 2.0 Updates: [\[link\]](https://blog.matter-labs.io/zksync-2-0-hello-ethereum-ca48588de179)

zkSync Ambassador Program: [\[link\]](https://matterlabs.notion.site/zkSync-Ambassador-Program-387f26f8ed2940f0903f3f744fb38dfa)





