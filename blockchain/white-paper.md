# White Paper Liberland Blockchain

## Abstract 

Liberland is a country founded in 2015 on a terra nullius between Croatia and Serbia, with its founders being enthusiasts of blockchain and liberty. The goal of the Liberland Blockchain is to provide all e-government services to its citizens via a substrate-based blockchain system, with governance as its first use case. The Liberland Blockchain is designed as a layer 1 public blockchain, governed by the holders of its native tokens, the Liberland Dollar (LLD) and Liberland Merit (LLM). The system also supports Non-Fungible Tokens (NFTs) representing land and other assets, and implements a decentralized identity solution. In future, we will support an online judiciary system, enabling non-smart but self-executing contracts on the blockchain with the judiciary as an oracle. The judiciary will also enable features like account recovery and recourse against fraud and theft.

## System Overview

Liberland Blockchain is a layer 1 public blockchain owned by holders of LLD, but governed by the holders of LLM. The codebase is a fork of Substrate/Polkadot, and the license is MIT, the same as Bitcoin. Liberland does not claim ownership of the blockchain or related materials. The blockchain allows permissionless usage of tokens and coins as a store of value or medium of exchange. Advanced functionalities critical to the project's future are permissioned. DeFi projects on the Liberland chain are not permissioned unless designed by third-party developers on a per-project basis.

## Liberland Blockchain Design

### Public Blockchain
The Liberland Blockchain is a fork of the Parity Substrate/Polkadot code base. The code base is licensed under MIT, similar to Bitcoin. It supports permissionless transactions for store of value and medium of exchange purposes, with advanced functionalities being permissioned for specific user types. 

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

#### Political pooling (PolitiPooling)

Participation in the political process of Liberland is not solely contingent upon ownership of LLM or citizen status. A further requirement exists in the form of political pooling, or 'PolitiPooling' of LLM. PolitiPooling is a long-term vesting which, mirroring the initial increase of token supply, only allows the unvesting of 10 percent of one's token supply per year. In additional, while unpooling, e.g. unvesting, one's PolitiPooled LLM supply loses its political power. This gradual release of vested tokens can be likened to a form of social security, however, Liberland's social security is funded by the individual's past tax contributions, rather than a collective pool. The unpooling mechanism is structured to be triggered on a monthly basis, with 1/12th of 1/10th of the total vested supply becoming available each month.

The act of PolitiPooling LLM is representative of voluntary tax contribution and a further display of dedication to the nation's prospective development. This mechanism is grounded in game theory, suggesting that significant personal investment, whether in the form of time or resources, typically results in a heightened sense of responsibility and commitment to the success of the invested project.

### NFTs

Native NFTs are used to represent land in both physical Liberland and the metaverse. These NFTs are integral to the land registry dApp, which tracks registered property. Additionally, a range of soulbound NFTs will be used in future stages of the project to represent Citizenship and various government functions, enabling Liberland to implement transition of power through smart contracts.
In future iterations, the project will tokenise everything in that metaverse and real-world Liberland. Selling and purchases will be facilitated through NFTs, representing “deeds of ownership” to the real-life objects. Where there is a dispute, the Judge needs only to look on-chain who owns the NFT about that object.

### Contract-based (3rd party) tokens

The Chain will exhibit comprehensive compatibility with Smart Contracts, as it operates on a derivative of the Polkadot Virtual Machine. This functionality empowers both our internal team and external developers to establish their decentralized architectures. We foresee the emergence of a robust Decentralized Finance (DeFi) ecosystem on our chain, akin to the thriving DeFi environments observed on other Rust-based chains like Polkadot, Kusama, and Solana.

## Frontend

The user-facing component will encompass an array of interfaces, crafted with the intention of enabling Liberland's citizens to directly engage with their governance structures. This assembly of user interfaces will encompass but will not be confined to the subsequent sub-domains:

