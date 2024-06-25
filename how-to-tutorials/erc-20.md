# ERC-20

{% hint style="info" %}
## 📜 **TL;DR:**

* This tutorial guides you through deploying an ERC-20 token using [Hardhat](https://hardhat.org/), a comprehensive Ethereum development environment. Hardhat is recommended for its powerful features, but you can use any Ethereum development tool.
* Ensure Node.js, Hardhat, and Solidity are set up correctly for effective ERC-20 token development and deployment.
{% endhint %}



***

## 🏁 Prerequisites

1. Download [VSCode ](https://code.visualstudio.com/download)or any other IDE
2. Install [Node.js](https://nodejs.org/en/download/)
3. [MetaMask Wallet Setup](docId:nS1WAge-Myjt-lTwTH710)
4. [Tunnel sepETH to Hemi](docId:xWIKu2QZ4kOETgKTp1CRa)

***

## 📚 Tutorial

### 1. Initialize Your NPM Project

* In your project directory, initialize a Node.js project

```shell
npm init -y
```

***

### 2. Install Hardhat & Ethers.js Plugin

* Install Hardhat along with the Ether.js plugin, and the OpenZeppelin contracts library.

```shell
npm install --save-dev hardhat @nomiclabs/hardhat-ethers ethers @openzeppelin/contracts
```

***

### 3. Create a HardHat Project

a) Inside your Node.js project, start a Hardhat project

```shell
npx hardhat init
```

b) Select `Create an empty hardhat.config.js`

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/vwOqdeFQBmRmd5dn5u5aO\_image.png)

***

### 4. Add Folder

In the root directory of your project, create `contracts` and `scripts` folders:

```shell
mkdir contracts && mkdir scripts
```

***

### 5. Write Your Contract

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/PbdlxnFGjB396RpLZIqHe\_image.png)

* In the `contracts` folder, create a file named `MyToken.sol` . This will be your ERC-20 token contract. Here's a basic example:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("MyToken", "MTK") {
        _mint(msg.sender, initialSupply);
    }
}
```

* This code defines a simple ERC-20 token with an initial supply and basic ERC-20 functionalities.

***

### 6. Compile Your Contract

```shell
npx hardhat compile 
```

***

### 7. Secure Your Private Key for Deployment

a) Export your Private Key from MetaMask:

* Open MetaMask, select your account icon, and go to `Account Details`

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/ZV2mIMUNSoJjryajgnG1F\_image.png)

* Select `Show private key`
* Enter your password.
* Select `Confirm`
* Select the unlock button to reveal your password.

b) Create an `.env` file in the root directory of your project and add your private key.

```none
PRIVATE_KEY=your_exported_private_key
```

:::hint{type="danger"} Ensure this file is never shared or committed to version control. :::

* Sample `.gitignore` code below

```none
node_modules/
.env
artifacts/
cache/
```

c) Install `dotenv` package

```shell
npm install dotenv
```

***

### 8. Configure Hardhat for the Testnet

a) Open `hardhat.config.js` in your project.

b) Configure Hemi Network

* Add the required modules at the top of the config file
* Add the Hemi Network settings in`module.exports`. Ensure you include the network's URL, Chain ID, and the accounts array with your private key (stored in an environment variable for security).

Here's an example configuration:

```javascript
/** @type import('hardhat/config').HardhatUserConfig */
require('dotenv').config()
require("@nomiclabs/hardhat-ethers");

module.exports = {
  solidity: "0.8.20",
  networks: {
    hemi: {
      url: "https://testnet.rpc.hemi.network/rpc",
      chainId: 743111,
      accounts: [`0x${process.env.PRIVATE_KEY}`],
    },
  }
};
```

***

### 9. Write a Deployment Script

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/2-Ua8\_3VwJN89awF\_u9lH\_image.png)

In the `scripts` folder, create a file named `deploy.js` to write a script for deploying your contract.

```javascript
const { ethers } = require("hardhat");

async function main() {
    const [deployer] = await ethers.getSigners();
    const initialSupply = ethers.utils.parseUnits("1000", "ether");

    const Token = await ethers.getContractFactory("MyToken");
    const token = await Token.deploy(initialSupply);

    console.log("Token deployed to:", token.address);
}

main().catch((error) => {
    console.error(error);
    process.exit(1);
});
```

This script is deploying `MyToken` with an initial supply (customize the supply as needed).

***

### 10. Deploy the Contract

```shell
npx hardhat run scripts/deploy.js --network hemi
```

{% hint style="info" %}
If the deployment is successful, you will see messages indicating the token was deployed to

`Token deployed to: 0x5fc5c2265E4f77E63e82f7F10FE803d04Cc53D82`
{% endhint %}



To view the details of your deployed contract, enter the contract address from your success message into the [HEMI testnet explorer](https://explorer.testnet.hemi.network). This will provide you with information about the contract's transactions and state.

Contract details we just deployed:

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/KjbK1i2kxKgeiQ35kJjXE\_image.png)
