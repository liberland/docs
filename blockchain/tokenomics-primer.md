# Tokenomics Primer

## Division of Power
As all modern democratic countries, Liberland employs division of power in its government and, thereby, also on its blockchain governance mechanism. 
The main concentration of power on a blockchain is in the node owners and those who write new blocks - the [Validators](https://en.wikipedia.org/wiki/Proof_of_stake#Validator). 
In a [DAO](https://en.wikipedia.org/wiki/Decentralized_autonomous_organization), the power of democracy in the system would directly derive from ownership of the coin that the Validators and Nominators use.
Such a concentration of power is not desirable, as, in effect, it would ensure with mathematic certainty that those best poised to become officials in Liberland would also be those who count the votes.

To counter this, we have separated the Validator power from the governance power. So the two-token system was born: the governance token, Liberland Merit (LLM), and the coin, Liberland Dollar (LLD).




## Liberland Dollar (LLD)
### Overview
Liberland Dollar is the native coin of Liberland Blockchain. Its primary purposes are:
1. Operational token of the Liberland blockchain, used by validators and stakers to secure the chain, as well as paying gas fees for transactions, contracts, judiciary and companies
2. the money to purchase goods and services (mainly off-chain), hence, the medium to record market values of primarily real-world articles.

Despite the name, LLD is not a stablecoin but tradeable digital money, just like BTC. As such, the price is strictly market-based.
The price of LLD is determined by [open markets](https://www.coingecko.com/en/coins/liberland-lld).

Please note that any references to a "preferred currency" refers solely to a government unit of accounting. There is no legal tender in Liberland. Everybody in Liberland is able to pay with whatever currency, barter, favours or other means of exchange the seller will accept, without any government interference.


### Tokenomics
#### General
The system is a sovereign chain based on a fork of Parity's Substrate framework, 
which powers the [Polkadot](https://en.wikipedia.org/wiki/Polkadot_(cryptocurrency)) (DOT) blockchain and parachains.
The main mechanisms Liberland adopted from polkadot have been created by researchers, and tested both by auditors and in practice.

### Initial distribution
The system issued **3 000 000 LLD** at time of token generation, which is markedly less than the initial offerings of most cryptocurrencies.
Tokens were initially airdropped to Liberland citizens and other holders of staked LLM, proportional to their LLM holdings.

'Day 0' initial distribution, on 11.2.2024 was roughly as follows

|   Name	|   Amount	| 
|---	|---	|
|   Liberlanders & LLM holders	|   1,350,000	|
|   Liberland government	|   850,000	|
|   Listing liquidity reserve	|   800,000	|

### Current distribution

As of 27.07.2024 the distribution of tokens is roughly as follows

|   Category	|   Description	|   # Tokens	|   % of Total	|
|---	|---	|---	|---	|
|   Total	|   Total amount of existing tokens	|   3,107,200	|   100%	|
|   Staked	|   Staked tokens	|   528,224	|   17%	|
|   Government Liquid	|   LLD across all government accounts	|   255,309	|   8.21%	|
|   Government Locked	|   Unlocking 50k/month	|   500,000	|   16.1%	|
|   CEX liquidity	|   CEX liquidity or reserved for new listing	|   737,768	|   23.8%	|
|   DEX liquidity	|   DEX liquidity pools	|   ~350,000	|   11.26%	|
|   Liberlanders and traders	|   Not staked, not on exchanges	|   735,899	|   23.7%	|

### Government tokens

Government of Liberland has LLD holdings that it uses to invest and reward contributors to the Liberland ecosystem. 
A significant portion of the tokens (500,000), representing about 70% of all LLD held by the government are held in lock contracts,
unlocking 50k monthly. List of lock contracts can be [found here](https://docs.google.com/spreadsheets/d/1QRwazEjj6jeGD_D6LgtxDgkr2InmgRwFv-pbR2ZTvWk/edit?usp=sharing)

A majority of government 'spending' so far has been for providing liquidity to new exchange listings, such as Uniswap and MEXC.

The rest of the tokens are 'soft precommited' over a period of a few years in the following manner

|   Purpose	|   Description	|   # Tokens	|   % of Government	|   % of Total	|
|---	|---	|---	|---	|---     |
|   Total government	|   All LLDs across all govt accounts	|   776,530	|   100%	|   100%	|
|   Liquidity for new exchanges	|   Planned Bybit, Bitget, Kucoin, OKX, Raydium	|   200,000	|   25.7%	|   6.4%	|
|   Settlement	|   Physical settlement on Liberland, Ark, Liberbase	|   125,000	|   16.1%	|   4%	|
|   Marketing	|   	|   175,000	|   22.5%	|   5.6%	|
|   Development	|   Judiciary, hybrid contracts and company ecosystem, other dev	|   115,000	|   14.8%	|   3.7%	|
|   Diplomacy & legal	|   Representative offices, international compliance etc.	|   85,000	|   10.9%	|   2.7%	|
|   Incentives & misc	|   Misc spendings including incentives for example liquidity farming	|   76,530	|   9.6%	|   2.5%	|

#### Inflation
The maximum coded inflation is 10 percent per year, subject to reduction by governance. 
Inflation is distributed to validators, stakers and the government.
The purpose of inflation is to make sure the servers running the blockchain - validators - are running sustainably and to incentivise staking.
Given that Liberland blockchain is a proof of stake chain, validator costs will stay comparatively low as adoption increases.

##### Path to deflation
Inflation is expected to decrease as LLD price and adoption(and with it, gas fees income) increase. 
After a certain degree of adoption transaction and gas fees will be enough to cover validator costs.
Fees for complex business uses such as legally and internationally enforcable on-chain contracts under Liberland court jurisdiction 
could be enough to justify removing inflation by setting it to 0% after which burn mechanisms will make LLD slightly deflationary.  


### Validators
[Validators](https://wiki.polkadot.network/docs/learn-staking#selection-of-Validators) get selected by the algorithm based on the size of their stake. 
Validators must be Liberland Citizens. 
Their responsibility is to [produce new block candidates](https://wiki.polkadot.network/docs/learn-consensus#block-production-babe) and [finalize blocks](https://wiki.polkadot.network/docs/learn-consensus#finality-gadget-grandpa). 
Validators are selected per epoch and misbehaving Validators can be "slashed" by the system.

### Nominators and stakers
[Nominators](https://wiki.polkadot.network/docs/learn-staking#selection-of-Validators), also known as stakers, ensure the true decentralization of the chain. 
Anyone can be a Nominator and becoming one is the question of having some LLD and setting up a stash. 
Nominators don't get reward for hosting a node, but for staking their LLD into a node of an existing Validator, hereby increasing their chance at nomination.

[Read the staking guide here](./for-validators-nominators-and-stakers/staking.md)

### Crosschain bridge
Liberland tokens can be [bridged using a crosschain Hashi bridge](cross-chain-bridge.md), which allows LLD to be tradeable on other chains, such as Ethereum, SORA, and (coming soon) BnB.

The bridge works both ways, so tokens from other chains, such as ETH, wBTC, USDT, XOR, DOT and others 
are available for Liberland exchanges, companies, contracts and courts directly on the Liberland blockchain. 

|   Tokens on chain	|   # Tokens	|   % of Total	|
|---	|---	|---	|
|   Liberland	|   2,474,217	|   79.7%	|
|   Ethereum	|   532,883	|   17.1%	|
|   Sora	    |   1,000	|   ~0%	    | 
|   Solana      |   100,000 |   3.2%    |

### Listing
LLD is now [listed on several centralized exchanges](./how-to-acquire-lld.md), 
and wrapped verions of the token available on decentralized exchanges on [Ethereum](https://matcha.xyz/tokens/ethereum/0x054c9d4c6f4ea4e14391addd1812106c97d05690), Polkaswap on SORA Network, Liberland DEX on Liberland Blockchain and, soon, [Raydium](https://raydium.io/swap/?inputMint=sol&outputMint=GwKKPsJdY5oWMJ8RReWLcvb82KzW6FKy2bKoYW7kHr16) on Solana.

This combination of CEXs and DEXs makes it easier for Citizens, e-Residents and other supporters to easily obtain LLD and LLM.

Decentralized exchanges are, in the opinion of the Senate and core contributors, more closely related with Satoshi's vision of peer-to-peer electronic cash than centralized exchanges.

## Liberland Merit (LLM)
### Overview
Liberland Merit (LLM) is the governance token representing a share in the State and nationhood of Liberland. LLM is not a security created with the expectation of revenue; instead, it is legally close to shares in joint ownership, like in case of housing cooperatives; LLM represents one's share in the country. Governance power is connected to LLM, and there is no possibility of other governance and no separating of this power from the token.

![LLM Management Flow](media/LLMTokenomics.png)

### PolitiPooling
To prevent [plutocratic](https://en.wikipedia.org/wiki/Plutocracy) concentration of power, one can only utilize LLM in politics if one vests them on a tight schedule. This vesting is called "PolitiPooling." PolitiPooled LLM is locked, and the user can only unvest 10 percent in a year: payable monthly, 1/12th of 1/10th of total vested amount, each month.

### Citizenship on the Blockchain
Liberland, as a country, acknowledges the importance of citizenship. Only Citizens with 5000 PolitiPooled (a.k.a. staked) LLM have full political rights associated with citizenship in Liberland. In this way, Liberland replaces the usual requirements proving a personal connection to the country through vesting. Where one should gain "honorary citizenship" for their contributions, they won't be able to vote in elections or referenda unless they also PolitiPool. We can expect those who commit their funds to Liberland long-term to have a provable bond with the land and a stake in the country's success. 

### Tokenomics
Inspired by Bitcoin (BTC), LLM has a fixed maximum supply of **70 000 000** tokens. With losses expected due to lost wallets and other factors, this token will, in time, become deflationary. The initial price for LLM was 1 USD, increased to 2 USD on 11 September 2023, and will change frequently when LLM begins to trade on the open market. According to Liberland's ethos and paraphrasing Adam Smith, the price of 1 LLM will be <i>"whatever the purchasers are willing to pay for it."</i>
