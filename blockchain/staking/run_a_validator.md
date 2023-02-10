# Run a validator

## Introduction

This guide will walk you through the process of setting up a new validator on Liberland Chain.

Note:
* *DO NOT* expose your validators RPC ports (9933 and 9944 by default) publicly on the internet. Treat validators with more care than full nodes.
* You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.

## Requirements

* ~10 GB of free disk space

## Installation
### Option 1: automatic script

This script is for Ubuntu and Debian servers. If you're not running Ubuntu or Debian, please contact dev team - they can add support for your distribution.

Run the following command on your server:
```
curl -sSL https://raw.githubusercontent.com/liberland/liberland_substrate/main/scripts/install/install.sh | bash
```

The script will ask you for confirmation before every action. It will:
* install dependencies
* download liberland node and chain specification
* setup a systemd service, so that the node starts automatically
* configure time synchronization
* generate session keys for use in next step

If everything goes OK, you will see something like this:

```
Your node is now running. Useful commands:
	Check status: sudo systemctl status liberland-validator
	Stop: sudo systemctl stop liberland-validator
	Start: sudo systemctl start liberland-validator
	Logs: sudo journalctl -u liberland-validator
Node data is stored in /opt/liberland/data.
Session keys for your node: [long text starting with 0x here]
```

Copy the session keys, you will need them when adding validator.

### Option 2: using docker

See [Docker guide](../dev/docker.md).

### Option 3: manually using prebuilt binaries

See [Using prebuilt binary](./using_prebuilt_binary.md)

### Option 4: using source

See [Using source](./using_source.md)

## Wait for your node to sync

Monitor logs of your node.

While syncing, you will see `Syncing` messages and lots of `maybe_release ran all the way` messages.

When synced, `maybe_release ran all the way` will mostly disappear and you will see mostly `Idle` and `Imported` messages.

## Add validator

> Note that in order to do this step you will need some LLD, so ask someone to give you some if you dont already have it.

1. Visit [Staking Accounts on Polkadot.js Apps for PowellGoHome](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking/actions)
2. Click "+ Validator" button.
3. Set your stash and controller accounts and select how much LLD you want to bond.
4. Click "Next" button.
5. Paste the session keys you got from installation step to `Keys from rotateKeys` form.
    * Note: if you lost your session keys, see [Regenerating session keys](./regenerate_session_keys.md)
6. Click "Bond & Validate"

## Verify

Immediately after adding validator, you should see it as "Waiting":

1. Visit [Staking on Polkadot.js Apps for PowellGoHome](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking)
2. Click "Waiting" button.
3. You should see your Stash account in the "Intentions" table.

Now you have to wait to see if it gets elected to current set of validators. You may need to wait until new era starts and then the chance of being elected is based on the amount of staked LLD. To see current set of validators:

1. Visit [Staking on Polkadot.js Apps for PowellGoHome](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking)
2. Click "All validators" button.
2. Click "Active" button.
3. You should see list of active validators in the "Validators" table.

## Optional: add nominators
Once your validator is up and running and you have a solid track record of no downtime you can ask other LLD holders to nominate your validator node.
