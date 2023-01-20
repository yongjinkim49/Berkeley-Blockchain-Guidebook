# Hash Algorithm and Merkel Tree

### Definition&#x20;

Hash (hash or hash) algorithms, also often referred to as fingerprint or digest algorithms, are a very basic and important class of algorithms. It can map a binary plaintext string of arbitrary length to a shorter (usually fixed length) binary string (Hash value), and it is difficult to map different plaintexts to the same Hash value.

Hash algorithm is a common one-way encryption algorithm, which encrypts a string of data into a binary string, but cannot be restored from the binary to the original data. The algorithm has the following characteristics: in the case of no collision, the same input gets the same binary string, different pairs of inputs get different binary strings, but the output binary length is the same

For example, calculate the SHA-256 Hash value of "this is berkeley blockchain".

```
echo "this is berkeley blockchain"|shasum -a 256
ade48ffcdb068f59093ce7cbc1c09a82f81d1493d0244f8c7941795acdc9865b  -
```

### Hash Functions in Blockchain

Two cryptographic hash functions are generally used in the Bitcoin system, one is SHA256 and the other is RIPEMD160. RIPEMD160 is mainly used to generate Bitcoin addresses; SHA256 is the main cryptographic hash function used to construct the blockchain.

In the HyperLedger-Fabric blockchain platform, the hash function is mainly used for detecting unauthorized modifications of data, signer identification and anti-repudiation.

Therefore, hashing algorithms are used in many places in a blockchain, such as computing hash values on blocks. In a real blockchain, a block contains a block header with metadata and a long sequence of transactions immediately following it, which constitute the body of the block. There's another concept involved here: the Merkle tree

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

A Merkle tree, also known as a hash tree, is a tree data structure consisting of a root node, a set of intermediate nodes, and a set of leaf nodes. The bottommost leaf node contains the stored data or its hash value, and the nodes above it are the hashes of the contents of its children.

A Merkle trees have the following characteristics:

* Generally, they are binary trees, but they could also be multinomial trees with all the characteristics of a tree structure, or so-called m-ary tree, where m is the number of branches for each node.
* The root node of the tree depends only on the data and has nothing to do with the order of updates in it. Changing the order of updates, or even recalculating the tree from scratch, does not change the root node.
* When two Merkle trees have the same root node, it means that the data represented must be the same, and we can think that checking with the root node instead of all nodes can greatly reduce the amount of data transfer as well as the complexity of the computation.
* A branch of a Merkle tree is also a Merkle tree and can be verified as independent. When there are too many transaction data in the blockchain, the storage space can be effectively saved by keeping only the root node of the Merck tree and deleting the nodes under it.

### Digital Digest

Digital Digest is also one of the important uses of the Hash algorithm. As the name implies, the digital digest is a Hash operation on the original content to obtain a unique digest value. Using the collision-resistant feature of the Hash function, the digital digest can detect whether the content has been tampered with. Some people may notice that some websites provide the corresponding digital digest values when they provide files for download. After downloading the original file, the user can calculate the digest value locally and compare it with the provided digest value to ensure that the file content has not been tampered with.
