*Currently in draft*

Sequencers are the role that build blocks in rollups. They take transactions from users who are interacting with a rollup, determine the ordering of those transactions in a rollup block, and then send the block to the executor and provers to be executed in that given ordering. 

Now, why is that important?

Sequencers have the priveleged rollup of constructing a rollup block. This means that they can order transactions in any way they like, and, censor transactions they don't like. These are the two major issues that people bring up when talking about sequencer centralization.

In today's rollup world in Ethereum land, all sequencers are centralized. This means a single node builds all the rollup blocks for a specific rollup. Implmenting this on Bitcoin could be controversial due to the community's desire to maintain decentralization (although WoS would like to have a word). This also creates liveness failures because if the sequencer goes down, progress for the rollup halts. This has happened numerous times.

But, centralized sequencers are very good for performance! Users do like the fact that the user experience of a rollup is enhanced by the fact that a centralized server can produce rollup blocks really quickly. 

So, what do you do?

There's a large design space regarding sequencer decentralization. You could distribute the sequencer role out to a small, selected network of nodes, a larger consensus protocol, devise a forced transaction inclusion scheme, or simply use the Layer 1 for sequencing. 

Let's talk about some of the tradeoffs.

### Forced inclusion schemes

Forced inclusion is when a user can submit their unconfirmed L2 transaction the L1. This is useful in a scenario where the sequencer is not producing rollup blocks, or censoring a specific transaction type. In any scenario of sequencer design, rollups ensuring that users can exit through bypassing the sequencer is a necessary design.

### Decentralization

However, forced inclusion is still something that we'd idealy want to avoid in these systems. In a world where Bitcoin has a healthy and high fee market, most users could simply be priced out of using the Bitcoin Layer 1 for forcing their transactions through. This means their funds would be effectively stuck in the rollup. In a world where their being censored, you could equate this to them (basically) losing access to their funds.

This is why most teams developing rollups agree that you need to decentralize the sequencer role. 

The first question people need to ask is what is decentralized. Remember, rollups inherit the security of the Layer 1 protocol, and if designed correctly, can leverage the Layer 1 as an escape hatch if the sequencer goes down.

So this balance of decentralization and performance is a delicate one. 

That's why a lot of people discussing sequencer decentralization opt for a consensus protocol versus a selected list of small nodes for sequencing. In a world where there are 5 sequencer nodes, and their allow listed by the rollup operator, these node providers could censor transactons based on the request of the company determining the allow list.

By offloading the sequencer role to a permissionless consensus protocol, you could have an environment where anyone with the capacity to spin up a node can produce rollup blocks. In this situation, even if the majority of nodes are censoring transactions, you could have a subset build blocks including censored transactions. This is basically how Ethereum is playing out right now.

### Design



But, in Bitcoin, the block time is ten minutes. This doesn't create an optimal user experience. 
