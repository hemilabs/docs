# Wallet Support

{% hint style="info" %}
## 📜 **TL;DR:**

* The Ethereum network currently comprises a variety of networks with varying functionality, however Hemi builds primarily on only two: Ethereum mainnet and Sepolia.
* The Bitcoin network currently comprises a variety of networks with varying functionality, however Hemi builds primarily on only two: Bitcoin Mainnet and Bitcoin Testnet.
{% endhint %}

***

## 🔵 EVM Wallets

### Key Terms and Concepts

* [**EVM (Ethereum Virtual Machine):**](the-architecture/ethereum-virtual-machine-evm.md) A decentralized computing platform that allows developers to build and deploy smart contracts. MetaMask is an EVM wallet, meaning it can interact with any blockchain compatible with the EVM, not just Ethereum.
* **Private Key:** A secret code that allows you to access and control your cryptocurrency in your wallet. It is crucial never to share your private key with anyone, as it grants complete control over your funds.
* **Public Address:** An address that you can share with others to receive funds. It is a string of alphanumeric characters that acts like an account number on the blockchain.
* **Seed Phrase:** A series of 12 or 24 words that serve as a backup to restore access to your wallet. This phrase should be stored securely and privately; if lost or compromised, you could lose access to your funds.
* **Gas Fees:** Transaction fees paid to miners or validators on the blockchain to process and confirm transactions. Fees vary based on network congestion and the complexity of the transaction.
* **dApps (Decentralized Applications):** Applications that run on a blockchain network rather than a centralized server. MetaMask allows users to interact with dApps directly from their browser.

***

### Ethereum Explorer: Etherscan

[Etherscan](https://etherscan.io) is the primary blockchain explorer for Ethereum, providing a comprehensive interface to view transaction details, address balances, token transfers, and smart contract interactions. It’s an invaluable tool for MetaMask users to verify transaction status, track gas fees, and explore the Ethereum blockchain in depth.

* To view transaction details, address balances, token transfers, and smart contract interactions on the Hemi Network, visit the [Hemi block explorer](https://explorer.hemi.xyz).

***

### Ethereum Networks

The Ethereum network currently comprises a variety of networks with varying functionality, however Hemi build primarily on only two:

* **Ethereum Mainnet:** The primary Ethereum network where real ETH transactions occur. It is the live network that supports the Ethereum economy and decentralized applications (dApps), with transactions being irreversible and involving real value and fees.
* **Sepolia Testnet:** A testing environment for Ethereum that mimics the Mainnet but uses testnet ETH with no real value. It allows developers and users to test applications, transactions, and upgrades without risking real funds, providing a stable and efficient testing ground for Ethereum-based projects.

{% hint style="success" %}
If you are ready to get started with Ethereum, you can learn how to [**set up an EVM wallet** ](../how-to-tutorials/tutorials/metamask-wallet-setup.md)and interact with Ethereum on Hemi.
{% endhint %}



***

## 🟠 BTC Wallets

### Key Terms and Concepts

* **Private Key:** A secret code that allows you to access and control your cryptocurrency in your wallet. It is crucial never to share your private key with anyone, as it grants complete control over your funds.
* **Public Address:** An address that you can share with others to receive funds. It is a string of alphanumeric characters that acts like an account number on the blockchain.
* **Seed Phrase:** A series of 12 or 24 words that serve as a backup to restore access to your wallet. This phrase should be stored securely and privately; if lost or compromised, you could lose access to your funds.
* **Confirmation:** The process by which a Bitcoin transaction is included in a block on the blockchain. Each confirmation represents a layer of verification, with multiple confirmations providing increased security against double-spending.
* **UTXO (Unspent Transaction Output):** A key concept in Bitcoin that represents the amount of Bitcoin available to spend. UTXOs are outputs from previous transactions that have not yet been spent, and they form the balance of your Bitcoin wallet.
* **Mempool (Memory Pool):** The mempool is a holding area for unconfirmed transactions on a blockchain, where they wait to be included in the next block by miners or validators. Transactions are prioritized based on their attached fees; those with higher fees are typically confirmed faster. Monitoring the mempool helps users gauge current network congestion and set appropriate transaction fees for quicker confirmations.

***

### Bitcoin Address Types

Bitcoin addresses are the unique identifiers used to send and receive Bitcoin. Over time, several address types have been introduced to improve Bitcoin’s efficiency, security, and scalability.&#x20;

#### Types of Bitcoin Addresses:

* **Legacy (P2PKH):** This is the original and most widely recognized address format. &#x20;
* **Nested SegWit (P2SH-P2WPKH):** An interim solution that allows the benefits of SegWit while maintaining compatibility with Legacy wallets.
* **Native SegWit (bech32):** Native SegWit, also known as bech32, introduces significant improvements in transaction efficiency and scalability.&#x20;
* **Taproot:** Taproot is the latest upgrade to Bitcoin’s address formats, focusing on enhanced privacy, scalability, and flexibility.

***

### Bitcoin Explorer: Mempool.space

* [Mempool.space](https://mempool.space) is a blockchain explorer for Bitcoin that visualizes the current state of the mempool, the pool of unconfirmed transactions, and provides insights into transaction fees and block confirmations. It is particularly useful for BTC wallet users to check the status of their transactions and understand current network congestion.
* To view transaction details, address balances, token transfers, and smart contract interactions on the Hemi network, visit the [Hemi block explorer](https://explorer.hemi.xyz).

***

### Bitcoin Networks

The Bitcoin network currently comprises a variety of networks with varying functionality, however Hemi build primarily on only two:

* **Bitcoin Mainnet:** The primary Bitcoin network where real BTC transactions occur. It is the live network that supports the Bitcoin economy and has actual value, with transactions being irreversible and fees applying.
* **Bitcoin Testnet:** A testing environment for Bitcoin that mimics the Mainnet but uses test BTC with no real value. Developers and users can test applications, transactions, and upgrades without risking real funds. (Not to be confused with Bitcoin Testnet4, a version of Bitcoin Testnet with updated configurations and more stability for testing purposes. It offers an alternative and more reliable test environment compared to the older Testnet3, with no real value attached to the test BTC.

{% hint style="success" %}
If you are ready to get started with Bitcoin, you can learn how to [**set up a BTC wallet**](../how-to-tutorials/tutorials/btc-wallet-setup/) and interact with Bitcoin on Hemi.
{% endhint %}

***

## 💼 Hardware Wallets

If you use a hardware wallet and want to interact with Hemi, you can connect it through MetaMask to manage your assets securely. This approach allows you to maintain control of your private keys while accessing the Hemi network. For a step-by-step guide on connecting MetaMask with a hardware wallet, please refer to [this guide from Ledger Academy](https://www.ledger.com/academy/security/the-safest-way-to-use-metamask).
