# Liberland Blockchain Whitepaper

## Abstract 

Liberland is a country founded in 2015 on a terra nullius between Croatia and Serbia, with its founders being enthusiasts of blockchain and liberty. The goal of the Liberland Blockchain is to provide all e-government services to its citizens via a Substrate-based blockchain system, with governance as its first use case. 

The Liberland Blockchain is designed as a layer 1 public blockchain, governed by the holders of its native tokens, the Liberland Dollar (LLD) and Liberland Merit (LLM). The system also supports Non-Fungible Tokens (NFTs) representing land and other assets and implements a decentralised identity solution. 

In the future, it will support an online judiciary system, enabling non-smart but self-executing contracts on the blockchain with the judiciary as an oracle. The judiciary will also enable features like account recovery and recourse against fraud and theft.

## System Overview

Liberland Blockchain is a layer 1 public blockchain owned by holders of LLD but governed by the holders of LLM. The codebase is a fork of Substrate/Polkadot distributed under the MIT License, the same as Bitcoin. Liberland does not claim ownership of the blockchain or related materials. 

The blockchain allows permissionless usage of tokens and coins as a store of value or medium of exchange. Advanced functionalities critical to the project's future are permissioned. DeFi projects on the Liberland chain are not permissioned unless designed and designated as such by third-party developers on a per-project basis.

## Liberland Blockchain Design

### Public Blockchain
The Liberland Blockchain is a fork of the Parity Substrate/Polkadot code base. The code base is distributed under the MIT License, similar to Bitcoin. It supports permissionless transactions for the store of value and medium of exchange purposes, with advanced functionalities being permissioned for specific user types.

### Permissioned Access

To accommodate state-level security requirements, certain blockchain functions are only available to users with elevated privileges. Elevated privileges are obtained by undergoing the, currently, centralised KYC procedure operated by the government of Liberland, and fulfilling the requirements for becoming Citizens. 

The functions that require elevated privilege include, crucially, running Validator nodes and participating in on-chain governance. This system reflects the principle of citizenship on the blockchain: States allow only citizens to operate their systems of critical infrastructure, and typically, only citizens are given full political rights. As on-chain governance and politics are the same thing, the development of the system is, effectively, in the hands of the Citizens.

## On-Chain Assets

### On-Chain Assets and Division of Power

The blockchain contains two main assets: Liberland Dollar (LLD) and Liberland Merit (LLM). LLD serves as a medium of exchange and an instrument for maintaining network consensus and security. LLM represents a share in Liberland's state and nationhood, granting governance power with no possibility of separating this power from the token.

### Liberland Dollar (LLD)

The Liberland Dollar serves as the native token of the blockchain, fulfilling the following main functions: 

- A medium of exchange; and 
- An instrument for maintaining network consensus and security. 
- The token to register entities with and to manage them, such as companies, assets, real estate, etc.
- The token to operate the judiciary for traditional contracts.

LLD is minted according to rules inherited from Polkadot, including the "ideal staking ratio" mechanism. This system is well-researched, designed and tested through years of practical use.

Its tokenomics reflect - just like those of Polkadot’s DOT - the  "automatic central bank" system proposed by the Nobel-prize-winning economist Milton Friedman.

### Liberland Merit (LLM)

#### Overview

The Liberland Merit represents a share in the state and nationhood of Liberland. One's LLM supply can be converted to tokenized political power, with which a Citizen can vote.

With a fixed maximum supply of 70,000,000 tokens and a release schedule of 10 percent per year, LLM is a deflationary token. LLM represents the territory of Liberland, where 10 LLM represent 1 m2 of land. This is an ideal ownership scenario, but LLM holders will be acknowledged when titles to the land are sold. 

LLM is a token set up using the Assets pallet. The initial price for LLM will be USD $2, subject to change when trading begins.

#### Political pooling (PolitiPooling)

Participation in the political process of Liberland is not solely contingent upon ownership of LLM or citizen status. A further requirement exists in the form of political pooling, or 'PolitiPooling' of LLM. 

PolitiPooling is a long-term vesting which, mirroring the initial increase of token supply, only allows the unvesting of 10 percent of one's token supply per year. In addition, while unpooling, e.g. unvesting, one's PolitiPooled LLM supply loses its political power. 

