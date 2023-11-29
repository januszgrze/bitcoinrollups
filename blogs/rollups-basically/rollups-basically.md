## Rollups (Basically)

Rollups are blockchains that are built atop another blockchain (somtimes known as the parent blockchain or Layer 1). The reason Bitcoin community members have looked at adopting rollups is to increase transaction throughput, and also create additional execution environments that add more programmability to Bitcoin. To enhance the transaction capacity of Layer 1, rollups take the execution of transactions offchain.

Although the execution happens offchain, the state root and necessary transaction data is submitted to Layer 1. This specific design enables rollups to inherit some of the security from the blockchain that they are built on top of, and sets them apart from state channels and sidechains as these solutions mostly keep their transaction data offchain.

Simply put, rollups are solutions that could increase the amount of transactions Bitcoin is capable of, create different (or improved) ways to use BTC, and see their transaction data stored on the Bitcoin Layer 1 in an efficient way.

Bunch of jargon right? Let's break it down by going through the transaction lifecycle of a rollup transaction.

### Rollup transaction lifecycle

Rollup transactions start with a client initiating a transaction. Think of a user sumbitting a transaction via a mobile wallet. Because rollups enable different execution environments, the transaction can be whatever the rollup enables. Something like DeFi swaps on a rollup with smart contracts, an encrypted payment on a privacy preserving rollup, or a streamlined Oridinals mint. 

After a user initiates this, the transaction will be sent to something called a sequencer. A sequencer is the block builder and block producer for rollups. The sequencer will take the transaction, place and order it within a rollup block, and then send the proposed block to the executor and prover.

The executor and/or prover then take this block (a.k.a the list of transactions) and execute them in the given order order. It then submits a summary of state changes and necessary transaction data to the settlement layer. There are two ways to submit this summary of transactions - Optimistic and ZK.

#### Optimistic & ZK differences

This part gets a little more technical.

ZK rollups stand out as being higly efficient and secure. This is because both execution and computation happen offchain. ZK rollups utilize validity proofs to prove to the legitimacy of transactions. After a group of transactions is executed in a ZK rollup, the prover will compress the transaction data and verify that the group of transactions were executed correctly. After this computation is complete, the prover will send the proof to the rollup's settlement layer to be verified. Therefore, sending validity proofs and compressed data (state differences) is enough for verification in ZK rollups. Remember, we don't want to send the full transaction list to the layer 1 (because that's a lot of data), so the validity proof compresses all of the transaction update into a single proof (that's under 4MB of data) that says the updated state is correct.

Optimistic rollups, on the other hand, will execute transactions offchain, compress them into batches, and then send those batches to the settlement layer for verification. Optimistic rollups require executors to publish transaction data to the settlement layer, because they optimistically assume all the transactions were valid when they were executing them. The security in Optimistic rollups comes from fraud proof schemes, where anyone can submit a fraud proof to challenge that the transactions in a proposed state update are invalid. This window to challenge the state update usually lasts a week. If the challenge is successful, the rollup reexecutes the list of transactions. If there is no challenge, the rollup state update stays as is.

ZK-rollups are considered more secure because they instantly prove that the computation (execution of transactions) was correct. However, Optimistic rollups currently hold over 85% of marketshare in Ethereum, so it might be the case that users don't value this level of security. We're very early in this design space, and optimistic rollups did get to market faster than ZK-rollups, so are still waiting on seeing how all of this plays out.

Specific to Bitcoin, most teams are developing ZK-rollups because the development cycles already happened in Ethereum, and most teams prefer building on this technology stack.

#### Settlement

In either of the schemes, the rollup still needs a mechanism that sees these transactions settled and finalized. In Ethereum, most rollups are smart contract rollups. This design sees a smart contract verify the proposed state update sent from the rollup, and then settle and finalize the list of transactions.

But, because the Bitcoin Layer 1 doesn't currently verify validity proofs, the teams designing Bitcoin rollups are building something called "Sovereign Rollups". These rollups have a network of light nodes that agree on the proposed state change. This is really good for decentralization!

So after the network of nodes agree on the proposed update, the proof is then sent to Bitcoin for data availability. The main requirement for rollups **is that they store their data on Bitcoin so Bitcoin full nodes can download and review the entire history of the rollup**. If they do not do this, they are not a rollup. Shun them.

This is basically it. Where it gets more complicated is that there is a large design space where rollup teams can customize these various components to their specific preference or usecase. That's good! More customization can mean a better user experience because rollups can tailor their execution environments to a specific use case.

Additionally, because trustless bridging is not doable on Bitcoin, sovereign rollups can bridge BTC over to their rollup through a trusted environment (multi-sig or custodian), they can mint their own token, or they can do both. 

It's an ever growing design space. We'll be outlining the various designs and tradeoffs in follow-up posts. In the meantime, we recommend you review our [Basics](https://www.bitcoinrollups.io/the-basics) page for more information on ZK-rollups on Bitcoin.
