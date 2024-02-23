## More materials on Bitcoin rollups R&D

The list of materials specifically related to Bitcoin rollups is growing, and we're documenting them here. Here you'll find the teams building zk-rollups on Bitcoin. And, we list research papers, technical blog posts, forum posts, and more on how rollups can improve Bitcoin. We do our best to keep this page current. If you think we're missing a quality piece, please let us know.

### Research reports related to Rollups on Bitcoin

- [Validty rollups on Bitcoin](https://bitcoinrollups.org/) - Original research report outlining how it might be possibly to build validity rollups on Bitcoin.
- [OptiMine](https://medium.com/@build_on_bob/optimine-extending-bitcoins-pow-strength-to-diverse-ecosystems-d56f1170fdc8) - A white paper covering optimistically sequenced merged mining for rollups and sidechains.
- [BitStake](https://lightco.in/2024/02/13/bitstake/) - A post introducing a proof-of-stake bridge based on BitVM.

### BitVM

- [BitVM: Compute Anything on Bitcoin](https://bitvm.org/bitvm.pdf) - Whitepaper on how to enable Turing complete contracts on Bitcoin.
- [Our dedicated page to BitVM resources](https://bitcoinrollups.io/bitvm) - A list of resources related to BitVM and how it supports rollups.

### Research on opcodes that support rollups

- [Covenants - Bitcoincovenants.com](https://bitcoincovenants.com/) - A website introducing what Bitoin Convenants are and the usecases they support.
- [Covenants - Bitcoin Optech](https://bitcoinops.org/en/topics/covenants/) - A page highlighting where Covenants have been mentioned in Bitcoin Optech. 
- [Covenant-enabling Bitcoin Features](https://gist.github.com/RobinLinus/c96fb7c81430ec6dc92f048687bd3068) - A page mentioning the types of uses cases that Covenants could support.
- [New Tapscript Opcode for Validity Rollups](https://www.youtube.com/watch?v=Nldg_tjeX_A&t=1281s) - A conference talk highlighting what enabling a SNARK verifier into Bitcoin script would enable.
- [Brief commentary on opcodes in "Validity rollups on Bitcoin" paper](https://bitcoinrollups.org/#section-5-building-validity-rollups-on-bitcoin) - An overview on what opcodes could support building validity rollups on Bitcoin.

### Teams building zk-rollups on Bitcoin

- [ZeroSync](https://zerosync.org/) - The team building BitVM (with support from other open-source contributors) that enables trust-minimized bridging between the Bitcoin main chain and Layer 2 solutions.
- [Chainway](https://chainway.xyz) - Chainway is behind "Citrea". Citrea is a rollup that will leverage BitVM for bridging and zero-knowledge proofs to post data onto Bitcoin.
- [Build on Bitcoin (BOB)](https://gobob.xyz) - Build on Bitcoin is a team building zkVM rollups that respectively settle on Ethereum and Bitcoin. They are also exploring merge-mined, and BitVM, enabled sequencer designs.
- [Bison Labs](https://bisonlabs.io/) - Bison Labs is building a zk-rollup that supports BRC-20 trading.
- [Bnzk](https://bnzk.io/) - Bznk is looking to use zk-tech to improve BRC-20 indexing. They could potentially be building a sovereign rollup.
- [Alpen Labs](https://alpenlabs.io/) - Alpen Labs are an R&D company exploring various designs for validity rollups on Bitcoin.
- [Kasar Labs](https://www.kasar.io/) (in collaboration with [Taproot Wizards](https://taprootwizards.com/)) - Kasar Labs developed "Barknet", a sovereign rollup leveraging the Cairo VM, that uses Bitcoin for data availability.
- [Cartesi Project](https://cartesi.io/) - Cartesi Project are an optimistic rollup that uses a Linux-based VM. They are currently a part of the Ethereum space and are exploring Cartesi Rollups on Bitcoin.
- [Sovryn](https://sovryn.com/bitcoinos) - Sovryn is building BitcoinOS, which aims to be a network of interoperable rollups.
- [zkLayer](https://twitter.com/zkLayer_) - zkLayer is an upcoming project looking to build a zk-rollup on top of Bitcoin.
- [Heliosphere](https://twitter.com/HeliosphereOne) - Heliosphere is an upcoming project looking to build an optimistic rollup on top of Bitcoin.

### Teams building rollups on Bitcoin sidechains

- [Rollux](https://rollux.com/) - Rollux is an optimistic rollup that uses Syscoin for settlement and data availability.
- [RIF](https://dev.rootstock.io/rif/rollup/overview/) - RIF is an zk-rollup that uses Rootstock for settlement and data availability.

### Other notable contributors building infrastructure to support zk-rollups on Bitcoin

- [Sovereign Labs](https://www.sovereign.xyz/) - Sovereign Labs are building an SDK to make it easy to launch rollups. Chainway forked their data availability adapter to 
- [Rollkit](https://rollkit.dev) - Rollkit launched the first sovereign zk-rollup on Bitcoin on testnet.
- [Lambda Class](https://lambdaclass.com/) - Lambda Class are an R&D shop that have contributed code to Bitcoin rollups.
- [Babylon Chain](https://babylonchain.io/) - Babylon are building a Bitcoin restaking protocol that could potentially be used to secure 2nd layer protocols.

### Code repositories

- [Chainway Bitcoin DA Github repository](https://github.com/chainwayxyz/bitcoin-da)
- [ZeroSync Github repository](https://github.com/zerosync)
- [Rollkit Bitcoin DA Github repository](https://github.com/rollkit/bitcoin-da)
- [BOB Collective Github repository](https://github.com/bob-collective/bob)
- [Sovereign SDK Github repository](https://github.com/Sovereign-Labs/sovereign-sdk)
- [Rootstock RIF Rollup Github repository](https://github.com/rsksmart/rif-rollup)
- [LambdaClass, Starknet Rollup on Bitcoin](https://github.com/lambdaclass/starknet_rollup_on_bitcoin)

*Please do your own research before interacting with any of the protocols, or code, listed on this page. We are not advocating for the use of any of these technologies. This website, including the information listed on this page, is for informational purposes only. None of the content in this page should be considered financial advice*
