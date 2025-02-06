# Consensus and Security Protocols

{% hint style="info" %}
## 📜 **TL;DR:**

* Incorporates Bitcoin's security to prevent attacks, with PoP Miners embedding consensus data on the Bitcoin blockchain.
* **Rewards PoP Miners** in native tokens for strengthening consensus.
* **Utilizes Bitcoin confirmations** to ensure network integrity, achieving "Bitcoin Finality" for robust defense against reorganizations.&#x20;
{% endhint %}

***

{% hint style="success" %}
## 👀 Sneak Peek WIP

_**Overview**_

The Hemi Network's sequencer consensus combines **Proof-of-Stake** with **Proof-of-Proof** to address weak subjectivity and censorship attacks inherent in traditional PoS systems.&#x20;

_This hybrid model prevents forged chains through state proofs on the Bitcoin network and allows legitimate sequencers to regain control in adversarial conditions, ensuring the network's resilience and security._
{% endhint %}



***

#### 🔒 **Network Security and Finality**

* To inherit Bitcoin security, a new type of miner (a “PoP Miner”) publishes Hemi consensus information to the Bitcoin blockchain.
* After a state publication to Bitcoin, the Hemi Network’s consensus layer incorporates cryptographic proofs of these publications, with PoP Miners receiving a reward in the protocol’s native token. The network uses these proofs during fork resolution to prevent reorganizations with the full force of Bitcoin’s security.
* As they are produced, the Hemi Network’s chain segments initially receive Bitcoin confirmations, which means an attacker **would have to control increasingly large ratios of staking power to successfully affect a reorganization.**
* During normal operation, each block on the Hemi Network reaches full **“Bitcoin Finality”** **after 90 minutes, or nine Bitcoin blocks, on average**.

> At this point, it is mathematically impossible for anyone to reorganize the network without 51% attacking Bitcoin itself.
