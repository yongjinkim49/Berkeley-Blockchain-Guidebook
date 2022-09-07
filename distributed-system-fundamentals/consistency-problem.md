# Consistency Problem



{% hint style="info" %}
**Good to know:** TODO
{% endhint %}

### Consistency in Distributed Systems

In the book “Distributed Systems Concepts and Design” [\[1\]](consistency-problem.md#undefined), a distributed system is defined as a system in which hardware or software components are distributed across different network nodes; they communicate and coordinate with each other only through message passing. With the increasing complexity of network systems, most system designs have shifted from monolithic to distributed architectures, and non-traditional distributed systems led by blockchain have gained even more popularity in the past few years. Technologies such as blockchain, which are based on distributed technologies, are highly dependent on data consistency and consensus mechanisms, and in this section we will introduce each of these concepts.

The consistency problem is the top priority of distributed systems and the first problem to be solved in the blockchain. In the blockchain world, with an increasingly large number of nodes, the complexity of the system is increasing with the volume of the nodes, but in order to ensure the consistency of each node’s pace, we have to meet the requirements of the whole system in terms of scalability and fault-tolerance [\[2\]](consistency-problem.md#undefined).

### Definition of Consistency

For multiple nodes in a distributed system, given a set of instructions, we need to make the entire system reach a certain degree of agreement on the outcome of the instruction processing by fulfilling the consensus protocol [\[3\]](consistency-problem.md#undefined).

It may seem that all that is needed to get consistent results from distributed nodes is to ensure the serialized execution of instructions, but in reality it is difficult, for example:

* Network communication may be blocked and there may be time delays, which can cause disorder, delay or even loss of messages.
* The computing power and processing latency of each node and the results are not guaranteed, thus there may be a failed node at any time
* As the number of nodes increases, the complexity of communication between nodes may increase exponentially, making the system suffer from the trade-off between throughput and scalability.

### Consistency Requirements

In Leslie Lamport’s 1978 paper “Time, Clocks and the Ordering of Events in a Distributed System” [\[4\]](consistency-problem.md#undefined), it is pointed out that for an asynchronous system to determine a consistent result, it is required that systems with different clocks to execute commands in the same order. However, since each node in an asynchronous system has its own clock and there are time delays in communication, this event order has to be reasonably ordered in order to achieve a correct common outcome.

According to [\[5\]](consistency-problem.md#undefined), a distributed system must achieve the following 3 requirements.

* Termination: The system must be able to get the result in a limited time frame.
* Agreement: Each node must agree on the final outcome of the instruction.
* Validity: The decision must be generated in a compliant manner, even though there may be processing and communication delays among the nodes in the distributed system, if all nodes have the same initial value, then they must get the same result after executing the instruction.

In fact, there is a trade-off between the overall performance and consistency and scalability of an asynchronous system. So depending on the performance requirements of the system, one classifies the consistency requirements into different categories [\[6, 7\]](consistency-problem.md#undefined).

Sequential Consistency and Linearizability Consistency [\[8\] ](consistency-problem.md#undefined)are the more common Strong Consistency systems. The former is mentioned in Leslie Lamport’s [\[9\]](consistency-problem.md#undefined) in 1979, where the problem of consistency between local order and global order is addressed. That is, if there is a sequential order of execution between two processes in the vision of a process, then this order needs to be guaranteed in the global order as well. The latter concept of Linearizability Consistency [\[10\]](consistency-problem.md#reference) is always mentioned in operating system-related concepts, and it allows a certain degree of flexibility in the global ordering between processes, but it is very difficult to implement because it relies heavily on global clocks or mutual exclusion locks.

In reality, systems with strong consistency are often not as easy to implement. Most systems that do not require a high level of consistency but have a very high volume of transactions, such as in some designs of online shopping systems, tend to require only eventual consistency [\[11\]](consistency-problem.md#reference), which means that the user is always allowed to add items to the shopping cart, but will be eventually prompted with “inventory not available” when he is ready to pay. If we take the blockchain as an example, we can easily find that most of the time the ledger of each node may be inconsistent at different time periods, but every once in a while the consensus protocol will be used to achieve the ultimate consistency of the whole chain.

### Reference

\[1] George Coulouris, Jean Dollimore, and Tim Kindberg. Distributed systems: Concepts and design edition 3. System, 2(11):15.

\[2] Mayank Raikwar, Danilo Gligoroski, and Goran Velinov. Trends in development of databases and blockchain. In 2020 Seventh International Conference on Software Defined Systems (SDS), pages 177–182. IEEE, 2020.

\[3] Maarten Van Steen and A Tanenbaum. Distributed systems principles and paradigms. Network, 2:28, 2002.

\[4] Leslie Lamport. Time, clocks, and the ordering of events in a distributed system. In Concurrency: the Works of Leslie Lamport, pages 179–196. 2019.

\[5] Mukesh Singhal Ajay Kshemkalyani. Consensus and agreement. Cambridge University Press, Distributed Computing: Principles, Algorithms, and Systems.

\[6] Kenneth P Birman. Maintaining consistency in distributed systems. In Proceedings of the 5th workshop on ACM SIGOPS European workshop: Models and paradigms for distributed systems structuring, pages 1–6, 1992.

\[7] Michael J Fischer. The consensus problem in unreliable distributed systems (a brief survey). In International conference on fundamentals of computation theory, pages 127–140. Springer, 1983.&#x20;

\[8] Hagit Attiya and Jennifer L Welch. Sequential consistency versus linearizability. ACM Transactions on Computer Systems (TOCS), 12(2):91–122, 1994.

\[9] Leslie Lamport. How to make a multiprocessor computer that correctly executes multiprocess programs. In Concurrency: the Works of Leslie Lamport, pages 197–201. 2019.

\[10] Maurice P Herlihy and Jeannette M Wing. Linearizability: A correctness condition for concurrent objects. ACM Transactions on Programming Languages and Systems (TOPLAS), 12(3):463–492, 1990.&#x20;

\[11] Sebastian Burckhardt. Principles of eventual consistency. 2014.
