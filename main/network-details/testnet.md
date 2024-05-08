---
description: >-
  The following contains summary information to help you quickly integrate with
  the Hemi Testnet.
---

# Testnet

***

## Hemi Testnet Details

| Hemi Testnet                  |                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------ |
| **Gas Token/Currency Symbol** | ETH                                                                                        |
| **ChainID**                   | 743111                                                                                     |
| **RPC API endpoint**          | [https://testnet.rpc.hemi.network/rpc](https://testnet.rpc.hemi.network/rpc)               |
| **Explorer**                  | [https://testnet.explorer.hemi.xyz](https://testnet.explorer.hemi.xyz)                     |
| **Tunnel**                    | `in progress`                                                                              |
| **Faucet**                    | [https://discord.gg/hemixyz](https://discord.gg/hemixyz)                                   |
| **PoP Miner Endpoint**        | [wss://testnet.rpc.hemi.network/v1/ws/public](wss://testnet.rpc.hemi.network/v1/ws/public) |

***

## Code Snippets

Example HTTP request:

```curl
curl -X POST \
-H "Content-Type: application/json" \
--data '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":1}' \
https://testnet.rpc.hemi.network/rpc
{"jsonrpc":"2.0","id":1,"result":"0xaa3716"}
```
