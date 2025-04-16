# Overview

Liberland blockchain is based on [Polkadot SDK](https://polkadot.com/platform/sdk/).  
Recommended way to interact with the chain programmatically is through [@polkadot/api](https://github.com/polkadot-js/api) library.

## RPC endpoints & chain explorers

### Testnet

| Type     | URL                                                                                                                | Description                             |
| -------- | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------- |
| RPC      | `wss://testchain.liberland.org`                                                                                    | WebSocket endpoint                      |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Ftestchain.liberland.org%2F#/explorer) | Web interface for exploring the testnet |

### Mainnet

| Type     | URL                                                                                                           | Description                                                          |
| -------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| RPC      | `wss://mainnet.liberland.org`                                                                                 | WebSocket endpoint (operated by the Government)                      |
| RPC      | `wss://liberland-rpc.dwellir.com`                                                                             | WebSocket endpoint (operated by Dwellir)                             |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/explorer) | Web interface for exploring the mainnet (operated by the Government) |
| Explorer | [Polkadot Apps](https://polkadotjs.blockchain.liberland.org/?rpc=wss://liberland-rpc.dwellir.com#/explorer)   | Web interface for exploring the mainnet (operated by Dwellir)        |

# Common operations

## Get latest block number

### @polkadot/api

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const bestNumber = await api.derive.chain.bestNumber();
console.log(bestNumber.toNumber());
```

### RPC

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
    "number": "0x215", // Block number in hex
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

## Create a new address

To create a new address, a minimum of 1 LLD needs to be deposited as an existential deposit.

### @polkadot/api

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<RPC_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.balances.transfer(
  "<WALLET_ADDRESS_TO_CREATE>",
  AMOUNT, // 1_000_000_000_000 = 1 LLD
);
const txHash = await transferExtrinsic.signAndSend(sender);
```

### RPC

TODO

# Liberland Dollar (LLD)

LLD is a native token of the Liberland blockchain and all transactions, calls and queries related to LLD are identical to any other Substrate chain like Polkadot.

## Receiver wallet balance

### @polkadot/api

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const balance = await api.query.system.account("<ACCOUNT_ID>");
console.log(balance.data.free.toHuman());
```

### RPC

TODO

## Coin transfer

### @polkadot/api

The `transferAllowDeath` extrinsic performs a standard token transfer that can empty the sender's account, potentially removing it from the blockchain state if the balance falls below the existential deposit.

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.balances.transferAllowDeath(
  "<ACCOUNT_TO>",
  AMOUNT, // 1_000_000_000_000 = 1 LLD
);
const txHash = await transferExtrinsic.signAndSend(sender);
```

In contrast, `transferKeepAlive` ensures the sender's account remains active by automatically keeping the existential deposit amount in the account, preventing accidental account destruction.

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.balances.transferKeepAlive(
  "<ACCOUNT_TO>",
  AMOUNT, // 1_000_000_000_000 = 1 LLD
);
const txHash = await transferExtrinsic.signAndSend(sender);
```

### RPC

TODO

## Monitor LLD transfers

To monitor LLD transfers, subscribe to system events and filter for `Balances::Transfer` events.

### @polkadot/api

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

async function main() {
  const provider = new WsProvider("<WS_ENDPOINT>");
  const api = await ApiPromise.create({ provider });

  // Subscribe to system events
  const unsubscribe = await api.query.system.events((events) => {
    // Filter only the Balances.Transfer events
    events.forEach(({ event, phase }) => {
      if (api.events.balances.Transfer.is(event)) {
        // LLD transferred
        const [from, to, amount] = event.data;
        console.log(
          `LLD Transfer from: ${from.toString()} to: ${to.toString()} amount: ${amount.toString()}`,
        );
      }
    });
  });

  return unsubscribe;
}

main()
  .then((unsubscribe) => {
    console.log("Subscribed to Transfer events. Press Ctrl+C to exit.");
  })
  .catch((error) => {
    console.error("Error:", error);
    process.exit(1);
  });
```

# Liberland Merit (LLM)

LLM is an on-chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with ID of 1.

## Receive wallet balance

### @polkadot/api

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const LLMInfo = await api.query.assets.account(
  1, // ID of LLM
  "<WALLET_ADDRESS>",
);
console.log(LLMInfo.toJSON().data?.balance ?? "0x0");
```

### RPC

TODO

## Coin transfer

### @polkadot/api

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.llm.sendLlm("<ACCOUNT_ID>", AMOUNT); // 1_000_000_000_000 = 1 LLM
const txHash = await transferExtrinsic.signAndSend(sender);
```

Optionally, for token transfers, you can use the "assets.transfer" method and then provide the id of the asset you want to transfer. An example transfer for LLM (LLM=1).

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
// The following value 1 is the ID token of LLM.
const transferExtrinsic = api.tx.assets.transfer(1, "<ACCOUNT_TO>", AMOUNT); // 1_000_000_000_000 = 1 LLM
const txHash = await transferExtrinsic.signAndSend(sender);
```

See also https://polkadot.js.org/docs/api/cookbook/tx/#how-do-i-get-the-decoded-enum-for-an-extrinsicfailed-event for example on how to see if tx succeeded.

### RPC

TODO

## Monitor LLM transfers

To monitor LLM transfers, subscribe to system events and filter for `Assets::Transferred` events with an ID of 1.

### @polkadot/api

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

async function main() {
  const provider = new WsProvider("<WS_ENDPOINT>");
  const api = await ApiPromise.create({ provider });

  // Target asset ID to monitor
  const targetAssetId = 1;

  // Subscribe to system events
  const unsubscribe = await api.query.system.events((events) => {
    // Filter for Assets.Transferred events
    events.forEach(({ event, phase }) => {
      if (api.events.assets.Transferred.is(event)) {
        const [assetId, from, to, amount] = event.data;

        if (assetId.eq(targetAssetId)) {
          // LLM transferred
          console.log(
            `LLM Transfer from: ${from.toString()} to: ${to.toString()} amount: ${amount.toString()}`,
          );
        }
      }
    });
  });

  return unsubscribe;
}

main()
  .then((unsubscribe) => {
    console.log("Subscribed to LLM transfers. Press Ctrl+C to exit.");
  })
  .catch((error) => {
    console.error("Error:", error);
    process.exit(1);
  });
```

## Retrieve transaction details using TxID

Transactions (a.k.a. extrinsics) are uniquely identified by block hash and their index. See also https://wiki.polkadot.network/docs/build-protocol-info#unique-identifiers-for-extrinsics

### @polkadot/api

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

const txId = {
  blockHash: BLOCK_HASH,
  index: EXTRINSIC_INDEX,
};
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

### RPC

TODO
