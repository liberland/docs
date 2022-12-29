# StarLight is a testnet 

If Hazlitt is Polkadot then Star Light is Kusama

Star Light is running on `develop` branch:
https://github.com/liberland/liberland_substrate/commit/cc98f31af6b1a61a82befd617ecc537195676171

## STEP 1:

```bash
$ git clone https://github.com/liberland/liberland_substrate 
$ cd liberland_substrate && git checkout develop && cargo build --release
```

## STEP 2:

Generate your validator keys:
https://github.com/liberland/liberland.github.io/blob/main/docs/run_validator.md#generate-keys

Submit your keys:
https://github.com/liberland/liberland.github.io/blob/main/docs/run_validator.md#submit-keys


## STEP 3:

Sync your validator node:
```
./target/release/substrate --chain specs/starlight.raw   --validator --in-peers 256 
--base-path /home/<ENTER USER>/starlight_chain/ 
--bootnodes /ip4/162.55.230.228/tcp/1666/p2p/12D3KooWFztTwRSs6hhRNPcwxer5ueQDJYrSeJknPwZu2diVzbTm   
--force-authoring 
```

*NOTE: DONT FORGET TO RESTART YOUR VALIDATOR AFTER YOU SUBMITTED THE KEYS TO MAKE SURE THEY ARE LOADED CORRECTLY*



## STEP 4:

Once your validator has synced up you want to call "author_rotateKeys":
```
curl -H 'Content-Type: application/json' --data '{ "jsonrpc":"2.0", "method":"author_rotateKeys", "id":1 }' 127.0.0.1:9933
```

Take the output of the result and head over to `Polkadot.js > Network > Staking > Accounts > + Validator` to add your validator

## Step 5: 
Nominate your validator!

Ask your friends to select your validator and nominate your validator. the more nominations you got the higher chance you have to get selected.


## Step 6:

Wait! Now all you gotta do is wait, you can see in Polkadot.js that your validator is now queued up for being in an active session/era

