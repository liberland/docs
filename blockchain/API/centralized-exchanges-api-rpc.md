# Liberland CEX API: Low-Level RPC Overview

## Overview

This document provides a glimpse into the low-level RPC interactions that occur under the hood when working with the Liberland blockchain. While the recommended approach for most developers is to use the [@polkadot/api](https://github.com/polkadot-js/api) library (as mentioned in the main document), understanding these underlying RPC calls can be valuable for:

1. **Debugging** - When troubleshooting issues with higher-level libraries
2. **Educational Purposes** - To better understand the Substrate architecture
3. **Advanced Integration** - For systems that may need direct RPC access

> **Note:** The examples below are provided for reference and understanding only. In production environments, we strongly recommend using the [@polkadot/api](https://github.com/polkadot-js/api) library, which handles the complex encoding/decoding, transaction signing, and error management automatically.

## Common Operations

### Get Latest Block Number

```json
// Request
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "chain_getHeader",
  "params": []
}

// Response
{
  "jsonrpc": "2.0",
  "result": {
    "parentHash": "0xede218942dd683bab0c75ab1376c66143f358d65c5def66916ab14c7a9b9bbf8",
    "number": "0x215",
    "stateRoot": "0x060bf5a3fda2613c8b980cac4fcf7db7d2cf2dfd4aca37682c4828d30f8bfa9f",
    "extrinsicsRoot": "0x6ac870c6fea171a88339b9d7783fa79ed8a570c91b81945bf735bc1a8c61a134",
    "digest": {
      "logs": [
        "0x0642414245340200000000b7d7541100000000",
        "0x054241424501012ce4fadc4dd07868bacd773c90d4729856554334ccfe55d4e7d229ea01eeea3d4a4ecec32a87872ca961fe2f9d7f5f8e64995514e940ca92f07c1011fc176885"
      ]
    }
 },
  "id": 1
}
```

### Create a New Address

To create a new address, a minimum of 1 LLD needs to be deposited as an existential deposit.

In the `params` array, the extrinsic hex string contains the encoded and signed transaction with sender's address, recipient's address, and the LLD amount being transferred.

```json
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "author_submitExtrinsic",
  "params": [
    "0x310284ffd43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d00e5ca36b27c8573609a01479e341ea9c26aad786d25190ab8b52e96c7b359502cca8a3f9d027295611a29d262cf17e8b1cf53c6e4c08a54d889be1a0c40d000700e8764817"
  ]
}

// Response
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0x8982d2b1eb564d8ef357fc3537bb897aec453adcfa9f37a6168f6f5769e5057a"
}
```

## Liberland Dollar (LLD)

LLD is a native token of the Liberland blockchain and all transactions, calls and queries related to LLD are identical to any other Substrate chain like Polkadot.

### Receive Wallet Balance

The `params` array contains the storage key representing the `system.account` storage location combined with the encoded account address, and the response returns the full account data including nonce, balances, and other account information.

```json
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "state_getStorage",
  "params": [
    "0x26aa394eea5630e07c48ae0c9558cef7b99d880ec681799c0cf30e8886371da9de1e86a9a8c739864cf3cc5ec2bea59fd43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d"
  ]
}

// Response
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0x00000000000000000700e8764817000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"
}
```

### Coin Transfer

The request contains a hex-encoded signed extrinsic with the sender's address, recipient's address, and transfer amount, with the response returning the transaction hash. Following is a sample for calling `transferAllowDeath` extrinsic.

```json
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "author_submitExtrinsic",
  "params": [
    "0x310284ffd43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d00c4f5e6a4e9fe0030ac9d1b23a5ca99b5aca43a2d7c70ccd471c7e2c535c9fccb0300a0724e180900000500e8764817"
  ]
}

// Response
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0x2c543def9f11dee6e4efcff9a6d2744e6e4c8cf3cd92c6c0427caba82f147426"
}
```

## Liberland Merit (LLM)

LLM is an on-chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with ID of 1.

### Receive Wallet Balance

The `params` array contains the storage key that combines the `assets.account` prefix with the LLM asset ID (1) and the account address, with the response containing the encoded asset balance information.

```json
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "state_getStorage",
  "params": [
    "0x7bf3f91245a72b342adab25c7018753cb40e39fd5d8b3d5e4442e7398b672c656f8b0c2ae47d9164bbcb6a056e51807cd43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d"
  ]
}

// Response
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0x0100000000000000e8030000000000000000000000000000"
}
```

### Coin Transfer

The `params` array contains the encoded transaction that includes the asset ID (1), recipient address, and amount to transfer, with the response returning the transaction hash.

```json
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "author_submitExtrinsic",
  "params": [
    "0x310284ffd43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d019de8ad0130ac9d1b23a5ca99b5aca43a2d7c70ccd471c7e2c535c9fccb0300a0724e1809000"
  ]
}

// Response
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0x43a88e4de68db1c10ce9a9732d3161962c5379a5e6c7fb4c08140e7b9eb16e8f"
}
```
