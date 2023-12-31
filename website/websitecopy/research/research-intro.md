# Learn more about Bitcoin Rollup Research and Development

ZK-rollups on Bitcoin were a pipe-dream until this year. With the recent research around the subject, and the growing excitement around Bitcoin during the recent Ordinals craze, teams are now exploring ways to implement rollups on Bitcoin.

Let's dive into the research and development happening in the space. Below, we cover a few key research and development categories that are driving this new wave of development.

We also provide a list of research papers, Github repos, and documentation sites for you to dive into. You can skip to those here.

### Validity rollups on Bitcoin

The Validity rollups on Bitcoin research paper was the first comprehensive breakdown on how we could implement validity rollups on Bitcoin. It is still the most comprehensive report on Bitcoin rollups today, and a must read for anyone interested in the topic.

Read the paper [here](https://bitcoinrollups.org/).

You can also read:

- Bitcoin ZK-rollups technical blog post
- HRF's RFP that funded "Validity rollups on Bitcoin" paper

### BitVM

BitVM is a new computing paradigm that would enable turing complete smart contracts on Bitcoin. In the context of rollups, it could potentially give us a trust-minimized way to bridge BTC, and also optimistically verify rollups' state updates. 

Read the BitVM paper here.

You can also read:

- A introductory explainer on BitVM
- Our blog on why BitVM matters to rollups
- See our full list of BitVM resources here.

### The teams building rollups on Bitcoin

There are a number of teams building ZK-rollups on top of Bitcoin. These teams are taking a number of different design approaches to brinigng this technology to Bitcoin, and are moving at an extremely fast pace.

- Chainway: A general purpose ZK-rollup leveraging the EVM and a BitVM bridge
- Taproot Wizards: A general purpose sovereign ZK-rollup in collaboration with Kasar Labs
- Build on Bitcoin (BOB): A general purpose, zkVM rollup exploring BitVM sequencer designs and bridges
- Alpen Labs: A general purpose ZK-rollup exploring designs that leverage an "OP_STARK_VERIFY" opcode
- See the full list of teams here.

### Opcodes

Teams are optimistic that BitVM can give us a trust-minimized way to develop rollups on Bitcoin without a soft fork. But, adding new opcodes might make building rollups on Bitcoin easier, and give us even more trust-minimized, and potentially trustless, bridging.

The first opcode teams in this space are pushing for is OP_CHECKTEMPLATEVERIFY (CTV). You can read more about CTV here.

You can also check out:

- Covenant-enabling Bitcoin Features
- OP_STARK_VERIFY

### Applications

Rollups are positioned to scale Bitcoin and provide new functionalities to BTC users. These new use cases range from better privacy for sending and receiving BTC, new ways to use BTC as collateral for stablecoin loans, swapping BTC for a number of new asset types, and more. Note that some of these examples are not live on Bitcoin today, but would certainly be enabled when the Bitcoin rollups (that are entioned above) go live into production.

- Private swaps and sends with Railway
- Using BTC as collateral for stablecoin loans via
- Swapping BTC for stablecoins via Uniswap
- Read more about new usecases rollups provide here.

### Check out more resources

It's an exciting time to be a Bitcoiner! We do our best to stay up to date on all of the research and development happening in this space, and document those resources here. 

If you want to contribute resources to the website, check out our contribute page.