This gradual release of vested tokens can be likened to a form of social security, however, Liberland's social security is funded by the individual's past tax contributions rather than a collective pool. The unpooling mechanism is structured to be triggered on a monthly basis, with 1/12th of 1/10th of the total vested supply becoming available each month.

The act of PolitiPooling LLM is representative of voluntary tax contribution and a further display of dedication to the nation's prospective development. This mechanism is grounded in game theory, suggesting that significant personal investment, whether in the form of time or resources, typically results in a heightened sense of responsibility and commitment to the success of the invested project.

### NFTs

Native NFTs are used to represent land in both physical Liberland and the metaverse. These NFTs are integral to the land registry contract and dApp, which tracks registered property. Additionally, a range of soulbound NFTs will be used in future stages of the project to represent Citizenship and various government functions, enabling Liberland to implement a transition of power through smart contracts.

In future iterations, the project will tokenize everything in the Liberland metaverse and real-world Liberland. Sales and purchases will be facilitated through NFTs, representing “deeds of ownership” to real-life objects. Where there is a dispute, a Judge needs only to look on-chain to identify who owns the NFT for the object in question.

### Contract-based (3rd party) tokens

Liberland Blockchain will exhibit comprehensive compatibility with smart contracts as it operates on a derivative of the Polkadot Virtual Machine. This functionality empowers both our internal team and external developers to establish their decentralised architectures. 

We foresee the emergence of a robust Decentralised Finance (DeFi) ecosystem on our chain, akin to the thriving DeFi environments observed on other Rust-based chains like Polkadot, Near, and Solana.

## Frontend

The user-facing component will encompass an array of interfaces crafted with the intention of enabling Liberland's citizens to directly engage with their governance structures. This assembly of user interfaces will encompass but will not be confined to the subsequent sub-domains:

1. **A Wallet Interface**: A streamlined portal for managing digital assets.
2. **Validator/Nominator Interface**: A conduit for interactions with Validators, the custodians of blockchain integrity.
3. **Political Interface - Citizen-facing**: A dedicated space for electoral processes, candidacy declaration, and legislative drafting.
4. **Political Interface - Politician-facing**: Spaces for Congress, Senate and Cabinet.
5. **Government Registrars Interface**: An access point for government-related services and registrars.
6. **Internal Government Interface**: Exclusive interfaces for government officials to interact with the blockchain and conduct administrative duties.
7. **Treasury Interface**: A bespoke platform for managing Liberland's financial reserves.

Supplementing these, a collection of front-ends will be developed to facilitate the interaction between the blockchain and the metaverse, thereby enhancing the synergy between the digital and physical realms of Liberland.

# Governance: Legislative

## Referendum

### Validation of Proposals

The Referendum serves as a core instrument for decision-making within the political architecture of Liberland, facilitating citizens in the evaluation of laws, regulations, and assorted political propositions. 

The fulcrum of both on-chain governance and the political milieu of Liberland is the Referendum. Within the Liberland context, all laws require passage through the Referendum's direct democratic process for validation.

The functioning of the Referendum is predicated on a system evolved from Polkadot, integrating an anti-populist safeguard that escalates the voting threshold in proportion to declining voter participation. The voting requisite, i.e., the count of tokens required for the ratification of a proposal, rises in conjunction with declining turnover. Consequently, this system safeguards against the Referendum bypassing the will of the silent majority, irrespective of their voting inactivity. This mechanism is deactivated for Referenda initiated by the Congress, given its democratic election.

### Differentiation from Polkadot

In contrast to Polkadot, our system is streamlined to eliminate weighted voting and endorsements. Instead, we mitigate Distributed Denial of Service (DDoS) attacks by requiring the proposer to remit a specified amount of LLD to initiate each Referendum. Upon payment, the Proposal is automatically elevated to a Referendum status, aligning with the expectations of a bona fide political referendum.

### Referendum and Enactment Period

#### Referendum and Enactment Periods:

The Referendum shall be conducted over a designated Referendum Period lasting fourteen (14) days. Should the proposal be ratified, a subsequent Enactment Period of an additional fourteen (14) days shall ensue to facilitate the implementation of the new legislation. This structure is analogous to the "legis vacantis" period commonly observed in various jurisdictions.

