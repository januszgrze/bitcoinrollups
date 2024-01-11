### Rollups can enable improved privacy

One of the benefits of implementing rollups on Bitcoin is improved privacy for BTC users. The section below from the "Validity rollups on Bitcoin" introduces this possibility:

"In the years since Satoshi Nakamoto first contemplated how zk proofs could be used to improve bitcoin privacy, cryptographers have invented new protocols that greatly improve the quality and usability of private cryptocurrency transactions. Validity rollups make it possible to implement these new privacy protocols on bitcoin while inheriting the full ownership security of BTC owned on L1. This would provide bitcoin users with state-of-the-art privacy without having to give up self-custody of their BTC." _See [sections 3.2](https://github.com/john-light/validity-rollups/blob/main/validity_rollups_on_bitcoin.md#-section-32-new-privacy-protections-) and [Appendix B](https://github.com/john-light/validity-rollups/blob/main/validity_rollups_on_bitcoin.md#appendix-b-comparing-alternative-cryptocurrency-privacy-techniques) in the paper that dive deeper._

Remember, Bitcoin is natively transaprent, and if someone knows your BTC address, they can track your address and learn about all of your past on-chain transactions. Thus, it can be difficult to maintain high levels of [privacy](https://bitcoiner.guide/privacy/) when using Bitcoin. 

But, we could use techniques known as zero-knowledge proofs, on the Layer 2 level, to provide better privacy guarantees for users. As stated on the Zcash website, zero-knowledge proofs a cryptographic techniques that prove something is true without revealing the facts that make it true. This means you can prove that a transaction took place between two users, but not reveal who the users are, their BTC holdings and past activity, and the amount of value transferred in the transaction. This is really good for privacy!

There a few different ways that rollups could help improve privacy protections for BTC users. You could, of course, build a Zcash-style rollup that leverages shielded pools similar to those implented in Zcash (and other Layer 1 blockchains like Namada and Penumbra). This is similar to the design [Aztec is implementing in their privacy-preserving rollup](https://aztec.network/).

Or, you could implment a privacy-preserving smart contract like Railgun on a general purpose rollup. This would implement a shielded pool as a smart contract on the rollup. If a user deposits BTC (or another Bitcoin asset) into the smart contract, they would receive a tokenized equivalent of that asset that they can transact with privately.

In either of these designs, users could bridge their BTC to the rollup via a trustless bridge, maintain self-custody of the BTC, and would see their transactions within the rollup, or smart contract, be completely encrypted. No information about the users' addresses would be revelead.

Wallet applications could then build user interfaces that enable users to transact their encrypted BTC privately while maintaining self custody. Below is a demo that shows an encrytpted wBTC transaction using the Railway mobile wallet. This transaction was done within the Railgun smart contract on Arbitrum, a general purpose, EVM rollup on Ethereum.

[demo]

Both users maintain self-custody of their assets, experience lower fees than they would on the L1, and the rollup inherits the security of the Ethereum L1. And, no on-chain transaction was required to onboard on of the users to the rollup!

Rollups could help scale BTC payments and provide better privacy. Below, you can learn more about the privacy-preserving applications that can be enabled by rollups on Bitcoin:

- Resource link
- Resource link
- Resource link
