# White Paper Liberland Blockchain

## Introduction 
* Liberland is a country established in 2015, on a no man’s land (terra nullius) between Croatia and Serbia (www.liberland.org). Liberland’s founders are blockchain and liberty enthusiasts. Liberland’s State project could be summarised by two concepts: Minimal state and distributive governance. 
* We want to make all e-government services available to our citizens using our substrate-based blockchain (https://github.com/liberland/liberland).
* While working on establishing the physical State in the designated area, Liberland is building a virtual representation of that area in its Metaverse. This “virtual Liberland” governance shall become the first use case for our system. The Metaverse is being built as we speak (world.liberland.org).

## The Scope:
### Liberland Blockchain / Node
* We create our own Substrate based blockchain. Based on Polkadot, the consensus mechanism will be a version of Delegated Proof of Stake. 
* Our project is not a parachain of Polkadot but a stand-alone blockchain.
* The node is easy to download & install for anyone with a basic knowledge of Linux, our first supported operating system. 

### Backend
* The backend is the database (or a set of databases further on) and the Substrate nodes. We will create API connections with the Metaverse and its specific functions and other extrinsic services.

### Frontend
* The front end will consist of pages designed for Liberlanders to interact with their government. It will include and will not be limited to the following sub-domains:  
a) a wallet interface;  
b) an interface with validators;  
c) political interface, i.e. for the elections, candidates, legislative drafting;  
d) an interface for government registers and other services;  
e) the internal government front ends for the officials to work in & access the chain;  
f) the treasury interface;  
* In addition, there will be a whole set of front-ends that will allow the blockchain to interact with the metaverse.
Public Blockchain
* This is a public blockchain owned by the holders of coins and tokens. Liberland funds and supports its development, and Liberland will provide the first use case or set of use cases. The licence is MIT, the same licence that Bitcoin uses, and Liberland is in no way the owner of the blockchain or the related materials.
* Anyone can use our codebase to clone our project and fork it or create a new project based on it.

## Permissioned Access
* Liberland is a State, and it needs to maintain its security in ways that normal blockchains do not require.
* To accommodate those needs, certain blockchain functions require permissioned access for special types of users: Citizens and E-Residents. To become either, one has to go through a KYC process. In addition, the access requires the purchase and a vested holding of a certain amount of our Token (LLM); see below.
* The main areas which require permissioned access are:
a) running a Validator node; and  
b) on-chain governance.  
* Access to these functionalities requires one to become a Citizen in Liberland. This is a substantial commitment. We may assume a level of loyalty to the project beyond a casual investor.
* Please note: Everyone can permissionlessly use the tokens and coins of our blockchain as a store of value or a medium of exchange. Only the advanced functionalities critical for the project’s future are permissioned.
DeFi projects on our chain will not be permissioned unless otherwise designed by the 3rd party developers on a per-project basis.
Coins:

## Liberland Dollar (LLD)
* Liberland Dollar is the coin of the blockchain. Its main functions are:
a) a medium of exchange; and  
b) an instrument to maintain network consensus and network security.   
* The LLD will be minted according to rules inherited from Polkadot, although tweaked to produce less of an inflationary curve. This means an “ideal staking ratio”, and if the total number of staked LLD is lower than that ideal ratio, the inflation rate speeds up. If it is higher, the inflation rate slows down.
There is no hard limit on the number of LLD in existence.
Liberland Merit (LLM)
Liberland Merit (LLM) will be our blockchain's governance token and Liberland itself. It has been set up using the Assets Substrate pallet. It will serve as the Store-of-Value token, the tokenomics being somewhat similar to the BTC:
There will be a hard cap of 70 million in total. A fixed amount of LLM will be minted over a timeframe of 48 years, allowing inflation to be fixed (being able to pre-calculate future inflation percentages) and controlled over time. Please see the details here: https://docs.google.com/spreadsheets/d/1uBuGNQMuyz9p4_JBbza7Wa8hWCYkGdGjoOISF0LPKro/edit#gid=0.
NFTs
The blockchain will set up a system of NFTs which will serve as a decentralised register for the (currently centralised) databases on which our Metaverse runs. This will entail all assets, but firstly assets representing what in the real world would be immovable property.
Later, the project will tokenise everything in that metaverse and real-world Liberland. Selling and purchases will be facilitated through NFTs, representing “deeds of ownership” to the real-life objects. Where there is a dispute, the Judge needs only to look on-chain who owns the NFT about that object.
Government NFT-like tokens
Citizenship and other on-chain identities like Senatorship, Membership in Congress or being a Judge will be tokenised. These will not be true NFTs since they will not be in general sellable, at least not on a free and unregulated market; for most of those tokens, selling them will be truly impossible. Selling will be heavily regulated for Citizenship tokens, requiring KYC equal to when someone becomes a Citizen and mints a new Citizenship token. This is to maintain State security.
Contract-based (3rd party) tokens
The Chain will fully support Smart Contracts, as it runs a fork of the Polkadot Virtual Machine. This will enable our team and 3rd party developers to set up their decentralised infrastructure. We envision a full-fledged De-Fi environment springing up on our chain, much like we see on other Rust-based chains such as Polkadot, Kusama or Solana.
Liberland Politics:
The basis for Liberland’s politics is our Constitution. This Constitution is in the public review phase, and you can view it (and place your comments!) here.
The following are the basic elements of Liberland’s politics that we will be hosting on our blockchain.
Citizenship
Citizenship and e-residency user statuses and roles shall be held on-chain and validated along with other transactions. We will implement a new Identity Pallet and adapt it to Liberland’s legal system.
Referendum
The central decision-making process in our system rests with the Referendum, in the good tradition of Swiss democracy. The Referendum allows all citizens (not all users) to make decisions regarding the future of the blockchain but, most importantly, to decide on Laws, other Regulations, and other motions in Liberland’s politics. All Laws must pass the direct democracy of the Referendum to gain legal force. Citizens can also propose Referenda. Referendum uses a Tally system inherited from Polkadot, which serves as a populism-preventing measure - the lower the turnover, the higher the tally needed to adopt a proposal.
Congress
Next to the Referendum, we are creating a representative democracy module (centred around the Congress Pallet, a custom-made pallet), where Congress is the main legislative organ of our government (the “Administration”). The Members of Congress (MoC) represent the Citizens. They have three main functions: 1) to propose rational Referenda, 2) to nominate and dismiss the Prime Minister (Executive), and 3) to decide budgetary matters. 
Our front end will enable an easy-to-use delegation system, so people can delegate their tokens to Members of Congress to vote instead of them. This will serve the voter who feels they don’t have the time directly to tackle every issue. Lastly, Congress can, with a ⅔ majority, cancel referenda they deem unconstitutional or otherwise bad-faith (going against individual liberty).
Executive
Our Executive will be an entity of its own, with its Pallet. Its main on-chain purpose will be to exercise certain powers of regulation under Law, emergency powers reminiscent of the Polkadot Technical Committee. The main focus will be the interaction with our e-government, such as the various registries, government websites, and communication platforms, which are all used to facilitate the day-to-day operations of Liberland. The Cabinet is composed of four ministers led by one prime minister. 
Senate & the Treasury
One of the standing values that Liberland has is that all taxes are paid voluntarily by the citizens of Liberland. We fork Polkadot’s Treasury and implement it as a multi-signature wallet held by the on-chain politicians of Liberland. Like Polkadot’s Treasury, we will handle funding proposals, mainly initiated by the Executive and Congress. 
The Senate is composed of the biggest investors in our project. The Senators can veto Laws and Regulations. They hold the Treasury keys, and no spending may commence without their direct action. They will likely set up a system for day-to-day checks on routine spending, handled by the President.
Their second power will be the ability to cancel malicious referenda regarding laws and also sub-legal regulations they see as impediments to Liberland’s prosperity.
Judiciary
The project will entail a fully working justice system inspired by Kleros, the Aragon Court, and Ulex. The development of this will commence at a later stage of the project.
The pre-alpha version of the white paper for this sub-system can be found here: Liberland dispute resolution system for the grant application
Citizen-facing Government Services:
Identity
The blockchain will contain encrypted information regarding the citizens' data, accessible only to the citizens and with their permission. One’s ID exists in Liberland to prove one’s identity where the Citizen or E-Resident wants to identify themselves, i.e., partake in a service. Whether or not this identification will take place remains in the hands of the user. 
Having the identity run on a blockchain, with immutability guaranteed by the network consensus, drastically lowers the danger of identity theft. Liberland ID will be useful far beyond the limits of Liberland itself - those who have it can log into third-party services with the confidence only blockchain security provides.
We will later set up a DAO or DAOs, which will enable “decentralized identification” concerning information people want others to know about. There will be networks working between verifiers and the verified. Qualified verifiers, like universities, will be able to encode information, like a university degree, cryptographically and put it in the hands of the data subject. This information will only be accessible to the user and those whom the user wants it to see.
We hope to create a new standard of information security, building on the current standards like the GDPR, but streamlining them, on the one hand, to remove needless administration and make them even more secure and safe on the other. The twinning of the blockchain (for immutability) with one-way cryptography (for safety) creates a combination of security, veracity and expedience unseen in current States.
Registers
We will build NFT-fuelled registers of several kinds of entities, starting with virtual real estate for our Metaverse and the real world.
We will first set up a Liberland-registered Companies register, where principals can keep the information public and up to date for their convenience. 
Secondly, we will create NFT-fueled Land and Immovable Property registers for the Metaverse and, later, the real-life Liberland.
Lastly, we will set up DAOs registering other assets, like movable property or even securities. We will rely heavily on third parties, bringing in the best available technologies tested on different chains and projects.
Annexe
Team Members
Dorian Stern-Vukotic, Frontend developer
Filip Kalebo, Rust substrate Team leader and developer; Github: https://github.com/flipchan;
As a backup and to provide a second opinion, we have the possibility of asking a second experienced team of developers who has a great track record in the development of crypto-related projects. Please see their earlier work here:
https://www.mantleblockchain.com/
https://www.masscrypto.io
https://www.hglobal.io
https://www.nftytoken.io
Team’s Website
https://github.com/liberland/liberland
Legal Structure
A Hong Kong-based Limited Liability Company; later a Liberland Company as the entity in charge.
For production:
Development Team at Rust Syndicate LLC, Tbilisi, Republic of Georgia.
Team
Team LinkedIn Profiles:
https://www.linkedin.com/in/djstern
https://se.linkedin.com/in/filip-k%C3%A4lebo-479314115
Team Code Repositories
https://github.com/liberland/liberland_backend
https://github.com/liberland/liberland_frontend
https://github.com/liberland/liberland_node
https://github.com/liberland/docs/blob/master/Blockchain%20Strategy.md
Contact:
justice@liberland.org
Intended Language of Development
Rust for the blockchain backend, Javascript / Angular for the Frontend.
Roadmap and Milestones
Basic blockchain
Deadline: Q3 2022
A basic mainnet blockchain based on Substrate. This is already built thanks to earlier efforts, but the project must be finished and deployed to a large extent.
Functional token transactions, send and receive LLM;
Frontend with on-chain wallet interaction;
Simple governance based on our model & elements inherited from Polkadot;
Publicly see and interact with the blockchain;
Simple node deployment instructions;
nPOS consensus
Active mainnet; and
Onboard users.
Frontend
Deadline: Q3 2022
In the Liberland frontend environment, our DAPP must be tested, audited, and connected firmly to the now-functioning backend. It should be:
running;
connective with the wallet extensions used (initially Polka JS);
without overt bugs;
giving all the necessary messages and feedback to the users;
the blockchain actions performed from the front end should be 100 percent explainable from the Polka JS and the Terminal Blockchain explorers;
providing the UX to the backend/node functionality of validating and nominating; and
be linked to our Liberland.org website.
State Governance
Deadline: Q4 2022
We split the governance by State powers (Montesquieu: Legislative, Executive, Judicial), and each power has a different priority. The highest priority is assigned to the Legislative Branch.
The reason for that is that the Legislative Branch is the most citizen-facing. We need our citizens and supporters to find themselves in our system - ASAP. This is why we have a burning need to implement the Legislative Branch first, far ahead of all the others.
The Legislative Branch also can work on its own without the other branches. 

