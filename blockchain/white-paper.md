# White Paper Liberland Blockchain

## Introduction 
Liberland is a country established in 2015, on a no man’s land (terra nullius) between Croatia and Serbia (www.liberland.org). Liberland’s founders are blockchain and liberty enthusiasts. Liberland’s State project could be summarised by two concepts: Minimal state and distributive governance. 
Liberland's aim is to make all e-government services available to our citizens using our substrate-based blockchain (https://github.com/liberland/liberland).
Liberland governance shall become the first use case for our system

## The Scope:
Liberland sponsored the building of a Level 1 (L1) Substrate based blockchain. Based on Polkadot, the consensus mechanism will be a version of Delegated Proof of Stake. This project is not a parachain of Polkadot but a stand-alone blockchain.

## Permissionless Core
Liberland Blockchain is a public blockchain owned by the holders of coins and tokens. Liberland funds and supports its development, and Liberland will provide the first use case or set of use cases. The licence is MIT, the same licence that Bitcoin uses, and Liberland is in no way the owner of the blockchain or the related materials.

Everyone can permissionlessly use the tokens and coins of our blockchain as a store of value or a medium of exchange. Only the advanced functionalities critical for the project’s future are permissioned.
DeFi projects on our chain will not be permissioned unless otherwise designed by the 3rd party developers on a per-project basis.

## Permissioned Access
Liberland is a State, and it needs to maintain its security in ways that normal blockchains do not require. To accommodate those needs, certain blockchain functions require permissioned access for special types of users: Citizens and E-Residents. 
To become either, one has to go through a KYC process. In addition, the access requires the purchase and a vested holding of a certain amount of our Token (LLM); see below. The main areas which require permissioned access are:
a) running a Validator node; and  
b) on-chain governance.  
Access to these functionalities requires one to become a Citizen in Liberland. This is a substantial commitment. Liberland assumes a level of loyalty to the project beyond a casual investor in one who is willing to undertake this commitment.

## On-Chain Assets
### Liberland Dollar (LLD)
Liberland Dollar is the ledger native token of the blockchain. Its main functions are:
a) a medium of exchange; and  
b) an instrument to maintain network consensus and network security.   

The LLD will be minted according to rules inherited from Polkadot. This includes Polkadot's [“ideal staking ratio”](https://wiki.polkadot.network/docs/learn-staking-advanced) mechanism. As such, there is no hard limit on the number of LLD in existence.

### Liberland Merit (LLM)
Liberland Merit (LLM) is the governance token representing a share in the State and nationhood of Liberland. LLM is not a security created with the expectation of revenue; instead, it is legally close to shares in joint ownership, like in case of housing cooperatives; the LLM represents one's share in their country. The governance power is connected to the LLM, and there is no possibility of other governance and no separating of this power from the token. 

Inspired by Bitcoin (BTC), the LLM has a fixed maximum supply of 70 000 000 tokens. With the expected losses due to lost addresses etc., this token will, in time, become deflationary. The initial price for LLM will be 1 USD, but this will change when the LLM begins to trade on the market.

## NFTs
The blockchain uses a set of native NFTs representing land in the physical Liberland and in the metaverse. This is relevant for the land registry dApp. This dApp is being developed track all property that someone might want to register, as NFTs. This primarily concerns the land in the physical Liberland and in the metaverse, since land and real estate have a long history of registered titles.

Other use case for NFTs is an extensive pallet of soulbound NFTs which serve as tokens representing Citizenship and the various functions within the government. In this way, Liberland is the first country to implement transition of power by smart contract.

## Frontend
The front end is the means by which Citizens and E-Residents interact with their government. It includes and is not limited to the following sub-domains:  
a) a wallet interface;  
b) an interface with validators;  
c) political interface, i.e. for the elections, candidates, legislative drafting;  
d) an interface for government registers and other services;  
e) the internal government front ends for the officials to work in & access the chain;  
f) the treasury interface.   

## Liberland Politics:  
### Citizenship
Citizenship and E-Residency user statuses and roles exist on-chain and are entities of the Identity Pallet taken from Substrate and adjusted.

### Referendum
The primary decision-making process in the Liberland political system rests with the Referendum. The Referendum allows all citizens to make decisions regarding the future of the country but, most importantly, to decide on Laws, other Regulations, and other motions in Liberland’s politics. All Laws in Liberland must pass the direct democracy of the Referendum to gain legal force. Citizens can also propose Referenda. 

Referendum uses a voting requirement system inherited from the Tally system of Polkadot. This serves as a populism-preventing measure - the lower the turnout, the higher the tally needed to adopt a proposal. The voting requirement system applies only on citizen-originated Referenda. Congress (see below) is democratically elected and, therefore, there is a presumption of greater legitimacy of its proposals.