#### Emergency Proposals:

The proposer may designate the Referendum as an "emergency" proposal, thereby abbreviating the aforementioned periods. Such an expedited process is subject to rigorous scrutiny by the Congress and may be subject to cancellation as delineated in the subsequent sections.

### Voting Pseudonymity

Our voting system allows for pseudonymity, enabling participants to either disclose or withhold their identity at their discretion. Public figures or significant stakeholders may opt for transparency to establish accountability, thereby enhancing their eligibility for elected roles. Conversely, ordinary voters are not obligated to reveal their identity, thereby preserving their privacy. This approach introduces a level of transparency in the voting process that is unparalleled in other systems, allowing for the comprehensive evaluation of politicians based on their complete political history.

### Revocation of Proposals

Furthermore, a specialized variant of the Referendum is operational for the retraction of legal validation from laws and other measures ratified by the Referendum. This is termed the Public Veto. An exclusive feature within the chain's toolkit, the voting for a Public Veto is conducted on a one-citizen-one-vote basis. This mechanism serves as a precautionary measure against potential plutocratic commandeering of the system.

## Congress

### Overview

The Congress operates as the representative entity within Liberland, tasked with

- initiating rational referenda that are exempt from the anti-populist voting requisites;
- Removing referenda which are obviously malicious or where the proposals are obviously not sufficiently thought out;
- The appointment and removal of the Prime Minister (Executive), and
- Participating in referenda on behalf of constituents who delegate their voting rights.

### Elections

The Congress is elected through a voting process involving all citizens, utilising their tokens. Elections occur on a quarterly basis. Inactive citizens in the most recent elections are not recorded as such; their vote in the last participated election is considered valid.

### Referendum Quality Control

The Congress is given the authority to rescind referenda deemed to be malicious in intent, such as those explicitly designed to disrupt the stability of Liberland or compromise the integrity of the blockchain. This authority extends to referenda with unjustifiably abbreviated Referendum or Enactment Periods, including those designated as "emergency" proposals without a substantiated basis for urgency. The Congress becomes a human oracle, providing a holistic review, the non-algorithmic element in an otherwise mathematically precise system. Such rescission is referred to as "Cancellation" within the Constitution of Liberland and must be accompanied by a reasoned justification. 

The proposer will be informed of the specific areas requiring improvement to avoid future cancellations. It is incumbent upon the proposer to ensure the proposal meets the requisite standards, as the LLD fee for cancelled proposals is non-refundable. This serves as a stringent regulatory mechanism.

The Senate possesses parallel authority for the cancellation of referenda. In instances where the proposer disputes the legitimacy of a cancellation, an appeal may be lodged with the Judiciary for impartial adjudication.

### Delegation

The concept of Delegation gains relevance for citizens who perceive their representative as more knowledgeable or more capable of in-depth study of the subject matter while they attend to their personal affairs. 

Delegation can be granted or rescinded at any point in time. This introduces a novel form of tangible representation into representative democracy, given that most states do not permit any form of post-election influence over the actions of the representative, barring a one-time vote cast every few years.

### Prime Member

The Congress is a derivative of the Substrate Council, retaining the original structure of the source. Consequently, the Congress also inherits the Council's system of the Prime Member. Within the Congress, the member amassing the maximum votes per voting period ascends to the role of the Prime Member. Their vote in any Congress deliberation is automatically adopted by all inactive or non-voting members of the Congress.

## Governance: Executive

### Role

The Executive carries out the routine operations of the nation. It also executes laws and measures ratified by Referendum and Congress, thus translating them into practice.

### Cabinet

The Executive operates in a hierarchical manner, spearheaded by the Cabinet, which technically is another offshoot of the on-chain Collective pallet. The Cabinet consists of one Prime Minister and four Ministers. All other executive functions fall under the purview of either one of the Cabinet members or the Cabinet as a whole.

The primary authority of the Cabinet lies in enforcing regulations within the legal framework. Subordinate Offices administer and regulate within the confines of the law and Cabinet regulations, with their heads appointed and dismissed by the Cabinet or a specific Minister.

### E-Governance

