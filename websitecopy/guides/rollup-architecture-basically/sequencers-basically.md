*Currently in draft*

Sequencers are the role that build blocks in rollups. They take transactions from users who are interacting with a rollup, determine the ordering of those transactions in a rollup block, and then send the block to the executor and provers to be executed in that given ordering. 

Now, why is that important?

Sequencers have the priveleged rollup of constructing a rollup block. This means that they can order transactions in any way they like, and, censor transactions they don't like. These are the two major issues that people bring up when talking about sequencer centralization.

In the Ethereum rollup ecosystem, all sequencers are centralized. This means a single node builds all the rollup blocks for a specific rollup. Implmenting this on Bitcoin could be controversial due to the community's desire to maintain decentralization (although WoS would like to have a word). This also creates liveness failures because if the sequencer goes down, progress for the rollup halts. This has happened numerous times.

But, centralized sequencers are very good for performance! Users do like the fact that the user experience of a rollup is enhanced by the fact that a centralized server can produce rollup blocks really quickly. 

So, what do you do?

There's a large design space regarding sequencer decentralization. You could distribute the sequencer role out to a small, selected network of nodes, a larger consensus protocol, maintain a centralized sequencer and devise a forced transaction inclusion scheme, or simply use the Layer 1 for sequencing. 

Let's talk about some of the tradeoffs.

### Forced inclusion schemes

Forced inclusion is when a user can submit their unconfirmed L2 transaction the L1. This is useful in a scenario where the sequencer is not producing rollup blocks, or censoring a specific transaction type. In any scenario of sequencer design, rollups ensuring that users can exit through bypassing the sequencer is a necessary design.

### Decentralization

However, forced inclusion is still something that we'd ideally want to avoid in these systems. In a world where Bitcoin has a healthy and high fee market, most users could simply be priced out of using the Bitcoin Layer 1 for forcing their transactions through. This means their funds would be effectively stuck in the rollup. In a world where their being censored, you could equate this to them (basically) losing access to their funds.

This is why most teams developing rollups agree that you need to decentralize the sequencer role. 

The first question people need to ask is how we should decentralized. Remember, rollups inherit the security of the Layer 1 protocol, and if designed correctly, can leverage the Layer 1 as an escape hatch if the sequencer goes down.

So this balance of decentralization and performance is a delicate one. 

That's why a lot of people discussing sequencer decentralization opt for a consensus protocol versus a selected list of small nodes for sequencing. In a world where there are 5 sequencer nodes, and they are allow listed by the rollup operator, these node providers could censor transactons based on the request of the company determining the allow list.

By offloading the sequencer role to a permissionless consensus protocol, you could have an environment where anyone with the capacity to spin up a node can produce rollup blocks. In this situation, even if the majority of nodes are censoring transactions, you could have a subset of block builders creating blocks with censored transactions. This is basically how Ethereum is playing out right now.

### Design

There are a few teams that are currently designing decentralized sequencers and they're focusing on consensus protocols that make certain design tradeoffs from the Layer 1. In the context of Bitcoin, it is very decentralized, but currently has slow blocktimes and only offers probablistic finality. 

This means that when designing a sequencer, you can make tradeoffs that can provide users a better UX while still maintaining high levels of decentralization. For example, you could design a consensus protocols that optimize for higher throughput and faster blocktimes, and maybe make tradeoffs regarding decentralization. In this situation, you could still leverage the Bitcoin as a fall back network in the event the sequencer isn't performing as designed.

For example, Espresso Systems is designing a sequencer protocol that uses HotShot consensus, which is a protocol designed to produce blocks extremely fast since it has no block time, and can scale up to thousands of nodes.

And Astria is building a shared sequencer built on Tendermint consensus which has a fast blocktime and is extremely battled tested in the Cosmos ecosystem.

Most sequencers are designing their consensus around Proof-of-Stake consensus protocols because they provide stronger finality guarantees than Proof-of-Work consensus protocols. This is because validators in Proof-of-Stake protocols have to put up collateral to participate, and validators risk losing that collateral if they attempt to revert a transaction.

Thus, it might be beneficial for the sequencing layer to implement a Proof-of-Stake consensus protocol so it can provide faster finality guarantees to users. These guarantees come in the form of pre-confirmations - a near-instant guarantee to a user that their transaction will be confirmed and settled on the Layer 1.

### Performance

One of the main reasons that you want to leverage a sequencer, outside of using the Layer 1 protocol, is to give users these pre-confirmations. When designing a rollup, there's advantages to providing user experiences that are superior to the Layer 1. In the context of something like payments, having a UX that sees a transaction confirm in a few seconds would be advantageous. 

A centralized sequencer can give these pre-confirmations instantaneuously, because when it confirms a user's transaction has been sequenced, users are assured that it will be included in a rollup block to be executed and confirmed on the Layer 1.

In various decentralized sequencer designs, you can still achieve pre-confirmations quickly. In protocols like HotShot (used in the Espresso Sequencer protocol) you can have near-instant pre-confirmations. In Tendermint, you can receive a pre-confirmation in 2 seconds. These performance benefits would give rollup applications a more seamless UX, and could rival solutions like Lightning and Federated Ecash mints for payment use cases.

So, when balancing out the tradeoffs between potential censorship and performance, it's still advantageous to decentralize the sequencer in a way that still provides fast preconfirmations. 

### Summary

Sequencer discussion will start to pick up in the Bitcoin space as more teams look to build rollups using Bitcoina as a DA layer. In the event that Bitcoin gets trustless bridging, these rollups will be seen as primary scaling solution. It's important that all of these projects begin analyzing their paths towards decentralization, even if we are very early.

Rollup projects can gain a competitive advantage related to UX and decentralization if sequencer designs are sorted out quickly. Rollups can focus solely on execution, the Layer 1 can focus on ensuring rollup transaction data is dynamically available, and the sequencer can act as a the middle layer responsible for rollup block production. This sequencer can remain highly performant, and still have a high degree of decentralization and censorship resistance. Bitcoin can remain as a fall back layer in worst case scenarios.

In order to avoid the centralization risk currently going on in Ethereum, the Bitcoin ecosystem can review ongoing sequencer development and design. Arguably the easiest thing would be opting into a shared sequencer (a decentralized sequencer used by many rollups) and avoid having to bootstrap the economic security for a new consensus protocol. But, Bitcoin rollups need to carefully analyze how shared sequencers are bootstrapping their own economic security, and see if that is viewed in contrast to Bitcoin's ethos. 

The biggest open ended question is determining how Bitcoin users, and rollups, could leverage BTC to secure the sequencer's consensus protocol. There is no current way to do this trustlessly, so rollups would either have to trust a custodial/federated bridge with the BTC securing the sequencer validator set, mint their own token to secure the sequencer, or opt-in to a competing ecosystem's shared sequencer.

To discuss these tradeoffs, we recommend you join the Bitcoin rollups telegram group. Please offer any thoughts or feedback on these notes.
