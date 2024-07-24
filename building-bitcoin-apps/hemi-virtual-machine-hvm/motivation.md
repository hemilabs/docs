# Motivation

{% hint style="info" %}
## 📜 **TL;DR:**

* Current BTC-Relay systems exist with current limitations.
* By embedding a full indexed Bitcoin node directly inside the EVM, hVM allows **anyone** to build custom Bitcoin interoperability infrastructure directly in the EVM, limitation-free.
* dApp developers to build all kinds of Bitcoin-aware dApps and custom Bitcoin interoperability infrastructure on hVM.
{% endhint %}

***

## 🚧 Limitations of Existing Approaches

Various Bitcoin header relay systems have been available on Ethereum as a primitive Bitcoin interoperability technology for nearly a decade. This approach has third-party relayers communicate new Bitcoin headers to a smart contract which maintains a lightweight view of Bitcoin consensus. Smart contracts can then verify a Merkle proof to verify that a specific Bitcoin transaction exists in the canonical Bitcoin chain.

However, this approach has significant limitations:

* Relies on third-party relayers
* Requires large inclusion proofs with expensive validation
* Can only prove a transaction exists in Bitcoin (no UTXO set proofs, no balance proofs, etc.)

Recently, other protocols have designed alternate Bitcoin interoperability primitives like 3-way noncustodial escrow systems validated with zk proofs, or smart-contract-controlled wallets run by the network validator set where network Sequencers facilitate UTXO queries.

However, these other approaches are only designed to serve specific use cases, and still don't provide smart contracts with a complete view of Bitcoin's state. Developers building on these primitives are also forced to accept the governance/security models that these one-off primitives provide, such as trusting a Sequencer doesn't withhold data from a UTXO query.

***

> 💡 With hVM, we set out to create something much more powerful and flexible that enabled anyone to build custom Bitcoin interoperability infrastructure directly in the EVM with complete access to Bitcoin state.

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
