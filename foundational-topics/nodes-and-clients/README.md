# Nodes & Clients

{% hint style="info" %}
## 📜 **TL;DR:**

* In cryptocurrency networks, a `node` is a computer (physical or virtual) that connects to the network, while a `client` is the software \*\*that allows the node to communicate with the network.
* The Hemi Network utilizes **five specialized types of nodes** — Bitcoin finality governors (BFG), Bitcoin-secure sequencers (BSS), Proof-of-Proof miners (PoP), Challengers and modified Geth nodes — to enhance network reliability by distributing functions, thus mitigating the impact of single node failures.
{% endhint %}

***

## 🖥️ **Nodes 101**

* Cryptocurrency networks are powered by a distributed array of computers, each referred to as **a node**, functioning in a peer-to-peer manner where each holds equal standing. Nodes, depending on the client software they run, fulfill different roles within the network.
* For instance, in the Bitcoin network, full nodes store a complete history of transactions for verification purposes, offering high security, while light nodes, focusing on transaction capability, rely on full nodes for information about the network's current state. This setup allows for a flexible network structure where nodes can freely join or leave without disrupting the network's overall functionality.

***

## 🛠️ **Hemi Node Structure**

* In contrast, the Hemi Network employs a more specialized node architecture to optimize network performance and security. It includes:
  * **Bitcoin Finality Governors**: Ensures transactions achieve finality on the Bitcoin blockchain.
  * **Bitcoin-Secure Sequencers**: Orders transactions in a secure manner, leveraging Bitcoin's security.
  * **Proof-of-Proof Miners:** Validates transactions across blockchains without requiring the entire blockchain data.
  * **Challengers**: Monitors and verifies the correctness of transactions and state proofs.
  * **Modified Geth Node:** Manages Ethereum transactions and block headers in a way tailored for Hemi’s bridging protocols.
* This segmentation of responsibilities across different node types significantly enhances the Hemi Network's fault tolerance. By isolating specific functions to particular node types, the network ensures that issues within one node type do not compromise the entire network's operations, thereby improving the system's overall reliability.
* This architecture allows user clients to interact seamlessly with both the Bitcoin and Ethereum networks without the complexity of managing diverse node functions.
