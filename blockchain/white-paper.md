# White Paper Liberland Blockchain

## Abstract 
Liberland is a country founded in 2015 on a terra nullius between Croatia and Serbia, with its founders being enthusiasts of blockchain and liberty. The goal is to provide all e-government services to its citizens via a substrate-based blockchain system, with governance as its first use case. The Liberland Blockchain is designed as a layer 1 public blockchain, governed by the holders of its native tokens, the Liberland Dollar (LLD) and Liberland Merit (LLM). The system also supports Non-Fungible Tokens (NFTs) representing land and other assets, and implements a decentralized identity solution.

## Introduction
Liberland's state project is centered around two principles: minimal state and distributive governance. By employing a substrate-based blockchain for e-government services, Liberland aims to create a transparent, secure, and efficient system for its citizens and e-residents.

## Liberland Blockchain Design
### 2.1 Public Blockchain
The Liberland Blockchain is a fork of the Substrate/Polkadot code base, licensed under MIT, similar to Bitcoin. It is not owned by Liberland, but rather by its token holders. It supports permissionless transactions for store of value and medium of exchange purposes, with advanced functionalities being permissioned for specific user types.

### 2.2 Permissioned Access
To accommodate state-level security requirements, certain blockchain functions require permissioned access for Citizens and E-Residents. This includes running validator nodes and participating in on-chain governance. Access is granted after completing a Know Your Customer (KYC) process and holding a vested amount of LLM tokens.

## On-Chain Assets
### 3.1 Liberland Dollar (LLD)
The LLD serves as a medium of exchange and a means to maintain network consensus and security. It will be minted according to rules inherited from Polkadot, with no hard limit on supply.

### 3.2 Liberland Merit (LLM)
The LLM is a governance token representing a share in Liberland's nationhood. It has a fixed maximum supply of 70 million tokens and its initial price will be 1 USD. LLM's value will change once it starts trading on the market.

## Non-Fungible Tokens (NFTs)
NFTs are used to represent land in both the physical Liberland and the metaverse, primarily for the land registry dApp. Additionally, NFTs represent Citizenship and various government functions, enabling Liberland to implement transition of power through smart contracts.

## Frontend
Citizens and E-Residents interact with the government through a frontend system, which includes a wallet interface, interfaces for validators, political interface, government registers and services interface, internal government frontend, and a treasury interface.

## Governance
### 6.1 Citizenship
Citizenship and E-Residency user statuses and roles are managed on-chain using the Identity Pallet forked from Substrate.

### 6.2 Referendum
Referendum serves as the primary decision-making process in Liberland, allowing all citizens to make decisions regarding the future of the country. It utilizes a voting requirement system inherited from Polkadot's Tally system.

### 6.3 Congress
Congress, forked from Substrate Council, serves as the representative body in Liberland, responsible for proposing rational referenda, nominating and dismissing the Prime Minister, voting in referenda, and deciding budgetary matters.

### 6.4 Executive
The Executive, consisting of one Prime Minister and four other Ministers, enacts regulations within the framework of the law and governs the country in day-to-day matters.

### 6.5 E-Governance
The Executive manages the citizen-facing e-government, with all communication between citizens and the government taking place through online tools.

### 6.6 E-Identity
Liberland's decentralized identity solution is a fork of the Identity pallet using NFTs of the Uniques pallet, with identification provided by registrars with KnownGood status.

### 6.7 Senate & Treasury
The Treasury is a fork of Polkadot's Treasury, and the Senate is a body based on the Council/Collective pallet, responsible for holding the Treasury keys and vetoing Laws and Regulations.

### 6.8 President & Vice-Presidents
The President, selected by the Senators, serves as the head of state and represents Liberland internationally. The President's actions require confirmation by at least one Vice-President.

### 6.9 Judiciary
The on-chain judiciary is in active development, aiming to combine trust-based elements, such as professional judges and process law, with blockchain-native solutions, inspired by Kleros, the Aragon Court, and Ulex.

## Development and Contact Information
The Liberland Blockchain is being developed by a team led by Dorian Stern-Vukotic, with Kacper Zuk as Senior Developer. The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company. The intended languages of development are Rust for the backend and Javascript/Angular for the frontend.

The Liberland team can be reached via email at justice@liberland.org, and the project's code repositories can be found at https://github.com/liberland/liberland_substrate and https://github.com/liberland/docs/blob/master/Blockchain%20Strategy.md.### 