1. A Wallet Interface: A streamlined portal for managing digital assets.
2. Validator Interface: A conduit for interactions with Validators, the custodians of blockchain integrity.
3. Political Interface: A dedicated space for electoral processes, candidacy declaration, and legislative drafting.
4. Government Registers Interface: An access point for government-related services and registers.
5. Internal Government Interface: Exclusive interfaces for government officials to interact with the blockchain and conduct administrative duties.
6. Treasury Interface: A bespoke platform for managing Liberland's financial reserves.

Supplementing these, a collection of front-ends will be developed to facilitate the interaction between the blockchain and the metaverse, thereby enhancing the synergy between the digital and physical realms of Liberland.

## Governance: Legislative

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

#### Prime Member

The Congress is a derivative of the Substrate Council, retaining the original structure of the source. Consequently, the Congress also inherits the Council's system of the Prime Member. Within the Congress, the member amassing the maximum votes per voting period ascends to the role of the Prime Member. Their vote in any Congress deliberation is automatically adopted by all inactive or non-voting members of the Congress.

## Governance: Executive

### Role

The Executive carries out the routine operations of the nation. It also executes laws and measures ratified by the Referendum and Congress, thus translating them into practice.

### Cabinet

The Executive operates in a hierarchical manner, spearheaded by the Cabinet, which technically is another offshoot of the on-chain Collective pallet. The Cabinet consists of one Prime Minister and four Ministers. All other executive functions fall under the purview of either one of the Cabinet members or the Cabinet as a whole.

The primary authority of the Cabinet lies in enforcing regulations within the legal framework. Subordinate Offices administer and regulate within the confines of the law and Cabinet regulations, with their heads appointed and dismissed by the Cabinet or a specific Minister.

### E-Governance

All the offices under the Cabinet constitute the E-Governance of Liberland on the blockchain. They are expected to have interfaces that facilitate seamless communication and service provision for the citizens of Liberland.

The initial such offices are the Company Registry and Land Registry, which are currently operational on the chain in a pilot stage. They are expected to be succeeded by additional applications, aimed at fulfilling traditional state roles.

Furthermore, the E-Governance will feature an inward component, specifically, budget management. The state budgets will be maintained on the blockchain, ensuring complete transparency and oversight.

The e-governance system also encompasses wallet interfaces, validator interfaces, political interfaces for elections and will include such elements as legislative drafting, interfaces for government registers and other services, internal government front ends for officials, and the treasury interface.

### Current Phase: The Provisional Government

In the early stages, the Cabinet is served by the Provisional Government of Liberland, with the President acting as the Prime Member. The roles within the Cabinet are therefore allocated by the President. Upon the development of a community in Liberland or a territory governed by Liberland (when at least 65 percent of Citizens are onboarded and settlement is actively in progress), the Provisional Government will relinquish its power and the President will transition into the role of a primarily symbolic head of state.

## Treasury

One of the standing values that Liberland has is that all taxes are paid voluntarily by the citizens of Liberland. We fork Polkadot’s Treasury and implement it as a multi-signature wallet held by the on-chain politicians of Liberland. Like Polkadot’s Treasury, we will handle funding proposals, mainly initiated by the Executive and Congress. 

## Senate

### Overview

The Senate is tasked with the management of Treasury keys and the power to veto Laws and Regulations. Laws can be vetoed during the referendum phase, whereas lower-tier Regulations can be vetoed at any time. Proposals related to the LLM Treasury necessitate the Senate's approval for execution. The Senate serves as Liberland's "House of Lords", with members appointed for life. Their power is purely of control, devoid of legislative or executive capacities.

A notable attribute of Senatorship is the possession (restricted to dividends) of one percent of Liberland reserves and of the parent company developed for Liberland, namely Liberland Limited, based in Hong Kong. We are also willing to provide you with veto control over the finances invested in Liberland.

### Powers

