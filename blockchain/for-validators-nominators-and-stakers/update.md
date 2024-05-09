# Node update guide

Update requires:
* updating to the latest node binary
* updating to the latest chain specification

For a detailed guide, please choose the proper instruction according to the method used to install the node:

* [Automated script](#automated-script-installs) (a.k.a. nodes installed with [this guide](./run-a-validator.md#option-1-automatic-script))
* [Docker](#docker-installs)
* [Manual](#manual-installs)

# Automated script installs

Run the following command on your server:

```
curl -sSLO https://raw.githubusercontent.com/liberland/liberland_substrate/main/substrate/scripts/install/install.sh
bash install.sh
```

The installer will detect existing install and perform the required updates without wiping any data or keys. If asked about which network to use - make sure you choose the correct one.

# Docker installs

You need to pull the latest image and recreate your container.

If you followed the [Complete example of running a validator on mainnet](../dev/docker.md) guide, follow these steps:

1. Pull the latest image:
    ```
    docker pull liberland/blockchain-node:latest
    ```
2. Stop and remove the old container. If you followed the guide, it won't remove any data or keys:
    ```
    docker stop liberland && docker rm liberland
    ```
3. Recreate the container:
    ```
    docker run --name liberland -d --network=host --restart always -v $HOME/liberland_data:/data liberland/blockchain-node:latest -d /data --chain /specs/mainnet.raw.json --validator
    ```

# Manual installs

If you've installed manually, you need to:
1. Download latest node binary (`linux_x86_build`) from the [releases page](https://github.com/liberland/liberland_substrate/releases)
2. Download latest chain spec (`mainnet.raw.json`) from the [releases page](https://github.com/liberland/liberland_substrate/releases)
3. Stop your node
4. Replace the binary and spec files you're using with the downloaded ones
5. Restart your node