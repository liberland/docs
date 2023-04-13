# Run a Liberland Node with Docker

 Prequirements:
 This guide assumes your running a Linux based operating system and have Docker already installed.

## Docker image details

Liberland's node docker image is hosted on Docker Hub: [liberland/blockchain-node](https://hub.docker.com/r/liberland/blockchain-node). It's build automatically from public [Dockerfile](https://github.com/liberland/liberland_substrate/blob/main/Dockerfile). Configuration:

* Node binary is stored at `/node`
* Embedded chain specifications are stored at `/specs/`
* Exposed ports: `30333`, `9933`, `9944`.
* Runs as unpriviledged user with UID 1000

## Usage examples

### Listing embedded chain specs

```bash
$ docker run -it --rm --entrypoint='/bin/sh' liberland/blockchain-node:latest -c 'ls /specs'
bastiat.json  bastiat.raw.json	mainnet.json  mainnet.raw.json	readme.md
```

### Minimal Bastiat (testnet) node with persistent data

To make sure your node's data is persistant, mount a host directory as a volume using `-v` argument:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm -v $HOME/liberland_data:/data liberland/blockchain-node:latest -d /data --chain /specs/bastiat.raw.json
```

### Using custom chain spec

To use custom chain spec, you must mount it into the container:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm -v $HOME/liberland_data:/data -v $HOME/custom_chain_spec.raw.json:/custom_chain_spec.raw.json liberland/blockchain-node:latest -d /data --chain /custom_chain_spec.raw.json
```

### Accessing your node locally via Polkadot.js Apps

To be able to access your node locally via Polkadot.js Apps, pass `--network=host` argument so that RPC port is accessible:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm --network=host -v $HOME/liberland_data:/data liberland/blockchain-node:latest -d /data --chain /specs/bastiat.raw.json
```

You'll now be able to access your node via [https://polkadot.js.org/apps/?rpc=ws://localhost:9944](https://polkadot.js.org/apps/?rpc=ws://localhost:9944).

### Complete example of running a validator on mainnet

This example:
* passes `-v $HOME/liberland_data:/data` to make data persistent on the host
* passes `--network=host` to make RPC accessible locally and P2P accessible on all interfaces
* passes `-d` to run in background
* passes `--restart always` to automatically restart node on reboot / crash
* uses Bastiat chain spec
* passes `--validator` option to node to enable acting as validator

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run --name liberland -d --network=host --restart always -v $HOME/liberland_data:/data liberland/blockchain-node:latest -d /data --chain /specs/mainnet.raw.json --validator
```

You can:
* monitor this instance with `docker ps -a`
* see its logs with `docker logs liberland`
* stop with `docker stop liberland` - note that it will restart automatically on reboot / Docker restart
* restart with `docker restart liberland`
* remove with `docker rm liberland`

#### Generate session keys

`author_rotateKeys` generates new keys and stores them in your node.

```
user@host:~/liberland/$ curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}' http://127.0.0.1:9933
{"jsonrpc":"2.0","result":"0x58db6952384f2d1f9600255a2fce9b116201e872e9951a0a0c0edd7c31124934c690eb603407f4b98a1c9fc0628d4b926fec03d577f233fda3af01d33e2a391b9ad7558c0ae9ba082b3b70236ec584471c92c3a5d78e9bc08f49de7c75961e132697e5419818bfcd31e1bc2cc7d0560a81db72a76af59374c1932bc7a96d773a","id":1}
```

Copy the contents of `result` from your terminal, thats the new session keys.

With an instance running like this you may now follow the [Run a validator](../staking/run_a_validator.md#wait-for-your-node-to-sync) starting with **Wait for your node to sync** section.
