# Oracles

## 🌐 Overview <a href="#redstone" id="redstone"></a>

Oracles play a critical role in bridging the gap between blockchain and the external world, enabling smart contracts on Hemi to access trustworthy off-chain data necessary for various use cases.&#x20;

The most common applications of oracles include:

* Providing up-to-date token prices for different pairs, which is essential for DeFi protocols and financial products.
* Enabling dynamic NFTs that can change their properties based on real-world events, adding a layer of interactivity and uniqueness.

***

## ⎑ Push vs Pull

Oracles operate using two primary models:

* **Push Model:** In this traditional approach, the oracle regularly pushes data to an on-chain contract, which dApps can access as needed.
* **Pull Model:** This newer model involves oracles signing data and keeping it on an external network. When dApps need updated data, users pull the signed data and submit it on-chain with their transaction.

***

## Pyth <a href="#redstone" id="redstone"></a>

Pyth offers push-based price feeds for Hemi.&#x20;

**Supported Networks**

* Hemi mainnet
* Hemi Sepolia

{% embed url="https://docs.pyth.network/home" %}

***

## Redstone <a href="#redstone" id="redstone"></a>

Redstone offers push-based price feeds for Hemi.&#x20;

#### Supported Networks:

**Hemi mainnet**

<table><thead><tr><th width="131">Symbol</th><th>Contract Address</th></tr></thead><tbody><tr><td>TBD</td><td>TBD</td></tr></tbody></table>

**Hemi Sepolia**

<table><thead><tr><th width="130">Symbol</th><th>Contract Address</th></tr></thead><tbody><tr><td>BTC</td><td><code>0x0d7697a15bce933cE8671Ba3D60ab062dA216C60</code></td></tr><tr><td>ETH</td><td><code>0x89F48f6671Ec1B1C4f6abE964EBdd21F4eb7076f</code></td></tr><tr><td>USDC</td><td><code>0x42Ea045b70856c8cc20784A5B45EA35a80C8aDd9</code></td></tr><tr><td>USDT</td><td><code>0x2C787Db499BD7BF1f592D8DDd79ead9a72420763</code></td></tr></tbody></table>

{% embed url="https://docs.redstone.finance/docs/introduction" %}
