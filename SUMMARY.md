# Table of contents

## 🏠 Main

* [Welcome to the Hemi Docs](README.md)
* [Getting Started](main/start-here/README.md)
  * [Developer Quickstart](main/start-here/developers.md)
  * [Enthusiast Quickstart](main/start-here/enthusiasts.md)
  * [Miner Quickstart](main/start-here/miners.md)
* [Network Details](main/network-details.md)

## ⛰️ Foundational Topics

* [The Architecture](foundational-topics/the-architecture/README.md)
  * [Consensus and Security Protocols](foundational-topics/the-architecture/consensus-and-security-protocols.md)
  * [Sequencer Consensus](foundational-topics/the-architecture/sequencer-consensus/README.md)
    * [PoS-Only Pitfalls](foundational-topics/the-architecture/sequencer-consensus/pos-only-pitfalls.md)
    * [PoS Solutions](foundational-topics/the-architecture/sequencer-consensus/pos-solutions.md)
  * [Proof-of-Proof (PoP)](foundational-topics/the-architecture/proof-of-proof/README.md)
    * [Proof-of-Proof Consensus & Bitcoin Finality](foundational-topics/the-architecture/proof-of-proof/pop-consensus-and-bitcoin-finality.md)
    * [Proof-of-Proof vs. Merged Mining](foundational-topics/the-architecture/proof-of-proof/proof-of-proof.md)
    * [Running a PoP Mining](foundational-topics/the-architecture/proof-of-proof/pop-mining.md)
  * [Tunnels](foundational-topics/the-architecture/tunneling/README.md)
    * [Ethereum Tunnel](foundational-topics/the-architecture/tunneling/ethereum-tunnel.md)
    * [Bitcoin Tunnel](foundational-topics/the-architecture/tunneling/bitcoin-tunnel.md)
  * [Ethereum Virtual Machine (EVM)](foundational-topics/the-architecture/ethereum-virtual-machine-evm.md)
  * [Blocks](foundational-topics/the-architecture/blocks.md)
  * [Transactions](foundational-topics/the-architecture/transactions.md)
  * [Gas](foundational-topics/the-architecture/gas.md)
  * [Nodes & Clients](foundational-topics/the-architecture/nodes-and-clients.md)
  * [Staking](foundational-topics/the-architecture/staking.md)
* [Ethereum Rollups](foundational-topics/ethereum-rollups/README.md)
  * [Pros & Cons](foundational-topics/ethereum-rollups/pros-and-cons.md)
  * [Decentralized Rollups](foundational-topics/ethereum-rollups/decentralized-rollups.md)
* [Wallet Support](foundational-topics/wallet-support.md)

## 📖 How-To Tutorials

* [Using Hemi](how-to-tutorials/using-hemi/README.md)
  * [Tunnel from Ethereum](how-to-tutorials/using-hemi/tunnel-from-ethereum/README.md)
    * [Tunnel ERC20s via Native Tunnel](how-to-tutorials/using-hemi/tunneling/tunnel-eth-to-hemi.md)
    * [Tunnel ERC20s via 3rd Party](how-to-tutorials/using-hemi/tunnel-from-ethereum/tunnel-erc20s-via-3rd-party/README.md)
      * [Tunnel via Stargate](how-to-tutorials/using-hemi/tunnel-from-ethereum/tunnel-erc20s-via-3rd-party/tunnel-via-stargate.md)
  * [Tunnel from Bitcoin](how-to-tutorials/using-hemi/tunnel-from-bitcoin/README.md)
    * [Tunnel BTC via Native Tunnel](how-to-tutorials/using-hemi/tunneling/tunnel-btc-to-hemi.md)
    * [Tunnel BTC via 3rd Party](how-to-tutorials/using-hemi/tunnel-from-bitcoin/tunnel-btc-via-3rd-party.md)
  * [Wallet Setup](how-to-tutorials/using-hemi/wallet-setup/README.md)
    * [EVM Wallet Setup](how-to-tutorials/tutorials/metamask-wallet-setup.md)
    * [BTC Wallet Setup](how-to-tutorials/using-hemi/wallet-setup/btc-wallet-setup/README.md)
      * [Switch Bitcoin Network](how-to-tutorials/using-hemi/wallet-setup/btc-wallet-setup/switch-bitcoin-network.md)
  * [Developer Tooling](how-to-tutorials/using-hemi/developer-tooling/README.md)
    * [Set Up a Safe Wallet](how-to-tutorials/tutorials/set-up-a-safe-wallet.md)
    * [Create a Capsule](how-to-tutorials/using-hemi/developer-tooling/create-a-capsule.md)
    * [Mint a Hemi Hatchling NFT](how-to-tutorials/using-hemi/developer-tooling/mint-a-hemi-hatchling-nft.md)
  * [PoP Mining](how-to-tutorials/using-hemi/pop-mining/README.md)
    * [CLI PoP Miner](how-to-tutorials/using-hemi/pop-mining/setup-part-1.md)
    * [\[mainnet draft\] of CLI PoP Miner](how-to-tutorials/using-hemi/pop-mining/setup-part-1-1.md)
    * [Web PoP Miner](how-to-tutorials/using-hemi/pop-mining/web-based-pop-miner.md)
    * [Add tHEMI to MetaMask](how-to-tutorials/using-hemi/pop-mining/add-themi-to-metamask.md)
