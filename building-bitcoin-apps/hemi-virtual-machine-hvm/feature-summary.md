# Feature Summary

{% hint style="info" %}
## 📜 **TL;DR:**

* Smart contracts on Hemi can access Bitcoin data by calling the hVM precompile contract.
* Future protocol upgrades will add additional precompile calls to provide additional information.
{% endhint %}

***

## 🌐 Overview

* Smart contracts on Hemi can access Bitcoin data by calling the hVM precompile contract addresses, which query the deterministic TBC node running inside the EVM.&#x20;
* Future protocol upgrades will add additional precompile calls to provide additional information like Bitcoin fee levels, Bitcoin block construction information, and popular metaprotocols like Ordinals, BRC-20s, and Runes.

***

## ℹ️ "Phase 0" Precompile Summary

<table><thead><tr><th>Name</th><th width="249">Address</th><th>Description</th></tr></thead><tbody><tr><td>BtcBalAddr</td><td>0x40</td><td>Gets the balance of an address in satoshis. Supports all address formats: P2PKH, P2SH, P2WPKH, P2WSH, P2TR.</td></tr><tr><td>BtcUtxosAddrList</td><td>0x41</td><td>Gets the list of Unspent Transaction Outputs (UTXOs) for an address. Supports pagination.</td></tr><tr><td>BtcTxByTxid</td><td>0x42</td><td>Gets parts of a Bitcoin transaction by its TxID. The caller can specify which part(s) of the transaction to return using packed bitflags to increase gas efficiency by dropping unnecessary data.</td></tr><tr><td>BtxTxConfirmations</td><td>0x43</td><td>Gets the number of confirmations a specified transaction by TxID has.</td></tr><tr><td>BtcLastHeader</td><td>0x44</td><td>Gets the most recent Bitcoin header known by hVM.</td></tr><tr><td>BtcHeaderN</td><td>0x45</td><td>Gets the canonical Bitcoin header at height N.</td></tr><tr><td>BtcAddrToScript</td><td>0x46</td><td>Converts a Bitcoin address to its corresponding script representation. Supports all address formats: P2PKH, P2SH, P2WPKH, P2WSH, P2TR.</td></tr></tbody></table>