All the offices under the Cabinet constitute the E-Governance of Liberland on the blockchain. They are expected to have interfaces that facilitate seamless communication and service provision for the citizens of Liberland.

The initial such offices are the Company Registry and Land Registry, which are currently operational on the chain in a pilot stage. They are expected to be succeeded by additional applications aimed at fulfilling traditional state roles.

Furthermore, E-Governance will feature an inward component, specifically, budget management. State budgets will be maintained on the blockchain, ensuring complete transparency and oversight.

The e-governance system also encompasses wallet interfaces, validator interfaces, and political interfaces for elections and will include such elements as legislative drafting, interfaces for government registers and other services, internal government front ends for officials, and the treasury interface.

### Registries

The electronic governance framework will incorporate multiple registry databases, serving as the authoritative repositories for various types of assets, as applicable. Initially, this will encompass all real estate holdings within Liberland, which will be virtually represented in a dedicated registry, thereby providing transparent ownership information.

The registration of additional asset categories will be facilitated in a similar manner. While participation in these registries is entirely voluntary, it offers significant advantages in judicial proceedings. Assets recorded on the blockchain will be legally recognized as the property of the registered account holder, thereby eliminating ambiguities and streamlining transactions.

The blockchain-based registry systems represent a groundbreaking advancement in economic management and expedited legal recourse, offering a streamlined and transparent approach to asset ownership and transactions.

### Current Phase: The Provisional Government

In the early stages, the Cabinet is served by the Provisional Government of Liberland, with the President acting as the Prime Member. The roles within the Cabinet are therefore allocated by the President. Upon the development of a community in Liberland or a territory governed by Liberland (when at least 65 percent of Citizens are onboarded and settlement is actively in progress), the Provisional Government will relinquish its power, and the President will transition into the role of a primarily symbolic head of state.

# Treasury

One of the standing values that Liberland has is that all taxes are paid voluntarily by the citizens of Liberland. We forked Polkadot’s Treasury and implemented it as a multi-signature wallet held by the on-chain politicians of Liberland. Like Polkadot’s Treasury, we will handle funding proposals, mainly initiated by the Executive and Congress. 

# Senate

## Overview

The Senate is tasked with the management of Treasury keys and the power to veto Laws and Regulations. Laws can be vetoed during the referendum phase, whereas lower-tier Regulations can be vetoed at any time. Proposals related to the LLM Treasury necessitate the Senate's approval for execution. The Senate serves as Liberland's "House of Lords", with members appointed for life. Their power is purely of control, devoid of legislative or executive capacities.

A notable attribute of Senatorship is the possession (restricted to dividends) of one percent of Liberland reserves and of the parent company developed for Liberland, namely Liberland Limited, based in Hong Kong.

### Powers

The Senate, as a collective, is endowed with the following authorities:

1. Nullify any referendum regarding Laws prior to them acquiring legal force; if a Veto is enacted, the proposed law will not acquire legal force;
2. Act as the supreme authority in budgetary and expenditure matters, maintaining oversight over any outflows from the Liberland Treasury; the Senate can halt any spending they deem unjustified;
3. Revoke any Regulation, other than a Law, even post-legal enactment; and
4. Cast votes for the President of Liberland.

## Implementation

The Senate, similar to the Congress and Council, is also a derivative of the Council pallet from Polkadot. Initially, Senators will be designated by the President. Subsequently, a co-option system will be established, wherein existing Senators vote to induct new members. 

It is important to note that while Senators have the power to admit, they cannot dismiss, as Senatorship is a property title and, as such, is safeguarded from expropriation in accordance with Liberland's property protection principles.

## President & Vice-Presidents

The President, selected by the Senators, operates as the head of state and represents Liberland on the international stage. Any actions undertaken by the President require the validation of at least one Vice-President. The President's main authority is as the Prime Member of the Senate Collective, implying that the votes of abstaining Senators automatically align with the President's. This holds true only when a Vice-President corroborates the vote; otherwise, the votes of abstaining Senators are deemed uncast.

Furthermore, the President is empowered to appoint Executive functionaries and Judges upon establishment of the Judiciary. The President's authority in this capacity is significant, allowing them to reject an appointment. However, this power is subject to the same checks as the Prime Member vote, demanding the countersignature of a Vice-President.

