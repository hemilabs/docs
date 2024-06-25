# PoP Mining

{% hint style="info" %}
📜 **TL;DR:**

* Participants can secure the Hemi Network to Bitcoin and earn rewards by operating the PoP Miner application.
{% endhint %}

***

## 🌐 **Overview**

* Mining within the Hemi Network involves a specialized process designed to intertwine the security of the Hemi Network with that of the Bitcoin blockchain.
* This is achieved through the operation of the PoP Miner application, which plays a pivotal role in this symbiotic security mechanism.

***

## 🛠️ **How It Works**

1. **Fetching Headers**: PoP Miner retrieves network headers from the Bitcoin Finality Governor for Bitcoin blockchain publication.
2. **Transaction Construction**: It constructs Bitcoin transactions embedding these Hemi Network headers.
3. **Proof of Publication**: The miner then submits cryptographic proofs back to the Governor, integrating these into Hemi's consensus layer and rewarding the miner.

***

## 💸 **Earning Rewards**

|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🔍 **Tracking Miner Activity**    | Visit the [Block Explorer](http://external-testnet.bvmdev.cc) and use [Setup Part 1 ](../tutorials/setup-part-1.md)to see your miner's history and activity.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ⏳ **Payout Processing Time**      | It takes about 30 minutesfrom **sending a transaction** to receiving a PoP payout.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ⚡️ **Quick Confirmation Rewards** | You'll earn PoP rewards for transactions that are quickly confirmed **(within the next 2-3 Bitcoin blocks)**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 🔄 **Static Rewards**             | Initial testnet rewards are fixed. In future testnets and on the mainnet, rewards will depend on the number of active PoP miners.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 💰 **tBTC Mining Sustainability** | <ul><li><strong>Rate: Engaging in PoP mining by sending one transaction every 5 minutes consumes approximately 0.001 tBTC per day.</strong></li></ul><ul><li><strong>Duration</strong>: With this rate, 1 tBTC can sustain mining activities for about 1000 days<em>Please note, this estimate is based on current conditions and may vary with changes in Bitcoin's mempool activity and fee market dynamics.</em></li></ul><ul><li><strong>Management Advice</strong>: We recommend developers periodically review their tBTC balance to ensure continuous mining operations without interruption. Strategies for tBTC account replenishment will be provided, ensuring miners can maintain active participation in the network over the long term. </li></ul> |
| 🔗 **Additional Links**           | [**github.com/hemilabs/heminetwork**](https://github.com/hemilabs/heminetwork)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

{% hint style="info" %}
## 📝 **Tips**

* 🚫 **Single Key, Single Miner**: Using the same key for multiple PoP miner instances can lead to conflicts, as they may attempt to use the same Bitcoin UTXO simultaneously, causing operational issues.
* 🗂 Purpose of `popm-address.json`: This file serves as a secure storage for your generated keys, meant for reference. The actual Bitcoin key used by the PoP Miner is specified through an environment variable at the program's start.
* 🔑 **Unified Private Key**: Your single private key generates both a Bitcoin address and a Hemi address. The Hemi network automatically processes your public key from Bitcoin transactions, converting it into a Hemi address to receive payouts.
* ⚡ **Bitcoin Testnet Dynamics**: The Bitcoin testnet can undergo periods of rapid block generation due to block difficulty adjustments after inactive periods. This unusual pace can temporarily impact the timing and processing of payouts.
{% endhint %}



***

## 🕵️ **Behind the Scenes**

* A Bitcoin Secure Sequencer (BSS) generates and broadcasts a new block.
* BSS nodes send the block header to Bitcoin Finality Governor (BFG) nodes.
* BFG nodes direct the header to PoP Miners.
* Miners create and send back signed Bitcoin transactions containing the header.
* BFG nodes push these transactions into the Bitcoin network.
* Once included in a Bitcoin block, BFG nodes generate PoP Transactions with proofs of Bitcoin inclusion.
* These transactions and Bitcoin headers are incorporated into a new Hemi block by a BSS node, updating the EVM with the latest Bitcoin state.
* Rewards are calculated and distributed to PoP Miners post-mining.
