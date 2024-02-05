Rollups are primarily viewed as scaling solutions in the Ethereum space. But in Bitcoin, rollups could also enable a whole suite of new functionality for BTC the asset and Bitcoin users.

This is because Bitcoin is limited in what it can do on the Layer 1. By enabling rollups, we can explore new execution environments and smart contract languages, and build applications that pay fees to secure the Bitcoin network. Rollups, coupled with trust-minimized bridging protocols, enable new use cases and provide further utility for BTC the asset without compromising on trust or decentralization. Teams are currently researching how [BitVM](https://bitcoinrollups.io/bitvm) could enable rollups with trust-minimized bridges.

You've read a lot about rollup infrastucture on our site. Let's dive into some real use cases Bitcoin rollups can provide!

### New smart contract languages

New smart contracting languages would give developers more freedom to create a new suite of Bitcoin applications. Today, you can't build with new smart contracting languages, like Cairo, on Bitcoin natively. To use these more expressive languages, developers have to build applications on alternative conesnsus protocols connected to Bitcoin via a two-way peg bridge. To use the applications, users would have to lock their BTC into a bridge and effectively use an BTC-backed IOU within the application.

The main difference with rollups, compared to sidechains, is that users can trustlessly maintain self-custody of BTC the asset. Additionally, Bitcoin nodes would verify a proof of correct computation which would be little to no burden on them.

This means rollups could enable execution environments that allow developers to use more expressive smart contract languages offchain, while ensuring that users who interact with these new applications maintain full custody of their BTC (and other Bitcoin assets).

You can read more about new smart contracting languages in the ["Validity Rollups on Bitcoin" paper](https://bitcoinrollups.org/#section-3-enabling-new-functionality).

### Stronger privacy guarantees

Rollups can also provide stronger privacy guarantees to users, by leveraging  techniques known as zero-knowledge proofs, on the Layer 2 level. As [stated on the Zcash website](https://z.cash/learn/what-are-zero-knowledge-proofs/), zero-knowledge proofs are cryptographic techniques that prove a statement is true without revealing the statement itself. This means you can prove that a transaction took place between two users, but not reveal who the users are, their BTC holdings and past activity, and the amount of value transferred in the transaction.

You could have a rollup implement a Zcash-style execution environment offchain that provides BTC users better privacy and scalability, or you could implement a privacy-preserving smart contract on a general purpose rollup. Wallet developers could use either of these technologies to build payments applications that protect user privacy.

Read more about rollup-privacy, and see demos of privacy-preserving rollup applications, in our guide here.

### Trustlessly enabling BTC-backed stablecoins

Users would also be able to trustlessly use their BTC as collateral for stablecoin loans on rollups. Today, you can take out stablecoin loans, using Bitcoin as collateral, on Sovryn. Sovryn is an application built on the Rootstock sidechain, and they recently [wrote a blog](https://sovryn.com/all-things-sovryn/reflecting-on-our-journey-beyond-sidechains) about why they’re looking to move beyond sidechains due to sidechains’ limitations.

Because of these limitations, they recently announced their intention to build [BitcoinOS](https://sovryn.com/bitcoinos), a framework that enables developers to deploy rollups on top of Bitcoin. Listen to Sovryn's Eden Yago speak about rollups, and why they're good for applications like Sovryn, [here](https://www.youtube.com/watch?v=yTIJWCL1o40).

### Decentralized finance applications

Developers could build more expressive financial applications on rollups. Because rollups could enable new execution environments and permissive smart contracting languages, we could build financial applications such as UniSwap, Maker, and more on Bitcoin. We could also create rollup execution environments responsible for BRC-20 trading, which would significantly decrease the fees needed to use these applications. 

We'll be building out a guide on these applications soon.

### And more!

There's a lot more interesting use cases that rollups can support. People have talked about rollups supporting lightning, streamlining Ordinals mints and other interesting applications. 

We'll continue to build out this page to showcase the possibilities that rollups on Bitcoin can provide! You can also [contribute](https://www.bitcoinrollups.io/contribute) by adding resources to this page.
