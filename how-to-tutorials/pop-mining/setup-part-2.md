# Start Mining: Part 2

{% hint style="info" %}
## 📜 **TL;DR:**

* Ensure you have basic CLI skills and your address is whitelisted.
* To start mining, claim tBTC provided by your Hemi onboarding Capsule or send `0.002 tBTC` to your provided testnet address and run the miner with your private key.&#x20;
{% endhint %}

***

## 🏁 Prerequisites

1. Basic CLI Knowledge
2. [tBTC](https://coinfaucet.eu/en/btc-testnet)
3. [metamask-wallet-setup](../metamask-wallet-setup/ "mention")
4. [setup-part-1.md](setup-part-1.md "mention")

***

## 📚 Tutorial

### 1. Import the ETH Address to MetaMask

* Check the JSON from [Setup Part 1](setup-part-1.md) for your `private_key`and import it into MetaMask.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/YwLmvNZlpItY8LA-iIQ4h\_image.png)

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/KYSRZGcGOeqU-b7zT9xTG\_image.png)

***

### 2. Fund your PoP Miner Address

To transfer `0.002 tBTC` to your testnet Bitcoin wallet address:

* **Find Your Wallet Address**: Check the JSON from **Step 5** for your `pubkey_hash`, which is your testnet Bitcoin address.
  * `"pubkey_hash": "m12345678P2xVWwVCWxq7tHJLGcJz2h6XYZ"`
* **Fund Your Wallet**: Claim tBTC provided by your Hemi Network onboarding Capsule or use a testnet wallet to send `0.002 tBTC` to your `pubkey_hash` address.

[👉 Get tBTC Here](https://coinfaucet.eu/en/btc-testnet)

***

### 3. Run the Miner

Currently, the Bitcoin testnet is busy which means you will need to set a higher fee level to PoP mine successfully. You can check the latest Bitcoin testnet fees [here](https://mempool.space/testnet). In the latest version of the PoP miner, this fee is set using an environment variable. In the future, the PoP miner will have more fee configuration options for dynamic fee calculation.

In your console, execute the following command while replacing `private_key` with the value that was generated in [Setup Guide Part 1](#user-content-fn-1)[^1]

*   #### Linux & macOS

    ```none
    export POPM_BTC_PRIVKEY=<private_key>
    export POPM_STATIC_FEE=<fee_per_vB_integer>
    export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
    ./popmd
    2024-02-06 18:03:19 INFO popmd popmd.go
    ```
*   #### For Windows

    ```none
    set POPM_BTC_PRIVKEY=<private_key>
    set POPM_STATIC_FEE=<fee_per_vB_integer>
    set POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public 
    popmd.exe
    ```

***

### 4. Expected Console Output

```none
2024-02-06 22:26:40 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:40 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:40 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:40 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:43 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:43 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:43 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:43 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:46 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:46 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:46 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:46 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:49 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:49 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:49 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:49 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:52 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:52 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:52 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:52 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:55 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:55 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:55 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:55 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:26:58 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:26:58 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:26:58 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:26:58 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:27:01 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:27:01 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:27:01 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:27:01 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:27:04 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:27:04 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:27:04 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:27:04 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
2024-02-06 22:27:07 INFO popm popm.go:450 Checking for new keystone headers...
2024-02-06 22:27:07 INFO popm popm.go:389 checking keystone received with height 88750 against last keystone 88800
2024-02-06 22:27:07 INFO popm popm.go:389 checking keystone received with height 88775 against last keystone 88800
2024-02-06 22:27:07 INFO popm popm.go:389 checking keystone received with height 88800 against last keystone 88800
```

***

### 5. 🎉 Congrats! You are now a Hemi PoP Miner!

[^1]: set
