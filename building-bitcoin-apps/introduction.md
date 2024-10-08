# Introduction

{% hint style="info" %}
## 📜 **TL;DR:**

* The **Hemi Virtual Machine (hVM)** and **Hemi Bitcoin Kit (hBK)** power Hemi’s Bitcoin Interoperability.
* **hVM** is an indexed Bitcoin full node directly accessible inside the EVM.
* **hBK** is a smart contract library running on Hemi that utilizes hVM and makes Hemi’s Bitcoin awareness easier to use.
* hVM’s precompile calls and hBK's functions are subject to change in future versions of the Hemi testnet.&#x20;
* **Latest hBK release on Hemi testnet:** [0xeC9fa5daC1118963933e1A675a4EEA0009b7f215](https://testnet.explorer.hemi.xyz/address/0xeC9fa5daC1118963933e1A675a4EEA0009b7f215)
{% endhint %}

***

## 🌐 Overview

* The **Hemi Virtual Machine (hVM)** and **Hemi Bitcoin Kit (hBK)** power Hemi’s Bitcoin Interoperability, empowering dApp developers to build novel Bitcoin dApps and robust interoperability infrastructure in a trustless, secure, and gas-efficient manner.
  * **hVM:** An indexed Bitcoin full node directly accessible inside the EVM, exposing data including transactions, address balances, UTXOs, and chain metadata to smart contracts on Hemi via custom precompiles.
  * **hBK:** A smart contract library running on Hemi that utilizes hVM and makes Hemi’s Bitcoin awareness easier to use by exposing higher-level functions that perform the precompile calls and handle the data marshaling, returning simple data structures developers can use in their dApps.&#x20;

***

{% hint style="warning" %}
### 👷‍♂️ In Development:

* hVM and Bitcoin Kit are in development and experimental.&#x20;
* hVM’s precompile calls and Bitcoin Kit’s functions are subject to change in future versions of the Hemi Testnet.&#x20;
* Prior to mainnet launch, the protocols will ossify and future upgrades will only add new hVM precompiles and Bitcoin Kit functions, ensuring full backwards compatibility.
{% endhint %}

***

### 📋 Latest Version

* Because new versions of hBK are being developed and tested, this document will always contain the latest “stable” contract available on Hemi’s testnet.&#x20;
* In Mainnet, Bitcoin Kit contracts will be deployed as predeploys with special addresses like 0x8400000000000000000000000000000000000001, with new versions offering additional features being deployed at incremented addresses.

> **Latest Bitcoin Kit release on Hemi Testnet:**\
> [0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c](https://testnet.explorer.hemi.xyz/address/0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c?tab=contract) (Updated May 8th 2024)
