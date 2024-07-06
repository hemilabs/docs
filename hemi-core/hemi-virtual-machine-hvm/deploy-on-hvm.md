# Deploy on hVM

{% hint style="info" %}
## 📜 **TL;DR:**

* To use hVM directly, you will have to call the appropriate precompile address with the appropriate serialized bytes to pass parameters to the function.&#x20;
* Most dApp developers will use the Hemi Bitcoin Kit (hBK) **rather** than hVM directly.&#x20;
{% endhint %}

***

## 🌐 Overview

* To use hVM directly, you will have to call the appropriate precompile address with the appropriate serialized bytes to pass parameters to the function.&#x20;
* Each successful precompile call will return serialized bytes according to the precompile’s return data specification.

***

## 🟨 Developer Tip

> **Most dApp developers will use the Hemi Bitcoin Kit (hBK) rather than hVM directly.**&#x20;

* If you’re looking for an easy way to get started developing Bitcoin-aware dApps on Hemi, checkout the “Hemi Bitcoin Kit (hBK)” section. Understanding how Bitcoin Kit uses hVM under-the-hood may be helpful, and dApp developers looking to maximize gas efficiency may benefit from using hVM directly to avoid paying overhead for unmarshalling data they don’t need for a specific use case.

***

## 📑 Example Contract in Remix

* In this section, we’ll deploy a small contract with a single method which calls the Bitcoin Balance precompile and returns the balance as a uint256. To follow along, you’ll need:
  * **Metamask** (or another Remix-supported web wallet) connected to Hemi testnet as a custom network;
  * **A nonzero ETH balance** tunneled over to a Hemi address in your wallet you want to deploy the demo contract with to pay deployment gas fees.

***

1. ### Create Contract

* To start, open Remix, delete any existing contracts in the “contracts” folder,.
* Create a new contract file, which for our example we’ll call “BitcoinBalDemo.sol”.
* Paste in the following code:

```solidity
pragma solidity ^0.8.0;

contract BitcoinBalDemo {
    function getBitcoinAddressBalance(string calldata btcAddress) public view returns (uint256 balance) {
    bytes memory converted = bytes(btcAddress);
    (bool ok, bytes memory out) = address(0x40).staticcall(converted);
    require(ok, "Failed to Call Bitcoin Balance hVM Precompile (0x40)");
    
    return uint64(bytes8(out));
  }
}
```

## &#x20;
