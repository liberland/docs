# White Paper Liberland Blockchain

## Introduction 
Liberland is a country established in 2015, on a no man’s land (terra nullius) between Croatia and Serbia (www.liberland.org). Liberland’s founders are blockchain and liberty enthusiasts. Liberland’s State project could be summarised by two concepts: Minimal state and distributive governance.   

Liberland's aim is to make all e-government services available to our citizens using our substrate-based blockchain (https://github.com/liberland/liberland).
Liberland governance shall become the first use case for our system  

## The Scope:

### Public Blockchain
Liberland Blockchain is a layer 1 public blockchain owned by the holders of coins and tokens. Liberland funds and supports its development, and Liberland will provide the first use case or set of use cases. The code base is a fork of Substrate/Polkadot. The licence is MIT, the same licence that Bitcoin uses, and Liberland is in no way the owner of the blockchain or the related materials. 

Everyone can permissionlessly use the tokens and coins of our blockchain as a store of value or a medium of exchange. Only the advanced functionalities critical for the project’s future are permissioned. DeFi projects on the Liberland chain will not be permissioned unless otherwise designed by the 3rd party developers on a per-project basis.  

### Permissioned Access
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

## Legislative:  
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
### Liberland Government
The Executive is the government of Liberland. The Cabinet is composed of one Prime Minister who is the head of Liberland's government, and only four other Ministers. The rest of the hierarchy will be placed under one of the Cabinet members.
On-chain, the Executive enacts regulations within the framework of the law and governs the country in day-to-day matters. 

### E-Governance
The executive also manages the citizen-facing e-government. All communication between citizens and the government takes place by means of online tools.

## E-Identity
Liberland presents a decentralized identity solution, a fork of the Identity pallet using NFTs of the Uniques pallet. The identification is accomplished by registrars who have a KnownGood status for issuing a particular form of identity. The basic identity is the connection between one's real name and crypto address. All identity related data on-chain is stored in an encrypted format. Other forms of identity may include professional credentials, experience, health record, certifications, etc.
*This solution is currently under development.*

## Senate & the Treasury
### The Treasury
The Treasury is a fork of Polkadot's Treasury. There will be at least two Treasuries, one for LLD and one for LLM, with others possible for implementation if there are more key tokens.

### The Senate
The Senate is a body based on the Council/Collective pallet composed of major supporters in the country and its project of achieving recognition. Senators can veto Laws and Regulations. The Senate holds the Treasury keys, and no spending may commence without their direct action.

### President & Vice-Presidents
The Senators select from their ranks the President who is the head of state of Liberland. The President selects two Senators to be the vice-president. The President represents Liberland internationally.

The President also serves as the Prime Member of the Senate. In accordance to Substrate rules, Senators who don't vote in on a particular proposal will automatically vote alongside with the President. The President's actions are all multisignature calls and at least one Vice-President has to confirm them in order to be written on-chain.

## Judiciary
The on-chain judiciary is currently in active development. It aims to combine the trust-based elements one expects to see in courtroom, such as professional judges and process law, with blockchain-native solutions. The main inspirations are Kleros, the Aragon Court, and Ulex. 

## Annexe  
### Team Members  
Dorian Stern-Vukotic, Tech Lead  
Kacper Zuk from Neti, Senior Developer  

### Team’s Website
https://github.com/liberland/liberland  

### Legal Structure
The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company.  

### Team
Team LinkedIn Profiles:  
https://www.linkedin.com/in/djstern  
Team Code Repositories  
https://github.com/liberland/liberland_substrate  
https://github.com/liberland/docs/blob/master/Blockchain%20Strategy.md  

### Contact:
justice@liberland.org

### Intended Language of Development
Rust for the blockchain backend, Javascript / Angular for the Frontend.

The current node implementation of Liberland’s blockchain has started, and we have an early beta version that you can find and download here: https://github.com/liberland/liberland_node

