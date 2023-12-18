# Using source

If you want to build from source instead of using prebuilt binary:

1. Checkout the `v6.0.0` tag of repo:
    ```
    git clone https://github.com/liberland/liberland_substrate.git --depth 1 -b v6.0.0
    cd liberland_substrate
    ```
2. Build the code - see [Build, run & test using source code](../dev/dev.md) guide. Only follow up to the end of **Build the node**.
3. Copy the relevant files:
    ```
    cp ./target/release/substrate node
    cp specs/bastiat.raw.json bastiat.raw.json
    cp specs/mainnet.raw.json mainnet.raw.json
    ```

## Run node

Make sure you replace `DATA_DIR` with a path to directory that can store at least a few gigabytes of data. Replace `NETWORK` with `mainnet` or `bastiat` depending on your needs.

```
user@host:~/liberland$ ./node \
    --chain NETWORK.raw.json \
    --validator \
    -d DATA_DIR
```

Note:
* *DO NOT* expose your validators RPC ports (9933 and 9944 by default) publicly on the internet. Treat validators with more care than full nodes.
* You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.

## Optional: making it a system service

To save the trouble of debugging the process, make sure that the following command that you are passing to it will work. Use absolute path to your `node` binary.

```
/home/user/liberland/node --chain bastiat.raw.json -d /data/liberland_node --validator
```

After verifying that your node works, it is recommended to do this step as a system process. On ubuntu, it would look something like:

```
sudo systemctl edit --force --full liberland_validator.service
```

Then edit the file created, it should look similar to this example. Make sure:
* insert the correct path to liberland node on your machine (the `/home/user/liberland` in example), both in `ExecStart` and `WorkingDirectory`
* if setting up mainnet validator, replace `bastiat.raw.json` with `mainnet.raw.json`
* replace `/data/liberland_node` with path to directory that exists and can store few gigabytes of data.

```                            
[Unit]
Description=Liberland Validator

[Service]
ExecStart=/home/user/liberland/node --chain bastiat.raw.json -d /data/liberland_node --validator
Restart=always
RestartSec=120
WorkingDirectory=/home/user/liberland

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

See [regenerate session keys](regenerate_session_keys.md) document.
