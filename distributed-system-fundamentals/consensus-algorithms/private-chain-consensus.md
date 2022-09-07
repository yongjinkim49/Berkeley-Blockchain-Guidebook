# Private Chain Consensus

### Paxos

The algorithm of Paxos was first proposed by Leslie Lamport in 1990 in [\[1\]](private-chain-consensus.md#undefined) and further refined in [\[2\]](private-chain-consensus.md#undefined), in which his design also takes into account fault tolerance, but only the impact of non-byzantine nodes, that is, there is no intentional evil nodes in the default system, so it is often used in distributed systems like zookeeper or private blockchain application scenarios. This algorithm uses a two-staged submission method (prepare stage 10 and commit stage), where a proposer is first selected from multiple proposal candidates, and then this proposal message is sent to other nodes, and the proposal is passed when the majority of nodes agree to it. The concept of majority of nodes is defined as “quorum” by Leslie Lamport in the paper. The fault tolerance of the Paxos algorithm is 1/2, which means that the system can reach a correct consensus when more than half of the nodes are working correctly.

### Raft

Raft’s algorithm evolved from Paxos, which was proposed by Diego Ongaro and John Ousterhout in 2014 in the paper “In Search of an Understandable Consensus Algorithm” [\[3\]](private-chain-consensus.md#undefined). Raft is more structured and easier to understand than Paxos, and provides better security. It ensures that any node in the cluster is consistent in some kind of state transition.

### Reference

\[1] Leslie Lamport. The part-time parliament. In Concurrency: the Works of Leslie Lamport, pages 277–317. 2019.

\[2] Leslie Lamport et al. Paxos made simple. ACM Sigact News, 32(4):18–25, 2001

\[3] Diego Ongaro and John Ousterhout. In search of an understandable consensus algorithm. In 2014 {USENIX} Annual Technical Conference ({USENIX}{ATC} 14), pages 305–319, 2014.
