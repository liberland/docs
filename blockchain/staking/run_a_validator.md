# How to run a validator

Note:
*DO NOT* expose your validators rpc port publicly on the internet. Treat validators with more care than full nodes
You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.

Prapare your machine to be able to run Rust, Substrate and Cargo
```
https://docs.substrate.io/install/
```

compile the node with cargo, following instructions for building from source:
[Build from source](../dev/dev.md)

install subkey:
```
cargo install --force subkey --git https://github.com/paritytech/substrate --version 2.0.2 --locked
```

## Generate keys:
Subkey generate command will return a secret mnemonic phrase and other keys similar to:
```
$ subkey generate
Secret phrase:       power popular buffalo predict renew gasp stay steak blanket opinion current stove
  Secret seed:       0x542c112cb6130d531ba9751cb209d8c3782c0158783562e1336b1628e834354a
  Public key (hex):  0xbefda47b8e41d8bd1642d6cdf4560b914915466ead377d7646a805cae9344141
  Account ID:        0xbefda47b8e41d8bd1642d6cdf4560b914915466ead377d7646a805cae9344141
  Public key (SS58): 5GP8JWw8Vg1VK42h1D2mXxBt5AQ7MDGdAH4F87QGoWCuD5nr
  SS58 Address:      5GP8JWw8Vg1VK42h1D2mXxBt5AQ7MDGdAH4F87QGoWCuD5nr


```

## Generate grandpa, babe, audi and imol keys for your validator

Run the script to generate session keys, and pass it the previously generated secret mnemonic seed when it asks for it.
Note that this might take some time to execute

```
./scripts/get_session_keys_from_seed.sh 
```


# Sync the node
Sync your node without the validator flag to the latest finalized block:
```
./target/release/substrate --chain specs/powell_go_home.raw.json  --bootnodes /ip4/164.92.254.132/tcp/30333/p2p/12D3KooWFzt9D5Pbza9ahfVjfXfRHsbsQRXmkf64FgY3LrLCSV8N --base-path /data/liberland_node
```
After sync is done, exit the process

## Submit keys

```
./scripts/insert_session_keys_from_seed.sh --chain specs/powell_go_home.raw.json -d /data/liberland_node/

```

## check that keys have been added
check the directory you specified with `--base-path`:
```
$ ls data/liberland_node/
```


### restart node with validator flag:
```
./target/release/substrate --chain specs/powell_go_home.raw.json  --bootnodes /ip4/164.92.254.132/tcp/30333/p2p/12D3KooWFzt9D5Pbza9ahfVjfXfRHsbsQRXmkf64FgY3LrLCSV8N --base-path /data/liberland_node --unsafe-pruning --pruning=1000 --validator
```

After verifying that it works, its recommended to do this step as a system process. On ubuntu, it would look something like

```
touch /etc/systemd/system/liberlandValidator.service
```
Then edit the file created, it should look similar to this example, but make sure to insert the correct path to liberland code on your machine.
You should insert the path both to exec start and WorkingDirectory.

To save the trouble of debugging the process, make sure that the following command that you are passing to it will work. Use absolute path.
```<PATH-TO-LIBERLAND-CODE>/target/release/substrate  --chain specs/powell_go_home.raw.json -d /data/liberland_node  --validator --bootnodes /ip4/164.92.254.132/tcp/30333/p2p/12D3KooWFzt9D5Pbza9ahfVjfXfRHsbsQRXmkf64FgY3LrLCSV8N```

Edit the created /etc/systemd/system/liberlandValidator.service file:
```                            
[Unit]
Description=Liberland Validator

[Service]
ExecStart=<PATH-TO-LIBERLAND-CODE>/target/release/substrate  --chain specs/powell_go_home.raw.json -d /data/liberland_node  --validator --bootnodes /ip4/164.92.254.132/tcp/30333/p2p/12D3KooWFzt9D5Pbza9ahfVjfXfRHsbsQRXmkf64FgY3LrLCSV8N
Restart=always
RestartSec=120
WorkingDirectory=<PATH-TO-LIBERLAND-CODE>
[Install]
WantedBy=multi-user.target
```
Save the file and then
````
systemctl enable liberlandValidator.service
systemctl start liberlandValidator.service
````
and verify it works with

```
systemctl status liberlandValidator.service
```

## Rotate keys

Run the following command and save the 'result' parameter it returns
```
curl -H 'Content-Type: application/json' --data '{ "jsonrpc":"2.0", "method":"author_rotateKeys", "id":1 }' 127.0.0.1:9933
```


## Submit validator in polkadot
Note that in order to do this step you will need some LLD, so ask someone to give you some if you dont already have it.
Head over to [polkadot.js](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org%2F#) and Go to Network > Staking > Accounts > `+ Validator` set your stash and controller and paste in the result from the previous step on the next page. click "Click "Bond & Validate" and your done! Your validator should soon come online

## Final Step:
Once your validator is up and running and you have a solid track record of no downtime.
You can ask other LLD holders to nominate your validator node.
