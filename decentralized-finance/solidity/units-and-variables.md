---
description: >-
  Source:
  https://docs.soliditylang.org/en/v0.8.16/units-and-global-variables.html#special-variables-and-functions
---

# Units and Variables

### Ether Units[](https://docs.soliditylang.org/en/v0.8.16/units-and-global-variables.html#ether-units)

A literal number can take a suffix of `wei`, `gwei` or `ether` to specify a subdenomination of Ether, where Ether numbers without a postfix are assumed to be Wei.

```
assert(1 wei == 1);
assert(1 gwei == 1e9);
assert(1 ether == 1e18);
```

The only effect of the subdenomination suffix is a multiplication by a power of ten.



### Special Variables and Functions[](https://docs.soliditylang.org/en/v0.8.16/units-and-global-variables.html#special-variables-and-functions)

There are special variables and functions which always exist in the global namespace and are mainly used to provide information about the blockchain or are general-use utility functions.

#### Block and Transaction Properties[](https://docs.soliditylang.org/en/v0.8.16/units-and-global-variables.html#block-and-transaction-properties)

* `blockhash(uint blockNumber) returns (bytes32)`: hash of the given block when `blocknumber` is one of the 256 most recent blocks; otherwise returns zero
* `block.basefee` (`uint`): current block’s base fee ([EIP-3198](https://eips.ethereum.org/EIPS/eip-3198) and [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559))
* `block.chainid` (`uint`): current chain id
* `block.coinbase` (`address payable`): current block miner’s address
* `block.difficulty` (`uint`): current block difficulty
* `block.gaslimit` (`uint`): current block gaslimit
* `block.number` (`uint`): current block number
* `block.timestamp` (`uint`): current block timestamp as seconds since unix epoch
* `gasleft() returns (uint256)`: remaining gas
* `msg.data` (`bytes calldata`): complete calldata
* `msg.sender` (`address`): sender of the message (current call)
* `msg.sig` (`bytes4`): first four bytes of the calldata (i.e. function identifier)
* `msg.value` (`uint`): number of wei sent with the message
* `tx.gasprice` (`uint`): gas price of the transaction
* `tx.origin` (`address`): sender of the transaction (full call chain)
