# Proof-of-Proof vs. Merged Mining

{% hint style="info" %}
## 📜 **TL;DR:**

* [**Merged mining** ](https://www.techopedia.com/definition/merged-mining)allows Bitcoin miners to simultaneously mine a Bitcoin sidechain, which can limit decentralization and lead to an attack on the sidechain.
* The **Proof-of-Proof (PoP)** consensus protocol utilized by Hemi enables PoP miners to independently publish data to the Bitcoin blockchain, cutting off this attack vector.


{% endhint %}

***

## ⛔️ The Trouble with Merged Mining

* Bitcoin miners must choose to participate by running nodes for the sidechain, which can curtail decentralization.
* This makes the sidechain more susceptible to attack, as Bitcoin miners can collude to attack the sidechain at no cost while reaping Bitcoin block rewards.
* Merged mining can introduce new security problems and issues with incentives.

***

## 🔍 **How Proof-of-Proof Works**

* Hemi uses a consensus protocol called **Proof-of-Proof (PoP)**, which allows Hemi to exceed Bitcoin's security at scale.
* Bitcoin miners don’t need to participate in Hemi directly; they confirm blocks that include Hemi transactions and collect transaction fees for doing so.
* Users who _do_ want to earn rewards in Hemi’s native token can run a super-lightweight PoP miner to publish Hemi consensus data to Bitcoin.

<mark style="color:orange;">**👉**</mark>[ <mark style="color:orange;">**It’s simple: Help create proofs and get tokens.**</mark>](pop-mining.md#run-a-pop-miner)&#x20;

* Each new Hemi block receives a Bitcoin confirmation, making reorganization increasingly unlikely until the block reaches finality.
* Bitcoin requires about 60 minutes to reach finality; **Hemi takes nine Bitcoin blocks (about 90 minutes)** to reach finality and **achieves** [**Superfinality** (_WIP_)](broken-reference) in just **two hours.**

Thus, in the Proof-of-Proof protocol, unlike with merged mining, Bitcoin miners needn’t be active to benefit; they can’t collude to attack the chain, and superfinality comes fast.

***

