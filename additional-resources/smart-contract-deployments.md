# FAQ

## General

<details>

<summary>Where can I learn more about Hemi?</summary>

You can learn more about Hemi by reading our documentation, visiting our website, reading the whitepaper, or joining the community on Discord.

</details>

<details>

<summary>How do I earn points, and how does incentivized testnet work?</summary>

Check out [incentives.md](../incentives/incentives.md "mention") for the most recent info.

</details>

## Smart Contract Deployments

<details>

<summary><strong>Why is my smart contract deployment failing on the testnet even though the contract seems to be created?</strong></summary>

**🌐 Overview**

* Deployment issues on testnet can stem from using features or opcodes not yet supported by the testnet's version of the EVM.

-   Check the `Raw trace` tab

    <figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

**👀 Common Culprits**

* <mark style="color:blue;">One frequent cause is the use of the</mark> <mark style="color:blue;">`PUSH0`</mark><mark style="color:blue;">opcode, which was introduced in</mark> <mark style="color:blue;">**EIP-3855**</mark> <mark style="color:blue;">with the</mark> _<mark style="color:blue;">**Shanghai upgrade**</mark>_<mark style="color:blue;">.</mark>

**✅ Solutions**

* To avoid such issues, it's best to wait until testnet officially supports these new features before attempting to deploy contracts that rely on them.
* 📜 We will make an announcement when we update this soon!

</details>

<details>

<summary>Gas Usage (e.g. are you at 100%?)</summary>

**🌐 Overview**

* Deployment failures can often be traced back to insufficient gas allocation.
* When a transaction consumes all allocated gas without completing, the network rejects it to avoid executing transactions that could run indefinitely.

**👀 Common Culprits**

* **100% Gas Consumption:** If a transaction fails and the gas usage is 100%, it suggests the gas limit set for the contract's deployment was too low to cover the computation required.
  * Check `Gas usage & limit by txn`

**✅ Solutions**

* **Increase Gas Limit:** Adjust the gas limit upwards based on the complexity of your contract and the estimations provided by gas estimation tools.
* **Optimize Contract Code:** Review and optimize your smart contract code to reduce gas consumption. This can involve simplifying functions, removing unnecessary operations, or leveraging patterns that consume less gas.
* **Test Thoroughly**

</details>

<details>

<summary>Did you verify your Smart Contract?</summary>

**🌐 Overview**

Preparing your smart contract for deployment involves a critical step: <mark style="background-color:green;">verification</mark>. This process not only helps in catching potential issues early but also enhances the contract's integrity before it goes live.

**🔍 Verification is Key**

Verifying your smart contract is paramount to ensure its readiness for deployment. This crucial step provides valuable insights into any potential errors or vulnerabilities that could compromise its performance or security.

**🛠 Steps to Verify:**

* **Navigate to Contract Details:** Access your contract's details within your development environment or via a testnet blockchain explorer where your contract will be deployed.
* Look for the `Verify and Publish` option. **Selecting this begins the verification process, which is essential for assessing whether your contract operates as intended and is ready for interaction with users.**

[Read more](https://docs.blockscout.com/for-users/verifying-a-smart-contract) about verifying smart contracts deployed on Hemi.

</details>

## Navigating the Hemi Portal

<details>

<summary>What tokens are currently supported?</summary>

You can use our platform to access a variety of tokens, including ETH, USDT, USDC, and DAI.

</details>

<details>

<summary>What is tunneling? What is a tunnel?</summary>

The Hemi Tunnel is designed for seamless cross-chain transactions.

Hemi’s Bitcoin and Ethereum Tunnels improve security while decentralizing asset portability. They do this by leveraging the Hemi Virtual Machine, which gives the network direct awareness of Bitcoin’s and Ethereum’s states.

</details>

## Capsules

<details>

<summary>What is Capsule?</summary>

Capsule is an asset transfer protocol that allows anyone to batch and transfer multiple assets in a single package on Hemi. Additionally, it provides users and developers with advanced functionality like gasless transactions, re-routing/recalling, and configurable security. Learn more about Capsule Labs by visiting the Capsule [site](https://capsulelabs.xyz).

</details>

## Grants

<details>

<summary>How do I apply for a grant?</summary>

_wip_

</details>

<details>

<summary>How do we review grants?</summary>

_wip_

</details>

## Getting Involved

<details>

<summary>How do I partner with Hemi?</summary>

You can find the partnership inquiry form [here](https://discord.com/channels/1202677849887080508/1219364577939030220/1219364577939030220).

</details>

<details>

<summary>How do we review partnership inquiries?</summary>

Read our review process in [partners.md](partners.md "mention").

</details>

Have more questions or concerns? E-mail **support@hemi.xyz** or [**join our Discord.**](https://discord.gg/hemixyz)
