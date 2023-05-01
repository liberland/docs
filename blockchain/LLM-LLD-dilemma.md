# LLD/LLM Split - Explanation

## Tokenization
Tokenization refers to the process of assigning units to something that would not be easily quantifiable otherwise. In the past, an individual's reputation in a village for generosity and hard work served this purpose.
In modern times, money replaces the nebulous concept of reputation, enabling the calculation of economic factors such as local scarcity, or "how much does item X cost." Public blockchains utilize governance tokens as the natural medium for power tokenization, with ownership shared among token holders and node owners.

## Governance Token
Governance tokens play the following roles in a typical blockchain/DAO system:
- Payment of transaction fees,
- Formation of consensus among nodes,
- Determination of who will write the next block on the chain,
- Acting as currency on the chain.

 ## Nominated Proof of Stake
In a nominated Proof of Stake (nPoS) system, the governance token holds even greater significance than in other systems.
Network security is tokenized by the governance token, as the validator selection for the next block is based on the possession and willingness to stake a larger quantity of this token. The governance of a DAO-like system depends on the governance token.
Those with many tokens staked into them will decide
- the political matters,
- the membership of representative bodies employed by the chain, and
- the vote counting, as they are likely to mint the relevant block(s).

## LLM Design
Liberland's design positions LLM as the ultimate tokenization of political power on the chain and within Liberland. It should serve as a stable "currency" of power, providing a predictable level of influence in Liberland's political landscape.

## Politicians - Vote Counters Dilemma
Utilizing the standard governance token scheme, those best positioned to become politicians are also likely to be well-suited to become validators.
Validators act as vote counters when considering the blockchain as a means for organizing elections, as is the case in Liberland.
Both politicians and validators are defined by substantial holdings of the governance token or the ability to secure trust from other parties, manifested as "borrowed" holdings through nominations or votes.

The similarity between votes and nominations can lead to the centralization of power.

Issues mitigated on blockchains by anonymity (and other means) become significant concerns in a State-on-blockchain due to the stricter transparency requirements of states when deciding on public matters on behalf of all citizens.

## Deflationary vs. Inflationary
LLM is designed as deflationary to preserve political power. Conversely, the governance token must be inflationary to continuously incentivize validators to create new blocks.

Without this incentive, validators would lose motivation if emission decreases without a corresponding increase in price, causing transaction fees to rise beyond what people are reasonably willing to pay.
 
 ## Chosen Solution
The adopted solution is to split the governance token concept into:
- The network governance coin for validators, nominators, and on-chain currency, and
- The political token.
By implementing this split, we can maintain the design without compromises and achieve full functionality of nPoS and the public blockchain core of our system.
The political token remains LLM, while a new governance token, LLD, takes over network consensus, validation, and Liberland currency functions.

## Pain Points
The chosen solution is a compromise that was not part of the original plan. It was devised in response to the situation described above, which became apparent thanks to our dedicated development partners.

The main issue is that the system is less intuitive than one with only a single governance token. People generally prefer simplicity.

The functions are logically delineated between LLD and LLM, but not intuitively so. Without deep understanding of blockchains, it may not be immediately apparent that a State-on-blockchain must split its governance token, nor that it should be done in the proposed manner.

Token issuance is an economic liability for the issuer. The token should be backed by financial reserves or other assets, such as the project's potential. Issuing more tokens increases the need for additional capital to cover the emission. We mitigate this by sensibly issuing both tokens, keeping initial token supply in the millions rather than the billions common in other projects.

Inflationary token supply increase means the governance token will be less of a "hard money" as its token supply grows. While this is an algorithmic rather than political gain, based on code-as-law, it may face objections from proponents of Austrian and other economic theories.
