Liberland blockchain is based on [Substrate](https://substrate.io/)

Recommended way to interact with the chain programmatically is through [PolkadotjsApi](https://github.com/polkadot-js/api)

[Testnet chain explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org%2F#/explorer)  
[Testnet endpoint](wss://testchain.liberland.org/)  
[Mainnet chain explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org%2F#/staking)  
[Mainnet endpoint](wss://mainnet.liberland.org/)  

#LLM

##Receive wallet balance
LLM is an on chain asset of the [Assets pallet](https://paritytech.github.io/substrate/master/pallet_assets/index.html) with id of 1

###Using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = ApiPromise.create({ provider });
// <ASSET_ID> of LLM is 1
const LLMInfo = await api.query.assets.account(<ASSET_ID>, <WALLET_ADDRESS>);
console.log(LLMInfo.toJSON().data?.balance ?? '0x0')
```
##Create Address
To create a new address, a minimum of 1 LLD needs to be sent as an existential deposit

###using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
import Keyring from "@polkadot/keyring";

const provider = new WsProvider(<WS_ENDPOINT>);
const api = ApiPromise.create({ provider });
const sender = Keyring.addFromUri(<SENDER-ACCOUNT-PRIVATE-KEY>);
// minimum <AMOUNT> is new BN('1000000000000');
const transferExtrinsic = api.tx.balances.transfer(<WALLET_ADDRESS_TO_CREATE>, <AMOUNT>);
const txHash = await transferExtrinsic.signAndSend(sender) ;
```

##Receive list of transactions by block number
TODO KACPER

##Receive the last block number

###Using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
const provider = new WsProvider(<WS_ENDPOINT>);
const api = ApiPromise.create({ provider });
const bestNumber = await api.derive.chain.bestNumber();
console.log(bestNumber.toNumber());
```

##Receive transaction information using TXID
TODO KACPET

##Coin transfer

###Using polkadotJsApi
```
const { ApiPromise, WsProvider } = require('@polkadot/api');
import Keyring from "@polkadot/keyring";

const provider = new WsProvider(<WS_ENDPOINT>);
const api = ApiPromise.create({ provider });
const sender = Keyring.addFromUri(<SENDER-ACCOUNT-PRIVATE-KEY>);
const transferExtrinsic = api.tx.llm.sendLlm(<ACCOUNT_TO>, <AMOUNT>);
const txHash = await transferExtrinsic.signAndSend(sender) ;
```

