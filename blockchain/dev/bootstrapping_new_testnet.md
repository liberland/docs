# Bootstrapping new testnet

## 1. Prepare your env

This guide assumes you have environment capable of building the substrate node.
Follow [Build, run & test using source code](dev.md) guide to
setup it.

## 2. Prepare release

Tag the commit from which you'll build the chain spec and run initial nodes. Use
this version of code for all following commands.

## 3. Preparing your initial nodes' keys

For each of your initial nodes/validators, you need following keys:

* controller account, that will allow starting/stopping validation
* stash account, that will actually hold staked LLD
* sessions keys:
  * grandpa (ed25519)
  * babe (sr25519)
  * im_online (sr25519)
  * authority_discovery (sr25519)

## 4. Preparing shell

Commands below require the `LIBERLAND_NODE` variable to be set to command of node binary. Examples:

```
liberland_substrate (develop)> export LIBERLAND_NODE="cargo run -q --release --" # build from source
liberland_substrate (develop)> export LIBERLAND_NODE="./target/release/substrate" # use locally built binary
liberland_substrate (develop)> export LIBERLAND_NODE="$HOME/linux_x86_node" # use downloaded prebuilt binary
```

Scripts also respect the `LIBERLAND_NODE` variable, but default to running `cargo` if variable is unset.

### Generating Controller and stash keys

These are regular accounts, you can use Polkadot Extension to generate them.

If you prefer, you can also generate them manually from seed:

```
liberland_substrate (develop)> $LIBERLAND_NODE key inspect '<<YOUR_SEED_HERE>>'
liberland_substrate (develop)> $LIBERLAND_NODE key inspect '<<YOUR_SEED_HERE>>//stash'
```

### Generating session keys

Make sure you're using different seed for each node.

#### Option 1: using script

Use the `get_session_keys_from_seed.sh`:

```
liberland_substrate (develop)> ./scripts/get_session_keys_from_seed.sh 
Provide your seed. If you don't have one, feel free to copy this freshly generated one:
 strong uncover fossil tag because announce coast mom blue endless file warrior
Seed: <<YOUR_SEED_HERE>>
gran (ed25519): 8280a7b1f74bc53e6fb2cf686566fbdcc850a61014e96a457e7d763a5e67a3e7
babe (sr25519): 0caf07d84a96f800892699d69eb74d963ae2d8c5ced5c54199c061a270d2b827
imon (sr25519): 509cd46a791813b05615a14b240319c56bc2f7a19106aadb26193bb126e27c40
audi (sr25519): 7c5f75b761139f09b612b4457f24615080dcb0721ba8eb88ee7571d9f4589731
```

#### Option 2: manually

Notice that first command (for `grandpa`) uses `ed25519` scheme and others use `sr25519` scheme.

```
liberland_substrate (develop)> $LIBERLAND_NODE key inspect --scheme ed25519 '<<YOUR_SEED_HERE>>//gran' # grandpa
liberland_substrate (develop)> $LIBERLAND_NODE key inspect --scheme sr25519 '<<YOUR_SEED_HERE>>//babe' # babe
liberland_substrate (develop)> $LIBERLAND_NODE key inspect --scheme sr25519 '<<YOUR_SEED_HERE>>//imon' # im_online
liberland_substrate (develop)> $LIBERLAND_NODE key inspect --scheme sr25519 '<<YOUR_SEED_HERE>>//audi' # authority_discovery
```

## 4. Building chain spec

While it's possible to create the spec file manually, it's recommended to build it from code.

Make sure you have the correct version of code checked out. Go to `bin/node/cli/src/chain_spec.rs` and find the `fn staging_testnet_config_genesis()` function. In there, do the 
following changes:

1. Update `initial_authorities`. This is the place were you need to put your initial nodes' keys from [Step 2](#2-preparing-your-initial-nodes-keys). The order for each item is:
    * Stash's public key (SS58)
    * Controller's public key (SS58)
    * Grandpa public key (hex)
    * Babe public key (hex)
    * Im_online public key (hex)
    * Authority_discovery public key (hex)
