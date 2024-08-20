# Liberland Chain Explorer API

## Overview

Liberland is running a chain indexer & explorer with publicly available GraphQL API. This API allows fetching & filtering historical information about the chain, especially data about past events and extrinsics (transactions).

For interacting with the API, you can use one of many [GraphQL clients](https://graphql.org/community/tools-and-libraries/?tags=client) or run raw HTTP queries.

## Endpoints & reference docs

API & GraphQL Playground endpoints:
* Liberland Mainnet: https://archive.mainnet.liberland.org/
* Bastiat (Liberland Testnet): https://archive.testchain.liberland.org/graphql

Visit the [Playground](https://archive.mainnet.liberland.org/) to see up-to-date reference schema and docs.

## Paging

Queries can use `first` param to limit the amount of returned entries and `after` param to get next page of data.
Use `hasNextPage` and `endCursor` values of `pageInfo` entity to populate them.
You can also use `totalCount` value to know total number of entries.

## Entities

### `assetTransfer`

All transfers of any [pallet-assets](https://paritytech.github.io/polkadot-sdk/master/pallet_assets/index.html)-based assets. Includes LLM (which is asset `1`), but not LLD.
Contains following values:

* `id` - unique identifier of this transfer - based on `blockNumber` and `eventIndex`
* `asset` - ID of the asset being transferred. See [list of assets on Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/assets).
* `fromId` - Address of the account that sent the asset
* `toId` - Address of the account that received the asset
* `value` - Amount of the asset transferred. Subject to decimals config of given asset (so value `1000000000000` for LLM asset means `1 LLM`)
* `blockId` - Hash of the block containing this transfer
* `blockNumber` - Number of the block containing this transfer
* `extrinsicIndex` - Index of the extrinsic in the block that caused this transfer. May be null if transfer wasn't done by extrinsic.
* `eventIndex` - Index of the transfer event in the block.
* `block` - Additional details about the block, including timestamp.

### `merit`

All transfers of the LLM token. Contains following values:

* `id` - unique identifier of this transfer - based on `blockNumber` and `eventIndex`
* `fromId` - Address of the account that sent the asset
* `toId` - Address of the account that received the asset
* `value` - Amount of the asset transferred. Subject to decimals config of given asset (so value `1000000000000` for LLM asset means `1 LLM`)
* `blockId` - Hash of the block containing this transfer
* `blockNumber` - Number of the block containing this transfer
* `extrinsicIndex` - Index of the extrinsic in the block that caused this transfer. May be null if transfer wasn't done by extrinsic.
* `eventIndex` - Index of the transfer event in the block.
* `block` - Additional details about the block, including timestamp.

### `transfer`

All transfers of the LLD token. Doesn't include actions like staking or transaction fees. Contains following values:

* `id` - unique identifier of this transfer - based on `blockNumber` and `eventIndex`
* `fromId` - Address of the account that sent the asset
* `toId` - Address of the account that received the asset
* `value` - Amount of the asset transferred. Subject to decimals (so value `1000000000000` for means `1 LLD`)
* `blockId` - Hash of the block containing this transfer
* `blockNumber` - Number of the block containing this transfer
* `extrinsicIndex` - Index of the extrinsic in the block that caused this transfer. May be null if transfer wasn't done by extrinsic.
* `eventIndex` - Index of the transfer event in the block.
* `block` - Additional details about the block, including timestamp.

### `staking`

LLD staking events. Contains following values:

* `id` - unique identifier of this staking event - based on `blockNumber` and `eventIndex`
* `userId` - Address of the account that this event refers to
* `value` - Amount of the asset transferred. Subject to decimals (so value `1000000000000` for means `1 LLD`)
* `method` - Method that triggered this event. Possible values:
    * `Bonded` - User staked LLD
    * `Withdrawn` - User unstaked LLD
    * `Rewarded` - User got rewarded with interest
* `blockId` - Hash of the block containing this transfer
* `blockNumber` - Number of the block containing this transfer
* `extrinsicIndex` - Index of the extrinsic in the block that caused this transfer. May be null if transfer wasn't done by extrinsic.
* `eventIndex` - Index of the transfer event in the block.
* `block` - Additional details about the block, including timestamp.

## Sample GraphQL queries

### Fetching LLD transfers of given user

Includes paging, fetches 50 entries per page.

```
query Transfers($userId: String, $cursor: Cursor) {
  transfers(
    filter: {
      or: [
        { fromId: { equalTo: $userId } },
        { toId: { equalTo: $userId } }
      ],
    },
    after: $cursor,
    first: 50,
    orderBy: BLOCK_NUMBER_DESC
  ) {
    nodes {
      id,
      fromId,
      toId,
      value,
      eventIndex,
      block {
        number
        timestamp
      },
    }
    pageInfo {
      hasNextPage,
      endCursor,
    }
    totalCount
  }
}
```

## Sample raw queries

### Fetching LLD transfers of a given user

URL: `https://archive.mainnet.liberland.org/`
Method: `POST`

Payload:
```
{
    "operationName": "Transfers",
    "variables": {
        "userId": "5EYCAe5g8CDuMsTief7QBxfvzDFEfws6ueXTUhsbx5V81nGH"
    },
    "query": "query Transfers($userId: String, $cursor: Cursor) {\n  transfers(\n    filter: {or: [{fromId: {equalTo: $userId}}, {toId: {equalTo: $userId}}]}\n    after: $cursor\n    first: 50\n    orderBy: BLOCK_NUMBER_DESC\n  ) {\n    nodes {\n      id\n      fromId\n      toId\n      value\n      eventIndex\n      block {\n        number\n        timestamp\n      }\n    }\n    pageInfo {\n      hasNextPage\n      endCursor\n    }\n    totalCount\n  }\n}\n"
}
```

To fetch next page, pass `endCursor` from previous call as `cursor` variable.

### Fetching LLM transfers of a given user

URL: `https://archive.mainnet.liberland.org/`
Method: `POST`

Payload:
```
{
    "operationName": "Merits",
    "variables": {
        "userId": "5EYCAe5g8CDuMsTief7QBxfvzDFEfws6ueXTUhsbx5V81nGH"
    },
    "query": "query Merits($userId: String, $cursor: Cursor) {\n  merits(\n    filter: {or: [{fromId: {equalTo: $userId}}, {toId: {equalTo: $userId}}]}\n    after: $cursor\n    first: 50\n    orderBy: BLOCK_NUMBER_DESC\n  ) {\n    nodes {\n      id\n      fromId\n      toId\n      value\n      eventIndex\n      block {\n        number\n        timestamp\n      }\n    }\n    pageInfo {\n      hasNextPage\n      endCursor\n    }\n    totalCount\n  }\n}\n"
}
```

To fetch next page, pass `endCursor` from previous call as `cursor` variable.

### Fetching asset transfers of a given user

URL: `https://archive.mainnet.liberland.org/`
Method: `POST`

Payload:
```
{
    "operationName": "AssetTransfers",
    "variables": {
        "userId": "5EYCAe5g8CDuMsTief7QBxfvzDFEfws6ueXTUhsbx5V81nGH"
    },
    "query": "query AssetTransfers($userId: String, $cursor: Cursor) {\n  assetTransfers(\n    filter: {or: [{fromId: {equalTo: $userId}}, {toId: {equalTo: $userId}}]}\n    after: $cursor\n    first: 50\n    orderBy: BLOCK_NUMBER_DESC\n  ) {\n    nodes {\n      id\n      asset\n      fromId\n      toId\n      value\n      eventIndex\n      block {\n        number\n        timestamp\n      }\n    }\n    pageInfo {\n      hasNextPage\n      endCursor\n    }\n    totalCount\n  }\n}\n"
}
```

To fetch next page, pass `endCursor` from previous call as `cursor` variable.

### Fetching staking events of a given user

URL: `https://archive.mainnet.liberland.org/`
Method: `POST`

Payload:
```
{
    "operationName": "Stakings",
    "variables": {
        "userId": "5EYCAe5g8CDuMsTief7QBxfvzDFEfws6ueXTUhsbx5V81nGH"
    },
    "query": "query Stakings($userId: String, $cursor: Cursor) {\n  stakings(\n    filter: {userId: {equalTo: $userId}}\n    after: $cursor\n    first: 50\n    orderBy: BLOCK_NUMBER_DESC\n  ) {\n    nodes {\n      id\n      userId\n      method\n      value\n      eventIndex\n      block {\n        number\n        timestamp\n      }\n    }\n    pageInfo {\n      hasNextPage\n      endCursor\n    }\n    totalCount\n  }\n}\n"
}
```

To fetch next page, pass `endCursor` from previous call as `cursor` variable.