The Senate, as a collective, is endowed with the following authorities:
1. Nullify any referendum regarding Laws prior to them acquiring legal force; if a Veto is enacted, the proposed law will not acquire legal force;
2. Act as the supreme authority in budgetary and expenditure matters, maintaining oversight over any outflows from the Liberland Treasury; the Senate can halt any spending they deem unjustified;
3. Revoke any Regulation, other than a Law, even post its legal enactment; and
4. Cast votes for the President of Liberland.

### Implementation

The Senate, similar to the Congress and Council, is also a derivative of the Council pallet from Polkadot. Initially, Senators will be designated by the President. Subsequently, a co-option system will be established, wherein existing Senators vote to induct new members. It is important to note that while Senators have the power to admit, they cannot dismiss, as Senatorship is a property title and as such is safeguarded from expropriation in accordance with Liberland's property protection principles.

## President & Vice-Presidents

The President, selected by the Senators, operates as the head of state and represents Liberland on the international stage. Any actions undertaken by the President require the validation of at least one Vice-President. The President's main authority is as the Prime Member of the Senate Collective, implying that votes of abstaining Senators automatically align with the President's. This holds true only when a Vice-President corroborates the vote; otherwise, the votes of abstaining Senators are deemed uncast.

Furthermore, the President is empowered to appoint Executive functionaries and Judges, upon establishment of the Judiciary. The President's authority in this capacity is significant, allowing them to reject an appointment. However, this power is subject to the same checks as the Prime Member vote, demanding the countersignature of a Vice-President.

## Future Outlook: Judiciary

### Overview

The on-chain judiciary is in active development, aiming to combine trust-based elements, such as professional judges and process law, with blockchain-native solutions, inspired by Kleros, the Aragon Court, and Ulex. The main mission is to conceive a blockchain-compatible solution that translates traditional dispute resolution and judiciary functionalities into the digital realm. Our vision includes a system that synergizes the virtues of centralized and decentralized models.

### Problem Description

#### Irreversibility: The Inflexibility of Blockchain Systems

A foundational trait of blockchain systems, originating from Bitcoin, is the principle of irreversibility. Once a transaction is executed, it cannot be undone. Here, intentions play a secondary role with the final action being recognized as the valid user input.

However, this level of accountability is often too demanding for many individuals. The common practice of associating human identities with addresses by third-party organizations is essentially a temporary fix, contradicting the core philosophy of blockchain. A single mistake can lead to catastrophic consequences, potentially resulting in the loss of millions without any inherent system recourse.

#### Absence of Authority: The Perilous Landscape of Cryptocurrency

The current cryptocurrency environment, teeming with scams and malicious actors, provides little protection against such threats. Redress against hackers and dishonest service providers typically happens outside the system, relying on national judiciaries and other external entities.

Cryptocurrency represents a risky environment balanced against the promise of opportunity. It is filled with disclaimers about using the service "as-is", and providers often disclaim liability for secondary damages caused by other users. As a result, victims often find themselves in a harsh situation, with few options for seeking justice.

Compounding the issue is the inherent system bias towards the savvy manipulator. With actions prioritized over intentions and the absence of an overseeing authority, the system inherently favors the crafty over the honest. This perceived intrinsic unfairness deters potential investors, especially businesses with lower risk tolerance.

#### Unfamiliarity: The Obscurity of Existing Solutions

Current judicial solutions in the blockchain field suffer from their highly specialized nature. These systems, primarily designed for technical issues, struggle to appeal to a wider audience. While solutions like Kleros and Ulex aim for a more generalist approach, they remain largely unfamiliar to the general public.

The reliance on complex mathematical algorithms and game theory may be theoretically sound, but these concepts are unfamiliar to most individuals. People generally trust expert legal opinions over abstract mathematical models. Acknowledging this gap, we aim to create a new solution that bridges this divide.

### Liberland Solution:  An On-Chain Judiciary System

#### Goals

