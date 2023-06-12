# White Paper Liberland Blockchain

## Abstract 
Liberland is a country founded in 2015 on a terra nullius between Croatia and Serbia, with its founders being enthusiasts of blockchain and liberty. The goal of the Liberland Blockchain is to provide all e-government services to its citizens via a substrate-based blockchain system, with governance as its first use case. The Liberland Blockchain is designed as a layer 1 public blockchain, governed by the holders of its native tokens, the Liberland Dollar (LLD) and Liberland Merit (LLM). The system also supports Non-Fungible Tokens (NFTs) representing land and other assets, and implements a decentralized identity solution. In future, we will support an online judiciary system, enabling non-smart but self-executing contracts on the blockchain with the judiciary as an oracle. The judiciary will also enable features like account recovery and recourse against fraud and theft.

## System Overview
Liberland Blockchain is a layer 1 public blockchain owned by holders of LLD, but governed by the holders of LLM. The codebase is a fork of Substrate/Polkadot, and the license is MIT, the same as Bitcoin. Liberland does not claim ownership of the blockchain or related materials. The blockchain allows permissionless usage of tokens and coins as a store of value or medium of exchange. Advanced functionalities critical to the project's future are permissioned. DeFi projects on the Liberland chain are not permissioned unless designed by third-party developers on a per-project basis.

## Liberland Blockchain Design
### Public Blockchain
The Liberland Blockchain is a fork of the Substrate/Polkadot code base, licensed under MIT, similar to Bitcoin. It supports permissionless transactions for store of value and medium of exchange purposes, with advanced functionalities being permissioned for specific user types. 

### Permissioned Access
To accommodate state-level security requirements, certain blockchain functions are only available to users with elevated privileges. Elevated privileges are obtained by undergoing the currently centralized KYC procedure operated by the government of Liberland and fulfilling the requirements for becoming Citizens. 

The functions that require elevated privilege include, crucially, running validator nodes and participating in on-chain governance. This system reflects the principle of citizenship on the blockchain: States allow only citizens to operate their systems of critical infrastructure and typically, only citizens are given full political rights. As on-chain governance and politics are the same thing, the development of the system is, effectively, in the hands of the Citizens.

## On-Chain Assets
### On-Chain Assets and Division of Power
The blockchain contains two main assets: Liberland Dollar (LLD) and Liberland Merit (LLM). LLD serves as a medium of exchange and an instrument for maintaining network consensus and security. LLM represents a share in Liberland's state and nationhood, granting governance power with no possibility of separating this power from the token.

### Liberland Dollar (LLD)
The Liberland Dollar serves as the native token of the blockchain, fulfilling two main functions: 

a) a medium of exchange; and 

b) an instrument for maintaining network consensus and security. 

The LLD is minted according to rules inherited from Polkadot, including the "ideal staking ratio" mechanism. Its tokenomics reflect the  "automatic central bank" system proposed by the Nobel-prize winning economist Milton Friedman.

### Liberland Merit (LLM)
#### Overview
The Liberland Merit represents a share in the State and nationhood of Liberland. One's LLM supply can be converted to tokenized political power with which a Citizen can vote.

With a fixed maximum supply of 70,000,000 tokens and a release schedule of 10 percent per year, LLM is a deflatioinary token. LLM represent the territory of Liberland, where 10 LLM represent 1 m2 of the land. This is an ideal ownership, but LLM holders will be acknowledge when titles to the land are sold. 

LLM is a token set up using the Assets pallet. The initial price for LLM will be 1 USD, subject to change when trading begins.

#### Political pooling
Participation in the political process of Liberland is not solely contingent upon ownership of LLM or citizen status. A further requirement exists in the form of political pooling, or 'politpooling' of LLM. Politpooling is a long-term vesting which, mirroring the initial increase of token supply, only allows the unvesting of 10 percent of one's token supply per year. In additional, while unpooling, e.g. unvesting, one's politpooled LLM supply loses its political power. This gradual release of vested tokens can be likened to a form of social security, however, Liberland's social security is funded by the individual's past tax contributions, rather than a collective pool. The unpooling mechanism is structured to be triggered on a monthly basis, with 1/12th of 1/10th of the total vested supply becoming available each month.

