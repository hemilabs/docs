# Hemi Bitcoin Kit (hBK)

{% hint style="info" %}
#### 📜 **TL;DR:**

* The Hemi Bitcoin Kit (hBK) is a library of smart contracts for developers to use to build Bitcoin-aware smart contracts.
* The hBK abstracts away the complications of interacting directly with the hVM Precompiles; parsing query results into data structures that are easy to understand and use.
* **Latest hBK release on Hemi:** [0x7007dd1C09527B92AEcd8Ae6570B73d09E0B8F12](https://explorer.hemi.xyz/address/0x7007dd1C09527B92AEcd8Ae6570B73d09E0B8F12)
* **Latest hBK release on Hemi testnet:** [0xeC9fa5daC1118963933e1A675a4EEA0009b7f215](https://testnet.explorer.hemi.xyz/address/0xeC9fa5daC1118963933e1A675a4EEA0009b7f215)
* **Bitcoin Kit Demo/Editor app :** [https://bitcoin-kit.hemi.xyz/code-editor](https://bitcoin-kit.hemi.xyz/code-editor)
{% endhint %}

***

## 🌐 Overview

* The Hemi Bitcoin Kit (hBK) is a set of smart contracts designed to bridge the Ethereum and Bitcoin blockchains, enabling developers to build Bitcoin-aware dApps on an EVM with full access to Ethereum assets and the cross-chain data calls that ETH L2s provide.
* The hBK abstracts away the complexities of dealing directly with hVM's low-level precompile contracts.

***

## 🧑‍💻 How is hBK Unique?

* The hVM is based on the Ethereum Virtual Machine (EVM) and comes stocked with built-in precompiles to interact with the embedded Bitcoin full node.
* Unlike other Bitcoin interoperability solutions, Bitcoin-aware smart contracts built using hBK don't rely on any external relayers, require gas-intensive proof validation, or suffer from limited views of Bitcoin's state.
* Performing a query for Bitcoin data is just as easy as reading the state of other contracts in the EVM. No need to design complex smart contracts that register requests to handle after the requested data is relayed.
* Pre-validated data directly available in the EVM significantly reduces both the complexity and cost of developing and maintaining Bitcoin-related applications

{% hint style="success" %}
The Hemi Bitcoin Kit brings five benefits to developers:

* **Easier development:** Access to a wide range of Bitcoin data is just one smart contract call away.
* **Rich data:** Access Bitcoin state like UTXOs and balances that is impractical or outright impossible to get with other solutions.
* **Security and reliability:** dApps get immediate information about any relevant events on the Bitcoin blockchain without having to rely on third-party relayers or trusted oracles.
* **Composability:** Anyone can design new layers of Bitcoin DeFi infrastructure for others on which to build.
* **Cost-effectiveness:** The hVM uses far less gas than other approaches and there's no need to incentivize third-party bots to watch for and relay events.
{% endhint %}

***

## 🏗️ Use Cases

Some examples of unique applications that the Hemi Bitcoin Kit enables:

* **Custom Bitcoin tunnels:** Connect chains to the Bitcoin network using customized security, cost, and speed settings.
* **Trustless BTC staking and re-staking protocols:** 99% of BTC is unbridged and/or unproductive. With Hemi, BTC can be used to secure networks and earn yield.
* **Bitcoin-authenticated AI-model marketplaces:** As an example of an AI use case, model owners can publish Bitcoin-secure hashes of their model weights, timestamping them to the Bitcoin blockchain.
* **Multichain DAOs:** Hemi DAOs operate across both Bitcoin and Ethereum, making decisions based on the collective input of stakeholders from both communities.

***

## 🛠️ Bitcoin Kit Demo

The [Hemi Bitcoin Kit Demo](https://bitcoin-kit.hemi.xyz/code-editor) provides developers with an interactive code editor and execution environment featuring six essential Bitcoin blockchain functions. Users can do the following:&#x20;

* Retrieve address balances,
* Access the latest block headers,&#x20;
* Query block headers by specific height,&#x20;
* Get detailed transaction information,&#x20;
* Check transaction confirmations,&#x20;
* List unspent transaction outputs (UTXOs) for any address.&#x20;

Each function comes with pre-written, well-documented code that demonstrates how to interact with Bitcoin's blockchain through smart contract calls, making it easy for developers to understand and implement Bitcoin functionality in their own applications. The demo serves as both a learning tool and a practical reference for app development, allowing users to execute real Bitcoin queries and see immediate results without needing to set up their own development environment.
