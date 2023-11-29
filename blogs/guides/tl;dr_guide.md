_This is a living document and will be updated regularly. Please feel free to request edits and add additional content._

As I'm building [bitcoinrollups.io](https://bitcoinrollups.io), I saw someone ask what would be the best resource for someone who wanted to catch up on Bitcoin development. In response to that, I wanted to build a guide that provides a tl;dr for the latest zk-rollup development on Bitcoin.

So, if you haven't paid attention to the Bitcoin space in 7-ish years, grab a coffee (or a whiskey) and get comfortable. Reading all the materials listed in this guide will take you an evening to get through.

## The start

In 2021, the Human Rights Foundation and Starkware put out an RFP for a research fellowship. The fellowship was tasked with covering if, or if not, zk-rollups would be beneficial to Bitcoin.

_"The fellowship is being created with the acknowledgment that ZK-rollups may not be a helpful or appropriate addition to Bitcoin, but with the open mind that they might be."_

It asked a number of questions around zk-rollups improving Bitcoin scaling, privacy and user experience. John Light was awarded the fellowship and produced the first and most comprehensive research report on the subject.

The first things you should do is:

- [Read the HRF's call for proposals](https://hrf.org/zkrollups)
- [Read the research report "Validity rollups on Bitcoin"](https://bitcoinrollups.org/)

## Understand the "problem"

Earlier in 2023, the Bitcoin protocol saw a spike in usage due to new interest in Ordinals and BRC-20 tokens. Let's cover the two things that enabled this.

The Ordinal protocol is a tracking system that assigns a number to a single satoshi (a denomination of Bitcoin). Inscriptions are the result of inscribing digital artifacts to specific satoshis. The Ordinal protocol enables inscriptions by combining compontents of two protocol upgrades to Bitcoin, "Taproot" and "SegWit". SegWit can see more data be stored in a Bitcoin block, up to 4 MB when comprised of arbitrary data. And Taproot enables inscribing a single file, just below this 4 MB limit, to a single satoshi.

When people figured out that you could (basically) create NFTs and shitcoins by inscribing files to single satoshis, everyone went nuts. This created a new phase of development, applications and financial speculation on the Bitcoin protocol. Some results of this?

New interest in Bitcoin and more usage of the Bitcoin protocol. This is good right?!

Yes, Bitcoin needs more transaction fees to sustain its 21 million supply cap. As of today, only 3% of rewards paid to miners are from transaction fees. So more usage of Bitcoin is needed.

But, the Bitcoin protocol hadn't gone under a recent stress test like this, so users experienced high fees and poor UX. Lightning, a layer 2 scaling solution on Bitcoin, had major problems operating in a self-custodial manner during this phase.

So, the issues of high on-chain fees, coupled with the stress put on the Lightning network, have caused developers to explore other scaling solutions.

To further understand the "problem", you should read:

- [Read Trust Machines' blog post on Ordinals](https://trustmachines.co/learn/what-are-bitcoin-ordinals-inscriptions/)
- [Read Bitcoin Magazine's analysis on Ordinals and BRC-20 controversy](https://bitcoinmagazine.com/technical/bitcoins-high-fees-create-controversy-and-challenges)

## Where rollups come into play

So with this ability to store (a little less than) 4 MB of arbitrary data on the Bitcoin blockchain, you can do a lot of cool stuff. One of the things you can do is post big blobs of data to the Bitcoin blockchain. Teams are now researching and implementing ways for developers to use these data blobs to post rollup transaction data to Bitcoin.

The first team to release a framework for this was Rollkit. The Rollkit team released a [framework](https://rollkit.dev/blog/sovereign-rollups-on-bitcoin) for developers to launch sovereign rollups using Bitcoin for data availability and consensus. Within this framework, you can launch rollups with different execution environments and potentially add cool features like Zcash-level privacy. The rollups handle their own settlement and execution, and they use Bitcoin for data availability and consensus. The design space is large, and the 4 MB block limit gives developers a lot of design freedom.

Various teams are now exploring how they can use the Ordinal protocol deploy build sovereign rollups on Bitcoin. Chainway, who maintains a [Bitcoin data availability adapter](https://github.com/chainwayxyz/bitcoin-da), is looking to launch the first in-production zk-rollup on Bitcoin. Kasar Labs, in [partnership with Bitcoin NFT project "Taproot Wizards"](https://twitter.com/kasarLabs/status/1697402477887275082), is looking to launch a Bitcoin zk-rollup leveraging the Starknet stack and Chainway's DA adapter. 

Note that these rollups are sovereign rollups and do not use a Layer 1 smart contract to update the rollup's state. Also, in Bitcoin you cannot have trustless bridging without implementing a soft fork, so these rollups would likely use their own native token versus BTC. However, there are benefits to using Bitcoin as a data availability and consensus layer, which is a reason developers are exploring these rollup designs.

Additionally, many of the proponents for zk-rollups on Bitcoin have voiced their support for a soft fork that would enable trustless smart contract validity rollups (highlighted in the research shared in this guide). You could view these initial sovereign rollup deployments as the first step to showing why Bitcoin should enable trustless bridging. In this future state, users could trustlessly use their BTC in a number of ways via different execution environments that are enabled by rollups.

To get up to date on the development of zk-rollups on Bitcoin, you should read the following:

- [Rollkit introducing their Bitcoin sovereign rollup framework](https://rollkit.dev/blog/sovereign-rollups-on-bitcoin)
- [Chainway outlining the design for their Bitcoin zk-rollup](https://medium.com/@chainway_xyz/a-sovereign-zk-rollup-on-bitcoin-full-bitcoin-security-without-a-soft-fork-ca0389a0b658)
- [Chainway open-sourcing its Bitcoin DA Adapter and outlining the need for rollups](https://ordinals.com/content/7b27406bb7b0c90da6cbef5074eaa56f1dbb92a9806a6a3c730c027e2b33b3e4i0)
- [ZK rollups are coming to Bitcoin by Bitcoin Magazine](https://bitcoinmagazine.com/technical/zk-rollups-are-coming-to-bitcoin-heres-all-you-need-to-know)
- [Blog outlining how zk-rollups might work on Bitcoin](https://trustmachines.co/learn/what-are-rollups-and-how-can-they-work-on-bitcoin/)
- [Comparing Bitcoin rollups with another Bitcoin Layer 2, Stacks](https://github.com/stacks-network/stacks/blob/master/bitcoin-rollups.md)

## Follow the developments

The development of zk-rollups on Bitcoin is very early and is an evolving space. I'll do my best to keep this document update, but recommend that you follow these accounts on Twitter to stay up to date on everything:

- [Chainway](https://twitter.com/chainway_xyz)
- [Kasar Labs](https://twitter.com/kasarLabs)
- [Rollkit](https://twitter.com/RollkitDev)
- [Sovereign Labs](https://twitter.com/sovereign_labs)
- [Rootstock](https://twitter.com/rootstock_io)
- [Build on Bitcoin (BOB)](https://twitter.com/build_on_bob)
- [ZeroSync](https://twitter.com/ZeroSync_)

I'll update this list as I see more teams building (or mentioning they might build) rollups on Bitcoin.

## Additional materials you can watch or listen to

There are a number of really good podcasts and conference talks on Bitcoin rollups. Some of those are listed below:

- [John Light and Eric Wall discuss Bitcoin rollups on Bankless](https://www.youtube.com/watch?v=qChILPxdOA4)
- [ZK rollups on Bitcoin panel at Bitcoin Miami 2023](https://www.youtube.com/watch?v=CJ8HUKeDy4Q&t=1s)
- [Bitcoin rollups panel at Modular Summit](https://www.youtube.com/watch?v=xOn2vjg27nM&t=1216s)
- [Eric Wall shares "Why a Bitcoiner loves a rollup" at Starkware Sessions](https://www.youtube.com/watch?v=_hLvvZGST_E)
- [John Light explaining Bitcoin rollups and ZKPs](https://www.youtube.com/watch?v=feODuDF2xv0)

To understand why Bitcoin should leverage zk-rollups, this podcast outlines the problem very well:

- [Udi Wertheimer on What Bitcoin Did](https://www.youtube.com/watch?v=97-hufd4M7s)

## To close

This document provides an extremely high level overview on Bitcoin rollups and some of the latest updates around them. Please consider that some of these topics are nuanced. If interested, please research them further. You can also contribute to this document by adding materials or provide further technical clarification if necessary.
