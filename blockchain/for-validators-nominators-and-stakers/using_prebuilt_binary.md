# Using prebuilt binary

## Download chain spec and node binary

```
user@host:~$ mkdir -p liberland/
user@host:~$ cd liberland/
user@host:~/liberland$ wget https://github.com/liberland/liberland_substrate/releases/download/v8.1.0/linux_x86_build -O node
user@host:~/liberland$ wget https://github.com/liberland/liberland_substrate/releases/download/v8.1.0/mainnet.raw.json
user@host:~/liberland$ wget https://github.com/liberland/liberland_substrate/releases/download/v6.0.0/bastiat.raw.json
user@host:~/liberland$ chmod +x node
```

After downloading verify files integrity. Checksums should match with this output:
```
user@host:~/liberland$ sha256sum node mainnet.raw.json bastiat.raw.json 
1331ca6064b41faad7d245e7fed434d54110f5d54b58763434fb53246e09f45b  node
dbf1e9cbba193c6e6096b21c3b865ed82b3de6fca2643cf93141ac891a13ead7  mainnet.raw.json
645df3a7c84ed64e3162cc7155624268fcb09a6dcde12b88bb8db8b2bfeec882  bastiat.raw.json
```

If not, abort and contact dev team.

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
