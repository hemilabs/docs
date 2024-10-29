# Overview

{% hint style="info" %}
### 📜 **TL;DR:**

* The Hemi Bitcoin Kit (hBK) enables direct interaction with Bitcoin blockchain data within Ethereum’s environment.
* hBK utilizes Hemi Virtual Machine (hVM) to embed a fully indexed Bitcoin node inside the Ethereum Virtual Machine (EVM).
* hBK allows Ethereum smart contracts to query Bitcoin data using precompiled calls, ensuring efficient, trustless data access.
{% endhint %}

***

## ⚙️ How It Works

#### Hemi Virtual Machine (hVM)

The hVM is the backbone of the hBK’s interoperability features, embedding a Bitcoin node within the EVM. This setup allows Ethereum smart contracts to directly query Bitcoin data without relying on external bridges or third-party oracles, ensuring trustless, efficient, and secure access to Bitcoin data.

* Direct Access: Smart contracts can communicate with Bitcoin data embedded in the EVM, enabling them to make queries and receive data via precompiled calls.
* Indexed Data: The fully indexed Bitcoin node maintains transaction history, UTXOs, and meta-protocols like Ordinals and BRC-20 tokens.

#### Developer Interface: Simplified Interaction with Bitcoin

The hBK abstracts technical complexities, offering developers straightforward methods for accessing Bitcoin data, allowing them to:

1. Directly Pass Data to Precompiled Calls: Simple data serialization/deserialization processes provide a transparent gateway to precompiled Bitcoin calls.
2. Enhanced Query Functions (Upcoming): hBK is set to introduce enhanced functions, combining multiple precompile calls and additional processing steps for advanced operations.

This dual approach ensures developers can create Bitcoin-aware applications without managing low-level integration details, focusing instead on innovation and functionality.

***

## 🔑 Key Features

* **Embedded Node Access:** hBK integrates a fully indexed Bitcoin node within Hemi’s EVM environment, exposing robust Bitcoin data for smart contract use.
* **Precompiled Calls for Direct Data Retrieval:** Passthrough functions facilitate Bitcoin data queries with direct calls, automatically handling the data structures.
* **Enhanced Functions for Advanced Queries:** Future upgrades will introduce enhanced functions, combining multiple calls and added processing to support more complex queries and data requirements.
