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
The Liberland Merit represents a share in the State and nationhood of Liberland. It is the governance token, legally similar to shares in joint ownership. Governance power is tied to the LLM, with a fixed maximum supply of 70,000,000 tokens. The initial price for LLM will be 1 USD, subject to change when trading begins.

### NFTs
Native NFTs are used to represent land in both physical Liberland and the metaverse. These NFTs are integral to the land registry dApp, which tracks registered property. Additionally, a range of soulbound NFTs are used to represent Citizenship and various government functions, enabling Liberland to implement transition of power through smart contracts.

## Frontend
Citizens and E-Residents interact with the government through a frontend system, which includes a wallet interface, interfaces for validators, political interface, government registers and services interface, internal government frontend, and a treasury interface.

## Governance
### Referendum
The Referendum serves as the primary decision-making mechanism within Liberland's political system, enabling citizens to determine the validity of Laws, Regulations, and other political propositions. All Laws must undergo the Referendum's direct democratic process to attain legal standing. The Referendum operates based on a system derived from Polkadot, incorporating an anti-populism measure that increases the voting threshold as voter engagement decreases.

Citizens can propose Referenda, which are subject to the anti-populism measure. Congress, a democratically elected entity, can also initiate referenda with a 50% plus one vote requirement, reflecting its presumed legitimacy and competence.

### Congress
Congress functions as Liberland's representative body, responsible for proposing rational Referenda, appointing and dismissing the Prime Minister (Executive), voting in referenda on behalf of citizens who delegate their vote, and deciding on budgetary matters. Congress is a fork of the Substrate Council, and the most influential member becomes the Prime Member, whose vote is followed by non-voting Congress members.

Key powers include:
- Proposing Referenda with a 50% plus one vote requirement, without anti-populism measures;
- Being delegated votes in Referenda by citizens who trust their representatives to vote on their behalf.

The Delegation becomes important for citizens who feel that their representative knows more about the subject matter than they do or can be expected to spend time studying it in depth, while they are busy with their own lives. Delegation can be given at any time and also taken back at any time. This represents a unique introduction of real representation into representative democracy, as currently, most states don't allow any voter ex-post control on representative behavior, besides a one-time vote once in several years.

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
