# Hemi Bitcoin Kit (hBK)

{% hint style="info" %}
### 📜 **TL;DR:**

* The Hemi Bitcoin Kit (hBK) is a library of smart contracts for developers to use to build Bitcoin-aware smart contracts.
* The hBK abstracts away the complications of interacting directly with the hVM Precompiles; parsing query results into data structures that are easy to understand and use.
* The level of deep Bitcoin introspection and programmability that hBK enables will allow developers to create Bitcoin dApps and interoperability infrastructure that would have previously been impossible or impractical to build with other interoperability solutions.
* **Latest hBK release on Hemi testnet:**\
  [0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c](https://testnet.explorer.hemi.xyz/address/0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c?tab=contract)
{% endhint %}

***

## 🌐 Overview

* The Hemi Bitcoin Kit (hBK) is a set of smart contracts designed to bridge the Ethereum and Bitcoin blockchains, enabling developers to build Bitcoin-aware dApps on an EVM with full access to Ethereum assets and the cross-chain data calls that ETH L2s provide.
* The hBK abstracts away the complexities of dealing directly with hVM's low-level precompile contracts.

***

## ⚙️ How It Works

* At the core of hBK's functionality is the Hemi Virtual Machine (hVM), a novel Bitcoin interoperability technology that embeds a fully indexed Bitcoin node within the Ethereum Virtual Machine (EVM).
*   The hVM facilitates direct communication between Ethereum smart contracts and the Bitcoin full node embedded in Hemi's EVM via precompiled calls. These calls allow smart contracts to query indexed Bitcoin data and return the results back into to the EVM.

    _This process ensures efficient and reliable access to Bitcoin blockchain data from within Hemi smart contracts._
* The hBK abstracts technical details such as data serialization and calling precompiles to provide developers with simple, straightforward methods to perform various data queries.
* Functions within the hBK can be categorized into two types:
  * **Direct passthroughs to precompiles:** Passthrough functions serve as simple gateways to precompiled calls, handling all necessary serialization and deserialization behind the scenes.
  * **Enhanced functions:** Enhanced functions, on the other hand, may combine multiple precompile calls or incorporate additional processing steps to facilitate more advanced queries or operations. _(Coming Soon)_
* This dual approach ensures that developers can focus on building features rather than navigating the complexities of low-level precompile interactions.

***

## 🧑‍💻 How is hBK Unique?

* The hVM is based on the Ethereum Virtual Machine (EVM) and comes stocked with built-in precompiles to interact with the embedded Bitcoin full node.
* Unlike other Bitcoin interoperability solutions, Bitcoin-aware smart contracts built using hBK don't rely on any external relayers, require gas-intensive proof validation, or suffer from limited views of Bitcoin's state.
* Performing a query for Bitcoin data is just as easy as reading the state of other contracts in the EVM. No need to design complex smart contracts that register requests to handle after the requested data is relayed. This pre-validated data directly available in the EVM significantly reduces both the complexity and cost of developing and maintaining Bitcoin-related applications
*

{% hint style="info" %}
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
