## Rollups can support a variety of new execution environments on Bitcoin

Rollups on top of Bitcoin would enable a whole new suite of functionality for BTC users.

But how do we build these new applications, and how are they better than those built on existing sidechains today?

### New execution environments

As mentioned in the "validity rollups on bitcoin" report, rollups would give Bitcoin developers, Bitcoin users, and BTC holders the ability to leverage alternative execution environments, such as the EVM. These new environments would exist on the rollups, not the Bitcoin network itself. However, the rollups would allow users to use BTC and other Bitcoin assets (e.g. Ordinals) in these execution environments with minimal trust assumptions.

In blockchains, virtual machines generally define how transactions are executed. If the virtual machine enables smart contracts, then developers can use these environments to create applications like on-chain gaming, decentralized finance, and improved privacy protocols.

Expressive [execution environments](https://celestia.org/glossary/execution-environment/) give developers more freedom to "build whatever" on top of Bitcoin. Based on findings within the [Electric Capital developer report (2023)](https://www.developerreport.com/developer-report), we can see that there has been more growth in the Ethereum developer community compared to Bitcoin’s. We can also see that full-time developer communities in two of Ethereum’s rollup ecosystems, [Arbitrum and Optimism](https://www.developerreport.com/developer-report?s=optimism-1315-solana-888-arbitrum), have grown 1300% and 700% respectively over a three-year time horizon.

These stats show that there is an appetite to build on protocols that enable smart contracts. It also shows that developers are building on top of rollups in the Ethereum ecosystem, as this is where the majority of user activity happens today.

As the Bitcoin ecosystem explores building rollups, a number of virtual machines have been proposed. Some of them are:

- [The Cairo VM](https://starkware.co/tech-stack/)
- [The EVM](https://ethereum.org/developers/docs/evm)
- [The Cartesi/Linux VM](https://docs.cartesi.io/machine/intro/)

There are many teams looking to run different virtual machines because they have different specializations. For example, the EVM is a more general virtual machine that has been mainly used to create on-chain financial applications. And the Cartesi VM, which is Linux-based, might be a better option for developers looking to build on-chain games. Additionally, adopting a VM also adopts the developer tooling from its ecosystem: frontend libraries, SDKs, educational materials, open-source code, etc. Bitcoin has a unique opportunity to not enshrine any specific virtual machine and allow developers to choose the one that is best suited for their use case.

They might also opt for a virtual machine that supports programming languages they're familiar with. For a full list of programming languages developers could use in rollups, see this [list](https://bitcoinrollups.org/#section-3-enabling-new-functionality).

### Applications

A wide variety of applications are being developed through these virtual machines. By looking at Starknet’s [Dappland](https://www.dappland.com/category/onramps) website (built by [Argent](https://www.argent.xyz/?utm_source=dappland)), we can see projects built on the Cairo VM ranging from DeFi protocols to onchain gaming.

Cartesi’s [Rollup Lab](https://rolluplab.io/) site also shows us how developers are leveraging the Cartesi VM to build applications using a number of different programming languages that its Linux-based VM supports.

And, of course, the EVM supports a robust [ecosystem of on-chain applications](https://dappradar.com/rankings/protocol/ethereum) on the Ethereum mainchain and EVM-compatible rollups.

These VMs provide developers with more flexible programming languages, and the end result is more applications and utility for BTC. In the height of the 2021-2022 frenzy, [you can see](https://www.theblock.co/data/on-chain-metrics/comparison-bitcoin-ethereum/transaction-fees-daily) that the Ethereum network had a higher fee revenue than Bitcoin. This could be down to the fact that Ethereum enabled developers to build more applications, some found product market fit, and users paid fees to interact with these applications.

To ensure that Bitcoin has a healthy fee environment to replace the block subsidy, it might be worthwhile to have developers create new waves of applications. If some of these applications find product market fit, users will use them and then pay more fees to Bitcoin miners as a result.

Rollups are a great candidate for providing more developer-friendly environments.

### Sidechains versus rollups

Some might argue, “well, we have EVM-compatible sidechains, and hardly anyone uses those.”

Currently, the only way users can use BTC on these sidechains is through federated bridges. As these projects implement more trust-minimized bridging, users will be able to take on less trust assumptions when interacting with these protocols.

It's worth noting that the distinction between a sidechain and a rollup is a bit hazy right now. Candidly, current sidechains and proposed rollup implementations cannot enable unilateral exit, so neither can be considered trustless.

Still, implementing new bridging technologies will see users take on less trust assumptions. And by modularizing Bitcoin, projects can design tradeoffs specific to their application. This enables a world where developers can design corresponding infrastructure to meet their applications' needs.

For example, privacy applications would arguable need more decentralized infrasturcture for better censorship-resistance guarantees, whereas on-chain gaming applications might be okay with centralized infrastructure for improved performance.

Developing these environments, with the current resources we have available to use, still has its advantages related to developer flexibility. And in the long term, the systems that are developed can present a stronger argument for the addition of [new opcodes](https://bitcoinrollups.org/#section-5-building-validity-rollups-on-bitcoin) that would enable true validity rollups. These rollups will see users not forgo self-custody of their BTC in order to interact with second-layer protocols.

This would enable a truestless, self-custodial scaling option that could also enable a better developer experience.

### To Finish

Rollups are no silver bullet, but they do enable more flexible developer environments. This could potentially create a wider range of applications on Bitcoin and give users more opportunities to spend BTC and pay fees to miners securing the network.

As teams build more scaling protocols in 2024, we should closely follow which onboard the most developers. We should also follow how new applications on these protocols pay fees directly to Bitcoin miners and strengthen the long-term security of the network.