* [Developing on Hemi](how-to-tutorials/developing-on-hemi/README.md)
  * [General](how-to-tutorials/developing-on-hemi/general/README.md)
    * [HelloWorld.sol](how-to-tutorials/developing-on-hemi/general/using-remix-ide.md)
    * [Deploy an ERC-20 Token](how-to-tutorials/tutorials/erc-20.md)
  * [hVM & hBK](how-to-tutorials/developing-on-hemi/hvm-and-hbk/README.md)
    * [Using the hBK Demo App](how-to-tutorials/developing-on-hemi/hvm-and-hbk/using-the-hbk-demo-app.md)
    * [Get Bitcoin Balance with Remix](how-to-tutorials/developing-on-hemi/hvm-and-hbk/using-remix-ide.md)

## ⚙️ Building Bitcoin Apps

* [Introduction](building-bitcoin-apps/introduction.md)
* [Hemi Virtual Machine (hVM)](building-bitcoin-apps/hemi-virtual-machine-hvm/README.md)
  * [Motivation](building-bitcoin-apps/hemi-virtual-machine-hvm/motivation.md)
  * [Feature Summary](building-bitcoin-apps/hemi-virtual-machine-hvm/feature-summary.md)
  * [Deploy on hVM](building-bitcoin-apps/hemi-virtual-machine-hvm/deploy-on-hvm.md)
* [Hemi Bitcoin Kit (hBK)](building-bitcoin-apps/hemi-bitcoin-kit-hbk/README.md)
  * [Overview](building-bitcoin-apps/hemi-bitcoin-kit-hbk/overview.md)
  * [hBK Smart Contract](building-bitcoin-apps/hemi-bitcoin-kit-hbk/hbk-smart-contract.md)

## ⚙️ Tooling

* [viem](tooling/viem.md)
* [Contract Addresses](tooling/contract-addresses.md)
* [Contract Verification](tooling/contract-verification.md)
* [Oracles](tooling/oracles.md)

## 📝 Incentives

* [Incentives](incentives/incentives.md)
* [Points](incentives/points.md)
* [Grants](incentives/grants.md)
* [Retroactive Funding](incentives/retroactive-funding.md)
* [One-Off Spends](incentives/one-off-spends.md)
* [Hemi Pilot Program](incentives/hemi-pilot-program.md)

## ⚡ Additional Resources

* [Partners](additional-resources/partners.md)
* [FAQ](additional-resources/smart-contract-deployments.md)
* [Official Links](additional-resources/official-links.md)
* [Brand Kit](additional-resources/brand-kit.md)

## 📨 Send Feedback

* [Contact Us](send-feedback/contact-us.md)
* [Report a Bug](send-feedback/report-a-bug.md)
