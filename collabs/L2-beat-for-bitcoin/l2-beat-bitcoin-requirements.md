We'll use this page to outline the [L2 beat website](https://l2beat.com/scaling/summary) (and other relevant resources) and determine what needs to be implemented into a version zero of a "Bitcoin L2" education site.

## Initial main requirements

- Value locked - breaks down total TVL and its source. Sources are L1 native tokens bridged to l2, other layer 1 tokens bridged over, and tokens native to L2
- Risk analysis - this would be different for Bitcoin, but basically this outlines all of the centralization risks in rollups. In Bitcoin we could figure out some different risk criteria for rollups versus sidechains. Especially when rollups go into prod
- Activity - shows how much each chain is being used

## Other requirements

- We need to differentiate between the different scaling techs, the stacks they use, and the stage of development they're in
- We need to outline the stage of development each technology is in
- Bitcoin scaling tech as a whole is a bit different than Ethereum's approach, so we'd need to outline what each technology is, what its goal is, and how it works towards that. EL15 versions.
- An FAQ section would be helpful. We have something like this in [bitcoinrollups.io](https://www.bitcoinrollups.io/) so could build on that
- This is very nuanced to Bitcoin, but we'd need a custodial versus non-custodial section
- We need a scoring criteria that weights some factors versus others. i.e. why is zkCoins type rollup better than fedimints if you have a centralized sequencer?
- Bridges section - L2beat has this as their own section, and maybe this should have its own section. THis could outline the risks of using "multi-chain bitcoin" which we know is quite useful.

## Scaling tech covered

- Rollups
- Lightning (should custodial and non-custodial be different categories?)
- RGB
- Federated Sidechains (Stacks, Rootstock, etc.)
- Ecash
- Fedimints
- Drivechain
- Add more

## Scaling project's specific page

Have information on the following for each project's specific page

- Links to
-   website, docs, source code, block explorer, social media sites
- High level overview
-   TVL, TPS, Breakdown of tokens used, stage of development, scaling tech used, purpose
- Chart showing TVL and activity
- Milestones, development stage
- Risk analysis
-   For rollups: State validation, data availability, upgradeability, sequencer failure, proposer failure
-   For others: add more
- Operator(s) (include bridge operators)
- Depositing and withdrawing funds

## Other needs

- Definitions - Something that needs to be done is building out a list of standardized definitions that we use for each section. I.e. When describing sequencer failure, can we just have a definition for centralized sequencers / no force transaction capability that we can insert into every project that has this issue.
- Add more

## Stretch goals

- Breakdown of TVL. Showing which bridges/contracts are used to escrow funds used on the L2.
- Add more
