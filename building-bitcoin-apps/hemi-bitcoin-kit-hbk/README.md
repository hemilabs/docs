# Hemi Bitcoin Kit (hBK)

{% hint style="info" %}
## 📜 **TL;DR:**

* The Hemi Bitcoin Kit (hBK) is a library of smart contracts for developers to use to build Bitcoin-aware smart contracts.
* The hBK abstracts away the complications of interacting directly with the hVM Precompiles; parsing query results into data structures that are easy to understand and use.
* The level of deep Bitcoin introspection and programmability that hBK enables will allow developers to create Bitcoin dApps and interoperability infrastructure that would have previously been impossible or impractical to build with other interoperability solutions.
* **Latest hBK release on Hemi testnet:**\
  [0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c](https://testnet.explorer.hemi.xyz/address/0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c?tab=contract)
*
*
{% endhint %}

***

## 🌐 Overview

* The Hemi Bitcoin Kit (hBK) is a set of smart contracts designed to bridge the Ethereum and Bitcoin blockchains, enabling easy interaction between the two.&#x20;
* The hBK builds upon the hVM foundation to offer developers an accessible and user-friendly interface for interacting with the Bitcoin blockchain.

***

## ⚙️ How It Works

* At the core of the Kit's functionality is the hVM (hemi Virtual Machine), a novel technology that embeds a fully indexed Bitcoin node within the Ethereum Virtual Machine (EVM).
*   The hVM facilitates direct communication between Ethereum smart contracts and the Bitcoin blockchain via precompiled calls. These calls allow smart contracts to query Bitcoin indexers and return the results back to the EVM.&#x20;

    _This process ensures efficient and reliable access to Bitcoin blockchain data from within Hemi smart contracts._
* The hBK abstracts technical details such as data serialization and assembly language to provide developers with simple, straightforward methods to perform basic data queries.
* Functions within the hBK can be categorized into two types:&#x20;
  * **Direct passthroughs to precompiles:** Passthrough functions serve as simple gateways to precompiled calls, handling all necessary serialization and deserialization behind the scenes.
  * **Enhanced functions:** Enhanced functions, on the other hand, may combine multiple precompile calls or incorporate additional processing steps to facilitate more advanced queries or operations.&#x20;
* This dual approach ensures that developers can effectively leverage the Bitcoin blockchain's capabilities within their Hemi applications, without needing to navigate the intricacies of direct precompile interaction.

***

## 🧑‍💻 How is hBK Unique?

* The hVM is based on the Ethereum Virtual Machine (EVM) and comes stocked with built-in shortcuts precompiled to abstract away complex transactions. These make it easier for developers to create their own smart contracts and, by extension, build decentralized applications.&#x20;
* Just as important, it makes the development of such applications cost-effective. Unlike other Bitcoin interoperability solutions that require developers to pay for expensive crypto validation operations, hBK offers direct access to pre-validated data. This pre-validated data eliminates the need for additional validation steps, significantly reducing both the complexity and cost of developing and maintaining Bitcoin-related applications.
* Because the hVM is an EVM wrapped around a Bitcoin node, it automatically extends that easy DeFi programmability to Bitcoin-based assets.&#x20;
* The Hemi Bitcoin Kit makes dApp development even easier. The Hemi Bitcoin Kit is a library of smart contracts that provides easy-to-use precompiles to smart contracts. They seamlessly translate smart contract queries so that data is easier to deal with.

{% hint style="info" %}
The Hemi Bitcoin Kit brings five benefits to developers:

* **Easier development:** Access to a wide range of Bitcoin data is just one smart contract call away.
* **Rich data:** You get access to data that is impractical or outright impossible to get with other solutions.
* **Security and reliability:** dApps get immediate information about any relevant events on the Bitcoin blockchain without having to rely on third-party relayers or trusted oracles.
* **Composability:** Anyone can design new layers of Bitcoin DeFi infrastructure for others on which to build.
* **Cost-effectiveness:** The hVM uses far less gas than other approaches and there's no need to incentivize third-party bots to watch for and relay events.
{% endhint %}

***

## 🏗️ Use Cases

Some examples of unique applications that the Hemi Bitcoin Kit enables:

* **Custom Bitcoin tunnels:** Connect chains to the Bitcoin network using customized security, cost, and speed settings.
* **Trustless BTC staking and re-staking protocols:** 99% of BTC is unbridged and/or unproductive. With Hemi, BTC can be used to secure networks and earn yield.&#x20;
* **Bitcoin-authenticated AI-model marketplaces:** As an example of an AI use case, model owners can publish Bitcoin-secure hashes of their model weights, timestamping them to the Bitcoin blockchain.
* **Multichain DAOs:** Hemi DAOs operate across both Bitcoin and Ethereum, making decisions based on the collective input of stakeholders from both communities.
