# Run a Liberland Node with Docker   
 
 Prequirements:
 This guide assumes your running a Linux based operating system and have Docker already installed.  
 
 
## Download the docker image
```
$ docker pull laissezfaire/liberland-node:0.3.2
```

## Select the chainspec
Select the chainspec for the chain you wish to connect to from `liberland_substrate/specs/`   


## Check that the image is downloaded
```
$ docker images -a
```

## Run node    
+ Forward ports 9933 and 9944 to local socket(-p)   
+ "-d", detach the docker image and run it as a daemon  
+ "-e", set the enviromental variables for the node(https://github.com/liberland/liberland.github.io/blob/main/docs/run_validator.md#restart-node-with-validator-flag), modify this based the node flags(--) you want to define       
```bash
$ docker run -p 9933:9933 -p 9944:9944 -d  \
-v /home/user/liberland/:/data laissezfaire/liberland-node:0.3.2 liberland_node  \  
-e "--chain starlight" -e "--bootnodes /ip4/162.55.230.228/tcp/1666/p2p/12D3KooWFztTwRSs6hhRNPcwxer5ueQDJYrSeJknPwZu2diVzbTm"
```

#### Check that node is running:   
```
$ docker ps
```

## Connect to your node with polkadot.js    
Head over to: https://polkadot.js.org/apps/#/explorer         
Select local node on the right side        


### Link to node docker image:    
https://hub.docker.com/r/laissezfaire/liberland-node   
