# Learn more about Bitcoin Rollup Research and Development

ZK-rollups on Bitcoin were a pipe-dream until this year. With the recent research around the subject, and the growing excitement around Bitcoin during the recent Ordinals craze, teams are now exploring ways to implement rollups on Bitcoin.

Let's dive into the research and development happening in the space. Below, we cover a few key research and development categories that are driving this new wave of development.

We also provide a list of research papers, Github repos, and documentation sites for you to dive into. You can skip to those here.

### Validity rollups on Bitcoin

The Validity rollups on Bitcoin research paper was the first comprehensive breakdown on how we could implement validity rollups on Bitcoin. It is still the most comprehensive report on Bitcoin rollups today, and a must read for anyone interested in the topic.

Read the paper [here](https://bitcoinrollups.org/). You can also read:

- [Bitcoin ZK-rollups technical blog post](https://tr3y.io/articles/crypto/bitcoin-zk-rollups.html)
- [HRF's RFP that funded "Validity rollups on Bitcoin" paper](https://hrf.org/zkrollups)

### BitVM

BitVM is a new computing paradigm that would enable turing complete smart contracts on Bitcoin. In the context of rollups, it could potentially give us a trust-minimized way to bridge BTC, and also optimistically verify rollups' state updates. 

Read the BitVM paper [here](https://bitvm.org/bitvm.pdf). You can also read:

- [An awesome explainer on BitVM](https://medium.com/crypto-garage/deep-dive-into-bitvm-computing-paradigm-to-express-turing-complete-bitcoin-contracts-1c6cb05edfca)
- [Our blog on why BitVM matters to rollups](https://www.bitcoinrollups.io/bitvm)
- See our full list of BitVM resources [here](https://www.bitcoinrollups.io/bitvm-resources).

### The teams building rollups on Bitcoin

There are a number of teams building ZK-rollups on top of Bitcoin. These teams are taking a number of different design approaches to brinigng this technology to Bitcoin, and are moving at an extremely fast pace.

- [Chainway](https://chainway.xyz/): A general purpose ZK-rollup leveraging the EVM and a BitVM bridge
- [Taproot Wizards](https://taprootwizards.com/): A general purpose sovereign ZK-rollup in collaboration with [Kasar Labs](https://www.kasar.io/)
- [Build on Bitcoin (BOB)](https://www.gobob.xyz/): A general purpose, zkVM rollup exploring BitVM sequencer designs and bridges
- [Alpen Labs](https://alpenlabs.io/): A general purpose ZK-rollup exploring designs that leverage an "OP_VERIFYSTARKPROOF" opcode
- See the full list of teams [here](https://www.bitcoinrollups.io/research-links).

### Opcodes

Teams are optimistic that BitVM can give us a trust-minimized way to develop rollups on Bitcoin without a soft fork. But, adding new opcodes might make building rollups on Bitcoin easier, and give us even more trust-minimized, and potentially trustless, bridging.

The first opcode teams in this space are pushing for is OP_CHECKTEMPLATEVERIFY (CTV). You can read more about CTV [here](https://bitcoinops.org/en/topics/op_checktemplateverify/). You can also check out:

- [Covenant-enabling Bitcoin Features](https://gist.github.com/RobinLinus/c96fb7c81430ec6dc92f048687bd3068)
- [An introduction to OP_VERIFYSTARKPROOF](https://www.youtube.com/watch?v=Nldg_tjeX_A&t=1s)

### Applications

Rollups are positioned to scale Bitcoin and provide new functionalities to BTC users. These new use cases range from better privacy for sending and receiving BTC, new ways to use BTC as collateral for stablecoin loans, swapping BTC for a number of new asset types, and more.

Read more about new applications enabled by rollups [here](https://bitcoinrollups.org/#section-3-enabling-new-functionality).

### Check out more resources

It's an exciting time to be a Bitcoiner! We do our best to stay up to date on all of the research and development happening in this space, and document those resources [here](https://www.bitcoinrollups.io/research-links). 

If you want to contribute resources to the website, check out our [contribute page](https://www.bitcoinrollups.io/contribute).
