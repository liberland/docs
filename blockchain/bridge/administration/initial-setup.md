# Initial Setup

## Ethereum Contracts

### Deployment

Prerequisites:

1. Create account on [Etherscan](https://etherscan.io/) and get the API key.
2. Create account on [Alchemy](https://dashboard.alchemy.com/), create Ethereum Mainnet app and get the HTTPS URL.
3. Create MetaMask wallet, fund it with a minimal amount of Eth (for tx fees only) and export its private key.

```
export ETHERSCAN_API_KEY=YOUR_KEY_HERE
export ALCHEMY_URL=YOUR_URL_HERE
export ETHEREUM_PRIVATE_KEY=YOUR_PRIVATE_KEY_HERE

git clone https://github.com/liberland/liberland_substrate.git -b v11.1.0
cd liberland_substrate/eth-bridge/contracts
curl -L https://foundry.paradigm.xyz | bash # only if foundry isn't installed already
forge install
forge build

forge script script/Deploy.s.sol --rpc-url $ALCHEMY_URL --private-key $ETHEREUM_PRIVATE_KEY --broadcast --verify
```

Create PR with new `broadcast/*` files.

### OpenZeppelin Defender

1. Create new account on [OpenZeppelin Defender](https://defender.openzeppelin.com). Add all other bridge admins as collabolators.
2. Add both bridge proxy contracts. Their ABI should be fetched automatically by Defender from Etherscan.
3. Create Multisig wallet (_Add Contract_ -> _Create Gnosis Safe_). Name it _Super Admin_, add all bridge admins as owners and set threshold to something high (ex. 80% of all owners)
4. Create Multisig wallet. Name it _Admin_, add all bridge admins as owners and set threshold to something low (ex. 1 or 2)

Grant roles to multisig wallets on both contracts:

1. Go to the contract on Etherscan
2. Click _Contract_ -> _Write as Proxy_
3. Click _Connect to Web3_
4. Click _grantRole_
    * `role (bytes32)` is: _0xa49807205ce4d355092ef5a8a18f56e8913cf4a201fbe287825b095693c21775_ (that's Admin role)
    * put _Admin's_ multisig address in `account (address)`
    * click _Write_
4. Click _grantRole_
    * `role (bytes32)` is: _0x7613a25ecc738585a232ad50a301178f12b3ba8887d13e138b523c4269c47689_ (that's Super Admin role)
    * put _Super Admin's_ multisig address in `account (address)`
    * click _Write_
5. (warning - after this step only multisig wallet will be able to manage the contract) Click _renounceRole_
    * `role (bytes32)` is: _0x7613a25ecc738585a232ad50a301178f12b3ba8887d13e138b523c4269c47689_ (that's Super Admin role)
    * put your address in `account (address)`
    * click _Write_


## Substrate

This needs to be done by all admins. See [Polkadot docs](https://support.polkadot.network/support/solutions/articles/65000181826-how-to-create-and-use-a-multisig-account#How-to-create-a-multisig-account). You need two multisig wallets:

* one for Super Admin, with high threshold (ex. 80% of all owners)
* one for Admin, which threshold `1`.