### Congress
Congress is forked from the Substrate Council and serves as the representative body in Liberland. There are four main functions: 
 * to propose rational Referenda,  
 * to nominate and dismiss the Prime Minister (Executive), 
 * to vote in referenda instead of the citizens who opt to delegate the vote to their Member of Congress, and  
 * to decide budgetary matters.  

## Executive
The Executive is the government of Liberland. The Cabinet is composed of one Prime Minister and only four other Ministers. The rest of the hierarchy will be placed under one of the Cabinet members.

On-chain, the Executive enacts regulations within the framework of the law and governs the country in day-to-day matters. The executive also manages the citizen-facing e-government. All communication between citizens and the government will happen by means of online tools.

## Senate & the Treasury
* One of the standing values that Liberland has is that all taxes are paid voluntarily by the citizens of Liberland. We fork Polkadot’s Treasury and implement it as a multi-signature wallet held by the on-chain politicians of Liberland. Like Polkadot’s Treasury, we will handle funding proposals, mainly initiated by the Executive and Congress. 
* The Senate is composed of the biggest investors in our project. The Senators can veto Laws and Regulations. They hold the Treasury keys, and no spending may commence without their direct action. 
* They will likely set up a system for day-to-day checks on routine spending, handled by the President.
* Their second power will be the ability to cancel malicious referenda regarding laws and also sub-legal regulations they see as impediments to Liberland’s prosperity.

## Judiciary
* The project will entail a fully working justice system inspired by Kleros, the Aragon Court, and Ulex. The development of this will commence at a later stage of the project.
* The pre-alpha version of the white paper for this sub-system can be found here: Liberland dispute resolution system for the grant application

## Citizen-facing Government Services:
### Identity
* The blockchain will contain encrypted information regarding the citizens' data, accessible only to the citizens and with their permission. One’s ID exists in 
* Liberland to prove one’s identity where the Citizen or E-Resident wants to identify themselves, i.e., partake in a service. Whether or not this identification 
* will take place remains in the hands of the user. 
* Having the identity run on a blockchain, with immutability guaranteed by the network consensus, drastically lowers the danger of identity theft. Liberland ID will be useful far beyond the limits of Liberland itself - those who have it can log into third-party services with the confidence only blockchain security provides.
* We will later set up a DAO or DAOs, which will enable “decentralized identification” concerning information people want others to know about. There will be networks working between verifiers and the verified. Qualified verifiers, like universities, will be able to encode information, like a university degree, cryptographically and put it in the hands of the data subject. This information will only be accessible to the user and those whom the user wants it to see.
* We hope to create a new standard of information security, building on the current standards like the GDPR, but streamlining them, on the one hand, to remove needless administration and make them even more secure and safe on the other. The twinning of the blockchain (for immutability) with one-way cryptography (for safety) creates a combination of security, veracity and expedience unseen in current States.

### Registers
* We will build NFT-fuelled registers of several kinds of entities, starting with virtual real estate for our Metaverse and the real world.
* We will first set up a Liberland-registered Companies register, where principals can keep the information public and up to date for their convenience. 
* Secondly, we will create NFT-fueled Land and Immovable Property registers for the Metaverse and, later, the real-life Liberland.
* Lastly, we will set up DAOs registering other assets, like movable property or even securities. We will rely heavily on third parties, bringing in the best available technologies tested on different chains and projects.
## Annexe
### Team Members
Dorian Stern-Vukotic, Frontend developer
Filip Kalebo, Rust substrate Team leader and developer; Github: https://github.com/flipchan;
As a backup and to provide a second opinion, we have the possibility of asking a second experienced team of developers who has a great track record in the development of crypto-related projects. Please see their earlier work here:
https://www.mantleblockchain.com/
https://www.masscrypto.io
https://www.hglobal.io
https://www.nftytoken.io

### Team’s Website
https://github.com/liberland/liberland

### Legal Structure
A Hong Kong-based Limited Liability Company; later a Liberland Company as the entity in charge.

#### For production:
Development Team at Rust Syndicate LLC, Tbilisi, Republic of Georgia.

#### Team
Team LinkedIn Profiles:
https://www.linkedin.com/in/djstern
https://se.linkedin.com/in/filip-k%C3%A4lebo-479314115
Team Code Repositories
https://github.com/liberland/liberland_backend
https://github.com/liberland/liberland_frontend
https://github.com/liberland/liberland_node
https://github.com/liberland/docs/blob/master/Blockchain%20Strategy.md

### Contact:
justice@liberland.org

### Intended Language of Development
Rust for the blockchain backend, Javascript / Angular for the Frontend.

The current node implementation of Liberland’s blockchain has started, and we have an early beta version that you can find and download here: https://github.com/liberland/liberland_node