2. Update the `citizens`. Each address on this list will be a valid citizen with a KnownGood judgement and will receive `10^18` LLD.
3. Update the `registrar_key` - it's the address of Citizenship Registrar that will be able to provide identity judgements for citizenship.
4. Update the `root_key` - it's the account capable of executing sudo calls
5. Update the `technical_committee`

After updating the code, we may now generate the human-readable template for spec:
```
liberland_substrate (develop)> $LIBERLAND_NODE build-spec --chain staging --disable-default-bootnode > new_chain_spec.json
```

Open the generated `new_chain_spec.json` file in your editor. You may want to adjust things like `name`, `id`, `properties.displayName` to match your new testnet.

Generate the raw chain spec:
```
liberland_substrate (develop)> $LIBERLAND_NODE build-spec --chain new_chain_spec.json --disable-default-bootnode > new_chain_spec.raw.json
```

The generated `new_chain_spec.raw.json` is the file that should be distributed to all participants of the network and will be used to run our initial nodes.

## 5. Running our first node

### Inserting session keys

#### Option 1: using script
If you've generated session keys using `get_session_keys_from_seed.sh`, you may now run `insert_session_keys_from_seed.sh` with the same seed. Make sure you pass the correct chain spec and path where node should store its data:
```
liberland_substrate (develop)> ./scripts/insert_session_keys_from_seed.sh --chain new_chain_spec.raw.json -d /data/liberland_node/
Provide your seed. If you don't have one, feel free to copy this freshly generated one:
 strong uncover fossil tag because announce coast mom blue endless file warrior
Seed: <<YOUR_SEED_HERE>>
gran (ed25519): 8280a7b1f74bc53e6fb2cf686566fbdcc850a61014e96a457e7d763a5e67a3e7
babe (sr25519): 0caf07d84a96f800892699d69eb74d963ae2d8c5ced5c54199c061a270d2b827
imon (sr25519): 509cd46a791813b05615a14b240319c56bc2f7a19106aadb26193bb126e27c40
audi (sr25519): 7c5f75b761139f09b612b4457f24615080dcb0721ba8eb88ee7571d9f4589731
```

#### Option 2: manually

Run following commands. Make sure you pass proper chain spec file, path to node storage and insert the same seed as one used for preparing keys for chain spec. 
Notice that first command (for `grandpa`) uses `ed25519` scheme and others use `sr25519` scheme.

```
liberland_substrate (develop)> $LIBERLAND_NODE key insert --chain new_chain_spec.raw.json -d /data/liberland_node --scheme ed25519 --key-type gran --suri '<<YOUR_SEED_HERE>>//gran'
liberland_substrate (develop)> $LIBERLAND_NODE key insert --chain new_chain_spec.raw.json -d /data/liberland_node --scheme sr25519 --key-type babe --suri '<<YOUR_SEED_HERE>>//babe'
liberland_substrate (develop)> $LIBERLAND_NODE key insert --chain new_chain_spec.raw.json -d /data/liberland_node --scheme sr25519 --key-type imon --suri '<<YOUR_SEED_HERE>>//imon'
liberland_substrate (develop)> $LIBERLAND_NODE key insert --chain new_chain_spec.raw.json -d /data/liberland_node --scheme sr25519 --key-type audi --suri '<<YOUR_SEED_HERE>>//audi'
```

### Running the first node

Make sure you pass the same chain spec and path to data as when inserting session keys:

```
liberland_substrate (develop)> $LIBERLAND_NODE --chain new_chain_spec.raw.json -d /data/liberland_node --force-authoring --validator
2023-01-03 12:27:50 Substrate Node    
2023-01-03 12:27:50 ✌️  version 3.0.0-dev-2c2aac70051    
2023-01-03 12:27:50 ❤️  by Parity Technologies <admin@parity.io>, 2017-2023    
2023-01-03 12:27:50 📋 Chain specification: Staging Testnet    
2023-01-03 12:27:50 🏷  Node name: energetic-button-0223    
2023-01-03 12:27:50 👤 Role: AUTHORITY    
2023-01-03 12:27:50 💾 Database: RocksDb at ../test1/chains/staging_testnet/db/full    
2023-01-03 12:27:50 ⛓  Native runtime: liberland-4 (liberland-node-0.tx1.au10)    
2023-01-03 12:27:53 [0] 💸 generated 3 npos voters, 3 from validators and 0 nominators    
2023-01-03 12:27:53 [0] 💸 generated 3 npos targets    
2023-01-03 12:27:54 🔨 Initializing Genesis block/state (state: 0x50e6…fc65, header-hash: 0x7899…7aac)    
2023-01-03 12:27:54 👴 Loading GRANDPA authority set from genesis on what appears to be first startup.    
2023-01-03 12:27:55 👶 Creating empty BABE epoch changes on what appears to be first startup.    
2023-01-03 12:27:55 Using default protocol ID "sup" because none is configured in the chain specs    
2023-01-03 12:27:55 🏷  Local node identity is: 12D3KooWL8az46KDc6d4iMCtwwx2RW7fxP7DfNYMVQRX7STWzBcj    
2023-01-03 12:27:55 💻 Operating system: linux    
2023-01-03 12:27:55 💻 CPU architecture: x86_64    
2023-01-03 12:27:55 💻 Target environment: gnu    
```

Note the `Local node identity is: 12D3KooWL8az46KDc6d4iMCtwwx2RW7fxP7DfNYMVQRX7STWzBcj` in output. Copy this ID from your output, we'll need it later.

## 6. Running remaining initial nodes

### Inserting session keys 

Follow [the same procedure as for the first node](#inserting-session-keys). Make sure you're using different seed for each node.

### Running the node

Create the bootstrap node address. The format is:
```
/ip4/<IP_ADDRESS>/tcp/30333/p2p/<ID>
```
Where:
* `<IP_ADDRESS>` must be replaced with the IP address of your initial node
* `ID` must be replaced with the `Local node identity` printed in startup log of your initial node.

Make sure you pass the same chain spec and path to data as when inserting session keys. 

```
liberland_substrate (develop)> $LIBERLAND_NODE --chain new_chain_spec.raw.json -d /data/liberland_node --validator --bootnodes /ip4/<IP_ADDRESS>/tcp/30333/p2p/<ID>
2023-01-03 12:27:50 Substrate Node    
2023-01-03 12:27:50 ✌️  version 3.0.0-dev-2c2aac70051    
2023-01-03 12:27:50 ❤️  by Parity Technologies <admin@parity.io>, 2017-2023    
[...]
2023-01-03 12:34:12 💤 Idle (1 peers), best: #0 (0x7899…7aac), finalized #0 (0x7899…7aac), ⬇ 0 ⬆ 0    
```

Make sure it shows `(1 peers)` (or more) in the logs after a minute. If not,
verify that your initial node is running and bootnode address is correct. It's
OK if it doesn't produce/finalize blocks yet, we need all nodes for that.

## 6. Verify

Now that we've added all initial nodes, we should see that blocks are getting finalized.

Good (notice `finalized #9`):
```
2023-01-03 12:34:12 💤 Idle (2 peers), best: #12 (0x608e…ba6f), finalized #9 (0xb83d…0e43), ⬇ 0 ⬆ 0    
```

Bad (notice `finalized #0`):
```
2023-01-03 12:34:12 💤 Idle (2 peers), best: #12 (0x608e…ba6f), finalized #0 (0x7899…7aac), ⬇ 0 ⬆ 0    
```

If blocks aren't finalized, verify that correct session keys were inserted to each node.
