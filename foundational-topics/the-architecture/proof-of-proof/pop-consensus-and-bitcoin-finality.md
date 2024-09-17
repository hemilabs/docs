# PoP Consensus & Bitcoin Finality

{% hint style="info" %}
## 📜 TL;DR:

* In **Proof-of-Proof (PoP) consensus**, a PoP miner periodically publishes proof of the Hemi Network’s state to the Bitcoin blockchain.
* By building on Bitcoin, PoP consensus **inherits the security and finality** of Bitcoin’s consensus.
* After **six Bitcoin blocks**, PoP consensus reaches a state of **superfinality**, where the security of the Hemi Network exceeds that of Bitcoin.
{% endhint %}

***

## 🌐 Overview

* Proof-of-Proof (PoP) is the Hemi Network’s additive consensus protocol, building on **Bitcoin’s consensus** for superior security. PoP miners publish cryptographic network-state proofs to the Bitcoin blockchain, protecting Hemi consensus with Bitcoin's proof of work.
* Hemi blocks achieve **finality** typically nine blocks (approximately an hour and a half) after their proofs are published to Bitcoin.

***

## ⏱️ Finality Delay in the Hemi Network

* The Hemi Network accounts for fluctuations in Bitcoin's transaction fees and block timings, recognizing that network-state proofs might not appear in every block.
* To manage this variability, a **finality delay** of nine Bitcoin blocks is implemented.

> If no competing fork publishes proofs to Bitcoin during this period, the network assumes finality, requiring a **51% attack on both the Hemi and Bitcoin networks** to alter this.

***

{% hint style="success" %}
## 👀 Sneak Peek WIP

_♾️ Superfinality: A New Benchmark in Blockchain Security_

_Upon reaching this finality, the Hemi Network attains a state of **'superfinality,'** where its chain state's security surpasses Bitcoin's._

_How?_

_This is achieved by combining Bitcoin’s **Proof-of-Work** consensus with Hemi’s **Proof-of-Stake**. After superfinality, altering the Hemi Network’s state proof would be economically infeasible even for nation-states. An attacker would need so simultaneously 51% attack Bitcoin and Hemi, which is even harder than attacking Bitcoin itself._
{% endhint %}