# Future Outlook: Judiciary

## Overview

The on-chain judiciary is in active development, aiming to combine trust-based elements, such as professional judges and process law, with blockchain-native solutions inspired by Kleros, the Aragon Court, and Ulex. The main mission is to conceive a blockchain-compatible solution that translates traditional dispute resolution and judiciary functions into the digital realm. Our vision includes a system that synergizes the virtues of centralised and decentralised models.

## Problem Description

### Irreversibility: The Inflexibility of Blockchain Systems

A foundational trait of blockchain systems originating from Bitcoin is the principle of irreversibility. Once a transaction is executed, it cannot be undone. Here, intentions play a secondary role, with the final action being recognized as the valid user input.

However, this level of accountability is often too demanding for many individuals. The common practice of associating human identities with addresses by third-party organisations is essentially a temporary fix, contradicting the core philosophy of blockchain. A single mistake can lead to catastrophic consequences, potentially resulting in the loss of millions without any inherent system recourse.

#### Absence of Authority: The Perilous Landscape of Cryptocurrency

The current cryptocurrency environment, teeming with scams and malicious actors, provides little protection against such threats. Redress against hackers and dishonest service providers typically happens outside the system, relying on national judiciaries and other external entities.

Cryptocurrency represents a risky environment balanced against the promise of opportunity. It is filled with disclaimers about using the service "as-is", and providers often disclaim liability for secondary damages caused by other users. As a result, victims often find themselves in a harsh situation, with few options for seeking justice.

Compounding the issue is the inherent system bias towards the savvy manipulator. With actions prioritised over intentions and the absence of an overseeing authority, the system inherently favours the crafty over the honest. This perceived intrinsic unfairness deters potential investors, especially businesses with lower risk tolerance.

#### Unfamiliarity: The Obscurity of Existing Solutions

Current judicial solutions in the blockchain field suffer from their highly specialised nature. These systems, primarily designed for technical issues, struggle to appeal to a wider audience. While solutions like Kleros and Ulex aim for a more generalist approach, they remain largely unfamiliar to the general public.

The reliance on complex mathematical algorithms and game theory may be theoretically sound, but these concepts are unfamiliar to most individuals. People generally trust expert legal opinions over abstract mathematical models. Acknowledging this gap, we aim to create a new solution that bridges this divide.

## Liberland Solution:  An On-Chain Judiciary System

### Overview

The Liberland Judiciary is designed to develop an on-chain system capable of acting on behalf of a party without their explicit permission in pre-approved ways with mutual consent given in advance.

1. Facilitate the integration of a 'court as a smart contract oracle', thereby enabling the execution of traditional, verbose contracts on-chain. This system allows for the imposition of sanctions as dictated by the applicable law and the contract itself in the event of a dispute.
2. Implement a body of norms or laws to regulate the system's operations, thereby eliminating arbitrary decisions and enhancing trust.
3. Guarantee decentralisation and security while ensuring that the system is operated by professionals who uphold the quality of decisions.
4. Retain recognizability by resembling a traditional courtroom rather than a streamlined IT service app.

The solution we propose introduces a hybrid entity, central yet decentralised, capable of interpreting the intent behind actions within the blockchain. Empowered to regulate transactions by reversing or counteracting them, this entity exercises authority, particularly in situations where malicious or bad faith intentions are identified. By introducing a virtual judiciary, any questionable actions can be evaluated and, if necessary, nullified.

This architecture enhances the breadth of on-chain business activity, facilitating enforcement of traditional contract agreements and enabling partial algorithmic execution. In effect, this approach instils confidence that transactions, whether off-chain or on-chain, offline or online, will be enforced. Additionally, it offers an authoritative entity to resolve any disputes arising from the obligations agreed upon by the parties involved. 

## Simple Process

### Outline

The Simple process is employed when all parties involved reach a consensus on selecting a judge or panel of judges to preside over their case. The selection can be explicit (naming a specific judge) or implicit (agreeing to let the system select). The system provides parameters (such as cost, experience level, etc.) for judge selection, stipulating that parties are bound by their agreement to accept the system's random selection within the agreed-upon parameters.

The Simple process is designed to be:

