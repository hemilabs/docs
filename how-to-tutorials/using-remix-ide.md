---
description: 🟩 This is a beginner track.
---

# Using Remix IDE

{% hint style="info" %}
## 📜 **TL;DR:**

* In this tutorial, we will utilize [Remix IDE](https://remix.ethereum.org/), a versatile, open-source web-based platform, to develop and deploy our smart contract onto Hemi Testnet.
* Ensure to use Solidity version **0.8.19 or earlier** for compatibility with the Hemi testnet environment.&#x20;
{% endhint %}

***

## 🏁 Prerequisites

1. [MetaMask Wallet Setup](metamask-wallet-setup/)
2. [Tunnel ETH to Hemi](tunnel-eth-to-hemi.md)

***

## 📚 Tutorial

### 1. Go to [Remix IDE](https://remix.ethereum.org/)

Remix IDE is a powerful, open-source web application for developing, compiling, and deploying Ethereum smart contracts with ease.

***

### 2. **Add the Smart Contract**

In Remix IDE, start by creating a new file named `HelloWorld.sol`.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/aASuOiQQ-J-6OoH-J-Nbg\_image.png)

* The following contract is a basic example designed for interaction. Copy the code below and paste it into the file `HelloWorld.sol`.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract HelloWorld {
    string public greeting = "Hello, World!";

    function getGreeting() public view returns (string memory) {
        return greeting;
    }

    function setGreeting(string memory _greeting) public {
        greeting = _greeting;
    }
}
```

***

### **3. Compile the Contract**

{% hint style="warning" %}
Ensure that the Solidity Compiler is configured to **version 0.8.19** or earlier. This is necessary for compatibility with the current smart contract requirements.&#x20;
{% endhint %}

Select `Compile HelloWorld.sol` button to use the Remix IDE's Solidity compiler. Check for any compilation errors and fix them.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/AlgvMWAYUOl5sELM5jnQg\_image.png)

***

### 4. Connect Remix To MetaMask&#x20;

{% hint style="warning" %}
The address you choose to connect **MUST** have a minimum balance of 0.10 ETH to pay for contract deployment fees. Refer back to earlier documentation to[ fund your Hemi address ](tunnel-eth-to-hemi.md)with ETH.&#x20;
{% endhint %}

Choose `Injected Provider - MetaMask` under "Environment".

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/b8Rpm5EDGY6VtoKaUGcB6\_image.png)

***

### 5. Confirm the Connection

* A pop-up from MetaMask will appear to confirm the connection. Select `Next`.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/DVAbARozcEhgs9u-aX12U\_image.png)

* Select `Connect`

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/jqNegecBy\_X2a2NY87n30\_image.png)

***

### 6. Link to Hemi Account

* Link to the relevant Hemi account in the "Account" drop-down.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/r5KAbf\_1pEkJBohPVd0Pk\_image.png)

***

### 7. Deploy

Execute the deployment of your smart contract to the Hemi network directly from Remix IDE.

{% hint style="warning" %}
Uncheck `Publish to IPFS.`Note: if you get a warning about Gas Limit, you may ignore it and proceed.&#x20;
{% endhint %}

* Select `Deploy`

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/1u--sVUSTA7c7XWMGdUtS\_image.png)

* Your MetaMask will pop-up to confirm the deployment of your smart contract. Select `Confirm`

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/ADm4Lo3PartN9VdYIQJj9\_image.png)

🥳 Whoooo! If successful you should see a ✅ in the console.

⚠️ If it fails, double check that the Solidity version in the compiler is the correct version.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/AlgvMWAYUOl5sELM5jnQg\_image.png)
