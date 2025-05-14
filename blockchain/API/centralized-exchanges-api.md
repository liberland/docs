# Liberland CEX API

## Table of Contents

- [Overview](#overview)
- [RPC Endpoints & Chain Explorers](#rpc-endpoints--chain-explorers)
  - [Testnet](#testnet)
  - [Mainnet](#mainnet)
- [Common Operations](#common-operations)
  - [Get Latest Block Number](#get-latest-block-number)
  - [Create a New Address](#create-a-new-address)
- [Liberland Dollar (LLD)](#liberland-dollar-lld)
  - [Receive Wallet Balance](#receive-wallet-balance)
  - [Coin Transfer](#coin-transfer)
  - [Monitor LLD Transfers](#monitor-lld-transfers)
  - [Retrieve LLD Transaction Details Using Block Hash and Index](#retrieve-lld-transaction-details-using-block-hash-and-index)
- [Liberland Merit (LLM)](#liberland-merit-llm)
  - [Receive Wallet Balance](#receive-wallet-balance-1)
  - [Coin Transfer](#coin-transfer-1)
  - [Monitor LLM Transfers](#monitor-llm-transfers)
  - [Retrieve LLM Transaction Details Using Block Hash and Index](#retrieve-llm-transaction-details-using-block-hash-and-index)

## Overview

Liberland blockchain is based on [Polkadot SDK](https://polkadot.com/platform/sdk/).  
Recommended way to interact with the chain programmatically is through [@polkadot/api](https://github.com/polkadot-js/api) library.
For those interested in a glimpse of the underlying RPC interactions, see the [Liberland CEX API: Low-Level RPC Overview](centralized-exchanges-api-rpc.md).

## RPC Endpoints & Chain Explorers

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

## Common Operations

### Get Latest Block Number

```javascript
import { ApiPromise, WsProvider } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const bestNumber = await api.derive.chain.bestNumber();
console.log(bestNumber.toNumber());
```

### Create a New Address

To create a new address, a minimum of 1 LLD needs to be deposited as an existential deposit.

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
const transferExtrinsic = api.tx.balances.transfer(
  "<WALLET_ADDRESS_TO_CREATE>",
  AMOUNT, // 1_000_000_000_000 = 1 LLD
);
const txHash = await transferExtrinsic.signAndSend(sender);
```

## Liberland Dollar (LLD)

LLD is a native token of the Liberland blockchain and all transactions, calls and queries related to LLD are identical to any other Substrate chain like Polkadot.

### Receive Wallet Balance

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const balance = await api.query.system.account("<ACCOUNT_ID>");
console.log(balance.data.free.toHuman());
```

### Coin Transfer

For LLD transfers with transaction status monitoring, you can use the `balances.transferKeepAlive` method which ensures the sender's account remains active by automatically keeping the existential deposit amount. This differs from `balances.transferAllowDeath` which can empty the sender's account completely, potentially removing it from the blockchain state if the balance falls below the existential deposit.

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

// Monitor transaction status
const unsub = await transferExtrinsic.signAndSend(
  sender,
  ({ status, events }) => {
    console.log(`Current transaction status: ${status.type}`);

    if (status.isInBlock) {
      console.log(`Transaction included in block: ${status.asInBlock.toHex()}`);
    }

    if (status.isFinalized) {
      console.log(
        `Transaction finalized in block: ${status.asFinalized.toHex()}`,
      );

      // Check if the transaction was successful
      events.forEach(({ event }) => {
        if (api.events.system.ExtrinsicSuccess.is(event)) {
          console.log("Transaction succeeded");
        } else if (api.events.system.ExtrinsicFailed.is(event)) {
          const [dispatchError] = event.data;
          let errorInfo;

          if (dispatchError.isModule) {
            const decoded = api.registry.findMetaError(dispatchError.asModule);
            errorInfo = `${decoded.section}.${decoded.name}`;
          } else {
            errorInfo = dispatchError.toString();
          }

          console.log(`Transaction failed: ${errorInfo}`);
        } else if (api.events.balances.Transfer.is(event)) {
          const [from, to, amount] = event.data;
          console.log(
            `LLD Transfer successful: ${amount} from ${from} to ${to}`,
          );
        }
      });

      unsub();
    }
  },
);
```

### Monitor LLD Transfers

To monitor LLD transfers, subscribe to system events and filter for `Balances::Transfer` events.

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

### Retrieve LLD Transaction Details Using Block Hash and Index

Many infrastructure providers on existing blockchains, e.g. Ethereum, consider a transaction's hash as a unique identifier. In Substrate-based chains, a transaction's hash only serves as a fingerprint of the information within a transaction, and there are times when two transactions with the same hash are both valid.
On a Substrate blockchain transactions (a.k.a. extrinsics) are uniquely identified by block hash and their index.

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
    api.events.balances.Transfer.is(event),
  );
  transferEvents.forEach(({ event }) => {
    const [fromAccount, toAccount, amount] = event.data;
    console.log(
      `Transfer of ${amount} grains of LLD from ${fromAccount} to ${toAccount}`,
    );
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

## Liberland Merit (LLM)

LLM is an on-chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with ID of 1.

### Receive Wallet Balance

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

### Coin Transfer

For token transfers with transaction status monitoring, you can use the `assets.transfer` method and subscribe to events. This allows you to track when the transaction is included in a block and finalized on the blockchain.

```javascript
import { ApiPromise, WsProvider, Keyring } from "@polkadot/api";

const provider = new WsProvider("<WS_ENDPOINT>");
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: "sr25519" });
const sender = keyring.addFromUri("<SENDER-ACCOUNT-PRIVATE-KEY>");
// The following value 1 is the ID token of LLM.
const transferExtrinsic = api.tx.assets.transfer(
  1,
  "<WALLET_ADDRESS>",
  1_000_000_000_000,
); // 1_000_000_000_000 = 1 LLM

// Monitor transaction status
const unsub = await transferExtrinsic.signAndSend(
  sender,
  ({ status, events, dispatchError }) => {
    console.log(`Current transaction status: ${status.type}`);

    if (status.isInBlock) {
      console.log(`Transaction included in block: ${status.asInBlock.toHex()}`);
    }

    if (status.isFinalized) {
      console.log(
        `Transaction finalized in block: ${status.asFinalized.toHex()}`,
      );

      // Check if the transaction was successful
      events.forEach(({ event }) => {
        if (api.events.system.ExtrinsicSuccess.is(event)) {
          console.log("Transaction succeeded");
        } else if (api.events.system.ExtrinsicFailed.is(event)) {
          const [dispatchError] = event.data;
          let errorInfo;

          if (dispatchError.isModule) {
            const decoded = api.registry.findMetaError(dispatchError.asModule);
            errorInfo = `${decoded.section}.${decoded.name}`;
          } else {
            errorInfo = dispatchError.toString();
          }

          console.log(`Transaction failed: ${errorInfo}`);
        } else if (api.events.assets.Transferred.is(event)) {
          const [assetId, from, to, amount] = event.data;
          if (assetId.eq(1)) {
            console.log(
              `Transfer successful: ${amount} LLM from ${from} to ${to}`,
            );
          }
        }
      });

      unsub();
    }
  },
);
```

### Monitor LLM Transfers

To monitor LLM transfers, subscribe to system events and filter for `Assets::Transferred` events with an ID of 1.

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

### Retrieve LLM Transaction Details Using Block Hash and Index

Many infrastructure providers on existing blockchains, e.g. Ethereum, consider a transaction's hash as a unique identifier. In Substrate-based chains, a transaction's hash only serves as a fingerprint of the information within a transaction, and there are times when two transactions with the same hash are both valid.
On a Substrate blockchain transactions (a.k.a. extrinsics) are uniquely identified by block hash and their index.

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