The act of politpooling LLM is representative of voluntary tax contribution and a further display of dedication to the nation's prospective development. This mechanism is grounded in game theory, suggesting that significant personal investment, whether in the form of time or resources, typically results in a heightened sense of responsibility and commitment to the success of the invested project.

### NFTs
Native NFTs are used to represent land in both physical Liberland and the metaverse. These NFTs are integral to the land registry dApp, which tracks registered property. Additionally, a range of soulbound NFTs will be used in future stages of the project to represent Citizenship and various government functions, enabling Liberland to implement transition of power through smart contracts.
In future iterations, the project will tokenise everything in that metaverse and real-world Liberland. Selling and purchases will be facilitated through NFTs, representing “deeds of ownership” to the real-life objects. Where there is a dispute, the Judge needs only to look on-chain who owns the NFT about that object.

### Contract-based (3rd party) tokens
The Chain will exhibit comprehensive compatibility with Smart Contracts, as it operates on a derivative of the Polkadot Virtual Machine. This functionality empowers both our internal team and external developers to establish their decentralized architectures. We foresee the emergence of a robust Decentralized Finance (DeFi) ecosystem on our chain, akin to the thriving DeFi environments observed on other Rust-based chains like Polkadot, Kusama, and Solana.

## Frontend
The user-facing component will encompass an array of interfaces, crafted with the intention of enabling Liberland's citizens to directly engage with their governance structures. This assembly of user interfaces will encompass but will not be confined to the subsequent sub-domains:

1. A Wallet Interface: A streamlined portal for managing digital assets.
2. Validator Interface: A conduit for interactions with validators, the custodians of blockchain integrity.
3. Political Interface: A dedicated space for electoral processes, candidacy declaration, and legislative drafting.
4. Government Registers Interface: An access point for government-related services and registers.
5. Internal Government Interface: Exclusive interfaces for government officials to interact with the blockchain and conduct administrative duties.
6. Treasury Interface: A bespoke platform for managing Liberland's financial reserves.

Supplementing these, a collection of front-ends will be developed to facilitate the interaction between the blockchain and the metaverse, thereby enhancing the synergy between the digital and physical realms of Liberland.

## Governance
### Referendum
#### Validation of Proposals
The Referendum serves as a core instrument for decision-making within the political architecture of Liberland, facilitating citizens in the evaluation of laws, regulations, and assorted political propositions. The fulcrum of both on-chain governance and the political milieu of Liberland is the Referendum. Within the Liberland context, all laws necessitate the passage through the Referendum's direct democratic process for validation.

The functioning of the Referendum is predicated on a system evolved from Polkadot, integrating an anti-populist safeguard that escalates the voting threshold in proportion to declining voter participation. The voting requisite, i.e., the count of tokens required for the ratification of a proposal, rises in conjunction with declining turnover. Consequently, this system safeguards against the Referendum bypassing the will of the silent majority, irrespective of their voting inactivity. This mechanism is deactivated for Referenda initiated by the Congress, given its democratic election.

#### Revocation of Proposals
Furthermore, a specialized variant of the Referendum is operational for the retraction of legal validation from laws and other measures ratified by the Referendum. This is termed the Public Veto. An exclusive feature within the chain's toolkit, the voting for a Public Veto is conducted on a one-citizen-one-vote basis. This mechanism serves as a precautionary measure against potential plutocratic commandeering of the system.

### Congress
#### Overview
The Congress operates as the representative entity within Liberland, tasked with

a) initiating rational Referenda that are exempt from the anti-populist voting requisites;

b) the appointment and removal of the Prime Minister (Executive), and

c) participating in referenda on behalf of constituents who delegate their voting rights.

#### Elections
The Congress is elected through a voting process involving all citizens, utilizing their tokens. Elections occur on a quarterly basis. Inactive citizens in the current elections are not recorded as such; their vote in the last participated election is considered valid.

