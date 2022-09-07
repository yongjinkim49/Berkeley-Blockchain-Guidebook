# How it Works

The Bitcoin system is a clever system of decentralized trustless verification based on cryptography, in contrast to conventional banking and payment systems. In bitcoin, trust is achieved as an emergent attribute via the interactions of various system members, as opposed to a central trusted authority. We will provide a high-level overview of bitcoin by following one transaction as it moves through the system, gets "trusted" and approved by the distributed consensus method used by bitcoin, and is finally recorded on the blockchain, the distributed ledger of all transactions.

### Bitcoin Basic Transaction

There is no concept of an account in Bitcoin. Therefore, every time a transaction occurs, the user needs to write the transaction record into the Bitcoin network ledger, and the transaction can be considered complete after the network confirms it.&#x20;

In addition to the coinbase transactions that are rewarded by mining, there are only outputs. Under normal circumstances, each transaction needs to include several inputs and outputs. The unspent Transaction Outputs (UTXO) can be used as the legal input of a new transaction. Spent Transaction Outputs (STXOs) can no longer be referenced as valid inputs. Therefore, a legitimate transaction in the Bitcoin network must refer to the UTXO of some existing transaction as the input of the new transaction, and generate a new UTXO.

#### Digital Signature

During the transaction, how does the payer prove that the UTXO quoted is legitimate? In Bitcoin, it is implemented through a "digital signature", and an "output script" is specified to limit the use of new UTXOs in the future to only the specified payee. For each transaction, the payer needs to sign to confirm.&#x20;

The way this works is that everyone generates a public and private key pair. Where private key is kept to yourself, and it changes for different messages. Then, producing a signature involves some function that depends both on the content and the private key. Private key insure you as the only one who can produce the signature, and the fact that it depends on the content means no one can copy your signature and forge it. Finally, a verification function comes into play with the signature and public key.

#### Transaction Fee

And, for each transaction, the total input cannot be less than the total output. The excess part of the total input compared to the total output is called the transaction fee, which is obtained by the miners who generate the block containing the transaction. Currently, it is stipulated that the transaction fee of each transaction cannot be less than 0.0001 BTC. The higher the transaction fee, the more miners are willing to include the transaction, and the sooner it will be put into the network. Transaction fees not only reward miners but also protect the network from a large number of attacks.

#### Distributed Ledger

Each transaction is broadcasted and recorded on the private ledger, and we want to find a way for all users to agree on the correct ledger. The trustful ledger is chosen to be the ledger with the most computational work. The computation is calculated using a hash function to convert messages or files into a "Hash" or "Digest".&#x20;

#### Unit

The smallest unit in a transaction is "satoshi", or one-hundred-millionth (10^-8) bitcoin.



