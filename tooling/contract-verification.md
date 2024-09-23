---
hidden: true
---

# Contract Verification

{% hint style="info" %}
## 📜 **TL;DR:**

* This guide explains how to verify smart contracts deployed on the Hemi blockchain using two methods:
  1. API-based verification using tools like Hardhat and Foundry/Forge.
  2. Manual UI-based verification via Blockscout.
{% endhint %}

***

## 🏁 Prerequisites

* Hemi RPC URL and deployed contract address.
* Contract source code available (flattened only if verifying manually via the Hemi Blockscout UI).
* API key from Hemi Blockscout (only needed for API-based verification).

***

## 🚧 API-Based Contract Verification

API-based verification is the preferred method since it automates the process using development tools like Hardhat or Foundry/Forge.&#x20;

### Hardhat Verification

#### 1. Install dependencies

If you haven't already installed Hardhat and the Etherscan plugin (adapted for Blockscout), run the following:

```
npm install --save-dev hardhat @nomiclabs/hardhat-etherscan
```

***

#### 2. Configure Hardhat for Hemi

In your \``hardhat.config.js`\`, set up the Hemi network and include Blockscout API key information for contract verification:

```javascript
require("@nomiclabs/hardhat-etherscan");

module.exports = {
  solidity: "0.8.4",
  networks: {
    hemi: {
      url: "RPC_URL",
      accounts: [process.env.PRIVATE_KEY]
    }
  },
  etherscan: {
    apiKey: {
      hemi: "YOUR_BLOCKSCOUT_API_KEY"
    },
    customChains: [
      {
        network: "Hemi Sepolia",
        chainId: 43111, // Hemi Sepolia Chain ID
        urls: {
          apiURL: "API_URL",
          browserURL: "https://testnet.explorer.hemi.xyz"
        }
      }
      {
        network: "Hemi Mainnet",
        chainId: 43111, // Hemi mainnet Chain ID
        urls: {
          apiURL: "MAINNET_API_URL",
          browserURL: "MAINNET_EXPLORER_URL"
        }
      }    
    ]
  }
};
```

***

#### 3. Deploy your contract

Deploy your contract using Hardhat (assuming it hasn’t already been deployed):

```
npx hardhat run scripts/deploy.js --network hemi
```

***

#### 4. Verify the contract 🎉

Once deployed, you can verify the contract using Hardhat’s \``verify`\` command. Make sure to include any constructor arguments if necessary:

```
npx hardhat verify --network hemi <DEPLOYED_CONTRACT_ADDRESS> "Constructor Argument 1" "Constructor Argument 2"
```

***

### Foundry / Forge Verification

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
forge verify-contract --chain-id 12345 --etherscan-api-key YOUR_BLOCKSCOUT_API_KEY --watch CONTRACT_ADDRESS src/MyContract.sol:MyContract
```

{% hint style="info" %}
Make sure to replace `YOUR_BLOCKSCOUT_API_KEY` and `CONTRACT_ADDRESS` with your actual values.
{% endhint %}

***

### Blockscout UI Verification&#x20;

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

Go to Hemi Blockscout Explorer and navigate to the Verify & Publish Contract page.

***

#### 3. Input contract information

Input your deployed contract address, contract license, and contract verification method.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

***

#### 4. Submit for verification 🎉

Once the required details are entered, submit the form. Blockscout will match the uploaded source code with the deployed bytecode, and if they match, your contract will be verified.

