# Run a validator

## Introduction

This guide will walk you through the process of setting up a new validator on Liberland Chain for non technical people.
[You can follow along a video here](https://www.youtube.com/watch?v=ufV7igODxcQ)
## Requirements

* Liberland wallet with at least 200 LLD. [Ask to be onboarded](https://matrix.to/#/#liberland-node:matrix.org)
* [PolkadotJs wallet](https://polkadot.js.org/extension/)
* A helper [Ask here if you dont have one](https://matrix.to/#/#liberland-node:matrix.org)

## Get wallet
* Go to [PolkadotJs wallet](https://polkadot.js.org/extension/)
* Download extension
* Use the extension and create a new wallet. Save the mnemonic key somewhere safe. If you lose the mnemonic key, your account is lost.

## Set up a server
* In this step, we will buy some server space and give access to a helper so he can setup the technical part of a validator for us.

* This guide is for digital ocean, but other server providers will work too.

[Go to Digital ocean](https://www.digitalocean.com/)

* Ask your helper for his ssh pubkey.
* Create a digital ocean account
* Click on create, and pick droplet
* Create a Ubuntu, version 22 droplet with at least 25GB of disk and 1GB of RAM ($6 option is fine)
* When creating a droplet, under access it will give option of password or ssh. Pick ssh. This will allow your helper to securely connect to your server.
* Add the ssh pubkey from your helper to the server.
* Create the droplet.

* Wait for a minute for droplet to initialize.
* Click on the droplet and copy the IP address and sent the IP to your helper.
* Wait for the helper to inform you that a validator is running.
* Do note that at this time, the helper has full access to your validator, and may decide to *hack* it, which is a potential security risk.
* In order to revoke access to your helper Go to Settings > Security and under SSH keys find your helper and under more pick delete.
* If something is wrong and you need to re-add access to your helper, go to Settings > Security and add ssh key of your helper again.

* At this point, your helper will give you your validator id which is needed for the next step
## Add validator

> Note that in order to do this step you will need some LLD, so ask someone to give you some if you dont already have it.

1. Visit [Staking Accounts on Polkadot.js Apps for Bastiat](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking/actions)
2. Click "+ Validator" button.
3. Set your stash and controller accounts and select how much LLD you want to bond (pick 100 for now).
4. Click "Next" button.
5. Paste the session keys you got from your helper.
    * Note: if you lost your session keys, see [Regenerating session keys](./regenerate_session_keys.md) to make them or ask the helper for them again.
6. Click "Bond & Validate"

## Verify

Immediately after adding validator, you should see it as "Waiting":

1. Visit [Staking on Polkadot.js Apps for Bastiat](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking)
2. Click "Waiting" button.
3. You should see your Stash account in the "Intentions" table.

You are now officially a validator on Liberland! Enjoy the staking rewards!

Now you have to wait to see if it gets elected to current set of validators. You may need to wait until new era starts and then the chance of being elected is based on the amount of staked LLD. To see current set of validators:

1. Visit [Staking on Polkadot.js Apps for Bastiat](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking)
2. Click "All validators" button.
2. Click "Active" button.
3. You should see list of active validators in the "Validators" table.

## Optional: add nominators
Once your validator is up and running and you have a solid track record of no downtime you can ask other LLD holders to nominate your validator node.
