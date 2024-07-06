# Hemi Virtual Machine (hVM)

{% hint style="info" %}
## 📜 **TL;DR:**

* Hemi’s hVM is an **EVM upgraded with Bitcoin awareness.**
* The Hemi network maintains an EVM-visible Bitcoin node using Hemi’s custom **“Tiny Bitcoin” (TBC)** daemon.&#x20;
* A **“Processed Bitcoin View”** synchronizes all Hemi nodes as part of the EVM state transition.
{% endhint %}

***

## 🌐 Overview

* Hemi’s hVM is an **EVM upgraded with Bitcoin awareness** via new precompile contracts that smart contracts can call to get data from the Bitcoin node embedded in the EVM.

***

## 🔍 Tiny Bitcoin Daemon (TBC)

* The Hemi network maintains an EVM-visible Bitcoin node using Hemi’s custom **“Tiny Bitcoin” (TBC)** daemon. TBC syncs with the regular Bitcoin network over P2P and **indexes Bitcoin blocks** up to the height specified by the protocol.&#x20;
* When a Hemi Sequencer creates a block, they can optionally include an additional “Bitcoin Attributes Deposited” transaction communicating one or more new Bitcoin headers to the Hemi protocol.&#x20;

***

## 🎚️ Processed Bitcoin View

* When these transactions occur, all nodes on the Hemi network process these Bitcoin blocks at the same Hemi block height creating a **“Processed Bitcoin View”** synchronized across all Hemi nodes as part of the EVM state transition.&#x20;
* This synchronization ensures execution of all Bitcoin-aware smart contracts are **deterministic** across all nodes.

***

> To expose Bitcoin data to smart contracts, hVM introduces a number of new precompile contracts accessible in the EVM which fetch the latest data from the Processed Bitcoin View maintained by the embedded TBC node at the time the request is made.

***

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 18.48.59.png" alt=""><figcaption></figcaption></figure>
