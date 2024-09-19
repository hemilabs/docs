# CLI PoP Miner

{% hint style="info" %}
### 📜 **TL;DR:**

* This guide provides straightforward steps to download, set up, and run your PoP Miner, either by downloading **pre-built binaries** or by **building from source**.
* Ensure you have your development environment ready and follow the steps below to join the mining network.
* Basic CLI skills are required.
* To start mining, claim tBTC via the Hemi [Discord faucet](https://discord.gg/hemixyz) or send at least `0.002 tBTC` to your provided Bitcoin testnet address and run the miner with your private key.
{% endhint %}

***

## 🏁 Prerequisites

* Basic CLI Knowledge
* **tBTC** - Join the Hemi [Discord](https://discord.gg/hemixyz) and visit our `#faucet` channel to acquire tBTC.

***

## 📚 Tutorial

### 1. Binaries

* [Download a pre-built binary](https://github.com/hemilabs/heminetwork/releases) or [build from source using the README](https://github.com/hemilabs/heminetwork?tab=readme-ov-file#-building-from-source).
*   Choose the release you want to use (_if unsure, choose the latest_), and click on `Assets` dropdown:

    <figure><img src="../../.gitbook/assets/pop-miner-binaries-v0.2.8 (1).png" alt=""><figcaption><p>Note: the version numbers may be different.</p></figcaption></figure>

    * The package you will need to download depends on your OS and architecture:
      * **Windows (Intel/AMD CPU):** heminetwork\_v0.2.8\_windows\_amd64.zip
      * **Mac (Intel CPU):** heminetwork\_v0.2.8\_darwin\_amd64.tar.gz
      * **Mac (Apple Silicon "M" CPU):** heminetwork\_v0.2.8\_darwin\_arm64.tar.gz
      * **Linux (Intel/AMD CPU):** heminetwork\_v0.2.8\_linux\_amd64.tar.gz
      * **Linux (ARM CPU):** heminetwork\_v0.2.8\_linux\_arm64.tar.gz
* After downloading the necessary files, you must extract them from their compressed format before you can use or access the software. On most operating systems, you can right-click on the downloaded archive and choose "Extract" or similar.&#x20;
  * On Linux/macOS, you can also use the command `tar xvf heminetwork_v0.2.8_linux_amd64.tar.gz`; see instructions below for how to open the Terminal and run commands.

{% hint style="info" %}
**Linux/macOS Tip**: Run the  `uname -a` command in the Terminal to view all system information, ensuring compatibility with the correct asset on GitHub. Depending on the output:\
"**x86\_64**" => Choose the "**amd64**" package corresponding to your OS\
"**arm64**" => Choose the "**arm64**" package corresponding to your OS
{% endhint %}

***

### 2. Open your CLI and navigate to the extracted folder

Launch your CLI:

{% hint style="info" %}
**For Windows:**

* Press `⊞ Win` + `R` together to open the "Run Program Or File" Window
* Type "cmd" and press `Enter`



**For macOS:**

* Press `⌘` + `Space` together to open Spotlight Search
* Type "terminal" and press Enter

\
**For Linux:**

* Depends on OS. On Ubuntu (Gnome): `Ctrl` + `Alt` + `T`
* For most other distros, you can press `Super` (Windows Key) and search for Terminal.&#x20;
{% endhint %}

Navigate to the folder you extracted by typing `cd` (**don't press `Enter` ye**t) and then drag the path of the extracted folder into your CLI, or type the path in manually and then press `Enter`.

* For example on Linux if you downloaded the package to your Downloads folder and extracted it through the GUI, you might run a command like:\
  \
  `cd '/home/user/Downloads/heminetwork_v0.2.8_linux_amd64'`

***

List the files:

{% hint style="info" %}
**For Windows:**

* `dir`  (and press `Enter`)Type "cmd" and press `Enter`



**For macOS:**

* `ls`  (and press `Enter`)
{% endhint %}

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

To ensure you downloaded the correct binaries and are able to run them, execute the command below:

```none
./popmd --help
```

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Linux &#x26; macOS</strong></td><td><p><mark style="color:purple;">⚠️ On Mac you will need to first remove the quarantine by running the following command in your Terminal:</mark></p><p><mark style="color:purple;"><code>xattr -d com.apple.quarantine ./popmd</code></mark></p></td><td></td></tr><tr><td><strong>Windows</strong></td><td><mark style="color:purple;">⚠️ <strong>Important Note for Windows Users</strong>: To successfully execute this command, you must use the Command Prompt (CMD), not PowerShell (which is the default terminal in environments like Visual Studio Code).</mark></td><td></td></tr></tbody></table>

This will display the help menu for `popmd`, indicating that it's installed and operational.

```none
Hemi Proof of Proof miner: v0.1.0-pre+f09d4e5ff
Usage:
	help (this help)
Environment:
	POPM_BFG_URL           : url for BFG (Bitcoin Finality Governor) (default: http://localhost:8383/v1/ws/public)
	POPM_BTC_CHAIN_NAME    : the name of the bitcoin chain to connect to (ex. "mainnet", "testnet3") (default: testnet3)
	POPM_BTC_PRIVKEY       : bitcoin private key (required) 
	POPM_LOG_LEVEL         : loglevel for various packages; INFO, DEBUG and TRACE (default: popmd=INFO;popm=INFO)
	POPM_PPROF_ADDRESS     : address and port popm pprof listens on (open <address>/debug/pprof to see available profiles) 
	POPM_PROMETHEUS_ADDRESS: address and port popm prometheus listens on 
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

If you are on Windows, see the above instructions for how to open the file in Notepad.

On Linux/macOS, you can run the following command to print the contents of your key file to the Terminal:

```none
cat ~/popm-address.json
```

You should see a result like:

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
* `network`: Refers to the specific blockchain environment that the generated address is compatible with. On Ethereum, addresses are the same for mainnet and testnet, however on Bitcoin addresses on each network are formatted differently.
* `private_key`: A secure digital code known only to the owner, used to access and manage the corresponding Ethereum address in wallets like MetaMask and Bitcoin address in wallets like UniSat. It’s essential for interacting with blockchain networks.
* `public_key`: Derived from the private key, this is shared publicly and used in the transaction signature process. For PoP mining and most other interactions with the Hemi network, you will not need to do anything directly with your public key.
* `pubkey_hash`: Represents a Bitcoin address generated from the private\_key. You will send tBTC to this address to use in PoP Mining. If you import your private key into a Bitcoin wallet like Unisat, you will have to select the address type - for now the PoP miner uses a "P2PKH" address type, and selecting that type will import the private key and use the corresponding address that matches the pubkey\_hash.
{% endhint %}

***

### 6. Import the ETH Address to MetaMask

* Check the JSON for your `private_key`and import it into MetaMask (only copy the hexadecimal digits; no quotes or spaces).

![](<../../.gitbook/assets/PoP 1.png>)

![](<../../.gitbook/assets/Pop 2.png>)

***

### 7. Fund your PoP Miner Address

To transfer at least `0.002 tBTC` to your testnet Bitcoin wallet address:

* **Find Your Wallet Address**: Check the JSON from **Step 5** for your `pubkey_hash`, which is your testnet Bitcoin address.
  * `"pubkey_hash": "m12345678P2xVWwVCWxq7tHJLGcJz2h6XYZ"`
* **Fund Your Wallet**: Claim tBTC in the [Hemi Discord faucet](https://discord.gg/hemixyz) to send at least`0.002 tBTC` to your `pubkey_hash` address.

👉 You can also get tBTC from faucets [like this one](https://coinfaucet.eu/en/btc-testnet/). However these faucets often don't provide enough tBTC to do much PoP mining.&#x20;

***

### 8. Run the Miner

In your console, execute the following commands while:

1. replacing `<private_key>` with the value found in the JSON from Step 5
2. replacing `<fee_per_vB_integer>` with the fee in sat/vB you want to pay. See the notice on "Bitcoin fee/vB" below if you need help determining what value to set here.&#x20;

*   **Linux & macOS**

    ```none
    export POPM_BTC_PRIVKEY=<private_key>
    export POPM_STATIC_FEE=<fee_per_vB_integer>
    export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
    ./popmd
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
* The lower you set the fee, the less tBTC you will pay per PoP transaction. But if your fees are too low, Bitcoin miners may not include your transaction quickly enough for you to successfully PoP mine.



**Beginner and intermediate users:**&#x20;

* We recommend setting the `POPM_STATIC_FEE` environment variable to `50` (50 sats/vB) to ensure PoP transactions are included in Bitcoin blocks.

**Advanced users:**&#x20;

1. Check Current Fee Levels: Visit [mempool.space](https://mempool.space/testnet) to see the current fee levels. Look at the "sat/vB" numbers for the different transaction fee priorities. It is recommended to set the value to the "High Priority" value or slightly higher.
2. Set the Static Fee: Re-run the command to set the `POPM_STATIC_FEE` environment variable from above (`export` on Linux/macOS, `set` on Windows) each time you want to change the fee, and restart the PoP Miner afterwards.
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

{% hint style="info" %}
Let us know how this process was for you via [Discord](https://discord.gg/hemixyz). We are constantly looking for ways to improve our documentation.
{% endhint %}
