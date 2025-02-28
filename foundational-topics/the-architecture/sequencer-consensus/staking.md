# Proof-of-Stake (PoS)

{% hint style="info" %}
## 📜 **TL;DR:**

* Pure Proof-of-Stake networks rely on social consensus to prevent censorship by majority stakers and long-range attacks using old **PoS keys (weak-subjectivity attacks).**
* **Staking** is the risking of an asset in return for the chance to construct a block.
* A user who acts maliciously will have his stake **slashed** (reduced) as punishment for attacking the network.
* **The Hemi Network** uses a hybrid staking system that incorporates network state proofs published to the Bitcoin network, preventing both censorship attacks and weak-subjectivity attacks.
{% endhint %}

***

## 🌐 **Overview**

* In Proof-of-Stake (PoS) consensus protocols, **staking** is a form of virtual mining in which users risk some amount of tokens (a “stake”) for the chance to construct a block and earn block rewards.  If the staker misbehaves (for example, by trying to cheat the system), the network will remove some or all of the stake (a process called “slashing”).  Under normal conditions when stakers act honestly, slashing is a rare occurrence.  PoS is a popular alternative to Proof-of-Work (as in Bitcoin) because staking is far less energy intensive than mining.

***

## ⚠️ **Security Risks in Proof-of-Stake**

* Conventional PoS networks, however, face two security risks inherent to staking.  If a malicious actor were to acquire more than half of the staking power on the network, he could censor transactions, including slashing transactions, which would prevent other honest validators from regaining control of the network. PoS systems also suffer from weak subjectivity.&#x20;
* If a malicious actor acquired enough old PoS keys to have the majority of staking power, he could use the old keys to create a valid alternative chain.  Pure PoS chains like Ethereum rely on social consensus to address these issues because the protocols themselves are vulnerable.

***

{% hint style="success" %}
## 👀 Sneak Peek WIP

**The Hemi Network's Hybrid Staking Approach**

The Hemi Network uses a modified PoS protocol to provide security. Sequencers and publishers on the Hemi Network stake the network’s native token, as part of their normal operations.  However, because of the network state proofs which proof-of-proof miners publish to the Bitcoin network, old staking keys cannot be used to construct a valid alternative chain.  Constructing a valid alternative chain would require also reorganizing the Bitcoin network to publish corresponding alternative state proofs.

Furthermore, even a staker with an overwhelming majority of staking power on the Hemi Network would not be able to censor transactions. They would still be forced to include Bitcoin block headers in the PoS blocks he produced, and any Hemi Network user could bypass active PoS censorship attacks by offloading transactions to the Bitcoin network.  The attacker’s stake would then be slashed and other validators would be allowed to process transactions.&#x20;
{% endhint %}

