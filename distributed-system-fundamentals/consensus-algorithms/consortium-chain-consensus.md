# Consortium Chain Consensus

### Practical Byzantine Fault Tolerance (PBFT)

Castro and Liskov first proposed PBFT in 1999 in “Practical Byzantine Fault Tolerance and Proactive Recovery” [\[1\]](consortium-chain-consensus.md#undefined). It is an excellent solution to the problem of the Byzantine faulty nodes in distributed systems, which leads to unsynchronized and inconsistent information. It is essentially based on the optimization of the Paxos algorithm, which for the first time reduces the complexity of the Byzantine fault-tolerant algorithm from the exponential level to the polynomial level. Additionally, when the total number of nodes in the system is _n_, and the number of faulty nodes is _f_, PBFT can guarantee the normal information communication of the whole system under the condition of _**n ≥ 3f + 1**_**.**

### The Two Generals Problem

Before we launch into an exposition of the discussion of the Byzantine problem, we first start with a more classical problem, the two generals problem, which was introduced back in 1975 in [\[2\]](consortium-chain-consensus.md#undefined). The two generals problem refers to the problem of two generals in an army whose units are separated by two locations, and they have to communicate with each other through their communications to reach a unanimous decision to either attack or withdraw. However, there is no universal solution to this problem according to the FLP impossibility principle, since the communicators may receive harassment from the enemy troops in the middle of the process leading to the loss of secret messages.

### The Byzantine Problem

As an extension of the dual generals problem, the Byzantine problem is more in line with the model characteristics of asynchronous distributed systems. The Byzantine problem was first formally introduced by Leslie Lamport in 1982 in the paper “The Byzantine Generals Problem” [\[3\]](consortium-chain-consensus.md#undefined), while Byzantine is the capital of the ancient Eastern Roman Empire. The generals refer to the nodes in the model of the distributed system. Since there may be traitors among the generals who may refuse to convey messages or even try to convey wrong orders to interfere with the consensus, the Byzantine problem is to solve the problem that the participants of consensus protocols in asynchronous distributed systems may appear to be faulty.

### Preliminary Ideas

In the paper “The Byzantine Generals Problem” [\[3\]](consortium-chain-consensus.md#reference), it is mentioned that if we assume that there are n nodes and _f_ faulty nodes under the asynchronous system in the Byzantine problem, then the whole system can reach the correct consensus result only when _n > 3f+1_.&#x20;

Let’s take a more practical example. Suppose there are 3 nodes and 1 faulty node in the system. When the proposer sends a consensus proposal, the faulty node may give the opposite result to interfere with the consensus, then the last remaining node may receive one positive and one negative message, in this case, it is difficult to discern who is right and who is wrong, so we cannot get the consensus result. Let’s generalize this example; similarly, when a node sends consensus proposal A and it is not an evil node, for a non-faulty node he will see _n − f_ consensus messages A, and at most _f_ consensus messages that are not A, denoted as ~~A~~. Then obviously only when _n − f > f_, that is, when _n > 2f_ we can get the correct consensus result.

What if the consensus proposal is made by the evil-doer? From the standpoint of the evildoer, in order to interfere with the consensus result, it will send contradictory results to _n − f_ participants, then there will be (n − f)/2 participants receiving the message A and another (n − f)/2 participants receiving the message ~~A~~. These honest participants will think that the system currently has half of the A consensus message and half of the ~~A~~ consensus message regardless of the result they receive. Moreover, in addition to the proposers themselves being evildoers, there are _f − 1_ evildoer remaining in the system, whose behavior is uncertain; they may send consensus message A, or they may send consensus message ~~A~~, or they may even refuse to participate in the consensus. Then, if honest participants want to get a consistent consensus result, they have to communicate with each other to confirm and count the consensus messages they receive, and select the majority result as the consensus result.

In a subsequent paper by Leslie Lamport entitled “Reaching agreement in the presence of faults” [\[4\]](consortium-chain-consensus.md#reference), it is shown that we can negotiate a consensus through at most _f + 1_ rounds of interaction when the perpetrators do not exceed 1/3 of the total number of nodes in the system. Otherwise, the consensus result is not guaranteed.

Imagine that for a consensus A, there are _f_ evil nodes and _t_ honest nodes in a system with n total nodes, where _f_ evil nodes can give the opposite result or refuse to participate in the consensus. When all the evil nodes give the opposite result ~~A~~ and _f_ of the _t_ honest nodes refuse to give a consensus response, the remaining _t − f_ honest nodes must have _t − f > f_, and because _t = n − f_ so _n − f − f > f,_ so finally our Byzantine fault tolerance is _n > 3f_.

### Types of Byzantine Failures

There are several types of Byzantine Failures, and we can simply divide them into nodes that are actively evil and nodes that are passively evil [\[5\]](consortium-chain-consensus.md#reference).

Active byzantine nodes may be adversary nodes used to try to steal user information or deliberately send incorrect consensus votes, and they may use a large number of byzantine nodes to frequently trigger attempts to switch protocols and thus affect the overall operational efficiency of the system.

There can be many kinds of passive nodes, the most typical ones being those that fail to return a result in time due to natural disasters or lack of maintenance resulting in long or temporary downtime.

### PBFT Protocols

We can also use simple language to explain the design concept of PBFT: Suppose I, as a member of the consensus nodes, receive a message from the leader, I will first subjectively judge it right or wrong and reject those messages that I think are wrong. But even if I think the message is right, I will still ask and refer to other nodes’ judgment. Only when I count the existence of more than _2f + 1_ people who believe that the leader’s message is correct, will I approve it and execute it. When the majority of nodes believe that the leader is wrong, we need to re-elect a new leader. Basically, PBFT is divided into three main parts: Consistency Protocol, View Switching Protocol, Checkpoint Protocol.

**Consistency Protocol**

Consistency protocol is the core component of the entire PBFT algorithm, which ensures the consistency of information across all nodes in the blockchain nodes. It divides the communicating nodes on the chain into 3 categories, client nodes, primary nodes and replica nodes. where the client node is the initial sender of the request and it sends a request to the primary node < REQUEST, _o, t, c_ >, where o is the specific operation, and _t_ is the timestamp. Once the primary node receives the request from client code, it need 3 interactive stages before it replies the client code, they are pre-prepare stage, prepare stage and commit stage.

* In the **PRE-PREPARE** stage, when the primary node receives a request, it first analyzes the request and discards the incorrect requests, then it sorts the remaining correct requests and assigns the number _n_ in order, and then broadcasts << PRE-PERPARE, _v, n, d >, m_ > messages to the other replica nodes in the system. Where d represents the summary of the REQUEST message, _n_ is the number of the message m, and v represents the view number.
*   &#x20;**** In the **PREPARE** stage, node _i_, which receives the pre-prepare message, first determines whether it agrees to enter the prepare stage and verifies the accuracy of the message, and broadcasts < PREPARE, _v, n, d, i_ > messages to other nodes including the primary node.



![Practical Byzantine Fault Tolerance Communication Graph](<../../.gitbook/assets/image (48).png>)



* In the **COMMIT** stage, when node _i_ receives _2f+1_ validated messages, it goes from the PREPARE stage to the COMMIT stage and sends < COMMIT, _v, n, D(m), i_ > messages to other nodes including the PRIMARY node.
* In the **REPLY** stage, when node _i_ receives 2f+1 commit messages to meet the consistency requirement, it then sends a consensus message in the format of < REPLY, _c, I, v, t, r_ > to the client node. _r_ represents the result of client request execution by node _i_. Finally, this consistency interaction is completed when the client node receives at least _f + 1_ REPLY messages. After that, the PRIMARY node needs to write the consensus data into the blockchain. If this data block is not generated, then this primary will be classified as a Byzantine node and the system will select a new primary node according to the view-change mechanism.

#### View-Change Protocol

The concept of view ensures that each node in the blockchain works under the same configuration information. When one of the following conditions is met, the primary node will be considered as a Byzantine node and the system will select a new primary node according to the view switching protocol:

* No pre-prepare broadcast message is received from the primary node at time _t1_
* No new module is generated within the time limit _t2 > t1_

After triggering the protocol for switching views, we first generate a number for the new view, _v′ = v + 1,_ then select the new primary node based on _p = v′ mod n_, and broadcast the view change message to all replica nodes.

Then when each replica node receives _2f + 1_ view change messages including its own, they will send a view-change-ack confirmation message to the new master node of the new view, and then the new master node will enter the new-view phase.

Finally, the new master node selects the checkpoint as the starting state of the new-view request and then executes the consistency protocol according to the local data block.

#### Checkpoint Protocol

In the process of consensus generation, a large amount of stored data is generated. The periodic operation of the checkpoint protocol largely reduces the data storage size of nodes and avoids the waste of resources. We will not go into details here.



### Advantages of PBFT

* **A certain degree of waste of resources is avoided.** PBFT does not require as much computing power as other distributed consensus protocols, such as those based on Proof of Work. Therefore, PBFT is a relatively energy-saving approach.
* **PBFT provides transaction finality.** As the name suggests, PBFT-based distributed systems eliminate the need for multiple validations after a request is submitted, unlike traditional Bitcoin, which requires each node to validate all transactions when adding a block to the local area; once a request is made, we can be sure that the request will generate a response within a limited time threshold.

### Bottleneck of PBFT Performance

The whole process requires two multi-casts for all nodes, which severely consumes the total number of communications and slows down the throughput, causing a large degree of resource consumption. In PBFT, the communication cost of each step is as follows:

1. the communication cost of request phase is **1**,
2. the communication cost of pre-prepare phase is _**n − 1**_,
3. the communication cost of prepare phase is _ **(n − 1)(n − 1)**_,
4. the communication count of commit phase is _ **n(n − 1)**_,
5. the communication count of reply phase is _**n**_**.**

Therefore, the overall complexity is _**2n 2 − n + 1 => O(n^2)**_. For a network model with a small number of nodes, e.g., _n_ less than or equal to 10, the overall data communication volume will not be very large, but considering that the number of nodes in today’s real-world application scenarios is often up to 1000, the squared time complexity is certainly not enough.

### Variations of BFT-Based Consensus Models

[\[7\]](consortium-chain-consensus.md#reference) proposed Scalable Byzantine Fault Tolerance (**SBFT**) algorithm. It treats a node as a fixed, error-free block producer. SBFT has a theoretical performance advantage of twice the throughput and 1.5 times the latency optimization compared to traditional PBFT. It introduces the concept of collectors in its design and uses threshold signatures to reduce communication to linear, and also borrows the fast path approach from Zyzzyva to reduce a significant amount of communication cost. Although this scheme greatly improves the performance of the PBFT algorithm, there are some drawbacks in its design, i.e., it does not consider the case where the primary node is a Byzantine node, and the performance improvement of SBFT is to some extent at the cost of reduced Byzantine fault tolerance.

[\[8\]](consortium-chain-consensus.md#reference) presented **Zyzzyva**, which pioneered the mechanism of speculation to reduce the communication cost of BFT-type consensus protocols. In Zyzzyva, the original three-phase commit protocol is replaced by the speculation model. This means that all replicas optimistically adopt the order proposed by a primary node. In case of an error in any of the replicas, the client node finds the inconsistencies at the end and helps them synchronize their responses to the existing state. In terms of performance, it can reach a theoretical throughput of 10,000, which is much higher than the traditional PBFT protocol, but since it is not used in systems prone to Byzantine nodes, the application scenario is greatly limited.

[\[9\]](consortium-chain-consensus.md#reference) proposed the Stellar Consensus Protocol (**SCP**). Unlike other Byzantine protocol models, it presupposes a list of members and opens the access to the list conditionally in order to promote the benign growth of the network. It reduces the complexity of consensus messages by replacing the public key signature with a vector of message authentication codes. And it can dynamically adjust the number of checkpoints, and the response time and space usage efficiency of the system is improved, but a part of the system security is sacrificed while the operation efficiency is improved.

The **HotStuff** [\[10\]](consortium-chain-consensus.md#reference) algorithm demonstrates the impact of structural optimization on the transmission complexity of PBFT. It innovatively changes the original network topology to a star network topology, so that each communication will only depend on the central node. Instead of reaching consensus through multiple rounds of multicast, it sends messages to the central node, which finally matches and verifies the messages and broadcast the consensus result to all the other nodes. in addition to providing _O(n)_ linear communication complexity, the Hotstuff algorithm also pioneered the optimization of view switching protocol complexity, which is not covered in any other optimization designs for BFT.

**OBFT** [\[11\]](consortium-chain-consensus.md#reference) was proposed in 2012 and it is a client node based BFT protocol. The O in its name stands for obfuscated, because replicas are not aware of each other’s existence. In other words, compared to message communication between replicas in PBFT, message communication in OBFT exists between client node and replicas, which greatly reduces the original message multicast. This prevents non-semantic attacks to some extent, because the attacked replica does not know about other replicas, so it does not disclose information about other replicas. In the consensus process, the primary node in the algorithm uses the speculative mode to send a request to the _2f + 1_ selected active set, when the request is matched by all the receiving nodes, the request will be submitted by the client node; otherwise the recovery mode will be enabled and the _2f + 1_ nodes will be reselected and started again. OBFT achieves good performance, compared with PBFT’s limited scalability and rapid decline in throughput as the number of clients increases, OBFT can achieve hundreds of nodes in a wide area network to participate in consensus at the same time. However, OBFT also has the limitation that it defaults the nodes participating in consensus are non-malicious also known as non-Byzantine nodes, in other words, the system allows node crashes but they cannot cheat.

**FastBFT** [\[12\]](consortium-chain-consensus.md#reference), proposed in “Scalable Byzantine Consensus via Hardware-Assisted Secret Sharing” in 2019, leverages novel message aggregation and hardware-based trusted execution environment to reduce the consensus transaction complexity from _O(n^2)_ to _O(n)_. Unlike other methods also based on message aggregation, its approach is based on lightweight secret sharing, so it does not require public-key operations like multisignatures but requires additional hardware support such as Intel SGX, thus saving a lot of compuatation overhead. It optimized the fault-tolerance performance, compared to the original PBFT of _3f + 1_, fastBFT only needs _2f + 1_ replicas to tolerate f faulty nodes. FastBFT uses the basic binary tree topology to optimize the communication efficiency to a certain extent, which can improve the system operation efficiency when the children of the tree are not Byzantine nodes.

**hBFT** [\[13\]](consortium-chain-consensus.md#reference) is a hybrid PBFT protocol with optimal resilience, which was proposed by Sisi Duan, Sean Peisert and Karl Levitt in 2015. In the normal case, hBFT uses speculation and assume the default primary is correct, i.e., the replica directly adopts the order from the primary and sends a reply to the client. And when there is inconsistency in the replica, it will be up to the user node to detect the inconsistency and help replicas to recover to the proper consensus result. It shifts the critical work to the client and has much fewer cryptographic operations than the original algorithm. However, its algorithm is based on assumptions of fault-free and normal cases, so the applicability scenario is greatly limited.

### Reference

\[1] Miguel Castro and Barbara Liskov. Practical byzantine fault tolerance and proactive recovery. ACM Transactions on Computer Systems (TOCS), 20(4):398–461, 2002.

\[2] Eralp A Akkoyunlu, Kattamuri Ekanadham, and Richard V Huber. Some constraints and tradeoffs in the design of network communications. In Proceedings of the fifth ACM symposium on Operating systems principles, pages 67–74, 1975.

\[3] Leslie Lamport, Robert Shostak, and Marshall Pease. The byzantine generals problem. In Concurrency: the Works of Leslie Lamport, pages 203–226. 2019.

\[4] Marshall Pease, Robert Shostak, and Leslie Lamport. Reaching agreement in the presence of faults. Journal of the ACM (JACM), 27(2):228–234, 1980.

\[5] Felix C G¨artner. Byzantine failures and security: Arbitrary is not (always) random. INFORMATIK 2003-Mit Sicherheit Informatik, Schwerpunkt” Sicherheit-Schutz und Zuverl¨assigkeit”, 2003.

\[6] Marko Vukoli´c. The quest for scalable blockchain fabric: Proof-of-work vs. bft replication. pages 112–125, Cham, 2016. Springer International Publishing.

\[7] Guy Golan Gueta, Ittai Abraham, Shelly Grossman, Dahlia Malkhi, Benny Pinkas, Michael Reiter, Dragos-Adrian Seredinschi, Orr Tamir, and Alin Tomescu. Sbft: A scalable and decentralized trust infrastructure. In 2019 49th Annual IEEE/IFIP International Conference on Dependable Systems and Networks (DSN), pages 568–580, 2019. doi:10.1109/DSN.2019.00063.

\[8] Ramakrishna Kotla, Lorenzo Alvisi, Mike Dahlin, Allen Clement, and Edmund Wong. Zyzzyva: Speculative byzantine fault tolerance. 27(4), jan 2010. doi: 10.1145/1658357.1658358.

\[9] David. Maziereso. Stellar consensus protocol. Open Problems in Network Security, 2016. URL: https://www.stellar.org/papers/stellar-consensus-protocol.&#x20;

\[10] Maofan Yin, Dahlia Malkhi, Michael K. Reiter, Guy Golan Gueta, and Ittai Abraham. Hotstuff: Bft consensus in the lens of blockchain, 2019. arXiv:1803.05069.

\[11] Ali Shoker, Jean-Paul Bahsoun, and Maysam Yabandeh. Improving independence of failures in bft. pages 227–234, 2013. doi:10.1109/NCA.2013.22.

\[12] Jian Liu, Wenting Li, Ghassan O. Karame, and N. Asokan. Scalable byzantine consensus via hardware-assisted secret sharing. IEEE Transactions on Computers, 68(1):139– 151, 2019. doi:10.1109/TC.2018.2860009.

\[13] Sisi Duan, Sean Peisert, and Karl N. Levitt. hbft: Speculative byzantine fault tolerance with minimum cost. IEEE Transactions on Dependable and Secure Computing, 12(1):58–70, 2015. doi:10.1109/TDSC.2014.2312331.