Basic representative democracy
running full elections into the Congressional Assembly, our parliament;
onboarding new Representatives (elected officials);
ending their term when the election cycle is over;
work with a special algorithm that allocates votes (you vote with your pooled LLM);
Representatives can vote on the Prime Minister and Ministers;
they can fire the Prime Minister or Ministers.
Basic legislative process
Congresspeople can propose laws;
They can vote for these laws with the LLM they had been voted in during the elections (the popular political power) + their LLM;
Laws can be accepted or rejected by the Assembly; and
Accepted Laws are written into the Blockchain and shown on the front end.
Basic Public Veto (direct democracy)
Citizens can propose the (binding, unlike with petitions) motion for the removal of a Law;
they can vote for it, one citizen, one vote; and
the Veto Proposal (referendum) stays open until 50 percent plus one citizen vote yea or nay.
Output
We will be able to run Liberland on-chain.
Smart Contracts
Deadline: Q1 2023
The final task in the Q4 to Q1 scope is to prepare the Smart Contract pallet. This pallet will enable others to write and run smart contracts, enabling functionality akin to Ethereum or BSC - DEXes and DAPPs. We do not expect this to be finished before the end of Q4, but significant work should already be done by then.
Deadline: The end of Q1 2023.
Subprojects
Prepare the Pallet
Take a similar pallet from Polkadot or another open-source. ;
Make sure it works in our system.
Test it with a sample smart contract or smart contract.
Prepare a demonstration, and run it in a meeting with us.
Launch of public block explorer
Smart contracts require a blockchain explorer capable of monitoring the action;
Take the free software of a similar blockchain explorer, such as Etherscan, and clone it.
Make minimal changes so that it is barely usable.
It needs not to be perfect by the end of Q4 - this is a monumental task in scope!
Set up guidelines to write Smart Contracts on Liberland
Please copy a similar guideline from the source material.
Make a Wiki explaining how it works.
Citizenship NFT
This will be the first Smart Contract we create on our new pallet. The purpose will be to represent the citizenship of every citizen.
The citizenship token will contain
a picture of the citizenship ID;
link to the owner's Liberland account (this will be the holder of that account, a citizen will be for the system this token!)
the number of LLM staked into the citizenship;
the history of this particular citizenship token, i.e. who was the previous holder and holders of this NFT, creating a potentially "collectable" NFT.
Output
We will be able to build smart contracts on our chain, which will create attractivity and use cases, enabling us to take our governance to the next level. We will be able to set up more government processes as smart contracts. We will provide every citizen with their tokenised citizenship right in their wallet.
Current Development Status
About twelve full months of development were spent on the project by various developers outside of the current team.
The current node implementation of Liberland’s blockchain has started, and we have an early beta version that you can find and download here: https://github.com/liberland/liberland_node

