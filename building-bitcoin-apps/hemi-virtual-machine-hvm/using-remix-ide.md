# Using Remix IDE

{% hint style="info" %}
## 📜 **TL;DR:**

* In this section, we’ll deploy a small contract in[ Remix IDE](https://remix.ethereum.org) with a single method which calls the Bitcoin Balance precompile and returns the balance as a uint256.&#x20;
* We recommend you use Solidity version **0.8.25 or later**, but previous versions are also expected to work.
{% endhint %}

***

## 🏁 Prerequisites

* To follow along, you’ll need:
  * **Metamask** (or another Remix-supported web wallet) connected to Hemi testnet as a custom network;
  * **A nonzero ETH balance** tunneled over to a Hemi address in your wallet you want to deploy the demo contract with to pay deployment gas fees.

***

## 📚 Tutorial

### 1. Create Contract

* To start, open Remix, delete any existing contracts in the “contracts” folder,.
* Create a new contract file, which for our example we’ll call “BitcoinBalDemo.sol”.
* Paste in the following code:

```solidity
pragma solidity ^0.8.25;

contract BitcoinBalDemo {
    function getBitcoinAddressBalance(string calldata btcAddress) public view returns (uint256 balance) {
    bytes memory converted = bytes(btcAddress);
    (bool ok, bytes memory out) = address(0x40).staticcall(converted);
    require(ok, "Failed to Call Bitcoin Balance hVM Precompile (0x40)");
    
    return uint64(bytes8(out));
  }
}
```

\
You can now compile and deploy this contract, and try out calling it with a Bitcoin address string to see the address's balance (in satoshis) returned by hVM.

