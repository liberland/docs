# Known issues

## Coinstore deposit not showing up (solved)

Coinstore deposits usually take from 15 minutes to 2 hours to arrive.

However, there is a known bug where deposits to coinstore wont show up in certain situations.

Heres how to solve them.

The bug is that Coinstore supports only 1 kind of transaction, and they refused to support the others for enigmatic reasons,
preferring to let customer support and customers themselves handle it  ¯\_(ツ)_/¯  .

The most common issue is when users transfer entire balance, for example, through subwallet LLD transfer and clicking on 'all'.

The transfer will go through, but will not show up on coinstore systems. 

(Any other amount except 'all' is supported by coinstore)

The 'safest' way to transfer is to use [https://blockchain.liberland.org](https://blockchain.liberland.org)

To fix it, you will need to contact ccoinstore support with proof of transaction and its hash.

Get your coinstore deposit address.

Search for the address using chainscan (replace the address in the link with your deposit address)

[https://chainscan.mainnet.liberland.org/account/5GjYePC6HKJGGnEzEZzSvimy6uctuMat4Kr2tjACtKyY9nhT](https://chainscan.mainnet.liberland.org/account/5GjYePC6HKJGGnEzEZzSvimy6uctuMat4Kr2tjACtKyY9nhT)

Make sure you used your coinstore deposit address, then click on LLD transfers.
You should see a LLD transfer you made here.

Click on the event id of the transfer. Then, click on extrinsic number. There, you will see a hash.
Copy the link and the hash.

Then, send a support ticket to coinstore. It should be resolved in a week

```
Hello

I deposited LLD on the Liberland network to my coinstore deposit address <COPY YOUR COINSTORE DEPOSIT ADDRESS> , 
however its not showing up in coinstore. 

Transaction hash is <COPY THE HASH HERE> which you can check on <COPY THE LINK HERE> .

Please manually credit me the LLDs from the deposit address.
```
