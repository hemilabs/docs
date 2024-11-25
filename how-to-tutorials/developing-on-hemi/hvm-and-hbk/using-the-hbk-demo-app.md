---
hidden: true
---

# Using the hBK Demo App

{% hint style="info" %}
## 📜 **TL;DR:**

*
{% endhint %}

***

## 🌐 Overview

* The Hemi Bitcoin Kit (hBK) Demo App is a tool designed for developers to interact with Bitcoin blockchain data directly from an Ethereum-compatible environment.&#x20;
* This demo app provides a user-friendly interface for querying Bitcoin information.
* By abstracting the complexities of interacting with Bitcoin data, the app allows developers to seamlessly retrieve and use Bitcoin blockchain data in their dApps without needing external services.&#x20;
* This makes it an effective resource for experimenting with Bitcoin-aware applications and understanding hBK’s capabilities within the Hemi ecosystem.

***

## 🏁 Prerequisites

To follow along, you’ll need:

* Nothing!

***

## 1. Get Address Balance

Retrieves the current balance (in satoshis) of a specified Bitcoin address.

***

## 2. Get Latest Block Header

Returns the latest Bitcoin block header containing metadata like hash, height, and timestamp.

<figure><img src="../../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
{
  "height": 0,
  "blockHash": "0x000000000933ea01ad0ee984209779baaec3ced90fa3f408719526f8d77f4943",
  "version": 1,
  "previousBlockHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "merkleRoot": "0x4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b",
  "timestamp": 1296688602,
  "bits": 486604799,
  "nonce": 414098458
}
```

***

## 3. Get Block Header by Height

Fetches the block header for a specific block height.

***

## 4. Get Transaction Details

Fetches the details of a Bitcoin transaction using its transaction ID, including all of its inputs and outputs.

***

## 5. Get Transaction Confirmations

Retrieves the number of confirmations for a specific transaction based on its transaction ID.

***

## 6. List Address UTXOs

Returns the UTXOs (Unspent Transaction Outputs) of a Bitcoin address, with pagination support.
