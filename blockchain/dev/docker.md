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
$ docker run -it --rm --entrypoint='/bin/sh' liberland/blockchain-node:powell_go_home -c 'ls /specs'
powell_go_home.json  powell_go_home.raw.json  readme.md

```

### Minimal PowellGoHome node with persistent data

To make sure your node's data is persistant, mount a host directory as a volume using `-v` argument:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm -v $HOME/liberland_data:/data liberland/blockchain-node:powell_go_home -d /data --chain /specs/powell_go_home.raw.json
```

### Using custom chain spec

To use custom chain spec, you must mount it into the container:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm -v $HOME/liberland_data:/data -v $HOME/custom_chain_spec.raw.json:/custom_chain_spec.raw.json liberland/blockchain-node:powell_go_home -d /data --chain /custom_chain_spec.raw.json
```

### Accessing your node locally via Polkadot.js Apps

To be able to access your node locally via Polkadot.js Apps, pass `-p 127.0.0.1:9944:9944` argument so that RPC port is published:

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run -it --rm -p 127.0.0.1:9944:9944 -v $HOME/liberland_data:/data liberland/blockchain-node:powell_go_home -d /data --chain /specs/powell_go_home.raw.json
```

You'll now be able to access your node via [https://polkadot.js.org/apps/?rpc=ws://localhost:9944](https://polkadot.js.org/apps/?rpc=ws://localhost:9944).

### Complete example of running a validator

This example:
* passes `-v $HOME/liberland_data:/data` to make data persistent on the host
* passes `-p 127.0.0.1:9933:9933 -p 127.0.0.1:9944:9944` to make RPC accessible locally
* passes `-p 30333:30333` to make P2P accessible on all interfaces
* passes `-d` to run in background
* passes `--restart always` to automatically restart node on reboot / crash
* uses PowellGoHome chain spec
* passes `--validator` option to node to enable acting as validator

```bash
$ mkdir $HOME/liberland_data
$ sudo chown 1000:1000 $HOME/liberland_data
$ docker run --name liberland -d -p 127.0.0.1:9933:9933 -p 127.0.0.1:9944:9944 -p 30333:30333 --restart always -v $HOME/liberland_data:/data liberland/blockchain-node:powell_go_home -d /data --chain /specs/powell_go_home.raw.json --validator
```

You can:
* monitor this instance with `docker ps -a`
* see its logs with `docker logs liberland`
* stop with `docker stop liberland` - note that it will restart automatically on reboot / Docker restart
* restart with `docker restart liberland`
* remove with `docker rm liberland`

With an instance running like this you may now follow the [Run a validator on PowellGoHome](../staking/run_a_validator_on_powell_go_home.md#generate-session-keys) starting with **Generate session keys** section.
