# Running a PoP Mining

{% hint style="info" %}
### 📜 **TL;DR:**

* Participants can secure the Hemi Network to Bitcoin and earn rewards by operating the PoP Miner application.
{% endhint %}

***

## 🌐 **Overview**

* Mining within the Hemi Network involves a specialized process designed to intertwine the security of the Hemi Network with that of the Bitcoin blockchain.
* This is achieved through the operation of the PoP Miner application, which plays a pivotal role in this symbiotic security mechanism.

***

## 🛠️ **How It Works**

1. **Fetching Headers**: The PoP Miner retrieves network headers from the Bitcoin Finality Governor for Bitcoin blockchain publication.
2. **Transaction Construction**: The miner constructs Bitcoin transactions embedding aforementioned Hemi Network headers.
3. **Proof of Publication**:  Miners broadcast transactions through the Governor. These transactions are then integrated into Hemi’s consensus layer after being validated via the Bitcoin network, resulting in miner rewards.

***

## ⛏️ Run a PoP Miner

The [CLI](../../../how-to-tutorials/using-hemi/pop-mining/setup-part-1/) (Command Line Interface) version of PoP mining is designed for long-term, continuous operation. It requires some technical knowledge for setup and maintenance but provides robust security and operational efficiency.&#x20;

***

## 💸 **Earning Rewards**

|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                               |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🔍 **Tracking Miner Activity**    | Visit the [Hemi Block Explorer](https://testnet.explorer.hemi.xyz) and visit [Run a PoP Miner](../../../how-to-tutorials/using-hemi/pop-mining/setup-part-1/) to see your miner's history and activity.                                                                                                                                                                                                                       |
| ⏳ **Payout Processing Time**      | It takes about **4 hours** on mainnet (30 minutes on testnet) after sending a transaction to receive a PoP payout.                                                                                                                                                                                                                                                                                                            |
| ⚡️ **Quick Confirmation Rewards** | You will earn PoP rewards for transactions that are quickly confirmed **(within the next 2-3 Bitcoin blocks)**.                                                                                                                                                                                                                                                                                                               |
| 🎁 **Rewards**                    | <p>Testnet rewards are fixed, with each successful transaction earning <strong><code>1</code></strong> <strong>tHEMI</strong>. Payouts occur after the transaction is successfully confirmed. You may expect a brief delay between transaction confirmation and the distribution of tHEMI to your address.<br><br><em>In future testnets and on the mainnet, rewards will depend on the number of active PoP miners.</em></p> |
| 🔗 **Additional Links**           | [**github.com/hemilabs/heminetwork**](https://github.com/hemilabs/heminetwork)                                                                                                                                                                                                                                                                                                                                                |

{% hint style="danger" %}
**Protect Your Private Key**

Your private key is the most sensitive part of your Bitcoin wallet and should be treated with the highest level of security. Access to your private key grants complete control over the funds associated with the wallet, including the Bitcoin you send to the miner and the rewards you collect. If someone gains access to your private key, they can steal your funds and rewards without your ability to recover them.
{% endhint %}

{% hint style="info" %}
### 📝 **Tips**

* 🚫 **Single Key, Single Miner**: Using the same key for multiple PoP miner instances can lead to conflicts, as they may attempt to use the same Bitcoin UTXO simultaneously, causing operational issues.
* 🗂 **Purpose of** **`popm-address.json`**: This file serves as a secure storage for your generated keys, meant for reference. The actual Bitcoin key used by the PoP Miner is specified through an environment variable at the program's start.
* 🔑 **Unified Private Key**: Your single private key generates both a Bitcoin address and a Hemi address. The Hemi network automatically processes your public key from Bitcoin transactions, converting it into a Hemi address to receive payouts.
* ⚡ **Bitcoin Testnet Dynamics**: Bitcoin testnet can undergo periods of rapid block generation due to block difficulty adjustments after inactive periods. This unusual pace can temporarily impact the timing and processing of payouts.
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
