---
hidden: true
---

# Oracles

## 🌐 Overview <a href="#redstone" id="redstone"></a>

Oracles play a critical role in bridging the gap between blockchain and the external world, enabling smart contracts on Hemi to access trustworthy off-chain data necessary for various use cases.&#x20;

The most common applications of oracles include:

* Providing up-to-date token prices for different pairs, which is essential for DeFi protocols and financial products.
* Enabling dynamic NFTs that can change their properties based on real-world events, adding a layer of interactivity and uniqueness.

***

## ⎑ Push vs Pull

Oracles operate using two primary models:

* **Push Model:** In this traditional approach, used by systems like Chainlink, the oracle regularly pushes data to an on-chain contract, which dApps can access as needed. While this ensures data is readily available, it can be inefficient since updates occur even when not immediately required.
* **Pull Model:** This newer model involves oracles signing data and keeping it on an external network. When dApps need updated data, users pull the signed data and submit it on-chain with their transaction. This method keeps data current and is more efficient, as data is submitted only when necessary.

***

## Redstone <a href="#redstone" id="redstone"></a>

Redstone offers push-based price feeds for Hemi.&#x20;

**Supported Networks**

* Hemi Mainnet
* Hemi Sepolia

{% embed url="https://docs.redstone.finance/docs/introduction" %}
