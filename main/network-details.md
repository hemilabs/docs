# Network Details

## Hemi Testnet&#x20;

<table><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td><strong>Gas Token/Currency Symbol</strong></td><td>ETH</td></tr><tr><td><strong>ChainID</strong></td><td>743111</td></tr><tr><td><strong>RPC API endpoint</strong></td><td><a href="https://testnet.rpc.hemi.network/rpc">https://testnet.rpc.hemi.network/rpc</a></td></tr><tr><td><strong>Explorer</strong></td><td><a href="https://testnet.explorer.hemi.xyz">https://testnet.explorer.hemi.xyz</a></td></tr></tbody></table>

### Additional Testnet Public RPC Endpoints

* PoP Miner: `wss://testnet.rpc.hemi.network/v1/ws/public`
* Explorer: [`https://testnet.explorer.hemi.xyz/api/v2/`](https://testnet.explorer.hemi.xyz/api/v2/)
  * Documentation: [`https://testnet.explorer.hemi.xyz/api-docs`](https://testnet.explorer.hemi.xyz/api-docs)

***

## Hemi Mainnet&#x20;

<table><thead><tr><th width="293"></th><th></th></tr></thead><tbody><tr><td><strong>Gas Token/Currency Symbol</strong></td><td>TBD</td></tr><tr><td><strong>ChainID</strong></td><td>TBD</td></tr><tr><td><strong>RPC API endpoint</strong></td><td>TBD</td></tr><tr><td><strong>Explorer</strong></td><td>TBD</td></tr></tbody></table>

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
