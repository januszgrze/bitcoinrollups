## Read the research that has sparked a Bitcoin Renaissance

ZK-rollups on Bitcoin were a pipe-dream until this year. With the recent research around the subject, and the growing excitement around Bitcoin during the recent Ordinals craze, teams are now exploring ways to implement sovereign rollups on Bitcoin.

Let's dive into the research. Below, we outline the key pieces to get you up to date on the development of zk-rollups on Bitcoin.

We also provide a list of research papers, Github repos, and documentation sites for you to dive into. Skip to those [here](https://bitcoinrollups.io/research-links).

## The tl;dr on Bitcoin rollup R&D

### Setting context

IIn 2022, the Human Rights Foundation and Starkware put out an RFP for a research fellowship. The fellowship was tasked with covering if, or if not, zk-rollups would be beneficial to Bitcoin.

It asked a number of questions around zk-rollups improving Bitcoin scaling, privacy and user experience. John Light was awarded the fellowship and produced the first and most comprehensive research report on the subject.

When catching up on R&D around Bitcoin rollups, the first thing you should do is:

- [Read the HRF's call for proposals](https://hrf.org/zkrollups)
- [Read the research report "Validity rollups on Bitcoin"](https://bitcoinrollups.org/)

### Understand what is enabling development

Earlier in 2023, the Bitcoin protocol saw a spike in usage due to new interest in Ordinals and BRC-20 tokens. Two upgrades to the Bitcoin protocol enabled these use cases, and they also enable rollups.

The Ordinal protocol is a tracking system that assigns a number to a single satoshi (a denomination of Bitcoin). Inscriptions are the content that is inscribed into a specific satoshi. The inscribing and storing of this data was enabled by the "Taproot" and "SegWit" upgrades. SegWit split Bitcoin transactions into two sections by adding a witness data section that is able to store arbitrary data. Taproot created an easier and more relaxed system for storing arbitrary data in Bitcoin transactions. With Taproot, you can fill a Bitcoin block with a little under 4 MB of arbitrary witness data in a single Bitcoin transaction.

- [Read the Ordinal Theory Handbook](https://docs.ordinals.com/inscriptions.html)

### Where rollups come into play

So with this ability to store (a little less than) 4 MB of arbitrary data in a Bitcoin block, you can do a lot of cool stuff. Teams are now researching and implementing ways for developers to use these data blobs to post rollup transaction data to Bitcoin.

Rollkit released a framework for developers to launch sovereign rollups using Bitcoin for data availability and consensus. Within this framework, you can launch rollups with different execution environments and potentially add features like Zcash-level privacy. The rollups handle their own settlement and execution, and they use Bitcoin for data availability and consensus.

Now other teams are exploring how they can use Taproot to deploy sovereign rollups on Bitcoin. Chainway, who maintains a Bitcoin data availability adapter, is looking to launch the first in-production zk-rollup on Bitcoin. Kasar Labs, in partnership with Bitcoin NFT project "Taproot Wizards", is looking to launch a Bitcoin zk-rollup leveraging the Starknet stack and Chainway's DA adapter.

To get up to date on the development of zk-rollups on Bitcoin, you should read the following:

- [Rollkit introducing their Bitcoin sovereign rollup framework](https://rollkit.dev/blog/sovereign-rollups-on-bitcoin)
- [Chainway outlining the design for their Bitcoin zk-rollup](https://medium.com/@chainway_xyz/a-sovereign-zk-rollup-on-bitcoin-full-bitcoin-security-without-a-soft-fork-ca0389a0b658)
- [ZK rollups are coming to Bitcoin by Bitcoin Magazine](https://bitcoinmagazine.com/technical/zk-rollups-are-coming-to-bitcoin-heres-all-you-need-to-know)
- [Blog outlining how zk-rollups might work on Bitcoin](https://trustmachines.co/learn/what-are-rollups-and-how-can-they-work-on-bitcoin/)

## More R&D Resources

### Bitcoin rollup research, code repositories and more

We've compiled a list of resources that documents the research, code repositories, forums and technical documentation surrounding Bitcoin rollups. You can check out the full list [here](https://bitcoinrollups.io/research-links).
