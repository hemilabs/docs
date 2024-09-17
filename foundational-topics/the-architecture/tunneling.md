# Tunnels

{% hint style="info" %}
## 📜 **TL;DR:**

* Bridging i.e. Tunneling allows the transfer of assets between disparate blockchains (such as between distinct L1s or between an L1 and an L2).
* While bridging addresses the siloed nature common to most blockchains, it typically suffers from centralization because most blockchains do not maintain state awareness of other networks.
* Because the **Hemi Network maintains protocol-level state awareness of both Bitcoin and Ethereum**, it enables sophisticated asset transfer and decentralization.
  * Hemi supports the [MetaMask](../../how-to-tutorials/tutorials/metamask-wallet-setup.md) EVM wallet for tunneling Ethereum assets.&#x20;
  * Hemi supports the [UniSat](../../how-to-tutorials/tutorials/btc-wallet-setup/) BTC wallet for tunneling Bitcoin assets.&#x20;
{% endhint %}

***

## 🌐 **Overview**

* Blockchain networks typically operate as independent systems with no knowledge of other networks, creating a siloed environment. This isolation makes it impossible to transfer assets directly from one chain to another.
* **Bridges** are developed to address this issue, enabling asset transfers between different blockchains. They function by accepting a token from one blockchain **(chain A)** and issuing a corresponding placeholder or wrapped token on another blockchain **(chain B).** This wrapped token represents the original token and can be redeemed for it.

***

## 🖼️ **Example**

* To illustrate, consider the process of transferring bitcoin to Ethereum. A user sends bitcoin to a bridge connecting to the Ethereum network. This bridge then issues a wrapped Ethereum token representing the bitcoin.
* The user can utilize this wrapped bitcoin within the Ethereum network or return it to the bridge to reclaim the original bitcoin on the Bitcoin network.

***

## 🔍 **Broader Applications & Limitations of Bridges**

* Bridges are not limited to transferring assets between distinct blockchains. They can also facilitate transfers between different network layers, like connecting a Layer 1 (**L1**) blockchain like Ethereum to a Layer 2 (**L2**) rollup chain. This connection allows assets to benefit from the L2's lower fees and other features.
* However, bridges often rely on centralized infrastructure due to the lack of protocol-level awareness between the connected chains. For example, while an L2 might maintain the state of its corresponding L1, the L1 lacks inherent knowledge of the L2. This disconnect necessitates a centralized third party to maintain awareness of both chains.

***

{% hint style="success" %}
## 👀 Sneak Peek WIP

**Introducing Tunnels for Decentralized Asset Transfers**

To promote greater decentralization and address the limitations of bridges, the Hemi Network introduces **tunnels**.&#x20;

_**Tunnels**_ allow for sophisticated, noncustodial bidirectional asset transfers between networks, such as Bitcoin and Ethereum. Unlike traditional bridges, tunnels within the Hemi Network maintain state awareness of both networks at the protocol level.

This enables a variety of custodianship approaches, both centralized and decentralized. For instance, BRC-20 tokens can be tunneled from Bitcoin to the Hemi Network or Ethereum, facilitating trading on Ethereum-based decentralized exchanges (DEXes). Additionally, tunnels benefit from the security features of the Hemi Network’s Bitcoin-based superfinality
{% endhint %}
