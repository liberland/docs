# Using source

If you want to build from source instead of using prebuilt binary:

1. Checkout the `v7.0.0` tag of repo:
    ```
    git clone https://github.com/liberland/liberland_substrate.git --depth 1 -b v7.0.0
    cd liberland_substrate
    ```
2. Build the code - see [Build, run & test using source code](../dev/dev.md) guide. Only follow up to the end of **Build the node**.
3. Copy the relevant files:
    ```
    cp ./target/release/substrate node
    cp specs/bastiat.raw.json bastiat.raw.json
    ```

## Run node

Make sure you replace `DATA_DIR` with a path to directory that can store at least a few gigabytes of data.

```
user@host:~/liberland/bastiat$ ./node \
    --chain bastiat.raw.json \
    --validator \
    -d DATA_DIR
```

Note:
* *DO NOT* expose your validators RPC ports (9933 and 9944 by default) publicly on the internet. Treat validators with more care than full nodes.
* You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.

## Optional: making it a system service

To save the trouble of debugging the process, make sure that the following command that you are passing to it will work. Use absolute path to your `node` binary.

```
/home/user/liberland/bastiat/node --chain bastiat.raw.json -d /data/liberland_node --validator
```

After verifying that your node works, it is recommended to do this step as a system process. On ubuntu, it would look something like:

```
sudo systemctl edit --force --full liberland_validator.service
```

Then edit the file created, it should look similar to this example, but make sure to insert the correct path to liberland code on your machine.
You should insert the path both to exec start and WorkingDirectory.

```                            
[Unit]
Description=Liberland Validator

[Service]
ExecStart=/home/user/liberland/bastiat/node --chain bastiat.raw.json -d /data/liberland_node --validator
Restart=always
RestartSec=120
WorkingDirectory=/home/user/liberland/bastiat

[Install]
WantedBy=multi-user.target
```

Save the file and then:
````
sudo systemctl enable liberland_validator.service
sudo systemctl start liberland_validator.service
````

and verify it works with
```
sudo systemctl status liberland_validator.service
```

## Generate session keys

`author_rotateKeys` generates new keys and stores them in your node.

```
user@host:~/liberland/bastiat$ curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}' http://127.0.0.1:9933
{"jsonrpc":"2.0","result":"0x58db6952384f2d1f9600255a2fce9b116201e872e9951a0a0c0edd7c31124934c690eb603407f4b98a1c9fc0628d4b926fec03d577f233fda3af01d33e2a391b9ad7558c0ae9ba082b3b70236ec584471c92c3a5d78e9bc08f49de7c75961e132697e5419818bfcd31e1bc2cc7d0560a81db72a76af59374c1932bc7a96d773a","id":1}
```

Copy the contents of `result` from your terminal, thats the new session keys.