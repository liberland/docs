# How to run a validator

Note:   
*DO NOT* expose your validators rpc port publicly on the internet. Treat validators with more care than full nodes      
You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.   


*THIS IS FOR HAZLITT CHAIN*


Prapare your machine to be able to run Rust, Substrate and Cargo
``` 
https://docs.substrate.io/install/
```

compile the node with cargo:

```
git clone https://github.com/liberland/liberland_substrate && cd liberland_substrate && cargo build --release

```

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

You will need the following keys:  
-  stash keys(use in polkadot.js) (ed25519 or sr25519)      
-  controller(use in polkadot.js) keys (ed25519 or sr25519)   
-  Babe keys(submit to validator) (sr25519)   
-  Grandpa keys(submit to validator)  (ed25519)   
-  ImOnline keys(submit to validator)  (sr25519)   
-  AuthorityDiscovery keys(submit to validator)  (sr25519)    


Grab your mnemonic seed phrase and use subkey inspect to generate the next keys, and save them in a safe place:

## Generate grandpa, babe, audi and imol keys for your validator   

```
$ subkey inspect "<SECRET_PHRASE>//grandpa" --scheme ed25519
$ subkey inspect "<SECRET_PHRASE>//babe" --scheme sr25519
$ subkey inspect "<SECRET_PHRASE>//im_online" --scheme sr25519
$ subkey inspect "<SECRET_PHRASE>//authority_discovery" --scheme sr25519

```




# Sync the node   
Sync your node without the validator flag to the latest finalized block:   
```
./target/release/substrate --chain specs/latest_hazlitt_raw  --bootnodes /ip4/162.55.230.230/tcp/30333/p2p/12D3KooWPhfahTY7p8pRshMwPbEhp5zAahyu4TwbjXqgGEUoavpr --base-path /tmp/hazlitt --unsafe-pruning --pruning=1000 
```

## Submit keys

```
curl http://localhost:9933  -H "Content-Type:application/json;charset=utf-8" -d '{
    "jsonrpc":"2.0",
    "id":1,
    "method":"author_insertKey",
    "params": [
        "babe",
        "SEEDGOESHERE//babe",
        "PUBKEY"
    ]
}'

curl http://localhost:9933  -H "Content-Type:application/json;charset=utf-8" -d '{
    "jsonrpc":"2.0",
    "id":1,
    "method":"author_insertKey",
    "params": [
        "gran",
        "SEEDGOESHERE//grandpa",
        "PUBKEY"
    ]
}'

curl http://localhost:9933  -H "Content-Type:application/json;charset=utf-8" -d '{
    "jsonrpc":"2.0",
    "id":1,
    "method":"author_insertKey",
    "params": [
        "imol",
        "SEEDGOESHERE//im_online",
        "5Ehp3to58kyKEpZd8PyXGWr2TpXVCS1b31W5TkiLKvxr4CJn"
    ]
}'

curl http://localhost:9933  -H "Content-Type:application/json;charset=utf-8" -d '{
    "jsonrpc":"2.0",
    "id":1,
    "method":"author_insertKey",
    "params": [
        "audi",
        "SEEDGOESHERE//authority_discovery",
        "PUBKEY"
    ]
}'

```

## check that keys have been added  
check the directory you specified with `--base-path`:  
```
$ ls /tmp/hazlitt/chains/hazlitt/keystore/
```





### restart node with validator flag:   
```
./target/release/substrate --chain specs/hazlittRaw.json  --bootnodes /ip4/162.55.230.230/tcp/30333/p2p/12D3KooWPhfahTY7p8pRshMwPbEhp5zAahyu4TwbjXqgGEUoavpr --base-path /tmp/hazlitt --unsafe-pruning --pruning=1000 --validator
```

## Rotate keys

Run the following command and save the 'result' parameter it returns
```
curl -H 'Content-Type: application/json' --data '{ "jsonrpc":"2.0", "method":"author_rotateKeys", "id":1 }' 127.0.0.1:9933
```


## Submit validator in polkadot 

Head over to polkadot.js and Go to Network > Staking > Accounts > `+ Validator` set your stash and controller and paste in the result from the previous step on the next page. click "Click "Bond & Validate" and your done! Your validator should soon come online


## Final Step:  
Once your validator is up and running and you have a solid track record of no downtime.  
You can ask other LLD holders to nominate your validator node.   
