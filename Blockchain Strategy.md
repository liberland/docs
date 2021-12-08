![](RackMultipart20211208-4-dazfz1_html_b156baae09b79fd6.jpg)

# Strategy LLM Blockchain Q4/2021 &amp; Q1/2022

## General description

We are in transition between providers of development services. We are currently evaluating the code we already have, and at the time of the writing, it is not clear which parts of it are usable. Regardless, we can already state the priorities for our further development, and those are in the order of urgency:

1. an MVP blockchain
2. a fully functioning blockchain with a front end
3. an MVP basic state governance (some form of legislative) / or functioning basic state governance (legislative as per our constitution)
4. MVP smart contracts

After Q1 2022 will come the time to implement the following functionalities (out of scope of this strategy):

1. functioning smart contracts
2. advanced state functions (executive)
3. interchain gateway
4. the judiciary

This is a mid-level strategy. The intended audience is all our development partners who may choose to help us take our project to the next level.

The low-level details, including the deadlines within the particular sub-projects and how these will be done hands-on, should be agreed upon with the team during bi-weekly meetings.

## 1. MVP blockchain

## Introduction

Here you will be making a &quot;Litecoin 2017&quot; or &quot;early Dogecoin&quot; state of a blockchain out of the provided material. You will turn on the system&#39;s beating heart, and we will maintain a laser-sharp focus on this core product until it works. The benefits of this step are many, and hence, this has the highest urgency; as we will be able to:

1. offer ICOs;
2. attract investors;
3. show off our product, i.e. on social networks;
4. build and maintain a Telegram community (Michal and Noah will help);
5. get audits
6. get listed on centralised and decentralised exchanges.

**Deadline**** : ASAP, mid 12/2021 at the latest (before Christmas break in Europe).**

## Subprojects

1. Audit the **backend** and the **node** repositories

2. Test it, deploy it as a testnet, make sure it is secure and workable by well-known security tests.

According to our previous developers, the backend and node should right now be able to do the following:

- send and receive LLM;
- log in on a Wallet, see balances;
- make a new Wallet account;
- see the actions on the blockchain in the Polka JS Explorer;
- see the activities on the blockchain in the Terminal under Developer tools in the Polka JS Explorer;
- deploy a node semi-easily, enabling anyone to become a validator;
- select 100 validators from the pool to be the validators for the next epoch based on the PHRAGMEN algorithm;
- stake LLM in PolkaStaking (28 days), i.e. to nominate validators;
- get rewards for block making as a Validator/Nominator;
- run testnet;
- start mainnet on cca ten servers securely in the hands of well respected Liberlanders/Liberland herself;
- enable Liberland to airdrop LLM into the mainnet.

3. If not secure and workable, please start the development to improve the material. Please take examples from working projects where possible, most applicable seems Polkadot; please copy what you can into our system, make it a clone of Polkadot in this stage, or Kusama.

4. Test it until you can report success.

5. **Deploy testnet and main net** on a number of servers, at least ten computers.

## Output

After the final testing is done, the development teams should inform us that this phase will finish. We will begin with a marketing campaign and a funding/investor-seeking campaign. We will give their work some publicity, and we will also start airdropping their wages.

## 2. Fully functioning blockchain with frontend

## Introduction

The original project was heavily front-end based, and there was much focus given to the Liberland environment, our &quot;DAPP&quot;. This front end must be tested and audited, and connected firmly to the now-functioning backend. It should be:

- running;
- connective with the wallet extensions used (initially Polka JS);
- without overt bugs;
- giving all the necessary messages and feedback to the users;
- the blockchain actions performed from the front end should be 100 per cent explainable from the Polka JS and the Terminal Blockchain explorers;
- enabling the proof of stake functionality, that is
  - nominating; and
  - validating.
- be linked to our Liberland.org website;
- be polished enough to be marketable, but perfection (at the cost of time) is not required at this stage.

**Deadline**** : End 2021 or at the latest mid-January 2022.**

## Subprojects:

### Auditing

1. Compile and deploy the contents of the **frontend** repository;
2. Test it whether it has the following functionalities; according to our previous developers, the code as it is now should be able to do the following:

- function as a wallet environment [like Terra Station or YOLO wallet for Cardano];
- sending, receiving transactions;
- transaction history incl. senders and recipients (KYCed entities where applicable);
- having at this stage one account only per wallet connection;
- it should have a fully functioning (polka) staking function;
- there should not be overt bugs;
- all action in the front end should one on one match the action in the Polka JS wallet

3. If any of this is missing, it needs to be added and then re-tested.
4. Test it for seamless integration with the backend.

### Implementing new functionality

Next, come the improvements. The following is the list of _core_ features our system does not yet have but should finish at this stage. It should:

- show a list of available validators;
- list of their rewards and risk parameters (how long have they been validating, how many slashing incidents);
- enable a validator to set themselves up in the system and say how much they reward their nominators;
- there should be a nominate function;
- there should be an overview for the validator (rewards list, uptime, etc.);
- there should also be an overview for the nominator (rewards list, ability to claim rewards);
- the rewards system should work fully with the front end.

Your sources of inspiration are Terra Station, Exodus Wallet, Yolo Wallet, Phantom Wallet, and the Polka JS environment (although that is not exactly user-friendly).

### Polishing

This phase will end with testing and adding new features that are largely cosmetic but necessary that the product won&#39;t be seen as half-done by the client. Those include:

- Having all popups functioning, i.e. that users know when a transaction fails, for what reasons, etc.;
- No bugs on login;
- Seamless working with the Polka JS extension;
- integration with our Liberland.org website; meaning: the E-Residency login will result in Liberland blockchain login, matching a wallet to the corresponding login;
- Having LLM from Liberland.org visible as mainnet LLM and vice versa;
- Setting up a mobile version (in a browser, Google Chrome at first);
- Anything else the testers might find necessary, instead of include &quot;merely nice to have&quot;.

### Optional

Provided there is development time, work can begin on a Liberand Android app, followed by an iOS app.

Make it a wallet application; inspirations: Trust Wallet, Mycelium, Blue Wallet; Phantom Wallet (for the staking features; that one is not yet mobile).

At first basic functionality only - send, receive, show, stake, see your stake, nominate stake to yourself or another validator, claim rewards.

## Output

We will now have a functioning and marketable frontend that will become a centrepiece of our popularisation efforts. Our e-residents will log in from their PCs and maybe from their smartphone. Staking will become easy and transparent, enabling us to market it as a source of passive income and a use case for our token.

Thanks to your efforts, Liberland will start building a name in the blockchain world!

## 3. State Governance

## Introduction

We split the governance by State powers (Montesquieu: Legislative, Executive, Judicial), and each power has a different priority. The highest priority is assigned to the Legislative Branch.

The reason for that is that the Legislative Branch is the most citizen-facing. We need our citizens and supporters to _find themselves_ in our system - ASAP. This is why we have a burning need to implement the Legislative Branch first, far ahead of all the others.

The Legislative Branch also can work on its own without the other branches. They are the guys and gals who make the rules, and they could even implement and enforce them until they &quot;outsource&quot; it to other Branches.

The software should, according to our old developer by now, already be capable of:


#### Basic representative democracy

- running full blockchain-based elections into the Congressional Assembly, our parliament;
- implementing our &quot;Proof of Commitment&quot; concept, also known as Liberstaking - you get political power by sacrificing your LLM to keep them Staked on a long vesting schedule; hence you prove your commitment to the future of our nation (caution, this part is half-finished, even according to the previous developer);
- onboarding new Representatives (elected officials);
- ending their term when the election cycle is over;
- work with a special algorithm that allocates votes (you vote with your Staked LLM);
- Representatives can vote in the Prime Minister and Ministers;
- they can fire the Prime Minister or Ministers.


#### Basic legislative process

- Representatives can propose laws;
- They can vote for these laws with the LLM they had been voted in during the elections (the popular political power) + their LLM;
- Laws can be accepted or rejected by the Assembly;
- Accepted Laws are written into the Blockchain and shown in the front end.

Basic Public Veto (direct democracy)

- Citizens can propose the (binding, unlike with petitions) motion for the removal of a Law;
- they can vote for it, _one citizen, one vote_;
- the Veto Proposal (referendum) stays open until 50 per cent plus one citizen vote yea or nay.

How we will do it will be based on the current state of the software. I propose to take one of the two approaches:

1. Say that the code for our state governance is really unfinished and nearly useless - we will create a rudimentary version of the legislative power: the **MVP State Governance.**
2. If the system is already built to some working extent (50 per cent finished or more), we will work towards a **fully implemented State Governance.**

Please be aware that the goal is **option 2, fully implemented State Governance.** _ **We should try for this if even slightly possible.** _

**Deadline: 01-04-2022** (regardless of whether we went for the MVP or the full version)

## Subprojects

### 1. MVP State Governance

Using our front end, which should be working already, we will create a simple, **non-binding**** petition system** in the beginning. Everybody who has an idea can push it through to a simple referendum like process. This referendum is not expected by the Constitution and hence, cannot be binding. It is however a good way to show the Citizens that they can participate.

People will send proposals and &quot;sweeten them&quot; by their Staked LLM (perhaps even PolkaStaked in this phase). The more LLM in a proposal by a person who proposes and the supporter, the more power to that side: yea or nay.

Proposals are **not binding,** but we can guarantee that the Provisional Government will discuss them in some capacity, and the Deputy Minister of Justice will report what has been decided about that proposal. We can then keep this system even into the mature Liberland, as most any democracy uses some kind of petition rights.

