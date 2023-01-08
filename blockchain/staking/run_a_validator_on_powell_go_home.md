# Run a validator on PowellGoHome

## Option 1: Using prebuilt binary

### Download chain spec and node binary

```
user@host:~$ mkdir -p liberland/powellgohome/
user@host:~$ cd liberland/powellgohome/
user@host:~/liberland/powellgohome$ wget https://github.com/liberland/liberland_substrate/releases/download/v4.0.0-rc2/linux_x86_build -O node
user@host:~/liberland/powellgohome$ wget https://github.com/liberland/liberland_substrate/releases/download/v4.0.0-rc2/powell_go_home.raw.json
user@host:~/liberland/powellgohome$ chmod +x node
```

After downloading verify files integrity. Checksums should match with this output:
```
user@host:~/liberland/powellgohome$ sha256sum node powell_go_home.raw.json 
9b95a4d72a40f53b19fd31a94d4e281e68a0c07edf7840a33cee95229f1ac800  node
089b4be8720b43d597ceb6ae51b186ef444bc5246bcb51edde23b542fd89326b  powell_go_home.raw.json
```

If not, abort and contact dev team.

## Option 2: Using docker

See [Docker guide](../dev/docker.md).

## Option 2: Using source

If you want to build from source instead of using prebuilt binary:

1. Checkout the `v4.0.0-rc2` tag of repo:
    ```
    git clone https://github.com/liberland/liberland_substrate.git --depth 1 -b v4.0.0-rc2
    cd liberland_substrate
    ```
2. Build the code - see [Build, run & test using source code](../dev/dev.md) guide. Only follow up to the end of **Build the node**.
3. Copy the relevant files:
    ```
    cp ./target/release/substrate node
    cp specs/powell_go_home.raw.json powell_go_home.raw.json
    ```

## Run your node

Make sure you replace `DATA_DIR` with a path to directory that can store at least a few gigabytes of data.

```
user@host:~/liberland/powellgohome$ ./node \
    --chain powell_go_home.raw.json \
    --validate \
    -d DATA_DIR \
    --bootnodes /ip4/FIXME/tcp/FIXME/p2p/FIXME
```

## Generate session keys

`author_rotateKeys` generates new keys and stores them in your node.

```
user@host:~/liberland/powellgohome$ curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}' http://127.0.0.1:9933
{"jsonrpc":"2.0","result":"0x58db6952384f2d1f9600255a2fce9b116201e872e9951a0a0c0edd7c31124934c690eb603407f4b98a1c9fc0628d4b926fec03d577f233fda3af01d33e2a391b9ad7558c0ae9ba082b3b70236ec584471c92c3a5d78e9bc08f49de7c75961e132697e5419818bfcd31e1bc2cc7d0560a81db72a76af59374c1932bc7a96d773a","id":1}
```

FIXME should we restart the node now? I dont think so.

Copy the contents of `result` from your terminal, thats the new session keys.

## Add validator

1. Visit [Staking Accounts on Polkadot.js Apps for PowellGoHome](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/staking/actions)
2. Click "+ Validator" button.
3. Set your stash and controller accounts and select how much LLD you want to bond.
4. Click "Next" button.
5. Paste the session keys you got from [previous step](#generate-session-keys) to `Keys from rotateKeys` form.
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