- Quick,
- More economical than the contested process, and
- The intent is to ensure expedient and cost-effective resolution, contrasting with contemporary systems where years can elapse before disputes are resolved. 

In Liberland, minor disputes could potentially be adjudicated within a day or a few days through the Simple process, and at a significantly reduced cost

### Mediation

The appointed judge endeavours to segment the case into manageable portions, drafting a mediation solution for each. This proposed solution is then presented to the involved parties. If an agreement is reached, the process concludes without litigation, and the judge is remunerated a flat fee, which is lower than the litigation tariff.

### Litigation
In instances where a mutual agreement is not achieved, the judge drafts a mediation solution and presents it to the involved parties. If an agreement is reached, the litigation process is averted, with the judge remunerated a flat fee that is lower than the tariff payable when Complex Process is used.

## Complex Process

### Outline

The Complex Process acts as a fallback mechanism when the parties cannot concur on the choice of a judge or other terms. A mutual agreement on jurisdiction must be established for any process to occur, but there may exist a level of distrust that prevents a jointly accepted judge. In such circumstances, the system adapts to assign three judges:

- The attorney representing the applicant,
- The attorney representing the respondent, and
- An arbitrator jointly selected by the two attorneys.

This system, although more involved, remains streamlined for efficiency and cost-effectiveness, maintaining the balance between swiftness and the demands of judicature. The Complex Process is designed to handle intricate issues requiring detailed attention and processual protections for the parties involved. Ultimately, the criminal process of Liberland will adopt the framework of the Complex Process.

### Mediation

1. A user (Party A) alleges that another user (Party B) has violated the standing body of rules (Liberland Law). In the case of a smart contract, this is done by triggering a function on the contract itself, which enters into 'litigation mode' until the process is resolved
2. Party A selects a judge (Attorney A) from the available roster, agrees to their terms, and pays collateral plus a transaction fee.
3. Party B is notified and selects a judge (Attorney B).
4. Party A and Attorney A compile and submit a Case.
5. Party B and Attorney B compile and submit a Response.
6. The Attorneys meet to create a Compromise, dividing the Case into parts and seeking resolution without litigation where possible.
7. Resolved parts of the Case are executed.
8. The unresolved parts proceed to Litigation.

### Litigation

1. Attorneys mutually select a third Judge (the Arbitrator).
2. The Arbitrator delivers a Judgement, analysing the Application and Response according to Liberland law and relevant contract, resulting in statements of "Party X pays to Party Y," backed by a rationale.
3. If the Parties accept, the judgement is executed. If a Party rejects, the Party pays the appeals fee, and an appeal process commences.

### Appeal

#### Outline

An appeal can ensue after either the Simple Process or the Complex Process is completed. It is initiated upon the request of a party, presenting costs to the petitioner and imposing time constraints, namely the period until adjudication, upon the other party. Additionally, the assurance of the first instance's final verdict is jeopardised. Parties may agree in advance to forgo the appeal process, rendering the first instance judgement as the final verdict, anticipated to be prevalent primarily with the Simple Process.

#### Steps of an Appeal
1. An Appeal Judge is appointed by the algorithm.
2. The Appeal Judge examines the appeal points and formulates an Appeal Verdict.

The final Verdict is executed on the Collateral and the Pooled LLM.

## Enactment of Awards

### The Optimal Circumstance

A contract or a case is collateralized such that the collateral is sufficient to cover any additional payments prescribed in the final verdict beyond the awarded sum and the Court Costs. In this scenario, the collateral serves as a mechanism for the execution of the judgement. A third party, such as an insurance company may handle collateral.

### Case with Insufficient Collateral

#### Seizing PolitiPooled LLM

The judge is imbued with the authority to designate an individual's politipooled (staked) LLM as collateral. Upon such a declaration, an involuntary unpooling of the owing party's pooled LLM stash will ensue, optionally carrying typical ramifications like the forfeit of voting rights associated with that stash. If the full amount is subsequently paid, this directive is withdrawn. However, under circumstances where:

- there is a violation of the Non-Aggression Principle, implicating aggressive conduct against another individual's person or property, or
- the damage incurred exceeds one's LLM stash,

The offender's LLM balance could turn negative, resulting in their listing on Liberland's 'wanted' roster, rendering them a 'persona non grata'. Consequently, they lose their voting rights and potentially access to other Liberland services until the owed amount is fully settled.

