# Using prebuilt binary

## Download chain spec and node binary

```
user@host:~$ mkdir -p liberland/powellgohome/
user@host:~$ cd liberland/powellgohome/
user@host:~/liberland/powellgohome$ wget https://github.com/liberland/liberland_substrate/releases/download/v4.0.0/linux_x86_build -O node
user@host:~/liberland/powellgohome$ wget https://github.com/liberland/liberland_substrate/releases/download/v4.0.0/powell_go_home.raw.json
user@host:~/liberland/powellgohome$ chmod +x node
```

After downloading verify files integrity. Checksums should match with this output:
```
user@host:~/liberland/powellgohome$ sha256sum node powell_go_home.raw.json 
006d6fa8840a25b5c41ef892a265393de5cfa0542c0d7f808c010f614ec0158f  node
089b4be8720b43d597ceb6ae51b186ef444bc5246bcb51edde23b542fd89326b  powell_go_home.raw.json
```

If not, abort and contact dev team.

## Run node

Make sure you replace `DATA_DIR` with a path to directory that can store at least a few gigabytes of data.

```
user@host:~/liberland/powellgohome$ ./node \
    --chain powell_go_home.raw.json \
    --validator \
    -d DATA_DIR
```

Note:
* *DO NOT* expose your validators RPC ports (9933 and 9944 by default) publicly on the internet. Treat validators with more care than full nodes.
* You *do not* need to a run a validator to earn LLD staking rewards. As a user you can simply become a nominator and stake your coins without needing to run a validator.

## Optional: making it a system service

To save the trouble of debugging the process, make sure that the following command that you are passing to it will work. Use absolute path to your `node` binary.

```
/home/user/liberland/powellgohome/node --chain powell_go_home.raw.json -d /data/liberland_node --validator
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
ExecStart=/home/user/liberland/powellgohome/node --chain powell_go_home.raw.json -d /data/liberland_node --validator
Restart=always
RestartSec=120
WorkingDirectory=/home/user/liberland/powellgohome

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
user@host:~/liberland/powellgohome$ curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}' http://127.0.0.1:9933
{"jsonrpc":"2.0","result":"0x58db6952384f2d1f9600255a2fce9b116201e872e9951a0a0c0edd7c31124934c690eb603407f4b98a1c9fc0628d4b926fec03d577f233fda3af01d33e2a391b9ad7558c0ae9ba082b3b70236ec584471c92c3a5d78e9bc08f49de7c75961e132697e5419818bfcd31e1bc2cc7d0560a81db72a76af59374c1932bc7a96d773a","id":1}
```

Copy the contents of `result` from your terminal, thats the new session keys.