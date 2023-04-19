# White Paper Liberland Blockchain

## Abstract 
Liberland is a country founded in 2015 on a terra nullius between Croatia and Serbia, with its founders being enthusiasts of blockchain and liberty. The goal is to provide all e-government services to its citizens via a substrate-based blockchain system, with governance as its first use case. The Liberland Blockchain is designed as a layer 1 public blockchain, governed by the holders of its native tokens, the Liberland Dollar (LLD) and Liberland Merit (LLM). The system also supports Non-Fungible Tokens (NFTs) representing land and other assets, and implements a decentralized identity solution.

## System Overview
Liberland Blockchain is a layer 1 public blockchain owned by coin and token holders. The blockchain is funded and supported by Liberland, providing the first set of use cases. The codebase is a fork of Substrate/Polkadot, and the license is MIT, the same as Bitcoin. Liberland does not claim ownership of the blockchain or related materials.

The blockchain allows permissionless usage of tokens and coins as a store of value or medium of exchange. Advanced functionalities critical to the project's future are permissioned. DeFi projects on the Liberland chain are not permissioned unless designed by third-party developers on a per-project basis.

## Liberland Blockchain Design
### Public Blockchain
The Liberland Blockchain is a fork of the Substrate/Polkadot code base, licensed under MIT, similar to Bitcoin. It is not owned by Liberland, but rather by its token holders. It supports permissionless transactions for store of value and medium of exchange purposes, with advanced functionalities being permissioned for specific user types.

### Permissioned Access
To accommodate state-level security requirements, certain blockchain functions require permissioned access for Citizens and E-Residents. This includes running validator nodes and participating in on-chain governance. Access is granted after completing a Know Your Customer (KYC) process and holding a vested amount of LLM tokens.

## On-Chain Assets
### On-Chain Assets and Division of Power
The blockchain contains two main assets: Liberland Dollar (LLD) and Liberland Merit (LLM). LLD serves as a medium of exchange and an instrument for maintaining network consensus and security. LLM represents a share in Liberland's state and nationhood, granting governance power with no possibility of separating this power from the token.

### Liberland Dollar (LLD)
The Liberland Dollar serves as the native token of the blockchain, fulfilling two main functions: a) a medium of exchange; and b) an instrument for maintaining network consensus and security. The LLD is minted according to rules inherited from Polkadot, including the "ideal staking ratio" mechanism.

### Liberland Merit (LLM)
The Liberland Merit represents a share in the State and nationhood of Liberland. It is the governance token, legally similar to shares in joint ownership. Governance power is tied to the LLM, with a fixed maximum supply of 70,000,000 tokens. The initial price for LLM will be 1 USD, subject to change when trading begins.

### NFTs
Native NFTs are used to represent land in both physical Liberland and the metaverse. These NFTs are integral to the land registry dApp, which tracks registered property. Additionally, a range of soulbound NFTs are used to represent Citizenship and various government functions, enabling Liberland to implement transition of power through smart contracts.

## Frontend
Citizens and E-Residents interact with the government through a frontend system, which includes a wallet interface, interfaces for validators, political interface, government registers and services interface, internal government frontend, and a treasury interface.

## Governance
### Referendum
The Referendum is the primary decision-making process in Liberland's political system, allowing citizens to decide on Laws, Regulations, and other political motions. All Laws in Liberland must pass through the direct democracy of the Referendum to gain legal force. Citizens can also propose Referenda.

### Congress
Congress serves as the representative body in Liberland, responsible for proposing rational Referenda, nominating and dismissing the Prime Minister (Executive), voting in referenda on behalf of citizens who delegate their vote, and deciding budgetary matters. Congress is forked from Substrate Council.

### Executive
The Executive, consisting of one Prime Minister and four other Ministers, enacts regulations within the framework of the law and governs the country in day-to-day matters.

### E-Governance
The executive manages citizen-facing e-government services, with all communication between citizens and the government occurring through online tools. The system includes wallet interfaces, validator interfaces, political interfaces for elections and legislative drafting, interfaces for government registers and other services, internal government front ends for officials, and the treasury interface.

### E-Identity
Liberland presents a decentralized identity solution, a fork of the Identity pallet using NFTs of the Uniques pallet. Identification is accomplished by registrars with KnownGood status for issuing particular forms of identity. All identity-related data on-chain is stored in an encrypted format.

### Senate & Treasury
The Treasury is a fork of Polkadot's Treasury, and the Senate is a body based on the Council/Collective pallet, responsible for holding the Treasury keys and vetoing Laws and Regulations.

### President & Vice-Presidents
The President, selected by the Senators, serves as the head of state and represents Liberland internationally. The President's actions require confirmation by at least one Vice-President.

### Judiciary
The on-chain judiciary is in active development, aiming to combine trust-based elements, such as professional judges and process law, with blockchain-native solutions, inspired by Kleros, the Aragon Court, and Ulex.

## Development and Contact Information
The Liberland Blockchain is being developed by a team led by Dorian Stern-Vukotic, with Kacper Zuk as Senior Developer. The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company. The intended languages of development are Rust for the backend and Javascript/Angular for the frontend.

The Liberland team can be reached via email at justice@liberland.org, and the project's code repositories can be found at https://github.com/liberland/liberland_substrate and https://github.com/liberland/docs/blob/master/Blockchain%20Strategy.md.### 
