---
hidden: true
---

# Ethereum Tunnel

{% hint style="info" %}
## 📜 **TL;DR:**

* Hemi’s Ethereum Tunnels facilitate secure and efficient asset transfers between Ethereum and the Hemi network.&#x20;
* While similar to other “lock-and-mint” cross-chain mechanisms, Hemi’s Tunnels are distinguished by their integration with Bitcoin’s Proof-of-Work finality model and decentralized dispute mechanisms, offering faster settlement times and enhanced security.
* By integrating these features, Hemi’s Ethereum Tunnels offer a more efficient and secure mechanism for cross-chain asset transfers, benefiting from both Ethereum’s smart contract capabilities and Bitcoin’s unrivaled security.
{% endhint %}

***

## 🚊 How Ethereum Tunnels Work

The Ethereum Tunnel process involves locking assets on one network while minting corresponding representative tokens on the other network. For Ethereum-native assets, tokens are minted on Hemi once the assets are locked in a Hemi validation contract on Ethereum.

This allows seamless asset transfers across chains, enabling users to leverage the strengths of both networks while minimizing the friction of cross-chain operations.

#### **Deposit to Hemi**

1. The process begins with the user initiating a deposit transaction on Ethereum. This deposit locks up Ethereum-native tokens in a Hemi validation contract on Ethereum. The validation contract plays a critical role by securing the assets and ensuring they remain locked throughout the tunneling process.
2. Once the deposit is secured in an Ethereum block, Hemi’s block derivation protocol kicks in. The Sequencer, responsible for ordering and generating Hemi blocks, is required to include the deposit in the first Hemi block derived from the Ethereum block that contains the deposit transaction. This ensures that the deposit is acknowledged in Hemi’s L2 environment almost immediately after its validation on Ethereum.&#x20;
3. After the deposit is included, Hemi mints a representative token on the Hemi Network, which serves as the equivalent of the locked asset on Ethereum. This token can now be freely used within the Hemi ecosystem, allowing users to engage with dApps or perform any transaction that requires the asset.

#### **Withdrawal to Ethereum**

1. To return the assets back to Ethereum, the user submits a withdrawal transaction on Hemi. When the withdrawal request is submitted, the representative tokens on Hemi are burned, which signals the user’s intent to withdraw their corresponding Ethereum-native assets.&#x20;
2. Hemi’s state transition system updates its rollup state root, which is then submitted to Ethereum by a Publisher. The state root acts as a cryptographic proof of the transactions that occurred on Hemi, including the user’s withdrawal request.
3. The key to finalizing the withdrawal lies in Hemi’s use of Bitcoin finality, which is a significant differentiator from other optimistic rollup bridges. (In traditional optimistic rollups, the finality of cross-chain transactions is delayed by a dispute window, during which fraud proofs can be raised. Hemi accelerates this process by leveraging Bitcoin’s highly secure Proof-of-Work consensus mechanism to finalize the state root on Ethereum.)
4. Once Bitcoin finality is achieved, and assuming no disputes are raised through the decentralized Challenger role, the state root is confirmed, and the user can submit a withdrawal proof on Ethereum to claim their assets from the Hemi validation contract.
5. The withdrawal proof ensures that the burned representative tokens on Hemi correspond to the original locked Ethereum-native tokens. Upon successful validation of the proof, the Ethereum-native assets are unlocked, completing the cross-chain asset transfer.

***

## 🔄 Tunneling Hemi-Native and Bitcoin-Native Assets to Ethereum

Hemi’s tunneling process is not limited to Ethereum-native assets. Phase 2 of Hemi's Ethereum Tunnel will support Hemi-native and Bitcoin-native assets, extending the functionality of the tunnels to a broader range of assets. This capability is crucial for enabling the use of Bitcoin within Ethereum’s extensive decentralized finance (DeFi) ecosystem, which traditionally lacks native Bitcoin interoperability.&#x20;

#### **Withdrawal to Ethereum**

1. The process for tunneling Hemi-native assets begins with the user submitting a deposit transaction on Hemi, locking their native assets within Hemi’s native asset tunnel contract.&#x20;
2. Similar to Ethereum-native asset transfers, the state root containing this deposit transaction is published to Ethereum.&#x20;
3. Once the rollup state root is confirmed (following Bitcoin finality and the absence of any disputes), the user submits a deposit proof on Ethereum to claim the corresponding representative tokens. These tokens represent the Hemi-native assets within the Ethereum ecosystem and can be used in Ethereum dApps or traded just like any other Ethereum-based token.

**Deposit to Hemi**

1. Moving Hemi-native assets back to Hemi from Ethereum involves a similar process. The user initiates a withdrawal on Ethereum, burning the representative tokens.&#x20;
2. This triggers Hemi’s block derivation protocol to include the withdrawal in the next Hemi block derived from the corresponding Ethereum block.&#x20;
3. Once the withdrawal is processed, the Hemi-native assets are transferred from Hemi’s native asset tunnel contract back to the user, completing the return to Hemi’s L2 environment.

One of the core advantages of this system is its flexibility. It allows Bitcoin-native assets, which are traditionally siloed on the Bitcoin network, to be tunneled through Hemi and into Ethereum. This enables Bitcoin to participate in Ethereum’s DeFi ecosystem while maintaining the security and decentralization that Bitcoin’s Proof-of-Work consensus provides.

***

## 🔍 Comparison to Standard Ethereum Bridges

While Hemi’s Ethereum Tunnels share the foundational principles of traditional bridges like the  Standard Bridge, there are several critical distinctions:

* The primary distinction between Hemi’s Tunnels and standard bridges lies in the finality model and security architecture. Standard bridges depend on an optimistic model with a delayed dispute window. The withdrawal process on these bridges typically takes **a week or longer**, as they await the potential for fraud proofs before finalizing the transaction.
* Hemi Tunnels enhance this process by incorporating Bitcoin finality. Instead of relying solely on an Ethereum-based dispute window, Hemi uses Bitcoin’s Proof-of-Work consensus as an additional layer of security. This allows Hemi to finalize transactions more quickly, as the Bitcoin network’s finality period is shorter and more secure than the traditional dispute windows of optimistic rollups.
* Hemi will decentralize the dispute process by distributing the Challenger role across a wider set of participants. This decentralization mitigates the risk of collusion or centralization of power within the bridging system, offering a more secure alternative to centralized or semi-centralized dispute mechanisms found in standard bridges.
