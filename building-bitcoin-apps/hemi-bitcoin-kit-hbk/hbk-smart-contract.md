# hBK Smart Contract

## 🌐 Overview

* The Hemi Bitcoin Kit smart contract provides utilities for interacting with Bitcoin data on the Hemi blockchain.&#x20;
* It includes methods to retrieve Bitcoin address balances, UTXOs, transaction details, and block headers.&#x20;
* The contract leverages hVM's new precompiles to perform Bitcoin-related queries.
* **Latest hBK release on Hemi testnet:**\
  [0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c](https://testnet.explorer.hemi.xyz/address/0x181dBA19ce25bbD6d884347d2471FE5E5C0fcA4c?tab=contract)

***

## 🚧 Phase 0 - Essentials

This initial phase is focused on core Bitcoin protocol data:

* Script/Address Balances
* UTXO Set
* Full Transactions w/ Output Availability
* Transaction Confirmations
* BTC Headers (Last and N)

***

## 🏗️ Struct Definitions

#### UTXO

Represents an unspent transaction output (UTXO).

```
struct UTXO {
  bytes32 txId;          // Transaction ID
  uint256 index;         // Index of the UTXO
  uint256 value;         // Value in satoshis
  bytes scriptPubKey;    // Script public key
}
```

***

#### Transaction

Represents a Bitcoin transaction.

```
struct Transaction {
  bytes32 containingBlockHash;   // Hash of the containing block
  uint256 transactionVersion;    // Transaction version
  uint256 size;                  // Transaction size
  uint256 vSize;                 // Virtual size of the transaction
  uint256 lockTime;              // Lock time
  Input[] inputs;                // Array of inputs
  Output[] outputs;              // Array of outputs
  uint256 totalInputs;           // Total number of inputs in the original transaction
  uint256 totalOutputs;          // Total number of outputs in the original transaction
  bool containsAllInputs;        // Indicates if all inputs are contained
  bool containsAllOutputs;       // Indicates if all outputs are contained
}
```

***

#### Input

Represents a Bitcoin transaction input.

```
struct Input {
  uint256 inValue;               // Value spent by the input in satoshis
  bytes32 inputTxId;             // Transaction ID of the input source
  uint256 sourceIndex;           // Index of the input in its transaction
  bytes scriptSig;               // Script signature
  uint256 sequence;              // Sequence number
  uint256 fullScriptSigLength;   // Full length of the script signature
  bool containsFullScriptSig;    // Indicates if the full script signature is contained
}
```

***

#### Output

Represents a Bitcoin transaction output.

```
struct Output {
  uint256 outValue;              // Value of the output in satoshis
  bytes script;                  // Output script
  string outputAddress;          // Output address
  bool isOpReturn;               // Indicates if the output is an OP_RETURN output
  bytes opReturnData;            // Data contained in the OP_RETURN output
  bool isSpent;                  // Indicates if the output is spent
  uint256 fullScriptLength;      // Full length of the output script
  bool containsFullScript;       // Indicates if the full output script is contained
  SpentDetail spentDetail;       // Details of the spent output
}
```

***

#### SpentDetail

Represents details of a spent output.

```
struct SpentDetail {
  bytes32 spendingTxId;          // Transaction ID of the spending transaction
  uint256 inputIndex;            // Index of the input in the spending transaction
}
```

***

#### BitcoinHeader

Represents a Bitcoin block header.

```
struct BitcoinHeader {
  uint32 height;                 // Block height
  bytes32 blockHash;             // Block hash
  uint32 version;                // Version
  bytes32 previousBlockHash;     // Previous block hash
  bytes32 merkleRoot;            // Merkle root
  uint32 timestamp;              // Timestamp
  uint32 bits;                   // Bits
  uint32 nonce;                  // Nonce
}
```

***

## 🧑‍💻 IBitcoinKit Interface

The `IBitcoinKit` interface defines the methods available for interacting with the BitcoinKit contract.

```
interface IBitcoinKit {
  function getUTXOsForBitcoinAddress(string calldata btcAddress, uint256 pageNumber, uint256 pageSize) external view returns (UTXO[] memory);
  function getTxConfirmations(bytes32 txId) external view returns (uint32 confirmations);
  function getBitcoinAddressBalance(string calldata btcAddress) external view returns (uint256 balance);
  function getTransactionByTxId(bytes32 txId) external view returns (Transaction memory);
  function getTransactionInputsByTxId(bytes32 txId) external view returns (Input[] memory);
  function getTransactionOutputsByTxId(bytes32 txId) external view returns (Output[] memory);
  function getLastHeader() external view returns (BitcoinHeader memory);
  function getHeaderN(uint32 height) external view returns (BitcoinHeader memory);
}
```

***

#### getBitcoinAddressBalance

Retrieves the balance of a given Bitcoin address.

Precompile Address: 0x40

```
function getBitcoinAddressBalance(string calldata btcAddress) public view returns (uint256 balance)
```

***

#### getUTXOsForBitcoinAddress

Precompile Address: 0x41

Retrieves UTXOs for a given Bitcoin address, page number, and page size.

```
function getUTXOsForBitcoinAddress(string calldata btcAddress, uint256 pageNumber, uint256 pageSize) public view returns (UTXO[] memory)
```

***

#### getTransactionByTxId

Retrieves UTXOs for a given Bitcoin address, page number, and page size.

Precompile Address: 0x42

```
function getTransactionByTxId(bytes32 txId) external view returns (Transaction memory);
```

***

#### getTxConfirmations

Retrieves the number of confirmations for a given transaction ID.

Precompile Address: 0x43

```
function getTxConfirmations(bytes32 txId) public view returns (uint32 confirmations)
```

***

#### getLastHeader

Retrieves the latest Bitcoin block header.

Precompile Address: 0x44

```
function getLastHeader() public view returns (BitcoinHeader memory)
```

***

#### getHeaderN

Precompile Address: 0x45

Retrieves the Bitcoin block header at a specific height.

```
function getHeaderN(uint32 height) public view returns (BitcoinHeader memory)
```

***