#### Delegation
The concept of Delegation gains relevance for citizens who perceive their representative as more knowledgeable or more capable of in-depth study of the subject matter, while they attend to their personal affairs. Delegation can be granted or rescinded at any point in time. This introduces a novel form of tangible representation into representative democracy, given that most states do not permit any form of post-election influence over the actions of the representative, barring the one-time vote cast every few years.

#### Technical
The Congress is a derivative of the Substrate Council, retaining the original structure of the source. Consequently, the Congress also inherits the Council's system of the Prime Member. Within the Congress, the member amassing the maximum votes per voting period ascends to the role of the Prime Member. Their vote in any Congress deliberation is automatically adopted by all inactive or non-voting members of the Congress.

### Executive
The Executive oversees Liberland's daily affairs, led by the Cabinet, a fork of the on-chain Collective pallet. The Cabinet comprises one Prime Minister and four Ministers, with all other Executive functions falling under a Minister. The Executive includes Offices using the original Offices Pallet, assigning an address to powers designated to specific Offices by law.

The Cabinet's primary power is enacting regulations within the legal framework. Lower Offices govern and regulate within the law and Cabinet regulations, with their heads nominated and dismissed by the Cabinet or a specific Minister.

Initially, the Provisional Government of Liberland serves as the Cabinet, with the President as the Prime Member. Upon the establishment of a community in Liberland or a Liberland-governed territory, the Prime Minister assumes the Prime Member role and selects Ministers. Congress appoints and dismisses the Prime Minister and Ministers. Dismissing a Prime Minister does not necessitate the resignation of all Ministers.

The system algorithmically manages the transition of power, with officials holding fixed terms of office, typically 20 Election Terms (5 years), renewable once.

### E-Governance
The executive manages citizen-facing e-government services, with all communication between citizens and the government occurring through online tools. The system includes wallet interfaces, validator interfaces, political interfaces for elections and legislative drafting, interfaces for government registers and other services, internal government front ends for officials, and the treasury interface.

### Senate & Treasury
The Treasury, a fork of Polkadot's Treasury, comprises two separate treasuries: one for LLD and one for LLM. The LLD Treasury operates identically to the Polkadot Treasury, while the LLM Treasury is managed by the Senate. The Senate, based on the Council/Collective pallet, is responsible for maintaining Treasury keys and vetoing Laws and Regulations. Laws are vetoed during the referendum phase, and lower Regulations can be vetoed at any time. All LLM Treasury proposals require Senate confirmation for execution. 

The Senate is the "House of Lords" of Liberland, and its members are appointed for life. They have, however, only control power, neither legislative nor executive powers.

### President & Vice-Presidents
The President, chosen by the Senators, serves as the head of state and represents Liberland internationally. The President's actions necessitate confirmation by at least one Vice-President. The President's main power is being the Prime Member of the Senate Collective, meaning abstaining Senators' votes automatically align with the President's. This only applies when a Vice-President confirms the vote; otherwise, abstaining Senators' votes are considered uncast.

Additionally, the President possesses the authority to appoint Executive functionaries and Judges when the Judiciary is established. The President's power in this capacity is real, enabling them to reject an appointment. However, this power is subject to the same checks as the Prime Member vote, requiring the countersignature of a Vice-President.


## Future Outlook
### Judiciary
The on-chain judiciary is in active development, aiming to combine trust-based elements, such as professional judges and process law, with blockchain-native solutions, inspired by Kleros, the Aragon Court, and Ulex.

### E-Identity
Liberland aims to present a decentralized identity solution, a fork of the Identity pallet using NFTs of the Uniques pallet. Identification is accomplished by registrars with KnownGood status for issuing particular forms of identity. All identity-related data on-chain is stored in an encrypted forma

## Development and Contact Information
The Liberland Blockchain is being developed by a team led by Dorian Stern-Vukotic, with Kacper Zuk as Senior Developer. The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company. The intended languages of development are Rust for the backend and Javascript/Angular for the frontend.

The Liberland team can be reached via email at justice@liberland.org, and the project's code repository can be found at https://github.com/liberland/liberland_substrate.
