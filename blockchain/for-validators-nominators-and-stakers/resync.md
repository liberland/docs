# Resyncing node

To resync your Liberland Node, you need to:
1. If you're a validator and the chain is live and not stalled:
   1. Stop validating using [Liberland dApp](https://blockchain.liberland.org/) or [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss://mainnet.liberland.org#/legacy-staking/actions)
   2. Make sure your node is not in [the active validator set](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/legacy-staking)
2. stop the node
3. remove the directory containing Liberland Node Database (`chains/mainnet/db`)
4. restart the node
5. wait until it resyncs

Node data directory structure is as follows:

```
chains
└── mainnet
    ├── db
    ├── keystore
    └── network
```

**DO NOT** remove `keystore` or `network` directories. Only remove the `db` directory.

For a detailed guide, please choose the proper instruction according to the method used to install the node:

* [Automated script](#automated-script-installs) (a.k.a. nodes installed with [this guide](./run-a-validator.md#option-1-automatic-script))
* [Docker](#docker-installs)


# Automated script installs

If your node is a validator and the chain is live and not stalled:
1. Stop validating using [Liberland dApp](https://blockchain.liberland.org/) or [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss://mainnet.liberland.org#/legacy-staking/actions)
2. Make sure your node is not in [the active validator set](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/legacy-staking)

When your node is no longer a validator, or the chain is currently stalled, run the following commands on your server:

```
systemctl stop liberland-validator
rm -rf /opt/liberland/data/chains/mainnet/db
systemctl start liberland-validator
```

# Docker installs

If your node is a validator and the chain is live and not stalled:
1. Stop validating using [Liberland dApp](https://blockchain.liberland.org/) or [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss://mainnet.liberland.org#/legacy-staking/actions)
2. Make sure your node is not in [the active validator set](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/legacy-staking)

When your node is no longer a validator, or the chain is currently stalled, run the following commands on your server:

```
docker stop liberland
rm -rf $HOME/liberland_data/chains/mainnet/db
docker start liberland
```

If you run it in a custom way, and not with the [Complete example of running a validator on mainnet](../dev/docker.md) guide, adjust the container name and DB path accordingly.