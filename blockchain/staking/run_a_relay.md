# Run a testnet bridge relay

## Introduction

Bridge relay is a server that facilitates transfers between Liberland and Ethereum blockchains.

## Requirements

* TBD
* Docker with Docker Compose plugin installed

## Install

FIXME - update to main branch when ready

```
$ mkdir relay
$ cd relay
$ curl -L https://raw.githubusercontent.com/liberland/liberland_substrate/eth-bridge-relay/eth-bridge/docker-compose.testnet.yml -o docker-compose.yml
$ curl -L https://raw.githubusercontent.com/liberland/liberland_substrate/eth-bridge-relay/eth-bridge/config_bastiat-sepolia_docker.toml -o config.toml
$ docker pull liberland/blockchain-bridge-relay:latest
```

## Generate keys

```
docker run --rm liberland/blockchain-bridge-relay:latest --config config.toml gen-keys --key-type liberland
docker run --rm liberland/blockchain-bridge-relay:latest --config config.toml gen-keys --key-type ethereum
```

Securely and privately store the `Liberland secret seed` and `Ethereum private key`. Don't share them with anyone.

Send the `Ethereum address` and `Liberland address` to Bridge Administrator (FIXME: how? who?)

## Configure

Run the command below and:
1. When asked for overwrite, answer yes.
2. Leave default database file path (just hit Enter).
3. Leave default WebSocket URLs (just hit Enter).
4. When asked if running a relay, answer yes.
5. Provide keys generated in previous step.
6. Leave default contract addresses (just hit Enter).

```
$ docker run --rm -it -v $(pwd)/config.toml:/config.toml liberland/blockchain-bridge-relay:latest --config /config.toml init
Config file /config.toml already exists.
> Do you want to overwrite it? Yes
> Database file path: /data/sqlite.db
> WebSocket URL to your Substrate archive node: ws://liberland-node:9944/
> WebSocket URL to your Ethereum EL node:  ws://eth-node:8545/
> Are you running a relay? Yes
> Provide relay's substrate secret seed: [redacted]
> Provide relay's ethereum private key: [redacted]
> Are you running a watcher? No
> Contract address for LLM Bridge: 0x5fc8…5707
> Contract address for LLD Bridge: 0x9fe4…a6e0
Config written! You can now start the daemon.
```

## Run

```
docker compose up -d
```

## Monitor

### Ethereum node

```
docker compose logs --follow eth-node
```

### Liberland node

```
docker compose logs --follow liberland-node
```

### Relay

Note: it's expected for relay to crash and keep restarting until both ethereum and liberland nodes are synced.

```
docker compose logs --follow relay
```