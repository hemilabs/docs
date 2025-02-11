# PoS-Only Pitfalls

{% hint style="info" %}
### 📜 TL;DR:

* Standard **Proof-of-Stake (PoS)** systems like Ethereum face two primary risks:
  1. **Weak Subjectivity**, where attackers could potentially gain majority control by accumulating old PoS keys, enabling them to create alternative chains; and
  2. **Censorship**, where a current majority stakeholder blocks or ignores transactions, akin to a traditional 51% attack.
{% endhint %}

***

## 🚨 Weak Subjectivity

* This risk involves an attacker accumulating enough keys of old PoS miners to gain majority control **at some point in the past**. With this control, they could create a valid, alternative/competing version of the blockchain which would appear equally valid to a bootstrapping node attempting to sync the network for the first time, and could also be used to create seemingly valid zero-knowledge proofs of chain state that differs from the legitimate canonical chain.
* While Ethereum relies on community consensus to avoid long-range reorganizations of its chain, its PoS protocol doesn’t _technically_ prevent this type of attack.

***

## 🚫 Censorship

* An attacker with **current majority stake** could potentially block or ignore certain transactions, exercising a form of **majority control** that undermines the network's decentralization and fairness.

***

## ❌ Lack of Protocol-Level Defenses

* Since PoS operates entirely within its network, it lacks **protocol-level defenses** against the types of attacks mentioned above.
* Among the vulnerabilities, the limitations are:
  * **No External Correction Mechanism**: If internal rules fail or are exploited, there's no external system to protect or correct the network.
  * **Self-Contained Security**: PoS systems handle all their security internally within the blockchain network.
* By using PoP, Hemi prevents against weak subjectivity attacks because the illegitimate chain an attacker produces when attempting a long-range reorg could not be appropriately published to Bitcoin. Hemi's fork resolution algorithm prevents a reorg from occurring if the new proposed fork does not have PoP publications that are in-step with or before the current chain's publications. As a result, Hemi's consensus algorithm has strong subjectivity and reorganizing a segment of Hemi's chain which has reached Bitcoin finality would require the attacker to 51% attack Hemi and Bitcoin simultaneously.
* As a dual-chain L2, Hemi can also provide robust censorship resistance against attacks from majority block-consensus power actors. Any valid Hemi transaction can be published to either Bitcoin or Ethereum, and Hemi's block derivation protocol will force the inclusion of these transactions in Hemi blocks.
