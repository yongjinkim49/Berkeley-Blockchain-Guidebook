# CAP Therom

{% hint style="info" %}
**Good to know:** TODO
{% endhint %}

Distributed computing systems cannot guarantee the following three characteristics at the same time: strong consistency, high availability, and partitioning. Therefore, in the design of distributed systems, it is often necessary to weaken the guarantee of one of the characteristics [\[1\]](cap-therom.md#reference).

* **Strong consistency:** all nodes in the distributed system can see the same data content at any time.
* **High availability:** Any node in the distributed system that is not non-faulty can respond to the request.
* **Partitioned tolerance:** The network may be partitioned, meaning that communication between partitioned nodes is not guaranteed.

### Reference

\[1] Seth Gilbert and Nancy Lynch. Brewer’s conjecture and the feasibility of consistent, available, partition-tolerant web services. Acm Sigact News, 33(2):51–59, 2002.
