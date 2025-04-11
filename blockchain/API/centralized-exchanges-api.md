# Overview

Liberland blockchain is based on [Polkadot SDK](https://polkadot.com/platform/sdk/).  
Recommended way to interact with the chain programmatically is through [@polkadot/api](https://github.com/polkadot-js/api) library.

## RPC endpoints & chain explorers

### Testnet

| Type     | URL                                                                                                                | Description                                      |
| -------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------ |
| RPC      | `wss://testchain.liberland.org/`                                                                                   | WebSocket endpoint for connecting to the testnet |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Ftestchain.liberland.org%2F#/explorer) | Web interface for exploring the testnet          |

### Mainnet

| Type     | URL                                                                                                           | Description                                                          |
| -------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| RPC      | `wss://mainnet.liberland.org`                                                                                 | WebSocket endpoint (operated by the Government)                      |
| RPC      | `wss://liberland-rpc.dwellir.com`                                                                             | WebSocket endpoint (operated by Dwellir)                             |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/explorer) | Web interface for exploring the mainnet (operated by the Government) |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss://liberland-rpc.dwellir.com#/explorer)   | Web interface for exploring the mainnet (operated by Dwellir)        |

# LLD

LLD is a native token of the Liberland blockchain and all transactions, calls and queries related to LLD are identical to any other substrate chain like Polkadot.

# LLM

## Receive wallet balance

LLM is an on chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with id of 1

### Using polkadotJsApi

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
// <ASSET_ID> of LLM is 1
const LLMInfo = await api.query.assets.account(
  "<ASSET_ID>",
  "<WALLET_ADDRESS>",
);
console.log(LLMInfo.toJSON().data?.balance ?? "0x0");
```

## Create Address

To create a new address, a minimum of 1 LLD needs to be deposited as an existential deposit

### using polkadotJsApi

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const { Keyring } = require("@polkadot/api");

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
// minimum <AMOUNT> is new BN('1000000000000');
const transferExtrinsic = api.tx.balances.transfer(
  "<WALLET_ADDRESS_TO_CREATE>",
  "<AMOUNT>",
);
const txHash = await transferExtrinsic.signAndSend(sender);
```

## Receive list of transactions by block number

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const hash = await api.rpc.chain.getBlockHash("<BLOCKNUMBER>");
const block = await api.rpc.chain.getBlock(hash);
console.log(block.block.extrinsics.toHuman());
```

## Receive the last block number

### Using polkadotJsApi

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const bestNumber = await api.derive.chain.bestNumber();
console.log(bestNumber.toNumber());
```

## Receive transaction information using TXID

Transactions (a.k.a. extrinsics) are uniquely identified by block hash + their index. See also https://wiki.polkadot.network/docs/build-protocol-info#unique-identifiers-for-extrinsics

```javascript
const txId = {
  blockHash: BLOCK_HASH,
  index: EXTRINSIC_INDEX,
};

const { ApiPromise, WsProvider } = require("@polkadot/api");
const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const apiAt = await api.at(txId.blockHash);
const allEvents = await apiAt.query.system.events();

const txEvents = allEvents.filter(
  ({ phase }) =>
    phase.isApplyExtrinsic && phase.asApplyExtrinsic.eq(txId.index),
);

const successEvent = txEvents.find(({ event }) =>
  api.events.system.ExtrinsicSuccess.is(event),
);
const failureEvent = txEvents.find(({ event }) =>
  api.events.system.ExtrinsicFailed.is(event),
);

if (successEvent) {
  const transferEvents = txEvents.filter(({ event }) =>
    api.events.assets.Transferred.is(event),
  );
  transferEvents.forEach(({ event }) => {
    const [assetId, fromAccount, toAccount, amount] = event.data;
    if (assetId == 1) {
      console.log(
        `Transfer of ${amount} grains of LLM from ${fromAccount} to ${toAccount}`,
      );
    }
  });
} else {
  const [dispatchError, dispatchInfo] = failureEvent.event.data;
  let errorInfo;

  // decode the error
  if (dispatchError.isModule) {
    // for module errors, we have the section indexed, lookup
    // (For specific known errors, we can also do a check against the
    // api.errors.<module>.<ErrorName>.is(dispatchError.asModule) guard)
    const decoded = api.registry.findMetaError(dispatchError.asModule);

    errorInfo = `${decoded.section}.${decoded.name}`;
  } else {
    // Other, CannotLookup, BadOrigin, no extra info
    errorInfo = dispatchError.toString();
  }

  console.log(`ExtrinsicFailed:: ${errorInfo}`);
}
```

## Coin transfer

### Using polkadotJsApi

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const { Keyring } = require("@polkadot/api");

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.llm.sendLlm("<ACCOUNT_TO>", "<AMOUNT>");
const txHash = await transferExtrinsic.signAndSend(sender);
```

Optionally, for token transfers, you can use the "assets.transfer" method and then provide the id of the asset you want to transfer. An example transfer for LLM (LLM=1).

```javascript
const { ApiPromise, WsProvider } = require("@polkadot/api");
const { Keyring } = require("@polkadot/api");

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
// The following value 1 is the ID token of LLM.
const transferExtrinsic = api.tx.assets.transfer(1, "<ACCOUNT_TO>", "<AMOUNT>");
const txHash = await transferExtrinsic.signAndSend(sender);
```

See also https://polkadot.js.org/docs/api/cookbook/tx/#how-do-i-get-the-decoded-enum-for-an-extrinsicfailed-event for example on how to see if tx succeeded.
