# Public Chain Consensus

{% hint style="info" %}
**Good to know:** TODO!
{% endhint %}

### Proof of Work (PoW)

PoW is the most common and original consensus algorithm used in blockchain applications. Its concept was first proposed by Cynthia Dwork and Moni Naor in 1993 [\[1\]](public-chain-consensus.md#reference), and was made more complete and coined in a 1999 article by Markus Jakobsson and Ari Juels [\[2\]](public-chain-consensus.md#reference). The main applications that use the PoW consensus algorithm are Bitcoin [\[3\]](public-chain-consensus.md#reference), which we know best, Ethereum [\[4\]](public-chain-consensus.md#reference), and Litecoin [\[5\]](public-chain-consensus.md#reference), which is popular in the cryptocurrency trading market, as well as Dogecoin [\[6\]](public-chain-consensus.md#reference), which is getting a lot of attention these days because of Elon Musk’s recommendation.&#x20;

In PoW, a blockchain participant (also known as a Miner) must solve a complex computational problem if it wants to add a piece of transaction. To keep the block generation time constant, the complexity of this computation changes accordingly, e.g., in Bitcoin, the generation time of new blocks is set to every 10 minutes. When multiple miners are working on a chain at the same time, then the one with the fastest growth and the longest chain length will be recognized as the winner. Under this premise, the chain is secure as long as more than half of the transactions submitted by miners are trusted. This has the advantage of avoiding the 51% attack, meaning that if the adversary wants to take management control of the blockchain by generating the faulty blocks and making the majority (51%) accept it, such an attack will turn out to be unprofitable and costly. Although PoW-based blockchain systems have countless applications in the industry, this approach requires too much computing power and thus wastes a lot of electricity resources, so many scholars are aiming to replace it.

### Proof of Stake (PoS)

PoS is a good remedy for the shortcomings of the PoW algorithm and has been applied in the latest generation of Ethereum. Compared to POW, which relies mainly on the costly power of arithmetic to prevent witch attacks, PoS relies on the “monetary policy” in the blockchain. PoS allows each Miner to mine or verify new blocks depending on the amount of cryptocurrency they have (Stake) and not on their computing power as in PoW. This means that in PoS, the more Stakes you have, the more chances you have to mine the next block, and the system also encourages verifiers to participate in the network through incentives and thus promotes consensus. This approach avoids wasting computing power and electricity, but the node with more stakes in this setup may have a long-term advantage.

### Delegated Proof-of-Stake (DPoS)

DPoS, also known as “Proof of Share Authority Mechanism”, was proposed by Dan Larime of Bitshares in 2014 [\[7\]](public-chain-consensus.md#reference). It is a highly scalable blockchain consensus protocol based on a further optimization of the PoS method. It requires all nodes to vote every once in a while and elect a specified number of super nodes as block producers, where the weight of the vote is based on the number of stakes held, and the more stakes you have the more important the vote is. These super nodes have exactly equal weight and they vote and create blocks in a round-robin order. When a block is voted on by more than 2/3 of the block producers, the block will be determined. Otherwise, the longest chain rule is followed. If during this process the verifier finds the presence of any malicious node, it is excluded in the next round of super node voting. Since only a small number of super nodes are voted in as block producers to participate in consensus, the throughput of DPoS is considerably higher than that of PoW. However, because of this, DPoS is also considered a solution that sacrifices decentralization for throughput. Typical applications are BitShares [\[8\]](public-chain-consensus.md#reference) and Ark [\[9\]](public-chain-consensus.md#reference).



### Reference

\[1] Cynthia Dwork and Moni Naor. Pricing via processing or combatting junk mail. In Annual international cryptology conference, pages 139–147. Springer, 1992.

\[2] Markus Jakobsson and Ari Juels. Proofs of work and bread pudding protocols. In Secure information networks, pages 258–272. Springer, 1999.

\[3] Satoshi Nakamoto. Bitcoin: A peer-to-peer electronic cash system. Decentralized Business Review, page 21260, 2008.

\[4] Vitalik Buterin et al. Ethereum white paper. GitHub repository, 1:22–23, 2013.

\[5] Adrian Gallagher. Litecoin core v0.18.1 release, Jun 2020. URL: https://blog. litecoin.org/litecoin-core-v0-18-1-release-233cabc26440.

\[6] Ian Young. Dogecoin: A brief overview & survey. Available at SSRN 3306060, 2018.

\[7] Daniel Larimer. Delegated proof-of-stake (dpos). Bitshare whitepaper, 81:85, 2014.

\[8] Fabian Schuh and Daniel Larimer. Bitshares 2.0: general overview. accessed June2017.\[Online]. Available: http://docs. bitshares. org/downloads/bitshares-general. pdf, 2017.

\[9] Ark.io. Ark - the simplest way to blockchain. URL: https://ark.io/.

