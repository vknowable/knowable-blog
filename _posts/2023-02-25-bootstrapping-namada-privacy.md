---
layout: post
title: 'Bootstrapping Namada Privacy with Rewards'
---

\
<img src="https://knowable.vc/assets/gavin-avatar.jpg" width="75" height="75"><br>By [Gavin Birch](https://twitter.com/Ether_Gavin), updated Feb 25, 2023 <br><br> _Can Web3 reach adoption without privacy? Namada’s poised to launch in March 2023. Shielded assets will be rewarded with NAM–here’s why and what to pay attention to. We’ll be running a local bare metal validator (and you can too! [DM](https://twitter.com/vKnowable), [email](mailto:hi@knowable.vc)). [Stay in the Know](https://forms.gle/HRAQBSo85HGzKVSg9) for alerts._

A blockchain gives you a ledger and the guarantee that if you use it, your numbers can’t be manipulated unexpectedly. Staking ensures that integrity, so everyone using the ledger benefits from more staking. The ledger accounts aren’t named, but since all transactions are transparent, it’s only a matter of time before your ledger accounts are tied to your identity. Who will use a blockchain, knowing that all of their accounts and account transactions are exposed for the entire world to see? We likely can’t have meaningful blockchain adoption without preserving the privacy of accounts (and still ensuring transaction accountability).

[image]


## Data Security, the Missing Piece

We have a few privacy options, like Zcash, but we’d have to trade our assets into and use ZEC coins to benefit from Zcash. Nearly all other chains are fully transparent–how can these users secure their privacy? Namada proposes to retrofit privacy.

When Namada launches (end of Q1), you’ll be able to deposit your assets (from Ethereum or Cosmos ecosystems) into Namada’s custody. They’ll be combined with all of the other assets that have been deposited, and claims on those assets will be kept secret. This is known as a shielded pool. “Shielded” because claims on the pool of assets are kept secret–ZK (zero-knowledge) proofs are used to make verifiably-valid claims without revealing sensitive account data. Bengt Lofgren published [Understanding the MASP/CC](https://blog.namada.net/understanding-the-masp-and-cc-circuits/) on Jan 31, 2023.

Since it’s a multi-asset shielded pool, all deposited asset types (including NFTs) will be custodied by the Namada validator set as a single pool of assets, (rather than separate shielded pools, like Tornado Cash and Aztec’s zk money,) and the users will control their share of the assets in secret.


## The Privacy Game

However, observers can still make inferences about who is making specific claims, unless there’s a crowd to blend into. So there’s a bootstrapping problem: the earliest depositors have little to no privacy, so why join the shielded pool?

[image]



### Who goes first?

If I'm the first depositor, it’s easy to infer that any claim on the pool of assets is mine. A second depositor doesn’t help much, but each additional depositor makes it harder and harder to infer who is making claims on the asset pool to withdraw or transact with assets held by Namada. 

The more deposits there are from unique addresses, and the larger the deposits are, the stronger the privacy enjoyed by the smaller depositors (because it gets harder to infer who is making withdrawal claims). So if we’re to make Namada a thing worth using (for secure interchain asset privacy), we’ll need to incentivize enough reasonably-sized deposits to get sufficient-enough strength of privacy guarantees.

We need to attract many deposits, but we can’t reward participants based on the number of deposits, because then we’d incentivize each account owner to repeatedly deposit/withdraw. We also can’t solve this by rewarding unique deposits, since we’d reward participants for dividing up their assets into multiple accounts to maximize their reward rate. Thus, **deposit numbers** can’t be accounted for in a way that we can reward them for benefiting our privacy set.


### Privacy rewards get things rolling

We can reward depositors based on deposit sizes and deposit time. Minting NAM to reward deposits (based on size) is a cost to the Namada stakeholders–a bet that we’ll attract enough unique depositors of sufficient deposit sizes that in sum will generate enough activity and uncertainty that Namada will be crowded enough for privacy-seekers to blend in.

[image]


Yield seekers will likely farm (exploit) Namada’s shielded pool rewards, but in exchange we will use their deposits to bootstrap privacy guarantees. It’s a good trade! Yield farmers assume the risks of being early depositors (a novel chain, a novel bridge ☠️) in exchange for optimal yields (earning and selling NAM for profits that exceed other yield opportunities). When deposit metrics are sufficient enough to attract privacy-seeking depositors, deposit amounts should increase, and yield rates should decrease. We can then expect yield farmers to exit, while privacy-seeking deposits should organically replace the yield-seeking deposits (if all goes well).

Namada will introduce a new incentive game to secure its asset data. Bengt Lofgren explains the subsidy design rationale in his Jan 17, 2023 article, [Privacy as a Public Good](https://blog.namada.net/privacy-as-a-public-good/).


## Privacy Incentives

When you deposit assets with Namada, they’ll never be locked. The governance system will be used to designate which assets should be rewarded and the target deposit amount. NAM rewards paid for depositing each designated asset will be a variable rate. It’s an interesting opportunity to acquire NAM without using an exchange or staking, which could ease the onboarding of new participants (who will need NAM to pay for Namada transactions).

Up to 10% of NAM inflation will be allocated to privacy yields. If you’re looking to optimize privacy rewards, you’ll want to ask these questions:



* Is the asset type incentivized?
* How much of this asset has been deposited, relative to the target deposit size?

We should expect that as each asset approaches its target deposit size, the rewards rate will decrease in favour of incentivizing asset types that are much further away from reaching their target. Thus, the privacy rewards game encourages yield-seekers to deposit large amounts as early as possible in order to maximize their yield, and neither Namada nor its bridge are battle-tested. [Stay in the Know](https://forms.gle/HRAQBSo85HGzKVSg9) for alerts.



[image]



### Participation Challenges

Our incentive mechanism is a hopeful one, because eg. [a single large ETH depositor](https://etherscan.io/tx/0x6acdc4e6b6fd224d004c76bb497648550f92e3e8b5f203023d43f0fa44e71cec) could dominate the yield for ETH deposits (driving down the reward rate for other potential yield-seeking depositors). How should we reason about privacy in Namada–is it a mistake to track “total value locked” (TVL) as an approximation for privacy-strength? Will we need to attract more unique deposits if depositing becomes unattractive to both yield-seekers and privacy-seekers? These may be non-problems, assuming that one or two large deposits with a few dozen small deposits provide better privacy guarantees than Monero does.

While privacy incentives are very different from AMM (automated market maker) liquidity incentives, which involve “impermanent losses,” **all depositors face the very real risks involved in cross-chain bridging assets from Ethereum to Namada.** 


### Ethereum Bridge Risks

There’s a well-established track record of record losses from bridge exploits: [Wormhole $250m](https://wormholecrypto.medium.com/wormhole-incident-report-02-02-22-ad9b8f21eec6) Feb 2022; [Ronin $540m](https://www.coindesk.com/business/2022/06/28/axie-infinity-restarts-ronin-bridge-months-after-625m-exploit/) March 2022; [Harmony $100m](https://techcrunch.com/2022/06/24/harmony-blockchain-crypto-hack/) June 2022; [Nomad $186m](https://www.coinbase.com/blog/nomad-bridge-incident-analysis) Aug 2022; and [a variety of others](https://www.coinbase.com/blog/what-are-bridges-illicit-use-of-bridges). In the short to medium term, Namada will first need to prove that its bridge and protocol will be able to safeguard all Ethereum deposits in the wild. Racing to deposit large amounts of assets is dangerous for an unproven bridge, so **depositors beware:** do not deposit anything that you are not prepared to lose unless you understand what the risks are. It will be important to understand the safety measures that will be implemented to mitigate the size and likelihood of loss. Jacob Turner published [The Namada Ethereum Bridge](https://blog.namada.net/the-namada-ethereum-bridge/) on Feb 15, 2023, and the  [https://blog.namada.net/the-namada-ethereum-bridge/](https://blog.namada.net/the-namada-ethereum-bridge/) and the [Ethereum bridge specifications are published here](https://specs.namada.net/interoperability/ethereum-bridge.html).

[image]


### Regulatory Risks

If Namada proves to be a reliable place to deposit and withdraw Ethereum assets, we imagine that the next challenge will be a regulatory one. What distinguishes Namada from Tornado Cash? If Namada proves to be truly open, secure, private, and censorship resistant, why wouldn’t eg. the North Korean hacker group, Lazerus, use Namada to obfuscate ill-gotten funds? They reportedly used Tornado Cash to make the funds stolen from the Harmony bridge exploit less traceable, which resulted in OFAC sanctions on Tornado Cash from the US Treasury [links]. Circle froze the USDC that was deposited in Tornado cash contracts. What happens to the funds of Namada depositors if they’re mingled with stolen funds controlled by US-sanctioned entities? We looking forward to exploring how digital asset privacy guarantees can coexist with different legal and executive jurisdictions.


[image]



## Looking Forward

Personally, I think it will be important for depositors to have sufficient notice and time to withdraw their assets before a smart contract upgrade. I’d also like to see a dashboard for deposit metrics that are useful enough to make inferences about privacy strength, as well as rewards rates for different types of assets. Could we have an emergency freeze option to halt stolen funds in Namada (without risking the confidence of other users)?

Namada’s an exciting piece of the adoption puzzle, and an exciting glimpse of what’s to come with Anoma. With interoperability expertise and lessons learned from bridge hacks, we expect Heliax team to take great care to mitigate damage of a bridge exploit. As Namada’s bridge earns a reputation for being battle-tested, we look forward to exploring how Namada’s privacy features can grow to benefit a wider set of users, together with other privacy-preserving ecosystems, [thanks to bridge privacy innovations](https://blog.namada.net/shaping-multichain-privacy/).

Namada is aiming to launch in March 2023. Join us! We’ll be running a local bare metal validator (and you can too!) → hi@knowable.vc

The Namada community is in [Discord](https://discord.com/invite/namada), on [Reddit](https://www.reddit.com/r/Namada/), and [Twitter](https://twitter.com/namada). Participate by [running a Namada validator](https://namada.net/testnets) or by [nominating someone](https://forum.namada.net/c/rpgf/5) for public goods funding. Follow along and [Stay in the Know](https://forms.gle/HRAQBSo85HGzKVSg9) for alerts from Knowable, and Heliax’s [Namada newsletter](https://eepurl.com/hQTYon).
