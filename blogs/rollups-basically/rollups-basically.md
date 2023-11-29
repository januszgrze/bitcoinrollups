## Rollups (Basically)

ZK-rollups are stripped down blockchains that take the execution of transactions offchain. This is beneficial because they can enable more throughput and different execution environments that enable different types of transactions. To ensure that they are minimizing the amount of data posted on the Layer 1 blockchain, they use validity proofs to compress the data, while still proving that the proposed state change of the rollup is true.

Bunch of jargon right? Let's break it down by going through the transaction lifecycle of a rollup transaction.

Rollup transactions start with a client initiating a transaction. Like a user sumbitting a transaction via a mobile wallet. Because rollups enable different execution envionrments, the transaction can be whatever the rollup enables. Something like DeFi swaps on a rollup with smart contracts, a shielded payment on a privacy preserving rollup, or a streamlined Oridinals mint. 

After a user initiates this, the transaction will be sent to something called a sequencer. A sequencer is the block builder + producer for rollups. The sequencer will take the transaction, place and order it within a rollup block, and then send the proposed block to the executor and prover.

The executor and prover then take this block (a.k.a the list of transactions) and executes them in that order. It then proves the execution of the transactions to the layer 1 by constructing a validity proof. Remember, we don't want to send the full transaction list to the layer 1 (because that's a lot of data), so the validity proof compresses all of the transaction update into a single proof (that's under 4MB of data) that says the updated state is correct.

Rollups can come to consensus through two ways. The first way is by having a smart contract in the Layer 1 protocol that verifies that the state change proposed by the validity proof is correct.

But, because the Bitcoin Layer 1 doesn't currently verify validity proofs, the teams designing Bitcoin rollups are building something called "Sovereign Rollups". These rollups have a network of light nodes that agree on the proposed state change. This is really good for decentralization!

So after the network of nodes agree on the proposed update, the proof is then sent to Bitcoin for data availability. The main requirement for rollups **is that they store their data on Bitcoin so Bitcoin full nodes can download and review the entire history of the rollup**. If they do not do this, they are not a rollup. Shun them.

This is basically it. Where it gets more complicated is that there is a large design space where rollup teams can customize these various components to their specific preference or usecase. That's good! More customization can mean a better user experience because rollup can tailor its environments to their specific use case.

Additionally, because trustless bridging is not doable on Bitcoin, sovereign rollups can bridge BTC over to their rollup through a trusted environment (multi-sig or custodian), they can mint their own token, or they can do both. 

It's an ever growing design space. We'll be outlining the various designs and tradeoffs in follow-up posts. In the meantime, we recommend you review our [Basics](https://www.bitcoinrollups.io/the-basics) page for more information on ZK-rollups on Bitcoin.
