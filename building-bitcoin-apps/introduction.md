# Introduction

{% hint style="info" %}
### 📜 **TL;DR:**

* The **Hemi Virtual Machine (hVM)** and **Hemi Bitcoin Kit (hBK)** power Hemi’s Bitcoin interoperability.
* **hVM** is an indexed Bitcoin full node directly accessible inside the EVM.
* **hBK** is a smart contract library running on Hemi that utilizes hVM and makes Hemi’s Bitcoin awareness easier to use.
* hVM’s precompile calls and hBK's functions are subject to change in future versions of the Hemi testnet.
* **Latest hBK release on Hemi:** [0x7007dd1C09527B92AEcd8Ae6570B73d09E0B8F12](https://explorer.hemi.xyz/address/0x7007dd1C09527B92AEcd8Ae6570B73d09E0B8F12)
* **Latest hBK release on Hemi testnet:** [0xeC9fa5daC1118963933e1A675a4EEA0009b7f215](https://testnet.explorer.hemi.xyz/address/0xeC9fa5daC1118963933e1A675a4EEA0009b7f215)
{% endhint %}

***

## 🌐 Overview

* The **Hemi Virtual Machine (hVM)** and **Hemi Bitcoin Kit (hBK)** power Hemi’s Bitcoin Interoperability, empowering dApp developers to build novel Bitcoin dApps and robust interoperability infrastructure in a trustless, secure, and gas-efficient manner.
  * **hVM:** An indexed Bitcoin full node directly accessible inside the EVM, exposing data including transactions, address balances, UTXOs, and chain metadata to smart contracts on Hemi via custom precompiles.
  * **hBK:** A smart contract library running on Hemi that utilizes hVM and makes Hemi’s Bitcoin awareness easier to use by exposing higher-level functions that perform the precompile calls and handle the data marshaling, returning simple data structures developers can use in their dApps.

***

{% hint style="warning" %}
#### 👷‍♂️ In Development:

* hVM and Bitcoin Kit are in development and experimental.
* hVM’s precompile calls and Bitcoin Kit’s functions are subject to change in future versions of the Hemi Testnet.
* Prior to mainnet launch, the protocols will ossify and future upgrades will only add new hVM precompiles and Bitcoin Kit functions, ensuring full backwards compatibility.
{% endhint %}

***

### 📋 Latest Version

* Because new versions of hBK are being developed and tested, this document will always contain the latest “stable” contract available on Hemi’s testnet.
* In Mainnet, Bitcoin Kit contracts will be deployed as predeploys with special addresses like 0x8400000000000000000000000000000000000001, with new versions offering additional features being deployed at incremented addresses.

> **Latest Bitcoin Kit release on Hemi Testnet:**
>
> [0xeC9fa5daC1118963933e1A675a4EEA0009b7f215](https://testnet.explorer.hemi.xyz/address/0xeC9fa5daC1118963933e1A675a4EEA0009b7f215) (Updated October 11th, 2024)
