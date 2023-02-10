# Using prebuilt binary

## Download chain spec and node binary

```
user@host:~$ mkdir -p liberland/bastiat/
user@host:~$ cd liberland/bastiat/
user@host:~/liberland/bastiat$ wget https://github.com/liberland/liberland_substrate/releases/download/v6.0.0/linux_x86_build -O node
user@host:~/liberland/bastiat$ wget https://github.com/liberland/liberland_substrate/releases/download/v6.0.0/bastiat.raw.json
user@host:~/liberland/bastiat$ chmod +x node
```

After downloading verify files integrity. Checksums should match with this output:
```
user@host:~/liberland/bastiat$ sha256sum node bastiat.raw.json 
2d3efa04b086859c73bb452453c3bf573679e8b578863fc23ce2170b028b64c9  node
645df3a7c84ed64e3162cc7155624268fcb09a6dcde12b88bb8db8b2bfeec882  bastiat.raw.json
```

If not, abort and contact dev team.

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