#### Enforcement Beyond the Chain

In instances where either of the aforementioned methods cannot enforce the judgement, the awarded sum will be incorporated into a conventional contract or appended as a supplement if the dispute is contract-related. This contract, endorsed by both parties, holds legitimacy outside of Liberland, akin to any other contract. It can be presented to an enforcement agency for execution, even against the unwilling party's resistance. Note that this is just an explanation of the process and doesn't represent a deliverable for the grant.

## Functionality: Traditional Contracts

### Overview

Most contractual relationships in the world aren't currently simple and predictable enough to be run on smart contracts. This is likely to remain so even in the age of AI, at least for a decade or so. In the meantime, dumb contracts, that is, traditional contracts, are what runs the world of business and your everyday life. What is a dumb contract? It is an agreement you make with another human being or corporation. It is also a smart contract, in a way, but it runs on the hardware and the operating system of your brain.

How will it work? Alice and Bob enter into a traditional contract for the sale of goods. They agree to use the Liberland Blockchain Judiciary system for any potential disputes. They choose a judge from the roster and agree on the collateral and fees. The contract is then recorded on the blockchain. Why would someone want to do this?

### Benefits:

- **Efficiency and Speed**: The Liberland Blockchain Judiciary system offers a Simple Process for dispute resolution. If a dispute arises, Alice or Bob can trigger the judge to give a binding opinion. This process is designed to be quick and more economical than traditional legal systems, potentially resolving disputes within a few days.
- **Cost-Effectiveness**: The system is designed to be more economical than traditional legal systems. The costs are defined upfront and include the judge's fees and any potential award to the victorious party. This transparency and predictability of costs can make the system more attractive to parties entering into a contract.
- **Security and Trust**: The system is built on the Liberland Blockchain, providing a secure and immutable record of the contract and any subsequent dispute resolution proceedings. This can increase trust between the parties and reduce the risk of fraudulent claims.
- **Payment Processing**: The blockchain can also be used to process payments related to the contract. This can be particularly useful in cases where the contract involves regular payments or where the amount of payment is dependent on certain conditions being met. The blockchain can automatically process these payments when the conditions are met, reducing the need for manual intervention and the risk of non-payment.
- **Smartification of Traditional Contracts**: While the contract itself may be a traditional contract, the use of the blockchain allows for certain aspects of the contract to be automated. For example, payments can be automatically triggered when certain conditions are met. This can make the contract more efficient and reduce the potential for disputes.

## Functionality: Advisory Option

In state administration beyond dispute resolution and advisory opinions, we plan to extend the use of this system to other areas, such as administrative decisions on-chain.

For example, the process of granting or denying citizenship could be complemented by our decentralised system. The Ministry of Interior’s Citizenship Agency would work with the Citizen applicant through steps such as proof of commitment (locked stake), KYC, and citizenship interview.

Afterwards, they would create a brief report on the results and a more detailed report on the applicant's background. The Judge would then Confirm or Reject the applicant. A Confirmed applicant becomes a Citizen, while a Rejected one must wait one year before re-applying.

This is not an exhaustive list of potential applications for our system. We encourage other builders to explore further expansions.

## Functionality: Decentralised Registers

Along with the previous system, we can also decentralise our property register operations. The relevant Ministry would create an entry and add background information, which is generally straightforward or automated.

The Judge then makes a final Confirmation or Rejection. These decisions will mostly be affirmations. Hence they are considered low-stakes/low gains procedures.

To make these processes more engaging, we could utilise the Complex Advisory Opinion and establish a group of on-chain Registrars who operate the Registry instead of the Ministry. These Registrars could even propose different opinions on what to inscribe, gamifying the processes and making these matters more interesting.

# Development and Contact Information

The Liberland Blockchain is being developed by a team led by Dorian Stern-Vukotic, with Kacper Zuk as Senior Developer. The team is supported by Liberland Limited, a Hong Kong-based Limited Liability Company. The intended languages of development are Rust for the backend and Javascript/Angular for the frontend.

The Liberland team can be reached via email at justice@liberland.org, and the project's code repository can be found at https://github.com/liberland/liberland_substrate.