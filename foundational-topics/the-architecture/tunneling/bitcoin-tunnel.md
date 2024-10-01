---
hidden: true
---

# Bitcoin Tunnel

{% hint style="info" %}
## 📜 **TL;DR:**

* Hemi’s Bitcoin Tunnel enables the secure transfer of Bitcoin and Bitcoin-native assets (such as Ordinals and BRC-20 tokens) between Bitcoin, Hemi, and eventually, EVM-compatible networks.&#x20;
* The Bitcoin Tunnel contract uses hVM to track Bitcoin addresses and outputs tied to custodianship vaults, ensuring efficient and secure asset management.&#x20;
* Hemi will offer two custodianship models: overcollateralized multisig and BitVM. These ensure decentralized, trust-minimized asset tunneling with high security and performance.
{% endhint %}

***

## 🚊 How Bitcoin Tunnels Work

The Bitcoin Tunnels allow Bitcoin assets to move between Bitcoin and Hemi by locking assets in custodial vaults and minting representative tokens on Hemi. Users can freely use these tokens on Hemi, and eventually, tunnel them to Ethereum or other EVM-compatible networks.

#### **Deposit to Hemi**

1. Users generate a deposit transaction by sending Bitcoin (or Bitcoin-native assets) to the selected custodianship vault’s Bitcoin address, managed by the multisig.
2. Once sent, the Bitcoin assets are locked in the custodianship vault.&#x20;
3. Hemi’s Bitcoin Tunnel verifies the successful deposit on the Bitcoin network by monitoring the UTXO table for the corresponding deposit. If the deposit is successfully verified, the system moves to the next step.
4. Upon verification, Hemi mints representative tokens equivalent to the deposited Bitcoin assets. These tokens are sent to the user’s Hemi address.

#### Withdrawal to Bitcion

1. The user on Hemi initiates a withdrawal transaction by selecting the amount of representative tokens they want to convert back to Bitcoin.
2. These representative tokens are burned on the Hemi network, signaling the system that the user intends to withdraw the corresponding amount of Bitcoin from the custodianship vault.
3. Hemi’s Bitcoin Tunnel updates the rollup state root with the details of the withdrawal transaction. This state root is submitted to Bitcoin by a Publisher to ensure that the withdrawal is accurately recorded.&#x20;
4. Hemi’s Bitcoin Tunnel verifies the correct burning of tokens and prepares the custodianship system for withdrawal.
5. The custodianship vault is notified of the withdrawal request. In the case of a multisig vault, the required number of signatures is collected to authorize the withdrawal.
6. Once verified, the custodianship vault releases the corresponding Bitcoin or Bitcoin-native assets to the user’s Bitcoin address.
7. The hVM system constantly monitors for any unauthorized withdrawals. In Phase 0, this requires an externally owned account (EOA) to flag any potential issues. In later phases, event notifications will allow automatic detection of unauthorized actions. If any misbehavior is detected during the withdrawal process, the responsible custodian is slashed on Hemi, and corrective measures are taken to prevent unauthorized fund transfers.

***

## 🔍 Comparison to Other Bitcoin Interoperabilty Solutions

* Hemi’s Bitcoin Tunnels leverage the power of hVM (Hemi Virtual Machine) to monitor and secure Bitcoin-based asset transfers.&#x20;
* The Bitcoin Tunnel contract uses hVM to track Bitcoin addresses and outputs tied to custodianship vaults, ensuring efficient and secure asset management.&#x20;
* In hVM Phase 0, an externally owned account (EOA) is required to notify the contract of any irregular withdrawals. Once flagged, hVM can verify the offending transaction and respond by slashing misbehaving custodians.&#x20;
* This contrasts with BTC interoperability solutions like BTC header relay, where users must manually construct cryptographic proofs of misbehavior and relay them to the contract for validation, introducing higher costs and risks of error.&#x20;
