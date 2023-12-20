# Add operator to the bridge
## Add new operator on Ethereum

### Initial tx creation

This needs to be done only by the first person. Feel free to ask someone from the dev team to do it.

1. Go to [OpenZeppelin Defender dashboard](https://defender.openzeppelin.com/#/admin)
1. Click `+ Add Proposal` (make sure you're on the main dashboard and not on a specific contract)
1. Click `Admin Action`
1. Select `LLM Bridge` as target contract
1. Select `setVotesRequired` function
    * set to one higher than current
    * Click `Add Step`
1. Click `+ Add Step` -> `Admin Action`
1. Select `LLM Bridge` as target contract
1. Select `grantRole` function
    * Put `0x077a1d526a4ce8a773632ab13b4fbbf1fcc954c3dab26cd27ea0e2a6750da5d7` in `role`. That's the Relay role.
    * Put operators address in `account`
    * Click `Add Step`
1. Click `+ Add Step` -> `Admin Action`
1. Select `LLM Bridge` as target contract
1. Select `grantRole` function
    * Put `0x2125d1e225cadc5c8296e2cc1f96ee607770bf4a4a16131e62f6819937437c89` in `role`. That's the Watcher role.
    * Put operators address in `account`
    * Click `Add Step`
1. Click `+ Add Step` -> `Admin Action`
1. Select `LLD Bridge` as target contract
1. Select `setVotesRequired` function
    * set to one higher than current
    * Click `Add Step`
1. Click `+ Add Step` -> `Admin Action`
1. Select `LLD Bridge` as target contract
1. Select `grantRole` function
    * Put `0x077a1d526a4ce8a773632ab13b4fbbf1fcc954c3dab26cd27ea0e2a6750da5d7` in `role`. That's the Relay role.
    * Put operators address in `account`
    * Click `Add Step`
1. Click `+ Add Step` -> `Admin Action`
1. Select `LLD Bridge` as target contract
1. Select `grantRole` function
    * Put `0x2125d1e225cadc5c8296e2cc1f96ee607770bf4a4a16131e62f6819937437c89` in `role`. That's the Watcher role.
    * Put operators address in `account`
    * Click `Add Step`
1. Select `Multisig` execution strategy
1. Select `Super Admin` wallet
1. Put title and description
1. Click `Create proposal`
1. Click `Approve`

Ask other owners to approve the proposal.

### Approval from other admin wallet owners

1. Go to [OpenZeppelin Defender dashboard](https://defender.openzeppelin.com/#/admin)
2. Click the `VIEW PROPOSAL` for the active proposal
3. Review details of the proposal
4. Click `Approve and Execute`. If there's no such option (meaning more approvals are required), click `Approve`.

## Add new operator on Substrate

### Initial tx creation

This needs to be done only by the first person:

1. Go to [Polkadot.js Apps for Liberland Mainnet](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/extrinsics)
1. Select multisig Super Admin account
1. Select `utility` and `batchAll(calls)`
1. in `0: Call: Call` choose `ethLLDBridge` and `setVotesRequired`. Set `votesRequired` to one higher than current.
1. Click `Add item`
1. in `1: Call: Call` choose `ethLLDBridge` and `addRelay`. Put operator's address in `relay: AccountId32`.
1. Click `Add item`
1. in `2: Call: Call` choose `ethLLDBridge` and `addWatcher`. Put operator's address in `relay: AccountId32`.
1. Click `Add item`
1. in `3: Call: Call` choose `ethLLMBridge` and `setVotesRequired`. Set `votesRequired` to one higher than current.
1. Click `Add item`
1. in `4: Call: Call` choose `ethLLMBridge` and `addRelay`. Put operator's address in `relay: AccountId32`.
1. Click `Add item`
1. in `5: Call: Call` choose `ethLLMBridge` and `addWatcher`. Put operator's address in `relay: AccountId32`.
1. Click `Submit transaction` and follow steps from step 2 of [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-use-a-multisig-account).
    * remember to copy the `multisig call data` before submission!

Ask other owners for approvals and share the copied `multisig call data` with them. Person making the final approval will need it.

### Signatures from other admin wallet owners

Follow from step 4 of [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-use-a-multisig-account).