The proposed solution is designed to achieve the following:
1. Create an on-chain mechanism capable of acting on behalf of a party without explicit permission.
2. Establish a set of norms or laws to govern system operations, thereby eliminating arbitrary decisions and increasing trust.
3. Ensure decentralization and security, while maintaining the system operation by professionals to maintain quality decisions.
4. Maintain recognizability by resembling a traditional courtroom rather than a simplified IT service app.

#### Law

The initial law guiding this system will be the Law of Liberland. However, the system is law-agnostic, allowing other users to implement their own laws, terms & conditions, internal norms, and case law to improve decision predictability.

#### Roles

The system consists of:
1. Party A: The applicant, the party submitting an application to the court.
2. Party B: The defendant, the party mentioned in the application to the court, usually as an opponent to the claim or a part of the claim.
3. Judge: A professional vetted by Liberland (or other users) representing the system's centralized element. The on-chain list of active judges includes their fees, case histories, and success-to-failure ratios.
4. Jury: Cryptographically anonymized users who vote on the merit of arguments based on game theory, aiming to align with the majority vote (Schelling point), representing the system's decentralized element.

### Functionality: Dispute Resolution

#### Mediation

1. A user (Party A) alleges that another user (Party B) has violated the standing body of rules (Liberland Law).
2. Party A selects a judge (Attorney A) from the available roster, agrees to their terms, and pays collateral plus a transaction fee.
3. Party B is notified and selects a judge (Attorney B).
4. Party A and Attorney A compile and submit a Case.
5. Party B and Attorney B compile and submit a Response.
6. The Attorneys meet to create a Compromise, dividing the Case into parts and seeking resolution without litigation where possible.
7. Resolved parts of the Case are executed.
8. The unresolved parts proceed to Litigation.

#### Litigation

1. Attorneys mutually select a third Judge (the Arbitrator).
2. The Arbitrator delivers a Judgement, analyzing the Application and Response according to Liberland law, resulting in statements of "Party X pays to Party Y," backed by a rationale.
3. The Jury reviews the Verdict and can Accept or Overturn each point, operating based on the Schelling Point system (rewarding majority-aligned votes).
4. If the Parties accept, the judgment is executed. If a Party rejects, the Party pays the appeals fee, and an appeal process commences.

#### Appeal

1. An Appeal Judge is chosen by the algorithm.
2. The Appeals Judge reviews the points of appeal and creates an Appeal Verdict.
3. The Jury votes on the Appeal Verdict, either Adopting or Overturning it.
4. The final Verdict is executed on the Collateral and the Pooled LLM.

### Functionality: Advisory Opinion

If a party wishes to seek the Court's advice on a specific legal, technical, or factual matter, even in the absence of a dispute, the system will offer two types of Advisory Opinions:

#### Simple Advisory Opinion

This is a binary yes/no question. The party formulates the question, provides reasoning, pays a fee, and submits the question to the Jury. They then wait for the Jury's decision and can either accept or reject it. If they reject it, they can pay an additional fee to re-run the game up to three times to view the opinions of three different Juries.

#### Complex Advisory Opinion

The party pays a higher fee, formulates a complex question, and selects a Judge. The Judge then formulates the Opinion on the points of the question. The party waits for the Jury's decision and, similar to a Simple Advisory Opinion, they can accept or reject it, paying an additional fee to re-run the game up to three times if they choose to reject it.

## Applications and Extensions

Beyond dispute resolution and advisory opinions, the system's use could be extended to other areas, such as Administrative Decisions on-chain.
For instance, the process of granting or denying citizenship could be complemented with our decentralized system. The Ministry of Internal Affairs, Citizenship Agency would work with the Citizen applicant through steps such as proof of commitment (locked stake), KYC, and Citizenship Interview.

## Development and Contact Information

The Liberland Blockchain is being developed by a team led by Dorian Stern-Vukotic, with Kacper Zuk as Senior Developer. The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company. The intended languages of development are Rust for the backend and Javascript/Angular for the frontend.

The Liberland team can be reached via email at justice@liberland.org, and the project's code repository can be found at https://github.com/liberland/liberland_substrate.
