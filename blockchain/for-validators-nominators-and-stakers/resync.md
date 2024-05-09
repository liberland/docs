# Resyncing node

To resync your Liberland Node, you need to:
1. stop the node
2. remove the directory containing Liberland Node Database (`chains/mainnet/db`)
3. restart the node
4. wait until it resyncs

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

Run the following commands on your server:

```
systemctl stop liberland-validator
rm -rf /opt/liberland/data/chains/mainnet/db
systemctl start liberland-validator
```

# Docker installs

If you followed the [Complete example of running a validator on mainnet](../dev/docker.md) guide, run these commands:

```
docker stop liberland
rm -rf $HOME/liberland_data/chains/mainnet/db
docker start liberland
```

If you run it in a custom way, adjust the container name and DB path accordingly.