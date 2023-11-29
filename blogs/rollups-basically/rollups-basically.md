## Rollups (Basically)

Rollups are blockchains that are built atop another blockchain (somtimes known as the parent blockchain or Layer 1). The reason Bitcoin community members have looked at adopting rollups is to increase transaction throughput, and also create additional execution environments that add more programmability to Bitcoin. To enhance the transaction capacity of Layer 1, rollups take the execution of transactions offchain. Although the execution happens offchain, the state root and necessary transaction data is submitted to Layer 1. This specific design enables rollups to inherit some of the security from the blockchain that they are built on top of, and sets them apart from state channels and sidechains as these solutions mostly keep their transaction data offchain.

Simply put, rollups are solutions that could increase the amount of transactions Bitcoin is capable of, create different (or improved) ways to use BTC, and see their transaction data stored on the Bitcoin Layer 1 in an efficient way.

Bunch of jargon right? Let's break it down by going through the transaction lifecycle of a rollup transaction.

Rollup transactions start with a client initiating a transaction. Think of a user sumbitting a transaction via a mobile wallet. Because rollups enable different execution envionrments, the transaction can be whatever the rollup enables. Something like DeFi swaps on a rollup with smart contracts, an encrypted payment on a privacy preserving rollup, or a streamlined Oridinals mint. 

After a user initiates this, the transaction will be sent to something called a sequencer. A sequencer is the block builder and block producer for rollups. The sequencer will take the transaction, place and order it within a rollup block, and then send the proposed block to the executor and prover.

The executor and/or prover then take this block (a.k.a the list of transactions) and executes them in that order. It then submits a summary of state changes and necessary transaction data to the layer 1. The type of rollup becomes important here in terms of being efficient in publishing data.

There are two types of rollups - Optimistic and ZK-rollups. They differ in the way that they verify the updated state of the rollup to the Layer 1. Optimistic rollups require sequencers to publish full transaction data to Layer 1 because they assumed all the transactions were valid when they were executing them. So, Layer 1 needs to see full transaction data to be able compute that transactions were indeed valid. Having to publish full transaction data increases the rollup cost.

ZK rollups, on the other hand, stand out as being higly efficient. Here both execution and computation happen offchain. ZK rollups utilize validity proofs to attest to the legitimacy of transactions in advance. Therefore, sending validity proofs and compressed data (state differences) is enough for verification in Zk rollups. Remember, we don't want to send the full transaction list to the layer 1 (because that's a lot of data), so the validity proof compresses all of the transaction update into a single proof (that's under 4MB of data) that says the updated state is correct.

Rollups can come to consensus through two ways. The first way is by having a smart contract in the Layer 1 protocol that verifies that the state change proposed by the validity proof is correct.

But, because the Bitcoin Layer 1 doesn't currently verify validity proofs, the teams designing Bitcoin rollups are building something called "Sovereign Rollups". These rollups have a network of light nodes that agree on the proposed state change. This is really good for decentralization!

So after the network of nodes agree on the proposed update, the proof is then sent to Bitcoin for data availability. The main requirement for rollups **is that they store their data on Bitcoin so Bitcoin full nodes can download and review the entire history of the rollup**. If they do not do this, they are not a rollup. Shun them.

This is basically it. Where it gets more complicated is that there is a large design space where rollup teams can customize these various components to their specific preference or usecase. That's good! More customization can mean a better user experience because rollups can tailor their execution environments to a specific use case.

Additionally, because trustless bridging is not doable on Bitcoin, sovereign rollups can bridge BTC over to their rollup through a trusted environment (multi-sig or custodian), they can mint their own token, or they can do both. 

It's an ever growing design space. We'll be outlining the various designs and tradeoffs in follow-up posts. In the meantime, we recommend you review our [Basics](https://www.bitcoinrollups.io/the-basics) page for more information on ZK-rollups on Bitcoin.
