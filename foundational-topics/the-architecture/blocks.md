# Blocks

{% hint style="info" %}
## 📜 TL;DR:

* **Blocks** in blockchain technology are packets of transactions and data, made secure through links to previous blocks.
* Altering past blocks requires modifying all subsequent ones, a security feature. The Hemi Network enhances this by segmenting blocks into five-minute "**keystone**" intervals, with a security proof sent to the Bitcoin network every second interval.
{% endhint %}

***

## 🌐 Overview

* A block is a component of blockchain technology that contains transactions and their associated data.&#x20;
* Its security is enhanced because all subsequent blocks in the chain cryptographically reference it, reinforcing the integrity of the entire blockchain with each new block added. Tampering with an earlier block requires altering not only that block but also every block after it.

***

## 🟦 Hemi Blocks

* In the Hemi Network, blocks are organized into **five-minute intervals known as keystones**. To inherit Bitcoin’s security, \*one Hemi Network state proof must be published to the Bitcoin network every two keystone intervals. \*
* The first block of each interval **cryptographically references the previous two keystone blocks**, ensuring that the network cannot be reorganized without a 51-percent attack against Bitcoin itself, a scenario considered highly unlikely even for powerful entities like nation-states.
