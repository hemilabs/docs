---
hidden: true
---

# Tunnel BTC via Native Tunnel

{% hint style="info" %}
## 📜 **TL;DR:**

* Move your BTC to Hemi by using the Bitcoin Tunnel, enabling interactions within the Hemi Network ecosystem with Bitcoin assets.
* An [EVM](../../tutorials/metamask-wallet-setup.md) and [BTC](../wallet-setup/btc-wallet-setup/) wallet are required to move BTC assets via the Bitcoin Tunnel.
* A minimum of `0.0001 BTC` is required to deposit and withdrawal using the Native Tunnel.
{% endhint %}

***

## 🏁 Prerequisites

* **Acquire BTC** - BTC can be purchased on any number of exchanges and on-ramps.&#x20;
* [**EVM (MetaMask) Wallet Setup**](../../tutorials/metamask-wallet-setup.md) **-** Set up your EVM wallet and add Hemi Network.
* [**BTC Wallet Setup**](../wallet-setup/btc-wallet-setup/) **-** Set up your BTC wallet.

{% hint style="info" %}
**TESTNET ONLY**\
\
If you plan on developing on or interacting with Hemi testnet, alternative prerequisites may apply. To test out the Bitcoin Tunnel on testnet, you can obtain tBTC (Testnet Bitcoin) via the [**Direct Faucet Access**](https://coinfaucet.eu/en/btc-testnet/)**.**
{% endhint %}

***

## 📚 Tutorial

### 1. Visit the Hemi Portal&#x20;

Go to [https://app.hemi.xyz/en/tunnel/](https://app.hemi.xyz/en/tunnel/) to access the Hemi Portal.

{% hint style="info" %}
Select your network of choice using the network dropdown located at the bottom left.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

***

### 2. Connect wallet

Click `'Connect Wallets'` in the top-right corner of the Hemi Portal.

<figure><img src="../../../.gitbook/assets/image (127).png" alt=""><figcaption></figcaption></figure>

***

### 3. Connect your EVM wallet

Currently, MetaMask and Rabby are the only EVM wallets Hemi supports. Our team is working to add  support for additional wallets.

{% hint style="info" %}
Connecting an EVM wallet is required for the initial version of the Bitcoin Tunnel. The address connected will receive the tunneled Bitcoin assets.&#x20;
{% endhint %}



<figure><img src="../../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

***

### 4. Connect your BTC wallet

Connect your BTC wallet (currently only UniSat supported). If you do not have a UniSat wallet, you can view our [tutorial](../wallet-setup/btc-wallet-setup/) to create and set one up.&#x20;

<figure><img src="../../../.gitbook/assets/Screenshot 2025-02-19 at 12.27.22 (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

***

### 5. Select 'Bitcoin' as the 'From Network'

Ensure that you are connected to the Bitcoin network.&#x20;

<figure><img src="../../../.gitbook/assets/Screenshot 2025-02-19 at 12.29.01.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Tunneled BTC will be sent to the EVM address connected** (denoted by the '`Receiving Hemi Address`' at the bottom of the screen). In future versions, you will be able to manually input the preferred receiving address.
{% endhint %}

***

### 6. Enter the amount of BTC to tunnel

Input the amount of BTC you wish to tunnel to Hemi. There is a minimum amount of `0.0001 BTC` to deposit and withdrawal. &#x20;

<figure><img src="../../../.gitbook/assets/Screenshot 2025-02-20 at 11.25.33.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

After you have confirmed the gas fee and wish to proceed with the deposit, click `'Deposit.'`

***

### 7. Confirm the deposit in UniSat

Confirm your BTC deposit in the UniSat browser extension.

<figure><img src="../../../.gitbook/assets/Screenshot 2025-02-20 at 11.27.04.png" alt=""><figcaption></figcaption></figure>

***

### 8. You have successfully tunneled BTC to Hemi! 🎉

Your transaction has been initiated and must go through two confirmation periods to confirm your deposit:

1. Withdrawal from BTC address (\~1hr) - When you initiate a deposit request, a transaction is signed from your BTC address to transfer the specified amount into a secure vault on the Bitcoin network. This deposit requires six block confirmations, which generally takes about one hour to complete.
2. Deposit into EVM Hemi address - Once the deposit is fully confirmed on the Bitcoin network, the Hemi Network validates the transaction and mints a corresponding token receipt (`hemiBTC`) on the Hemi blockchain, ensuring a seamless transition of assets.

You can check the status and view the transaction in the `'Transaction History'` tab.&#x20;

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
`hemiBTC` can be tracked and added to your wallet at the following contract address: **`0xAA40c0c7644e0b2B224509571e10ad20d9C4ef28`**
{% endhint %}

#### Manual confirmation of deposit

After six confirmations, Hemi can confirm a successful deposit from the Bitcoin network and deposit the funds to your address. Occasionally, the vault operator will require a manual confirmation in order to complete the deposit.&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>
