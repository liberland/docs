# Build, run & test the Liberland Blockchain Node using source code

This guide will walk you through:

* building the blockchain node from source code,
* running a local development instance, which spawns a new single-node testnet,
* interacting with development instance,
* running automated tests.

## Install dependencies

For Ubuntu & Debian derivatives:

```
sudo apt install build-essential git clang curl libssl-dev llvm libudev-dev make protobuf-compiler
```

Next install Rust itself. Run and follow prompts:
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

And switch to Rust Nightly:
```
rustup default nightly
```

See [Substrate docs](https://docs.substrate.io/install/) for detailed guide and other platforms.

## Fetch latest source code

Development of Liberland Blockchain Node happens in two branches:

* `main`, which contains latest stable release
* `develop`, which contains latest, not yet released as stable changes

To fetch source code, run the following (you may replace `main` with `develop` if desired):
```
git clone https://github.com/liberland/liberland_substrate.git -b main
cd liberland_substrate
```

## Build the node

To build the node, run:

```
cargo build --release
```

Note that this will likely take a long time. If everything goes correctly, you'll see:

```
    Finished release [optimized] target(s)
```

And will be able to run the node using built executable (output might differ slightly):

```
user@machine:~/liberland_substrate$ ./target/release/substrate --version
substrate 3.0.0-dev-41cd30e9e7d
```

## Run and interact with development instance

To run a development instance of Liberland node, execute:
```
cargo run --release -- --dev
```

Development instance is a single-node testnet, in which standard development
accounts (Alice, Bob, etc.) are endowed with assets. To interact with it, visit
[Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=ws://localhost:9944).

## Run automated tests

Liberland Blockchain node is comprehensively covered with automated unit tests.
To run them, execute:

```
cargo test --release --features runtime-benchmarks
```

As these typically take a long time, you can also choose to run tests only for
specific pallets. Here's example for the legislation pallet:

```
cargo test --release --features runtime-benchmarks -p pallet-liberland-legislation --lib
```
