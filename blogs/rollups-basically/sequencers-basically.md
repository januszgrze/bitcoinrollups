*Currently in draft*

Sequencers are the role that build blocks in rollups. They take transactions from rollup users, determine the ordering of those transactions in a rollup block, and then send the block to the executor to be executed in the given order. 

So miners...?

They can be miners! But, there's a number of ways to design sequencer operators. So, we'll use the term "block producer" to remain neutral.

Sequencers have the privileged role of constructing rollup blocks. In the current rollup landscape on Ethereum, all sequencers are [centralized](https://www.binance.com/en/research/analysis/ethereums-rollups-are-centralized-a-look-into-decentralized-sequencers). That means a single node (yes, a single node) is responsible for producing blocks for the entire rollup.

This single server holds a lot of power! They can order transactions in any way they like, and (perhaps more crucially) censor transactions they don't like. Centralized sequencers can also cause [liveness failures](https://thedefiant.io/arbitrum-outage-2) because if the sequencer goes down, progress for the rollup halts. This has happened numerous times.

As we look to bring rollups to Bitcoin, leveraging centralized sequencers could be controversial. Bitcoiners are typically not fans of protocol centralization. And, to be honest, if we want rollups to offer better scaling and trust assumptions than current Bitcoin Layer 2s (L2s), should we implement centralized chokepoints at all?

But, centralized sequencers are very good for performance! Users like the fact that the user experience of a rollup is enhanced by the fact that a centralized server can produce rollup blocks really quickly. Additionally, a centralized sequencer does not centralize all aspects of a rollup and inherits many aspects of security from its underlying L1 and its proof mechanism. The sequencer must provide data availability to the underlying L1, cannot brute force invalid state transitions through a validity proof (i.e., steal), cannot reorder transactions once they achieve L1 finality, and cannot censor long-term (more on forced inclusions below).

So, what do you do? Do you even need to decentralize the sequencer? Why is it important to do so?

Let's break it down. There's a large design space regarding sequencer decentralization. You could distribute the sequencer role out to a small, federated network of nodes, a larger consensus protocol, use a centralized sequencer and devise a forced transaction inclusion scheme, or simply use the Layer 1 (L1) for sequencing. 

### Forced inclusion schemes

[Forced inclusion](https://docs.arbitrum.io/sequencer#unhappyuncommon-case-sequencer-isnt-doing-its-job) is when a user can submit their unconfirmed L2 transaction the L1. This is useful in a scenario where the sequencer is not producing rollup blocks, or censoring a specific transaction type.

Here, a user would simply find that their transaction hasn't been included in a rollup block and given a pre-confirmation. Pre-confirmations are when the sequencer includes a rollup transaction in a block, and users are given a promise that the transaction will be executed. 

So after the user finds that their transaction wasn't included, and no pre-confirmation was given, they can go through the process of submitting a transaction directly to the L1 for sequencing.

L2 users should be able to withdraw from the rollup whenever they need to, for whatever reason. Ensuring that users can exit permissionlessly, and bypass the sequencer, is a necessary design.

### Decentralization

However, forced inclusion is still something that we'd ideally want to avoid in these systems. In a world where Bitcoin has a healthy and high fee market, most users could simply be [priced out of using the Bitcoin Layer 1](https://twitter.com/EspressoSys/status/1686851505339453440/video/1) for forcing their transactions through.

In a future world where forced inclusion is availble to all rollup users, users can theoretically exit the rollup, but some may be practially stuck in the rollup and lose the ability to interact with their funds. This is why most teams developing rollups would agree (at least publicly) that you need to decentralize the sequencer role. 

Now, how do you decentralize the sequencer? What is sufficently decentralized? Rollup users expect better performance and lower fees than the L1, but want similar trust assumptions to using the L1. 

[we want it all meme]

So this balance of decentralization and performance is a delicate one.

That's why a lot of people discussing sequencer decentralization opt for a consensus protocol versus a selected list of small nodes for sequencing. In a world where there are 5 sequencer nodes, and they are allow-listed by the rollup operator, these node providers could censor transactions based on the request of the company determining the allow list. Don't censor? You're booted and no longer operating a node.

By offloading the sequencer role to a permissionless consensus protocol, you could have an environment where anyone with the capacity to spin up a node can produce rollup blocks. In this situation, even if the majority of nodes are censoring transactions, you could have a subset of block builders creating blocks with censored transactions.

#### Design

There are a few teams currently designing decentralized sequencers. They're leveraging separate consensus protocols that make certain design tradeoffs from the L1. In the context of Bitcoin, the L1 is very decentralized, but currently has slow blocktimes and only offers probabilistic finality. 

This means that when designing a sequencer, you can make [tradeoffs](https://twitter.com/EspressoSys/status/1724525476423590390) that can provide users with a better UX while still maintaining sufficient levels of decentralization. For example, you could design a consensus protocols that optimize for higher throughput and faster blocktimes, and maybe make tradeoffs regarding decentralization. In this situation, you can still leverage the Bitcoin as a fall back network in the event the sequencer isn't performing as designed. 

For example, [Espresso Systems](https://www.espressosys.com/) is designing a sequencer protocol that uses [HotShot consensus](https://hackmd.io/@EspressoSystems/HotShot-and-Tiramisu), which is a protocol designed to produce blocks extremely fast, since it is optimistically responsive and has no block time, and can scale up to thousands of nodes.

And [Astria](https://www.astria.org/) is building a shared sequencer built on [Tendermint consensus](https://docs.astria.org/docs/overview-of-astria/architecture/the-astria-sequencer/) which has a fast blocktime and is extremely battled tested in the Cosmos ecosystem.

Most sequencers are designing their consensus around Proof-of-Stake consensus protocols because they provide stronger finality guarantees than Proof-of-Work consensus protocols. This is because validators in Proof-of-Stake protocols have to put up collateral to participate, and validators risk losing that collateral if they attempt to revert a transaction.

Thus, it might be beneficial for the sequencing layer to implement a Proof-of-Stake consensus protocol so it can provide faster finality guarantees to users. As mentioned, these guarantees come in the form of [pre-confirmations](https://twitter.com/EspressoSys/status/1693684942868541516) - a near-instant guarantee to a user that their transaction will be confirmed and settled on the Layer 1. Or, they could opt for a different Proof-of-Work algorithm like RandomX. It simply depends on the use case for the rollup, and what they want to achieve with decentralizing sequencing and block production.

But, bootstrapping a consensus set for a sequencer...? Seems like you'd need a lot of capital to secure the network? Correct, but, rollups can opt-in to sharing a decentralized sequencer. If there was a sequencer network that offered sufficient performance and decentralization for 95% of rollups on Bitcoin, it might be adventageous that they all share the same network. This is because they wouldn't have to bootstrap economic security for their own consensus protocol, allowing them to get to market faster. And, there are interoperability benefits when you share a sequencer.

Tl;dr - there's a big design space for sequencer decentralization. Rollups should make tradeoffs specific to their own use case.

PS - some zk-rollup teams are exploring how they can [combine the prover and the sequencer](https://www.youtube.com/watch?v=ub-IxvVKsmM) into the same consensus set.

#### Performance

One of the main reasons that you want to leverage a sequencer, outside of using the Layer 1 protocol, is to give users pre-confirmations. When designing a rollup, there's advantages to providing user experiences that are superior to the Layer 1. In the context of something like payments, having a UX that sees a transaction confirm in a few seconds is preferred. 

A centralized sequencer can give these pre-confirmations instantaneously. But, as rollups scale to millions of users, trusting a single node for this promise isn't practical (in the context of blockchains).

In various decentralized sequencer designs, you can still achieve pre-confirmations quickly. In protocols like HotShot (used in the Espresso Sequencer protocol) you can have near-instant pre-confirmations. In Tendermint, you can receive a pre-confirmation in 2 seconds. These performance benefits would give rollup applications a more seamless UX, and could rival solutions like Lightning and Federated Ecash mints for payment use cases.

When balancing out the tradeoffs between potential censorship and performance, it's still advantageous to decentralize the sequencer in a way that still provides fast preconfirmations. 

So, we can get decentralization and maintain performant UX?

[Yes meme]

### Summary

Sequencer discussion will start to pick up in the Bitcoin space as more teams look to build rollups on Bitcoin. In the event that Bitcoin gets trustless bridging (see [here](https://bitvm.org)), rollups could be seen as optimal scaling solution for all BTC users. It's important that all of these projects begin analyzing their paths towards decentralization, even if we are very early.

Rollup projects can gain a competitive advantage, related to UX and decentralization, if sequencer designs are sorted out quickly. Rollups can focus solely on execution, the Layer 1 can focus on ensuring rollup transaction data is dynamically available, and the sequencer can act as a the middle layer responsible for rollup block production. The sequencer can remain highly performant, and still have a high degree of decentralization and censorship resistance. Bitcoin can remain as a fall back layer in worst case scenarios.

In order to avoid the centralization risk currently going on in Ethereum, the Bitcoin ecosystem can review ongoing sequencer development and design. Arguably the easiest thing would be opting into a shared sequencer (a decentralized sequencer used by many rollups) and avoid each rollup having to bootstrap the economic security for a new consensus protocol.

An open question is determining how Bitcoin users, and rollups, could leverage BTC to secure the sequencer's consensus protocol. There is no current way to do this trustlessly, so rollups would either have to trust a custodial/federated bridge with the BTC securing the sequencer validator set, mint their own token to secure the sequencer, or opt-in to a competing ecosystem's shared sequencer. Using Tendermint consensus to decentralize the sequencer, and [leverage Babylon restaking](https://babylonchain.io/), is a promising approach should trustless bridging be implemented.

To discuss these tradeoffs, we recommend you join the Bitcoin rollups [telegram group](https://t.me/+_pb6J2hiyC0wMWQ0). Please offer any thoughts or feedback on these notes.

*Disclaimer: The author of this blog post works for Espresso Systems, the company designing the Espresso Sequencer. The post was reviewed and edited by others to ensure neutrality.*
