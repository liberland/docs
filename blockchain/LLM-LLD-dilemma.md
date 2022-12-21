# LLD/LLM Split - Explanation

## Tokenization
* Tokenization means giving units to something that would otherwise not be easily countable. In the old days, you had a reputation in the village for being generous and hard-working. 
* Nowadays, you have money instead of this amorphous concept of reputation, which allows you to calculate economic issues such as local scarcity, aka. "how much does item X cost."
* Blockchains use the so-called governance token as their natural medium for power tokenization: The public blockchain is owned by the token holders as well as by node owners.

## Governance Token
* Governance tokens play the following role in a typical blockchain/DAO system:
  * paying transaction fees,
  * forming a consensus between nodes,
  * deciding, in whichever manner, who is going to write the next block on the chain,
  * money on the chain.

 ## Nominated Proof of Stake
* In a nominated Proof of Stake (nPoS) system, the governance token is an even bigger deal than in other systems.
* The network security is tokenized by the governance token, as the selection of the validator for the next block is based on who holds and is willing to stake a more extensive stash of this token.
* Whatever DAO-like politics govern such a chain are likewise based on the governance token.
* Whoever has many tokens staked into them will therefore be deciding 
  * the political matters themselves,
  * whoever will be sitting in whichever representative bodies that chain employs, and
  * how the votes will be counted, as they are likely the ones to mint the relevant block(s).

## LLM Design
* Liberland's design places LLM as the definitive tokenization of political power on the chain and in Liberland. It should be a stable "currency" of power, giving one a predictable amount of influence on Liberland's political scene.

## Politicians - Vote Counters
* Using the standard governance token scheme, we would have a high likelihood of those best in position to become politicians to also be in an excellent place to become validators.
* Validators translate into vote counters if we see the blockchain as a vessel for organizing elections, as we do in Liberland.
* This is because politicians and validators are defined by big stashes of the governance token or by the ability to secure trust from other parties, translated into "borrowed" stashes, either as nominations or votes.
* Votes and nominations being "too similar" to each other translate into the centralization of power.
* What is mitigated on blockchains by anonymity (and other means) becomes a real, painful issue in a State-on-blockchain. States have much stricter criteria for transparency, as they decide on public matters on behalf of all citizens.

## Deflationary vs. Inflationary
 * LLM is designed as deflationary, as it must conserve your political powers. 
 * The governance token must, on the other hand, be inflationary to continuously motivate validators into making new blocks. 
 * Were this not the case, the validators would lose motivation should the emission go down without the price going up sufficiently. The transaction fees would then grow beyond what people would reasonably be willing to pay.
 
 ## Chosen Solution
 * The obvious solution, and the one that was taken, is to split the concept of the governance token into:
   * The network governance coin, for validators, nominators, and as money on the chain, and
   * the political token.
 * In so doing, we can simultaneously keep the design intact without compromises and also achieve full functionality of nPoS and the public blockchain core of our system.
 * Let the political token remain LLM. Let there be a new governance token that takes over network consensus, validation, and Liberland money: LLD.

## Pain Points
* This solution was a compromise. It had not been planned from the start this way and was instead designed to react to the situation described above when we became fully aware of it thanks to our dedicated development partners.
* The biggest issue I find as a designer is that the system is less intuitive than the one with only one governance token. People like number one better than number two.
* The functions are delimitated between LLD and LLM in a logical but not intuitive manner. Unless you think long and hard about blockchains, it will not be *obvious* to you that a State-on-blockchain must split its governance token and do so precisely as we propose.
* Any token issuance is a *liability* in the economic sense to the issuer. The token should be covered by financial reserves or something else, such as the project's potential. The more tokens one issues, the more bags they have to split their capital into to cover the emission. We mitigate this by sensible issuance of both tokens: Where many projects start in billions, we leave the initial token supply in the millions.
* Inflationary token supply increase: the governance token will be less of a "hard money" as its token supply increases. This is an algorithmic, not a political gain, based on code-as-law, but still, one might object to it from the standpoint of Austrian and other economic theories.
