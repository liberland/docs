Liberland blockchain is based on [Substrate](https://substrate.io/)

Recommended way to interact with the chain programmatically is through [PolkadotjsApi](https://github.com/polkadot-js/api)

[Testnet chain explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org%2F#/explorer)  
[Testnet endpoint](wss://testchain.liberland.org/)  
[Mainnet chain explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org%2F#/staking)  
[Mainnet endpoint](wss://mainnet.liberland.org/)  

# LLM

## Receive wallet balance
LLM is an on chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with id of 1

### Using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
// <ASSET_ID> of LLM is 1
const LLMInfo = await api.query.assets.account(<ASSET_ID>, <WALLET_ADDRESS>);
console.log(LLMInfo.toJSON().data?.balance ?? '0x0')
```
## Create Address
To create a new address, a minimum of 1 LLD needs to be sent as an existential deposit

### using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
import Keyring from "@polkadot/keyring";

const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: 'sr25519' });
const sender = keyring.addFromUri(<SENDER-ACCOUNT-PRIVATE-KEY>);
// minimum <AMOUNT> is new BN('1000000000000');
const transferExtrinsic = api.tx.balances.transfer(<WALLET_ADDRESS_TO_CREATE>, <AMOUNT>);
const txHash = await transferExtrinsic.signAndSend(sender) ;
```

## Receive list of transactions by block number

```
const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
const hash = await api.rpc.chain.getBlockHash(<BLOCKNUMBER>);
const block = await api.rpc.chain.getBlock(hash);
console.log(block.block.extrinsics.toHuman());
```

## Receive the last block number

### Using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
const bestNumber = await api.derive.chain.bestNumber();
console.log(bestNumber.toNumber());
```

## Receive transaction information using TXID

Transactions (a.k.a. extrinsics) are uniquely identified by block hash + their index. See also https://wiki.polkadot.network/docs/build-protocol-info#unique-identifiers-for-extrinsics

```
const txId = {
  blockHash: BLOCK_HASH,
  index: EXTRINSIC_INDEX,
};

const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
const apiAt = await api.at(txId.blockHash);
const allEvents = await apiAt.query.system.events();

const txEvents = allEvents.filter(({ phase }) => phase.isApplyExtrinsic && phase.asApplyExtrinsic.eq(txId.index));

const successEvent = txEvents.find(({ event }) => api.events.system.ExtrinsicSuccess.is(event));
const failureEvent = txEvents.find(({ event }) => api.events.system.ExtrinsicFailed.is(event));

if (successEvent) {
  const transferEvents = txEvents.filter(({ event }) => api.events.assets.Transferred.is(event));
  transferEvents.forEach(({ event }) => {
    const [assetId, fromAccount, toAccount, amount] = event.data;
    if (assetId == 1) {
      console.log(`Transfer of ${amount} grains of LLM from ${fromAccount} to ${toAccount}`);
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

```
const { ApiPromise, WsProvider } = require('@polkadot/api');
import Keyring from "@polkadot/keyring";

const provider = new WsProvider(<WS_ENDPOINT>);
const api = await ApiPromise.create({ provider });
const keyring = new Keyring({ type: 'sr25519' });
const sender = keyring.addFromUri(<SENDER-ACCOUNT-PRIVATE-KEY>);
const transferExtrinsic = api.tx.llm.sendLlm(<ACCOUNT_TO>, <AMOUNT>);
const txHash = await transferExtrinsic.signAndSend(sender) ;
```

See also https://polkadot.js.org/docs/api/cookbook/tx/#how-do-i-get-the-decoded-enum-for-an-extrinsicfailed-event for example on how to see if tx succeeded.