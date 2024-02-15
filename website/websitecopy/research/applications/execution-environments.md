## Rollups can support a variety of new execution environments on Bitcoin

Rollups on top of Bitcoin enable a whole new suite of functionality for BTC users.

But how do we build these new applications, and how are they better than those built on existing sidechains today?

### New execution environments

As mentioned in the "validity rollups on bitcoin" report, rollups would give Bitcoin developers, Bitcoin users, and BTC holders the ability to leverage alternative execution environments, such as the EVM. These new environments would exist on various rollups, not the Bitcoin network itself. However, the architecture of rollups will allow BTC and other Bitcoin assets (e.g. Ordinals) to be used in more expressive execution environments for new use cases, all with minimal trust assumptions.

Users would be able to access these new applications by bridging their BTC over to the application. They would deposit their BTC into a bridge contract and then be able to access a wrapped version of the asset on the rollup.

Turing-complete execution environments give developers more freedom to build whatever they want on top of Bitcoin. Based on findings within the [Electric Capital developer report (2023)](https://www.developerreport.com/developer-report), we can see that there has been more growth in the Ethereum developer community compared to Bitcoin’s. We can also see that full-time developer communities in two of Ethereum’s rollup ecosystems, [Arbitrum and Optimism](https://www.developerreport.com/developer-report?s=optimism-1315-solana-888-arbitrum), have grown 1300% and 700% respectively over a three-year time horizon.

Some virtual machines that have been proposed for Bitcoin rollups are:

- [The Cairo VM](https://starkware.co/tech-stack/)
- [The EVM](https://ethereum.org/developers/docs/evm)
- [The Cartesi VM](https://docs.cartesi.io/machine/intro/)

There are many teams looking to run different virtual machines because they have different specializations. Modularizing the stack enables developers to be more flexible with the programs that they write, which in turn gives users more applications they can interact with.

Reminder: even [recent breakthroughs](https://bitvm.org/bitvm.pdf) in Bitcoin scaling were partly inspired by development efforts undertaken in Ethereum. It’s important we don’t discount innovation that is happening in external ecosystems.

### Applications

There’s a wide variety of applications being developed through these virtual machines. By looking at Starknet’s [Dappland](https://www.dappland.com/category/onramps) website (built by [Argent](https://www.argent.xyz/?utm_source=dappland)), we can see projects built on the Cairo VM ranging from DeFi protocols to onchain gaming.

Cartesi’s [Rollup Lab](https://rolluplab.io/) site also shows us how developers are leveraging the Cartesi VM to build applications using a number of different programming languages that its Linux-based VM supports.

And, of course, the EVM supports a robust [ecosystem of on-chain applications](https://dappradar.com/rankings/protocol/ethereum) on the Ethereum mainchain and EVM-compatible rollups.

### Minimized trust assumptions

Some might argue, “well, we have EVM-compatible sidechains, and hardly anyone uses those.”

But, the only way users can use BTC on these sidechains is through federated bridges. As new offchain scaling solutions implement BitVM, sidechains and rollups will have bridges with minimized trust assumptions.

Is this trustless? No. But, they would take on similar trust assumptions to Arbitrum, which is the most popular scaling solution in Ethereum today.

This is arguably a better trust model than using today's sidechains, custodial scaling solutions, or custodial applications leveraged in other Layer 2 protocols.

### Sidechains versus rollups

Before we dive in here, it's worth noting that the distinction between a sidechain and a rollup is a bit hazy right now. But, we want to clarify why it might be better for teams to build rollups.

Sidechains see users take on additional trust assumptions because they're interacting with an entirely different consensus protocol in addition to the 1-N trust assumption from BitVM. They have to trust validators of that consensus protocol that their transactions will be included in blocks and that the sidechain's data is made available to node operators.

Now, these chains can be sufficiently decentralized, but this doesn't discount that users are trusting a completely separate consensus protocol.

Rollups, on the otherhand, inherit consensus and data availability from Bitcoin. The major trust assumption users take on is 1-N 
Other components of the blockchain’s architecture can be offloaded to other consensus protocols. Developers can use the Bitcoin L1 for data availability, BitVM to verify execution, and alternative consensus protocols for sequencing and proving. Or, they might opt for a centralized system for better performance. 

Modularization enables developers to make tradeoffs specific to their application. For example, what’s the best sequencer design for your rollup?

It completely depends on what you’re building.

Privacy applications might be fine with slower performance for improved censorship resistance. On-chain gaming applications might be okay with a centralized sequencer even if there is a potential for liveness failures.


But, this seems like a lot of development effort having to build sequencer protocols, decentralized prover coordination and more…

Again, it completely depends on what the rollup’s goals are.

Rollups might want to build their own decentralized sequencer and prover coordination protocol. That may see it get longer to market, for the tradeoff that it would have a dedicated design around decentralization. Or, rollups can opt-in to sharing a credibly neutral network that is shared by any number of rollups.

All of these design choices are dependent on the goals of the rollup. And through protocol modularity, developers will have more flexibility and choice around how we construct protocols and applications.

