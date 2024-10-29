# Contract Verification

{% hint style="info" %}
## 📜 **TL;DR:**

* This guide explains how to verify smart contracts deployed on the Hemi blockchain using two methods:
  1. Manual UI-based verification via Blockscout.
  2. API-based verification using tools like Hardhat and Foundry/Forge.
{% endhint %}

***

## 🏁 Prerequisites

* Hemi RPC URL and deployed contract address.
* Contract source code available (flattened only if verifying manually via the Hemi Blockscout UI).

***

## 🖥️ Blockscout UI Verification&#x20;

{% hint style="info" %}
Manual verification is performed directly through the Blockscout UI. This method requires flattening the contract source code and uploading it manually.
{% endhint %}

#### 1. Flatten the contract

Flattening a contract is necessary when verifying through the UI.&#x20;

**For Hardhat:**

```
npx hardhat flatten contracts/MyContract.sol > MyContractFlattened.sol
```

**For Foundry:**

```
forge flatten src/MyContract.sol > MyContractFlattened.sol
```

***

#### 2. Access Hemi Blockscout

Go to Hemi Blockscout Explorer and navigate to the [Verify & Publish Contract](https://testnet.explorer.hemi.xyz/contract-verification) page.

***

#### 3. Input contract information

* `Smart contract / Address`:  Paste the address that your smart contract was deployed to.
* `Contract license`:  Select 'No License' unless otherwise specified.
* `Verification method`: Choose Solidity (Flattened source code).
* `Is Yul contract`: Leave unchecked unless your contract is written in Yul.
* `Include nightly builds`: Select only if required.
* `Compiler`: Choose the exact version specified in `pragma solidity X.X.X` in your code.
* `EVM Version`: Set to default unless you used a specific EVM version.
* `Optimization enabled`: Deselect optimization.

Copy and paste the entire flattened contract code into the Contract code field and click 'Verify & publish'.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

***

#### 4. Submit for verification 🎉

Once all required details are entered, submit the form. BlockScout will compare the uploaded source code with the deployed bytecode. If they match, your contract will be verified.

{% hint style="success" %}
To confirm verification, search for your contract address on BlockScout. A green check mark next to your contract indicates successful verification.
{% endhint %}

<figure><img src="../.gitbook/assets/image (2).png" alt="" width="375"><figcaption></figcaption></figure>

***

## 🚧 Hardhat Verification

#### 1. Install dependencies

If you haven't already installed Hardhat and the verification plugin (adapted for Blockscout), run the following:

```
npm install --save-dev hardhat @nomiclabs/hardhat-etherscan @nomicfoundation/hardhat-verify
```

***

#### 2. Configure Hardhat for Hemi

In your \``hardhat.config.js`\`, set up the Hemi network and include Blockscout API information for contract verification:

```javascript
require('dotenv').config()
require("@nomiclabs/hardhat-ethers");
require("@nomicfoundation/hardhat-verify");

module.exports = {
  solidity: "0.8.20",
  networks: {
    hemi: {
      url: "https://testnet.rpc.hemi.network/rpc",
      chainId: 743111,
      accounts: [`0x${process.env.PRIVATE_KEY}`],
    },
  },
  etherscan: {
    apiKey: {
      // Is not required by blockscout. Can be any non-empty string
      'hemi-sepolia': "abc"
    },
    customChains: [
      {
        network: "hemi-sepolia",
        chainId: 743111,
        urls: {
          apiURL: "https://testnet.explorer.hemi.xyz/api",
          browserURL: "https://testnet.explorer.hemi.xyz",
        }
      }
    ]
  },
  sourcify: {
    enabled: false
  }
};
```

***

#### 3. Verify the contract

Once deployed, you can verify the contract using Hardhat’s \``verify`\` command. Make sure to include any constructor arguments if necessary:

```
npx hardhat verify --network hemi <DEPLOYED_CONTRACT_ADDRESS> "Constructor Argument 1" "Constructor Argument 2"
```

***

#### 4. Verification successful! 🎉

{% hint style="warning" %}
If you encounter the following error, visit the [Hemi Block Explorer](https://testnet.explorer.hemi.xyz) and search your contract address to confirm verification:
{% endhint %}

```
hardhat-verify found one or more errors during the verification process:

Etherscan:
The block explorer's API responded that the contract contracts/MyToken.sol:MyToken at <CONTRACT ADDRESS> is already verified.
This can happen if you used the '--force' flag. However, re-verification of contracts might not be supported
by the explorer (e.g., Etherscan), or the contract may have already been verified with a full match.
```

***

## 🏗️ Foundry / Forge Verification

#### 1. Install Foundry

If you haven’t installed Foundry, you can do so by running:

```
curl -L https://foundry.paradigm.xyz | bash
foundryup
```

***

#### 2. Set Up Forge Project

To set up a Forge project, initialize the project:

```javascript
mkdir my-foundry-project
cd my-foundry-project
forge init
```

***

#### 3. Deploy your contract

Deploy your contract to Hemi using Forge:

```
forge create --rpc-url <URL> --private-key $PRIVATE_KEY src/MyContract.sol:MyContract
```

***

#### 4. Verify the contract 🎉

Use the following command to verify the contract using the Blockscout API:

```
forge verify-contract --chain-id 743111 --etherscan-api-key YOUR_BLOCKSCOUT_API_KEY --watch CONTRACT_ADDRESS src/MyContract.sol:MyContract
```

{% hint style="info" %}
Make sure to replace `YOUR_BLOCKSCOUT_API_KEY` and `CONTRACT_ADDRESS` with your actual values.
{% endhint %}

***

