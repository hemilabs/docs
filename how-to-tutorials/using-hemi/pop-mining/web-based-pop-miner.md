# Web PoP Miner (deprecated)

{% hint style="warning" %}
**Support for the Web PoP Miner has since been deprecated.** \
\
To learn more about how we implemented the application, feel free to view our codebase here: [https://github.com/hemilabs/web-pop-miner](https://github.com/hemilabs/web-pop-miner)\
\
Follow our [CLI PoP Miner guide](setup-part-1.md) to run a PoP Miner.
{% endhint %}

***

## 🌐 Overview

* The web PoP miner was designed for ease of use, allowing users of any experience level to test and run their own PoP miner.&#x20;
* Due to its lightweight nature, it required no specific hardware, making it accessible from any standard computer.&#x20;
* While it was not intended for long-term mining operations, it served as an excellent entry point for users interested in transitioning to the more durable CLI version, providing an introduction to Hemi's architecture and its unique integration with the Bitcoin network.

***

## 🔐 Security Note

{% hint style="warning" %}
* The web miner uses the same secure code as the CLI miner. However, it also relies on your web browser, which introduces additional security risks.&#x20;
* When transitioning to the CLI PoP Miner, **it is recommended to generate a new public key.** Private key information obtained via the web PoP Miner, although encrypted, is not fully secure and is not meant for extended mining operations.&#x20;
{% endhint %}
