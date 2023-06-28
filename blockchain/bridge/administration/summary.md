# Ethereum Bridge administrator guide

## Introduction

This guide is for mainnet only.

There are two roles in the bridge:

* Super Admin, which is capable of adding relays, removing watchers and changing number of required votes (a.k.a. things that potential attacker would really like to do)
* Admin, which is capable of adding watchers, removing relays, changing fees and stopping/starting the bridge

Super Admin MUST be a secure multisig wallet, requiring sign-off from multiple parties. Admin should be a multisig wallet with a low threshold.

The recommendation is to use the same people for super admin and admin accounts, but with different thresholds (for ex. 4/5 for Super Admin and 1/5 for Admin).

## Creating Ethereum multisig wallet

[Safe](https://app.safe.global) is the wallet of choice for the bridge administration.

The steps are as follows:
* collect Ethereum addresses from all designated owners
* one person creates the wallet
* other people import the wallet

### Creating Safe Wallet

This needs to be done by the first person only. Follow these steps twice - once for Super Admin and once for Admin:

1. Visit the [Create new Safe Account page](https://app.safe.global/new-safe/create?chain=eth).
2. Connect your standard Ethereum wallet (ex. MetaMask).
3. Name the wallet: `Bridge Super Admin` or `Bridge Admin` and click `Next`.
4. Add keys of all owners.
5. Set the threshold. For normal Admin this should be `1`, for Super Admin this should be something higher (ex. 80% of all owners).
6. Click `Next`, review the details, click `Next`. Wait for the wallet to be created.
7. Click `Start using Safe Wallet`
8. Copy the new wallet address from top left corner and share it with all other owners - remember to tell whether this is Admin or Super Admin.

### Importing Safe Wallet

This needs to be done by all owners except the wallet creator. Follow these steps twice - once for Super Admin and once for Admin:

1. Visit the [Add existing account page](https://app.safe.global/new-safe/load?chain=eth)
2. Put the name of wallet you got from the creator: `Bridge Super Admin` or `Bridge Admin`
3. Put the wallet address you got from the creator and click `Next`.
4. Optionally put names to wallet owner addresses (helpful to later see who signed and who didn't) and click `Next`.
5. Review and click `Add`.

## Creating Substrate multisig wallet

This needs to be done by everyone. See [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-create-a-multisig-account). You need two wallets:

* one for Super Admin, with high threshold (ex. 80% of all owners)
* one for Admin, which threshold `1`.

## Basic admin tasks

### Add new operator on Ethereum

#### Initial tx creation

This needs to be done only by the first person:

// FIXME create json template?

1. Go to your [Safe Wallet](https://app.safe.global/).
2. Select the `Super Admin` wallet.
3. Click `New transaction` on the left.
4. Click `Contract interaction`.
5. Enter the contract address:
    * for EthLLMBridge: `FIXME`
    * for EthLLDBridge: `FIXME`
6. Enter ABI - copy-paste [this file](https://gist.githubusercontent.com/kacperzuk-neti/e5c6667d032f882f9f9cb822d2edef0a/raw/2c51ea65f420ca5d3d4228c8503f0d72e3329071/bridge.json) // FIXME check if maybe it will load it from etherscan verified contract?
7. In Contract Method Selector choose `setVotesRequired` and set to one higher than current.
8. Click `Add transaction`
9. In Contract Method Selector choose `grantRole`.
10. Put `0x077a1d526a4ce8a773632ab13b4fbbf1fcc954c3dab26cd27ea0e2a6750da5d7` in `role (bytes32)`. That's the Relay role.
11. Put operators address in `account (address)`
12. Click `Add transaction`
13. In Contract Method Selector choose `grantRole`.
14. Put `0x2125d1e225cadc5c8296e2cc1f96ee607770bf4a4a16131e62f6819937437c89` in `role (bytes32)`. That's the Watcher role.
15. Put operators address in `account (address)`
16. Click `Add transaction`
17. Repeat steps 5-16 for second contract.
18. Click `Create batch`
19. Click `Send Batch` and `Submit`

#### Signatures from other admin wallet owners

1. Go to your [Safe Wallet](https://app.safe.global/).
2. Select the `Super Admin` wallet.
3. Select transaction in `Transaction queue`
4. Review and click `Confirm`
5. Review and click `Submit`

### Add new operator on Substrate

#### Initial tx creation

This needs to be done only by the first person:

1. Go to [Polkadot.js Apps for Liberland Mainnet](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/extrinsics)
2. Select multisig Super Admin account
3. Select `utility` and `batchAll(calls)`
4. in `0: Call: Call` choose `ethLLDBridge` and `setVotesRequired`. Set `votesRequired` to one higher than current.
5. Click `Add item`
6. in `1: Call: Call` choose `ethLLDBridge` and `addRelay`. Put operator's address in `relay: AccountId32`.
7. Click `Add item`
8. in `2: Call: Call` choose `ethLLDBridge` and `addWatcher`. Put operator's address in `relay: AccountId32`.
9. Click `Submit transaction` and follow steps from step 2 of [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-use-a-multisig-account). Remember to copy the multisig call data before clicking `Sign and Submit`!

Repeat for `ethLLMBridge`.

#### Signatures from other admin wallet owners

Follow from step 4 of [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-use-a-multisig-account).

### Remove operator on Ethereum

#### Initial tx creation

This needs to be done only by the first person:

// FIXME create json template?

1. Go to your [Safe Wallet](https://app.safe.global/).
2. Select the `Super Admin` wallet.
3. Click `New transaction` on the left.
4. Click `Contract interaction`.
5. Enter the contract address:
    * for EthLLMBridge: `FIXME`
    * for EthLLDBridge: `FIXME`
6. Enter ABI - copy-paste [this file](https://gist.githubusercontent.com/kacperzuk-neti/e5c6667d032f882f9f9cb822d2edef0a/raw/2c51ea65f420ca5d3d4228c8503f0d72e3329071/bridge.json) // FIXME check if maybe it will load it from etherscan verified contract?
7. In Contract Method Selector choose `setVotesRequired` and set to one lower than current.
8. Click `Add transaction`
9. In Contract Method Selector choose `revokeRole`.
10. Put `0x077a1d526a4ce8a773632ab13b4fbbf1fcc954c3dab26cd27ea0e2a6750da5d7` in `role (bytes32)`. That's the Relay role.
11. Put operators address in `account (address)`
12. Click `Add transaction`
13. In Contract Method Selector choose `revokeRole`.
14. Put `0x2125d1e225cadc5c8296e2cc1f96ee607770bf4a4a16131e62f6819937437c89` in `role (bytes32)`. That's the Watcher role.
15. Put operators address in `account (address)`
16. Click `Add transaction`
17. Repeat steps 5-16 for second contract.
18. Click `Create batch`
19. Click `Send Batch` and `Submit`

#### Signatures from other admin wallet owners

1. Go to your [Safe Wallet](https://app.safe.global/).
2. Select the `Super Admin` wallet.
3. Select transaction in `Transaction queue`
4. Review and click `Confirm`
5. Review and click `Submit`

### Remove operator on Substrate

#### Initial tx creation

This needs to be done only by the first person:

1. Go to [Polkadot.js Apps for Liberland Mainnet](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/extrinsics)
2. Select multisig Super Admin account
3. Select `utility` and `batchAll(calls)`
4. in `0: Call: Call` choose `ethLLDBridge` and `setVotesRequired`. Set `votesRequired` to one lower than current. 
5. Click `Add item`
6. in `1: Call: Call` choose `ethLLDBridge` and `addRelay`. Put operator's address in `relay: AccountId32`.
7. Click `Add item`
8. in `2: Call: Call` choose `ethLLDBridge` and `addWatcher`. Put operator's address in `relay: AccountId32`.

Repeat for `ethLLMBridge`.

#### Signatures from other admin wallet owners

Follow from step 4 of [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-use-a-multisig-account).