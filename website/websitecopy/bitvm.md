## BitVM

BitVM is an offchain virtual machine that would give Bitcoin a lot of promising new features. In the context of rollups and sidechains, it could enable more trust-minimized bridging. This would enable Layer 2 protocols to reduce users' trust assumptions when they move BTC onto their L2.

Teams are also exploring how BitVM can be used to optimistically verify state updates provided by rollups.

And, there have even been discussions on BitVM [bringing a ZK-Verifier to Bitcoin](https://x.com/stskeeps/status/1722339542630306284?s=20).

The best part? This can all be enabled without a softfork (although a softfork might [help](https://twitter.com/robin_linus/status/1737097335719575831) 😄). Let's dive into the resources.

Want to contribute to improving this page? Head to our [GitHub repo](https://github.com/januszgrze/bitcoinrollups/blob/main/website/websitecopy/bitvm.md).

### What is BitVM

The core idea of BitVM is to take computation off-chain with an on-chain fraud proving mechanism. Bitcoin Script is very simple, so to run more advanced programs, you need to run them off-chain and somehow prove that the computation was done correctly. To verify computation, BitVM uses a similar scheme to optimistic rollups - a prover (who executes the computation off-chain) makes a claim about the output of the computation. If this claim is disputed, the verifier can challenge it on the Bitcoin blockchain. The Bitcoin blockchain would only be used for disputes in this scheme.

Tl;dr? It allows you to develop new applications on Bitcoin that may provide more utility to BTC the asset.

### Why does it matter to rollups?

BitVM allows us to create a fraud-proof mechanism that is conceptually similar to TrueBit’s or Arbitrum’s design - likely enabling optimistic rollups on Bitcoin!

There are, however, a few subtle but important differences. As of writing, the committee of Provers and Verifiers, i.e., participants who can trigger a dispute, must be pre-defined for each BitVM setup. This means that the trust assumption of a BitVM setup is 1-of-N known participants, rather than “at least any one honest and online network participant”. Another difference is that due to lack of smart contract functionality on Bitcoin, we cannot make use of succinct non-interactive proving techniques, as opposed to Ethereum.

As a result, the challenge-and-response protocol must be interactive. This means that the exchanges between accused Provers, and challenging Verifiers, must be on-chain Bitcoin transactions over a prolonged period. This takes place until either one of them is slashed due to timeout or equivocation. But, the Verifier can make use of a similar bisection protocol as other well-known fraud-proof mechanisms. It can essentially perform an efficient binary search over the pre-committed program (specifically, the program broken down into the underlying logical gates) to determine which parts should be challenged. This optimization already allows to cut down on-chain costs to approximately 30-40 transactions per challenge, in the worst case. 

Another potential limitation of BitVM is the size of the pre-committed off-chain programs, in terms of logical gates. To the best of our knowledge, the current implementation will allow 4 billion gates - which in theory should be enough for most anticipated use cases. More complex programs, e.g. full state validation of an EVM rollup, may require a pre-processing step to reduce size by compressing them into a succinct zero-knowledge proof.

Tl;dr? BitVM can likely give us optimistic rollups with different trust assumptions as to those on, let’s say, Ethereum.

### Can it give us trust-minimized bridging?

First, let’s review the current state of Bitcoin bridges. When a user bridges BTC to a Layer 2, or another blockchain, they have to deposit that BTC into a bridge contract. On Bitcoin, a bridge will use one of two designs:

Statistical security: a multi-sig (or threshold signature) controlled by N parties. As long as the majority M of N is honest, the bridge is secure. Notable examples include rBTCs (multisig) or tBTC (larger set via threshold signatures). 

Economic security: bridge operators are collateralized on the target chain in assets other than Bitcoin. If an operator steals BTC or fails to perform a peg-out, their collateral is liquidated and used to reimburse the user. While this design is very secure (users always get BTC back or are repaid in full in other assets), the associated capital costs for operators limit scalability. Collateral quality is another concern, as other assets may fluctuate in price compared to BTC or exhibit lesser security properties. Variations of this design are used by Interlay, Cardano (anetaBTC), TeleBTC (on Polygon), Harmony and Stack’s sBTC.

Both designs can be combined to improve security and balance between large signer committees and full/partial collateralization. See here for more details on Bitcoin bridges.

#### BitVM & Bitcoin Bridges 

BitVM can offer a major improvement over existing bridges in terms of security and capital efficiency. Specifically, we may be able to use BitVM to implement a light client for the target chain / Layer 2 that would allow us to verify correct processing of peg-in and pre-out transactions (on the other chain that is assumed to have smart contracts). 

The idea is that deposits made into BitVM are controlled by a committee of N Provers and Verifiers, and as long as one of these N participants is honest, the deposits remain secure. Whenever a user requests a peg-out the (current) Prover verifies the state of the L2 off-chain and, if everything is correct, sends BTC to the user. Verifiers observe this process and verify correctness. If the Prover misbehaves, i.e., remains unresponsive or sends BTC to a wrong BTC address, they trigger an on-chain challenge and prevent the Prover from accessing the BTC deposits. This, of course, requires the Prover verify the state of the L2 off-chain

It makes use of so-called cross-chain light clients: programs that can programmatically verify that certain state changes have happened on another blockchain. The sidechain, assumed to have smart contract functionality, implements a Bitcoin light client that can verify Bitcoin transactions, and vice-versa. Bitcoin’s Script language lacks expressiveness to encode light clients as on-chain programs. Instead, the sidechain light client is implemented via BitVM, a novel paradigm on Bitcoin based on optimistic program execution: participants pre-commit to the program via a set of pre-signed Bitcoin transactions, the execution happens off-chain, and if participants disagree a challenge-response protocol is performed to determine the correct outcome. 

The billion dollar question is how to scale the set of Verifiers and ensure a good user experience to users. Given this, BitVM can finally make centralized multi-sig bridges redundant!

---

Want to dive deeper? Check out the resources on BitVM below.

### BitVM Papers

- [BitVM: Compute anything on Bitcoin](https://bitvm.org/bitvm.pdf)

### Written resources on BitVM

- [Deep dive into BitVM Computing Paradigm - Ichiro Kuwahara](https://medium.com/crypto-garage/deep-dive-into-bitvm-computing-paradigm-to-express-turing-complete-bitcoin-contracts-1c6cb05edfca).
- [The BitVM Primer - Tyler Whittle](https://mirror.xyz/twhittle.eth/zXzocAl-wWiMSBAzhKnd6w0AJsftqgPTUfnh115fVPM)
- [BitVM: A Breakthrough in Computing on the Bitcoin Layer - Trust Machines](https://trustmachines.co/blog/bitvm-a-breakthrough-in-computing-on-the-bitcoin-layer/)
- [The Big Deal with BitVM - Bitcoin Magazine](https://bitcoinmagazine.com/technical/the-big-deal-with-bitvm-arbitrary-computation-now-possible-on-bitcoin-without-a-fork)
- [BitVM FAQs](https://github.com/PraiseTheMithra/BitVm-FAQ)

### Video and audio resources on BitVM

- [BitVM Uses a 'Compilation of a Couple Tricks' to Overcome Limitations of Bitcoin's Script: Robin Linus](https://finance.yahoo.com/video/bitvm-uses-compilation-couple-tricks-141723622.html)
- [What is BitVM? with Robin Linus and Super Testnet (SLP520) - Stephan Livera Podcast](https://www.youtube.com/watch?v=XxqQU6j6jI8)
- [Zero Sync - Bitcoin Amsterdam](https://www.youtube.com/watch?v=rubs5SrkGsM)
- [BitVM two way peg design - Ordinals Show](https://twitter.com/i/spaces/1YqKDgYMqlvxV?s=20)
- [BitVM - A Tiny Web3 Podcast](https://twitter.com/cartesiproject/status/1729893087143759950)
- [Everything on Bitcoin with Robin Linus & Super Testnet - Bitcoin Audible](https://pod.link/1359544516/episode/413027f0bdb982a8593d50f4466930f5)
- [BitVM Takeover with Super Testnet - Layer Two Labs](https://x.com/LayerTwoLabs/status/1712855344764834076?s=20)
- [BitVM, Convenants and Scaling - Bitcoin News](https://x.com/BitcoinNewsCom/status/1715392573555040265?s=20)
- [BitVM and UTXO Dealership](https://twitter.com/i/spaces/1OyJAWapbAOKb)
- [BitVM Discussion - Ordinals Show](https://x.com/TO/status/1716265121373172075?s=20)

### Related Github Repos

- [BitVM Toy Implementation](https://github.com/BitVM/BitVM)
- [Things BitVM Needs](https://github.com/supertestnet/things-bitvm-needs)
- [Awesome BitVM - Rsync25, an amazing resource on technical resources regarding BitVM](https://github.com/Rsync25/awesome-bitvm)

### Tweet threads on BitVM

- [Decentralized two way peg on BitVM - Alex Emidio](https://twitter.com/AlexEmidio7/status/1735276812198986210)
- [BitVM Explainer - Bob Bodily](https://twitter.com/BobBodily/status/1712305639366811997)
- [BitVM Explainer, BitVM GPT - Dylan LeClair](https://x.com/DylanLeClair_/status/1722995043932270854?s=20)

### Communities

- [BitVM Telegram](https://x.com/robin_linus/status/1711757377983086894?s=20)

### Our favorite tweets mentioning Rollups and BitVM

- [Chainway on their rollup using BitVM](https://twitter.com/chainway_xyz/status/1735361028160893235)
- [Chainway, What is BitVM?](https://twitter.com/chainway_xyz/status/1737542123434467737)
