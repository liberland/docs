# Cross chain HASHI bridge

Liberland blockchain is connected to SORA, Ethereum, Polkadot, Kusama, and more upcoming (BnB) through the [HASHI bridge](https://polkaswap.io/#/bridge/).
The bridge is permissionless so anyone can use it at any time.

To use the bridge, you will need native tokens on the chain you are bridging to.

For example, bridging from Liberland to SORA to Eth would require LLD, XOR and ETH gas fees.

In addition, this will interact with dApps so you need a way to do that. For example, [PC browser with wallet extensions](for-citizens/desktop-wallet.md) or [Subwallet](for-citizens/mobile-wallet.md) on mobile.

Edge wallet will not work for this.

## Liberland <> SORA bridge
For this, you will just need LLD or XOR depending on the direction of bridging

Go to [HASHI bridge](https://polkaswap.io/#/bridge/).

Connect your substrate account that you will use for Liberland and SORA.

Select the Liberland network.

Choose the token you wish to bridge and the direction (Liberland to SORA or SORA to Liberland)

![Liberland SORA bridge](media/LLDSORABridge.png)

Choose the amount and click on bridge. Your wallet will ask you to confirm transactions.


## SORA <> ETH bridge

For bridging from SORA to ETH, you will need an ETH account with some ETH on it, and a substrate account with some XOR on it.

### Getting XOR
If you bridged from Liberland, you can swap [LLD for XOR on Polkaswap](https://polkaswap.io/#/swap/LLD/XOR).
About 5 USDT of XOR should be enough, so 2 to 5 LLD swapped for XOR to be on the safe side.

![Swap LLD for XOR](media/LLDXORSwap.png)

Alternatively, if you bridged from ETH to SORA you can just sell some ETH for XOR instead.

Or DOT from Polkadot. Or KSM from Kusama. Hashi bridge is kinda awesome like that, you have options.

### Getting ETH
You need to get ETH account with enough ETH to pay gas fees. We recommend like 50 USD worth of ETH to have enough to bridge and open a position on exchange.


### SORA <> ETH bridge

With tokens and wallets ready,
Go to [HASHI bridge](https://polkaswap.io/#/bridge/)

Select the ETH network

Select the token

Connect both substrate and ETH wallet (Subwallet supports both)

Enter the amount and bridge! This may take a few minutes. After its done, it should ask you to add the token to your wallet. Accept and you should see it.

![Liberland SORA bridge](media/SORAETHBridge.png)

You are now ready to trade on DEXes such as [Uniswap](https://matcha.xyz/tokens/ethereum/0x054c9d4c6f4ea4e14391addd1812106c97d05690?buyChain=1&buyAddress=0xdac17f958d2ee523a2206206994597c13d831ec7&sellAmount=500)
