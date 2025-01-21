# Using the hBK Demo App

{% hint style="info" %}
## 📜 **TL;DR:**

*
{% endhint %}

***

## 🌐 Overview

* The [Hemi Bitcoin Kit (hBK) Demo App](https://bitcoin-kit.hemi.xyz/code-editor) is a tool designed for developers to interact with Bitcoin blockchain data directly from an Ethereum-compatible environment.&#x20;
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

<figure><img src="../../../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
514853116
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the Bitcoin address to confirm the above output.

<figure><img src="../../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

***

## 2. Get Latest Block Header

Returns the latest Bitcoin block header containing metadata like hash, height, and timestamp.

<figure><img src="../../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
{
  "height": 3520643,
  "blockHash": "0x00000000002be0cd198317218f374a484bd0b3c5fe4eaf098bb5dfc97d0fb8a7",
  "version": 536870912,
  "previousBlockHash": "0x00000000000000019bebcf5e1d1dc6baf664c5859f82add17f5543b3018c82de",
  "merkleRoot": "0xcc50e3a3ca39e37a7ccd5867a7f2a82192c98861f28a50d94f558305672d65de",
  "timestamp": 1733342457,
  "bits": 486604799,
  "nonce": 1100503385
}
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the Block header to confirm the above output.

<figure><img src="../../../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

***

## 3. Get Block Header by Height

Fetches the block header for a specific block height.

<figure><img src="../../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
{
  "height": 1321358,
  "blockHash": "0x000000000000023bf34cd847acfcd73ad3b010f9a9434069e9bc5941cf61a1bf",
  "version": 536870912,
  "previousBlockHash": "0x00000000000002d213e95ae971060d49f93d51c3ce0ac84c452f76a45c962036",
  "merkleRoot": "0xd0f34249cd9b3929b56a418ab6fe965e685f1765f2dcd605ed08a1382199e506",
  "timestamp": 1527980035,
  "bits": 436539705,
  "nonce": 3252632758
}
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the Block header height to confirm the above output.

<figure><img src="../../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

***

## 4. Get Transaction Details

Fetches the details of a Bitcoin transaction using its transaction ID, including all of its inputs and outputs.

<figure><img src="../../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

```
// Sample output

{
  "containingBlockHash": "0x00000000280425e8f1f2170230b3946bf4bf058d5ef9677a3f361d2fbead994f",
  "transactionVersion": "2",
  "size": "116",
  "vSize": "116",
  "lockTime": "0",
  "inputs": [
    {
      "inValue": "4834",
      "inputTxId": "0xe7b262c5ead12343f1c5734b65848fbe19362907fafcd9d07c999c9aa2ec79f0",
      "sourceIndex": "11689",
      "scriptSig": "0x",
      "sequence": "2",
      "fullScriptSigLength": "0",
      "containsFullScriptSig": false
    }
  ],
  "outputs": [],
  "totalInputs": "1",
  "totalOutputs": "0",
  "containsAllInputs": true,
  "containsAllOutputs": true
}
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the transaction ID to confirm the above output.

***

## 5. Get Transaction Confirmations

Retrieves the number of confirmations for a specific transaction based on its transaction ID.

<figure><img src="../../../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
653358
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the transaction ID to confirm the above output.

***

## 6. List Address UTXOs

Returns the UTXOs (Unspent Transaction Outputs) of a Bitcoin address, with pagination support.

<figure><img src="../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

```
// Sample output
[
  {
    "txId": "0xbd7b64df58115ca4e9c273b0bae477de3607154412a517dc31fdf5cd9f46e048",
    "index": "0",
    "value": "197506250"
  },
  {
    "txId": "0x452142a3dc4c9231ef8fd26674fa31ad55dfac5e880183d4b9d7452dd84e8b4f",
    "index": "0",
    "value": "199244750"
  },
  ...
]
```

**Verifying our Output**

Navigate to [https://blockstream.info](https://blockstream.info) and input the Bitcoin address to confirm the above output.