For inspiration, we should look at the link below:

[https://proposals.decred.org/?tab=approved](https://proposals.decred.org/?tab=approved)

### 2. Full State Governance

_This is the desired route._ It starts with the testers agreeing that the system _is_ salvageable.

### Auditing

1. Test the deployed version of the system; run elections; prepare and vote for laws. Populate the testnet Congressional Assembly with 7 Representatives
2. Use the provided list (in the Introduction of this section), start _from the top,_ and go down.
3. Make sure everything works smoothly as you go.
4. Whenever something is found that does not conform to the list above in Introduction, i.e. a feature is missing or incomplete, please finish it, test it, make sure all works.

### Improving

1. After the Auditing is complete, please _run again_ through the list;
2. Make a list of improvements or points which you find that may cause problems;
3. This can be software issues but also conceptual issues;
4. Set a meeting with the Deputy Minister of Justice and, if possible, with the President to develop a list of improvements based on your findings;
5. Make sure to organise your proposals so that there are a maximum of _four_ such meetings (2 - 3 hours each), which will work as follows:

- the initial proposal for changes should be discussed at the _first two_ meetings;
- the second two meetings are for complicated cases, details, or follow-up.

1. Code into the system the result of the four meetings.
2. Ask the Deputy Minister of Justice _frequent_ questions using his telegram; he is always available for you.

### Game testing

1. We will organise a series of 2 or 3 meetings where we sit together and play politics on the testnet.
2. We will together (each participant, the President voluntarily)of law prepare a few scenarios which seek to test the system in a _regular run_. So no attempts to hack the system.
3. In addition, we will prepare each _zero to__two_ scenarios where &quot;our&quot; politician tries to hack the system, game it to achieve some nefarious goal (i.e. get extra money from the State treasury, pass a law that makes his company the prefered State supplier, etc.)
4. The devs will participate and make notes; then, we will make a list of further improvements.
5. The devs will implement and test the improvements.
6. Note: This is a &quot;statistical&quot; attempt at improving, and we _do not have the time_ to make the system perfectly gaming-proof before the deadline.

### Forum

Whichever system we choose, MVP or Full, we should **create a forum on Liberland.org** or an affiliated website.

This forum will serve to debate Liberland politics and either to:

1. Propose petitions if MVP; or
2. Organise campaigns and lobby for proposals; and
3. Provide rooms for the Representatives (Reps only write, others view only) to discuss congressional assembly meetings if full governance.

## Output

We will have a system in which the politics of Liberland happens, and it will start happening for real. I don&#39;t want to repeat myself, but this will be a massive opportunity for all our PR people to make Liberland the news of the hour.

Why did we choose 1st April as the deadline? Because in mid-April, the anniversary event happens in the physical Liberland on the Danube. We would like to ask your help to help us prepare a big presentation of the political system for that event. There, we will formally introduce the fruits of your labour to the world and the Liberland public!

## 4. Smart Contracts

## Introduction

The final task in the Q4 to Q1 scope is to _prepare the Smart Contract pallet_. This pallet will enable others to write and run smart contracts, enabling functionality akin to Ethereum or BSC - DEXes and DAPPs. We do not expect this to be _completely_ finished before the end of Q4, but significant work should already be done by then.

**Deadline:**  **The end of Q1 2022.**

## Subprojects

### Prepare the Pallet

1. Take a similar pallet from Polkadot or (if possible, Adoria said that it was impossible) from Solana;

2. Make sure it works in our system.

3. Test it with a sample smart contract or smart contracts.

4. Prepare a demonstration, run it in a meeting with us.

### Clone &quot;Etherscan&quot; into Liberscan

1. Smart contracts require a blockchain explorer capable of monitoring the action;

2. Take the free software of a similar blockchain explorer such as Etherscan and clone it.

3. Make minimal changes so that it is _barely_ useable.

4. It needs not to be _perfect_ by the end of Q4 - this is a monumental task in scope!

### Set up guidelines to write Smart Contracts on Liberland

1. Please copy a similar guideline from the source material.

2. Make a Wiki explaining how it works.

### Citizenship NFT

This will be the first Smart Contract we create on our new pallet. The purpose will be to represent the citizenship of every citizen.

Citizenship token will contain

- a picture of the citizenship ID;
- link to the owner&#39;s Liberland account (this will be the _holder_ of that account, a citizen will be for the system this token!)
- the number of LLM staked into the citizenship;
- the history of this particular citizenship token, i.e. who was the previous holder and holders of this NFT, creating potentially &quot;collectakble&quot; NFT .

1. Make the smart contract to set up this token.

2. Test it.

## Output

We will be able to build smart contracts on our chain, which will create attractivity and use cases, which will also enable us to take our governance to the next level.

We will be able to set up more government processes as smart contracts. We will provide every citizen with their tokenised citizenship right in their wallet.
