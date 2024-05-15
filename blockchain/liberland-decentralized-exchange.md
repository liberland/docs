# LLDEX - Liberland Decentralized Exchange

Liberland has a native DEX at [blockchain.liberland.org/](https://blockchain.liberland.org/home/wallet/exchange),
under Wallet -> Exchange menu.

Here you can see all available token pairs and trade them, or add new pairs and liquidity into the pools.
LLD or any other Liberland asset, such as LLM, LLEUR, wrapped tokens like ETH, wBTC, USDT and others, as well as 
stock in Liberland companies can be listed. The DEX is completely permissionless, so be careful and ask for verification
if something looks suspicious.


## Trading

Browse the token pairs and click the button 'Sell X for Y' or 'Buy Y for x'

This will exchange one token for the other, according the current exchange rate.

Since the price is set algorithmically based on relative rations of the token pairs in the liquidity pool, be careful
when trading large amounts of tokens in pools with low liquidity.

For example, lets say there is a pair between 1000 Xcoin and 1000 Ycoin with current exchange rate of 1 Xcoin = 1 Ycoin.
Suppose you want to sell 500 Xcoin to buy Ycoin. You will not get 500 Ycoin because your order is significant percentage
of available liquidity, and you will raise the price of Ycoin significantly, getting only 250 Y for your 500 X.

Dont worry too much though, as you can immediately sell Y to get your X back in that case.

You can avoid this altogether by clicking on additional settings and defining your max desired price slippage.

You can also check the liquidity by clicking on 'show more'

## Adding and removing liquidity

You can add your own tokens in the liquidity pool and earn a small % of commission fees on trades on a token pair.

To do this, click on 'show more' and then the 'add liquidity' button. You need to provide both tokens to add liquidity.
In exchange, you get 'liquidity tokens', representing your share of total liquidity in the pool. Note that, when people trade,
the liquidity pool might end up with a different ratio of tokens you initially put in. You can remove the liquidity to get
your portion of the liquidity pool back into your account.

## Concepts

This DEX is based on asset conversion substrate pallet which is itself based on Uniswap v2.
Read more about concepts on [Uniswap V2 docs](https://docs.uniswap.org/contracts/v2/concepts/protocol-overview/how-uniswap-works)

## Adding pairs
To add pairs, use the assetConversion-createPool function at [block explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/settings)
under developer-extrinsics tab

## Stocks and custom assets
Since anyone can add asset pairs, those assets might come with their own special rules. For example, stock in Liberland companies
can only be owned by Liberland citizens and eresidents so buying them would get the transactions reversed. Other assets might be 
controlled by people or groups who do retain burn or admin functionalities over the assets. Make sure to know what you are trading,
especially if the assets are not official LLD, LLM or SORA bridged assets.
