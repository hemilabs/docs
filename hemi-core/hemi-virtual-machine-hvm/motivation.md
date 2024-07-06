# Motivation

{% hint style="info" %}
## 📜 **TL;DR:**

* Current BTC-Relay systems exist with current limitations.
* By embedding a full indexed Bitcoin node directly inside the EVM, hVM allows **anyone** to build custom Bitcoin interoperability infrastructure directly in the EVM, limitation-free.
* dApp developers to build all kinds of Bitcoin-aware dApps and custom Bitcoin interoperability infrastructure on hVM.
{% endhint %}

***

## 🚧 Relay Limitations

* Current BTC-Relay systems exist with current limitations:
  * Rely on third-party relayers
  * Require large proofs with expensive validation
  * Can only prove a transaction exists in Bitcoin (no UTXO set proofs, no balance proofs, etc.)
* Other protocols have designed alternate Bitcoin interoperability primitives that serve ONLY **specific use cases** like 3-party noncustodial escrow, or smart-contract-controlled wallets run by the network validator set.&#x20;
* dApp developers are limited to the narrow functionality and forced governance/security models that these enshrined primitives provide.

***

> 💡 With hVM, we set out to create something much more powerful and flexible that enabled anyone to build custom Bitcoin interoperability infrastructure directly in the EVM.

***

## 🔍 How?

By embedding a full indexed Bitcoin node directly inside the EVM, hVM:

* Does not involve any relayer system or trust assumption
* Does not require validation of any expensive proofs
* Supports secure queries for Bitcoin information that requires processing the entire chain like UTXOs, balances, and eventually popular Bitcoin metaprotocols

***

## 🏗️ Use Cases

hVM enables dApp developers to build all kinds of Bitcoin-aware dApps and custom Bitcoin interoperability infrastructure which was previously infeasible or outright impossible on other networks.

**Some use cases of hVM include:**

* Non-custodial BTC<->ETH asset exchanges
* Bitcoin MEV marketplaces
* Bitcoin lending markets
* Bitcoin staking systems
* Custom smart-wallets with configurable validator sets and signing technology
* Custom Bitcoin tunnels (Hemi’s own standard Bitcoin tunnel is being built entirely on hVM)
