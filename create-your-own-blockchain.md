# Create your own blockchain

First point to consider is why you would need your own blockchain. If you are at this point of consideration, then you are possibly feeling that the current public blockchains, either Layer1 or Layer2, are not fully supporting your business agenda. Then it would be the case that you are wishing for a more application specific blockchain for your business. From here, you can take 3 ways: 

- fork an existing public blockchain repository and make adjustments
- use some blockchain building framework SDK
- or completely from scratch

The first choice is quite possible if you have a good team of programmers with blockchain domain knowledge but if this is the case, depending on the ultimate reason why you turned to creating your own blockchain (TPS, privacy, etc), the marginal benefit from creating your own blockchain this way as opposed to using an existing blockchain may not be that big.

The second choice may be the most viable option for most developers. Frameworks such as Cosmos provides a developer-friendly tutorial of how to use its SDK and build a blockchain from it. Hyperledger, a private blockchain building framework, also provides documentation on how to use it. The question then boils down to what type of framework you should use. The recommendation would be to go for the one that best suits your business agenda and that has a developer-friendly tutorial or docs. No matter how good the framework maybe, if you, or any other developers who would be joining your team, cannot quickly learn how to use them, the building process and iteration will be very slow.

For the last choice, it recommendable to have not just a group of programmers but also those who really understand the mechanics of blockchains overall and a cryptography expert. In other words, it is a task that you alone would have a very hard time doing, much harder technically speaking and to justify compared to the first option. 

Note that for either case, you are engineering the Layer1, not d-Apps that live on top of it. Thereby, how experienced you are in Solidity (even for EVM-compatible ones) is mostly irrelevant in this realm. Many blockchains out there for Layer1 make very heavy use of Golang for the server architecture. For this part of the guidebook we refer to Cosmos SDK as one way to build your own blockchain. The tutorial link is provided below.

[https://tutorials.cosmos.network/](https://tutorials.cosmos.network/)
