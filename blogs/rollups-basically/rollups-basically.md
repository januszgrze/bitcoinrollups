## Rollups (Basically)

Rollups are blockchains that are built atop another blockchain (somtimes known as the parent blockchain or Layer 1). The reason Bitcoin community members have looked at adopting rollups is to increase transaction throughput, and also create additional execution environments that add more programmability to Bitcoin. To enhance the transaction capacity of Layer 1, rollups take the execution of transactions offchain.

Although the execution happens offchain, the state root and necessary transaction data is submitted to Layer 1. This specific design enables rollups to inherit some of the security from the blockchain that they are built on top of, and sets them apart from state channels and sidechains as these solutions mostly keep their transaction data offchain.

Simply put, rollups are solutions that could increase the amount of transactions Bitcoin is capable of, create different (or improved) ways to use BTC, and see their transaction data stored on the Bitcoin Layer 1 in an efficient way.

Bunch of jargon right? Let's break it down by going through the transaction lifecycle of a rollup transaction.

### Rollup transaction lifecycle

#### Transaction creation and block production

Rollup transactions start with a client initiating a transaction. Think of a user sumbitting a transaction via a mobile wallet. Because rollups enable different execution environments, the transaction can be whatever the rollup enables. Something like DeFi swaps on a rollup with smart contracts, an encrypted payment on a privacy preserving rollup, or a streamlined Oridinals mint. 

After a user initiates this, the transaction will be sent to something called a [sequencer](https://hackmd.io/@EspressoSystems/EspressoSequencer#A-Rollups-Overview). A sequencer is the block builder and producer for rollups. The sequencer will take transactions, place and order them within a rollup block, and then send the proposed block to the executor and prover.

#### Execution and proving

The executor and/or prover then take this block (a.k.a the list of transactions) and execute them in the given order. It then submits a summary of state changes and necessary transaction data to the settlement layer. There are two ways to submit this summary of transactions - optimistically and or through zero-knowledge proofs. This part gets a little more technical.

[ZK-rollups](https://ethereum.org/en/developers/docs/scaling/zk-rollups/) stand out as being higly efficient and secure. This is because both execution and computation happen offchain. ZK-rollups utilize validity proofs to prove to the legitimacy of transactions. After a group of transactions is executed in a ZK-rollup, the prover will compress the transaction data and verify that the group of transactions were executed correctly. After this computation is complete, the prover will send the proof to the rollup's settlement layer to be verified. In this design, sending validity proofs and compressed data (state differences) is all the settlement layer needs to verify the rollup's transactions. Remember, we don't want to send the full transaction list to the Bitcoin Layer 1 (because that's a lot of data), so we'd use a validity proof to compress all of the data into a single proof that's under 4MB of data. It's estimated that an account model rollup can fit up to [250,000 transactions](https://bitcoinrollups.org/#section-4-scaling-improvements) into a single Bitcoin block!

[Optimistic rollups](https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/), on the other hand, will execute transactions offchain, compress them into batches, and then send those batches to the settlement layer for verification. Optimistic rollups require executors to publish transaction data to the settlement layer, because they optimistically assume all the transactions were valid when they were executing them. The security in Optimistic rollups comes from [fraud proof schemes](https://ethereum.org/en/glossary/#fraud-proof), where anyone can submit a fraud proof to challenge that the transactions in a proposed state update are invalid. This window to challenge the state update usually lasts a week. If the challenge is successful, the rollup reexecutes the list of transactions. If there is no challenge, the rollup state update stays as is.

ZK-rollups are considered more secure because they instantly prove that the computation (execution of transactions) was correct. However, Optimistic rollups are currently cheaper to use than ZK-Rollups. Optimistic rollups currently hold over [85% of marketshare in Ethereum](https://l2beat.com/scaling/summary), so it might be the case that users value cost savings over higher levels of security.

However, specific to Bitcoin, most teams are developing ZK-rollups. This is because the development cycles have already happened in Ethereum. And, a lot of developers believe that ZK-rollups will become faster and cheaper to use in the next few years. Combine that with their security model, they appear to be a better long term solution.

We're very early in this design space, and optimistic rollups did get to market faster than ZK-rollups, so we are still waiting on seeing how all of this plays out.

But back to the transaction lifecycle! In either of these schemes, the executor will execute the list of transactions it receives from the sequencer, and then send the updated state of the rollup to the settlement layer.

#### Verification and settlement

After the rollup transactions are executed, the rollup still needs a mechanism that sees these transactions verified, settled and finalized. In Ethereum, most rollups are smart contract rollups. This design sees a smart contract verify the proposed state update sent from the rollup, and then settle and finalize the list of transactions on the Layer 1 blockchain.

But, because the Bitcoin Layer 1 doesn't currently verify validity proofs, the teams designing Bitcoin rollups are building something called a sovereign rollup. This design sees network of rollup light nodes verify and agree on a proposed state change. This was originally [introduced by Celestia](https://celestia.org/learn/sovereign-rollups/an-introduction/).

So after a network of nodes agree on the proposed state update, a proof containing the state change would then be sent to Bitcoin for data availability. This means that the rollup, and Bitcoin full nodes, can download the history of the rollup and verify the transactions for themselves. The main requirement for rollup on Bitcoin **is that they store their data on Bitcoin so Bitcoin full nodes can download and review the entire history of the rollup**. If they do not do this, they are not a rollup.

Remember that we mentioned that ZK-rollups compress transaction data into a proof just under 4MB? This is because when the sovereign rollup agrees on the state update, it sends the validity proof to Bitcoin, and the proof is then [inscribed into the arbitrary witness data through a Taproot transaction](https://trustmachines.co/glossary/inscriptions/). 

It's argued that sovereign rollups have more autonomy that smart contract rollups because the network of nodes decide on protocol upgrades versus a smart contract controlled by a multi-sig and/or token voting process. This is similar to how Layer 1 blockchains upgrade their systems. This autonomy can lead to improved decentralization.

Both sovereign and smart contract rollups can have trust minimized bridging to move the Layer 1's native asset (in this case BTC) to the rollup.

### To finish

Rollups can scale Bitcoin because they would move the execution of transactions offchain. They are potentially preferrable to sidechains because Bitcoin full nodes can verify the history of the rollup because the rollup's data is stored on the Bitcoin Layer 1. 

This is basically it. Where it gets more complicated is that there is a large design space where rollup teams can customize these various components to their specific preference or usecase. That's good! More customization can mean a better user experience because rollups can tailor their execution environments to a specific use case.

Additionally, because trustless bridging is not doable on Bitcoin, rollups can bridge BTC over to their rollup through a trusted environment (multi-sig or custodian), they can mint their own token, or they can do both.

It's an ever growing design space. We'll be outlining the various designs and tradeoffs in follow-up posts. In the meantime, we recommend you review our [Basics](https://www.bitcoinrollups.io/the-basics) page for more information on ZK-rollups on Bitcoin.

And for further reading, check out the [Chainway blog](https://medium.com/@chainway_xyz), and this post from [Trust Machines](https://trustmachines.co/learn/what-are-rollups-and-how-can-they-work-on-bitcoin/).
