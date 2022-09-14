# Blockchain Structure

{% hint style="info" %}
**Good to know:** Blockchain technology can be used to manage data and is seen as a multi-party collaborative database system. However, in terms of operational efficiency and difficulty of data management, the performance of the existing blockchain system is not necessarily better than that of traditional databases and cloud databases.
{% endhint %}

First of all, there are three basic components in the blockchain structure:

* **Transaction:** refers to all operations on the ledger.
* **Block: I**t is used to record all the transactions and states within a specified time interval, and can be considered as a consensus result for the current state of the ledger.
* **Chain:** A set of blocks which are listed in chronological order, and can be considered as a historical log of all the time nodes of the whole ledger.

The simple structure of a blockchain is shown in the Figure below, where the later blocks are linked into a chain by recording the hash value of the previous blocks. The blockchain is designed to pack and add a new block every once in a while, and this block is generated through the consensus protocol that we will mention later.

![Example of the Basic Blockchain Structure](<../.gitbook/assets/image (45).png>)

In the article “Bitcoin: A Peer-to-Peer Electronic Cash System” \[1], the user first initiates a transaction request through the client, which is propagated to the network and awaits confirmation. The node in the network will pack multiple transaction requests and add hash values and other information to form a block structure. Then the node will try to find a nonce random string through computation so that its hash result meets a specific requirement, and this whole process is often referred to as “mining”. When a node finds a nonce that satisfies the requirement, it submits a block that is broadcast to the network, and when other nodes receive this block, they verify it and add it to the local ledger.

It is important to note that once a block is submitted to the local chain, it cannot be deleted, which means that the length of the chain only increases and does not decrease, which is why the blockchain can provide the feature of no tampering, but it also limits the scalability of the whole system. This consensus mechanism is called Proof of Work (PoW), which can prevent malicious nodes from affecting the system to a certain extent, but it also wastes a lot of energy. We will include this concept in the later introduction of various consensus mechanisms.

### Reference

\[1] Satoshi Nakamoto. Bitcoin: A peer-to-peer electronic cash system. Decentralized Business Review, page 21260, 2008.
