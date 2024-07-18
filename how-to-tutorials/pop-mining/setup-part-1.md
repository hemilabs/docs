# CLI PoP Miner

{% hint style="info" %}
### 📜 **TL;DR:**

* This guide provides straightforward steps to download, set up, and run your PoP Miner, either by downloading **pre-built binaries** or by **building from source**.
* Ensure you have your development environment ready and follow the steps below to join the mining network.
* Basic CLI skills are required.
* To start mining, claim tBTC provided by your Hemi onboarding Capsule or send `0.002 tBTC` to your provided Bitcoin testnet address and run the miner with your private key.
{% endhint %}

***

## 🏁 Prerequisites

1. Basic CLI Knowledge
2. [metamask-wallet-setup.md](../metamask-wallet-setup.md "mention")
3. [tBTC](https://coinfaucet.eu/en/btc-testnet)

***

## 📚 Tutorial

### 1. Binaries

* [Download a pre-built binary](https://github.com/hemilabs/heminetwork/releases) or [build from source using the README](https://github.com/hemilabs/heminetwork?tab=readme-ov-file#-building-from-source).
*   View `Assets` \*

    ```
    ![](../../.gitbook/assets/heminetwork-binaries-screenshot-v0.1.1.png)
    ```

    * The files are named as `heminetwork_v0.1.1_<os>_<arch>.tar.gz` for Mac/Linux and `heminetwork_v0.1.1_windows_amd64.zip` for Windows.
* After downloading the necessary files, you must extract them from their compressed format before you can use or access the software.
  * For `.tar.gz` **files on Mac/Linux, use the `tar`** command in the Terminal
  * For `.zip` files on Windows, use the built-in extraction tool by right-clicking on the file and choosing `Extract All`

{% hint style="info" %}
Use the `uname -a`command in the CLI to view all system information, ensuring compatibility with the correct asset on GitHub.
{% endhint %}

***

### 2. Open the folder

* List the files

```none
ls
```

Your output should be:

*   **Linux & macOS**

    ```none
    bfgd    bssd    extool    hemictl    keygen    popmd    tbcd
    ```
*   **For Windows**

    ```none
    bfgd.exe    bssd.exe    extool.exe     hemictl.exe     keygen.exe     popmd.exe     tbcd.exe
    ```

***

### 3. Verify Configuration Success

To ensure the setup is correctly configured, execute the command below:

```none
./popmd --help
```

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Linux &#x26; macOS</strong></td><td><p><mark style="color:purple;">⚠️ On Mac you will need to first remove the quarantine by running:</mark></p><p><mark style="color:purple;"><code>xattr -d com.apple.quarantine ./popmd</code></mark></p></td><td></td></tr><tr><td><strong>Windows</strong></td><td><p><mark style="color:purple;">⚠️ <strong>Important Note for Windows Users</strong>: To successfully execute this command, you must use the Command Prompt, not PowerShell (which is the default terminal in environments like Visual Studio Code). Follow these steps to open Command Prompt:</mark></p><ol><li><mark style="color:purple;">Click on the <strong>Start Menu</strong> button or press the <strong>Windows</strong> key on your keyboard.</mark></li><li><mark style="color:purple;">Type <strong><code>cmd</code></strong></mark> <mark style="color:purple;">into the search bar and open it.</mark></li></ol></td><td></td></tr></tbody></table>

This will display the help menu for `popmd`, indicating that it's installed and operational.

```none
Hemi Proof of Proof miner: v0.1.1-pre+29f116fb4
Usage:
        help (this help)
Environment:
        POPM_BFG_URL           : url for BFG (Bitcoin Finality Governor) (default: http://localhost:8383/v1/ws/public)
        POPM_BTC_CHAIN_NAME    : the name of the bitcoing chain to connect to (ex. "mainnet", "testnet3") (default: testnet3)
        POPM_BTC_PRIVKEY       : bitcoin private key (required) 
        POPM_LOG_LEVEL         : loglevel for various packages; INFO, DEBUG and TRACE (default: popmd=INFO;popm=INFO)
        POPM_PPROF_ADDRESS     : address and port popm pprof listens on (open <address>/debug/pprof to see available profiles)
        POPM_PROMETHEUS_ADDRESS: address and port bssd prometheus listens on 
        POPM_REMINE_THRESHOLD  : the number of L2 Keystones behind the latest seen that we are willing to remine, this is handy for re-orgs (default: 0)
        POPM_STATIC_FEE        : specify the number of sats/vB the PoP Miner will pay for fees (default: 1)
```

***

### 4. Generate Your Public Key

Start by generating your public key, your identifier on the Hemi Network.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Linux &#x26; macOS</strong></td><td><p><mark style="color:purple;">⚠️ On Mac you will need to remove the quarantine by running:</mark></p><p><mark style="color:purple;"><code>xattr -d com.apple.quarantine ./keygen</code></mark></p></td><td><p><strong>Run the following command:</strong></p><pre data-overflow="wrap"><code>./keygen -secp256k1 -json -net="testnet" > ~/popm-address.json
</code></pre></td></tr><tr><td><strong>Windows</strong></td><td><p><mark style="color:purple;">⚠️ <strong>Important Note for Windows Users</strong>: To successfully execute this command, you must use the Command Prompt, not PowerShell (which is the default terminal in environments like Visual Studio Code). Follow these steps to open Command Prompt:</mark></p><ol><li><mark style="color:purple;">Click on the <strong>Start Menu</strong> button or press the <strong>Windows</strong> key on your keyboard.</mark></li><li><mark style="color:purple;">Type <strong><code>cmd</code></strong></mark> <mark style="color:purple;">into the search bar and open it.</mark></li></ol></td><td><ol><li><p>Type the following command and press Enter:</p><pre class="language-cmd" data-overflow="wrap"><code class="lang-cmd">keygen.exe -secp256k1 -json -net="testnet" > %HOMEDRIVE%%HOMEPATH%\popm-address.json
</code></pre></li></ol><p><strong>Note:</strong> After running the command, you might not see any immediate feedback in the Command Prompt. This is expected behavior.</p><ol start="2"><li>Open the Generated Key File</li></ol><p>After generating the key file, you'll want to check its contents. To do this, use the following command in Command Prompt:</p><pre class="language-cmd" data-overflow="wrap"><code class="lang-cmd">%HOMEDRIVE%%HOMEPATH%\popm-address.json
</code></pre><p>This command opens the <code>popm-address.json</code> file in Notepad, allowing you to view or edit the generated key.</p></td></tr></tbody></table>

***

### 5. Open the JSON

```none
cat ~/popm-address.json
```

You should get an example result like:

```none
{
  "ethereum_address": "0x12345FabcD298299b8250e16eEb7D6a7B81DfEdC",
  "network": "testnet",
  "private_key": "123456789abcdef123456789abcdef123456789abcdef123456789abcdef1234",
  "public_key": "04123456789abcdef123456789abcdef123456789abcdef123456789abcdef12345678abcdef123456789abcdef123456789abcdef123456789abcdef1234",
  "pubkey_hash": "m12345678P2xVWwVCWxq7tHJLGcJz2h6XYZ"
}
```

{% hint style="info" %}
**Glossary**

* `ethereum_address`: This is the unique identifier to which you can send Ethereum-based funds, including those on mainnets, testnets (like Sepolia), and Layer 2 networks (like Hemi). It facilitates cross-environment transactions, meaning the same address is applicable across different Ethereum networks.
* `network`: Refers to the specific blockchain environment (e.g., Ethereum mainnet, Sepolia testnet, or a Layer 2 solution) that a transaction or operation is intended for.
* `private_key`: A secure digital code known only to the owner, used to access and manage the corresponding Ethereum address in wallets like MetaMask. It’s essential for interacting with blockchain networks, allowing the execution of transactions from the Ethereum address.
* `public_key`: Derived from the private key, this is shared publicly and used in the encryption process. For the Hemi network, it's intended for future use to whitelist addresses with the Bitcoin Finality Governor (BFG) endpoint.
* `pubkey_hash`: Represents a Bitcoin address generated from the private\_key, which the PoP Miner application can use. It's recommended not to try importing this address into a wallet, as it's specifically for mining activities.
{% endhint %}

***

### 6. Import the ETH Address to MetaMask

* Check the JSON for your `private_key`and import it into MetaMask.

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/YwLmvNZlpItY8LA-iIQ4h\_image.png)

![](https://archbee-image-uploads.s3.amazonaws.com/P3jZYg6ia8u4bfG9Eix0B/KYSRZGcGOeqU-b7zT9xTG\_image.png)

***

### 7. Fund your PoP Miner Address

To transfer `0.002 tBTC` to your testnet Bitcoin wallet address:

* **Find Your Wallet Address**: Check the JSON from **Step 5** for your `pubkey_hash`, which is your testnet Bitcoin address.
  * `"pubkey_hash": "m12345678P2xVWwVCWxq7tHJLGcJz2h6XYZ"`
* **Fund Your Wallet**: Claim tBTC provided by your Hemi Network onboarding Capsule or use a testnet wallet to send `0.002 tBTC` to your `pubkey_hash` address.

[👉 Get tBTC Here](https://coinfaucet.eu/en/btc-testnet)

***

### 8. Run the Miner

In your console, execute the following command while replacing `private_key` with the value found in the JSON from Step 5.

*   **Linux & macOS**

    ```none
    export POPM_BTC_PRIVKEY=<private_key>
    export POPM_STATIC_FEE=<fee_per_vB_integer>
    export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
    ./popmd
    2024-02-06 18:03:19 INFO popmd popmd.go
    ```
*   **Windows**

    ```
    set POPM_BTC_PRIVKEY=<private_key>
    set POPM_STATIC_FEE=<fee_per_vB_integer>
    set POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public 
    popmd.exe
    ```

{% hint style="warning" %}
**Bitcoin fee/vB**

* The Bitcoin transaction (normally represented in satsoshis per virtual byte or sats/vB) is a fee paid to the Bitcoin miners to include a transaction in a Bitcoin block. It varies with network congestion, typically rising during periods of high transaction volume and decreasing when there is less activity. The PoP Miner consumes tBTC to pay the Bitcoin miners to include PoP transactions in Bitcoin blocks.
* In order to ensure PoP transactions from your PoP miner are included in Bitcoin blocks, ensure the configured fee is set to an appropriate value. The PoP miner can be configured to use a certain fee in sats/vB by changing the `POPM_STATIC_FEE` environment variable when running the PoP miner. In a future version, the PoP miner will automatically calculate the current network fee to guarantee PoP transactions are included in Bitcoin blocks.



**Beginner and intermediate users:**&#x20;

* We recommend setting the `POPM_STATIC_FEE` environment variable to `50` (50 sats/vB) to ensure PoP transactions are included in Bitcoin blocks.

**Advanced users:**&#x20;

* You can find the current Bitcoin transaction fees at [mempool.space](https://mempool.space/) and configure the PoP miner to use a more exact fee, to decrease the cost of running the PoP miner for long periods of time, or to fix issues caused by high transaction fees.
{% endhint %}

***

### 9. Expected Console Output

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
```

***

### 10. 🎉 Congrats! You are now a Hemi PoP Miner!
