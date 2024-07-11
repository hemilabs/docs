---
description: >-
  The following contains summary information to help you quickly integrate with
  the Hemi testnet.
---

# Testnet

***

## Hemi Testnet Details

| Hemi Testnet                  |                                                                              |
| ----------------------------- | -----------------------------------------------------------------------------|
| **Gas Token/Currency Symbol** | ETH                                                                          |
| **ChainID**                   | 743111                                                                       |
| **RPC API endpoint**          | [https://testnet.rpc.hemi.network/rpc](https://testnet.rpc.hemi.network/rpc) |
| **Explorer**                  | [https://testnet.explorer.hemi.xyz](https://testnet.explorer.hemi.xyz)       |
| **Tunnel**                    | [https://app.hemi.xyz](https://app.hemi.xyz)                                 |
| **Faucet**                    | [https://discord.gg/hemixyz](https://discord.gg/hemixyz)                     |
| **PoP Miner Endpoint**        | wss://testnet.rpc.hemi.network/v1/ws/public                                  |

***

## Code Snippets

Example HTTP request:

<pre class="language-sh"><code class="lang-sh">curl -X POST \
    -H "Content-Type: application/json" \
<strong>    --data '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":1}' \
</strong>    https://testnet.rpc.hemi.network/rpc

<strong># This will print the RPC response:
</strong># {"jsonrpc":"2.0","id":1,"result":"0xaa3716"}
</code></pre>
