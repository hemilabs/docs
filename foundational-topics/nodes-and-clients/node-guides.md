---
hidden: true
---

# Node Guides

## Proof-of-Proof Miners (PoP Miners)

#### 🌐 Overview

* PoP Miners embed Hemi headers — L2 keystones — into Bitcoin blocks, effectively “anchoring” Hemi state to Bitcoin’s security.
* PoP Miners receive Hemi headers from a BFG, create BTC transactions with those headers, and forward them to Bitcoin for inclusion in blocks.
* Successful PoP Miners are earn rewards on the Hemi network, incentivizing them to maintain network operation.

#### **🙋‍♂️ Who might run a PoP Miner?**

* **Network Miners and Operators:** Operators or enthusiasts who want to earn rewards by using their Bitcoin node connectivity. More PoP miners = stronger finality guarantees.

#### **🏁 Requirements**

**➡️ View complete instructions via the** [**PoP Miner tutorial.**](../../how-to-tutorials/using-hemi/pop-mining/setup-part-1/)

***

## Bitcoin Finality Governor (BFG)

#### **🌐 Overview**

* BFG nodes look for Proof-of-Proof (PoP) transactions that embed Hemi headers into Bitcoin, determining if Hemi blocks have attained Bitcoin-level finality.
* BFG nodes serve as the “checkpoint” mechanism for finality by confirming whether competing versions of Hemi blocks exist on-chain and identifying possible reorgs. The nodes then supply Hemi data to PoP Miners, parse resulting PoP transactions and communicate finality info to BSS nodes.

#### **🙋‍♂️ Who might run a BFG node?**

* **PoP Miners:** A custom BFG daemon can notify your local PoP miner and this will broadcast them to your Electrs+bitcoind setup so you don't rely on Hemi Labs — or any third party — which may be congested.
* **Enterprise Node Operators:** Exchanges, large dApp platforms, or custodial services that need independent, verifiable finality checks on Hemi transactions.

#### **🏁 Requirements**

* A PostgreSQL database, bfgd expects the sql scripts in `./database/bfgd/scripts/` to be run to set up your schema.
* A connection to:
  * An Electrs node on the proper Bitcoin network (testnet or mainnet).
  * bitcoind
  * bfgd

**➡️ View complete instructions via the** [**hemilabs GitHub repo.**](https://github.com/hemilabs/heminetwork?tab=readme-ov-file#%EF%B8%8F-running-bfgd)

***

## Bitcoin-Secure Sequencers (BSS Nodes)

#### 🌐 Overview

* BSS nodes combine Hemi transactions with Ethereum mainnet batches, creating a hybrid solution that inherits Bitcoin security signals (via BFG) and uses Ethereum’s smart contract capabilities.
* These nodes coordinate staking, unstaking, and slashing operations to secure the network, while incorporating finality checkpoints from the BFG. BSS nodes also facilitate cross-chain asset transfers by ensuring that Hemi’s on-chain transactions align with Ethereum-based bridging logic.

#### **🙋‍♂️ Who might run a BSS node?**

* **Validator/Sequencer Operators:** Entities responsible for generating Hemi blocks and maintaining chain consensus.

#### **🏁 Requirements**

* Connect to a live [bfgd](https://github.com/hemilabs/heminetwork/blob/main/cmd/bfgd) instance.

**➡️ View complete instructions via the** [**hemilabs GitHub repo.**](https://github.com/hemilabs/heminetwork?tab=readme-ov-file#%EF%B8%8F-running-bssd)

***

## Modified Geth Node

#### **🌐 Overview**

* Hemi Network runs a specialized Geth implementation that supports extended functionalities, enabling seamless interaction between Hemi’s chain state and Ethereum’s mainnet.
* This modified Geth node manages Ethereum transactions and block headers in a way tailored for Hemi’s bridging protocols. The node also consolidates Ethereum state so that BSS nodes (and other Hemi components) can quickly verify or execute cross-chain logic.

#### **🏁 Requirements**

* Clone the [Hemi Network GitHub](https://github.com/hemilabs/heminetwork) and follow instructions for the Modified Geth build.
