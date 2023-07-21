# Liberland Blockchain - the Judiciary

## Introduction
### Liberland Blockchain
Liberland Blockchain is a layer 1 public blockchain owned by coin and token holders. The blockchain is funded and supported by Liberland, providing the first set of use cases. The codebase is a fork of Substrate/Polkadot, and the license is MIT, the same as Bitcoin. Liberland does not claim ownership of the blockchain or related materials.

The blockchain allows permissionless usage of tokens and coins as a store of value or medium of exchange. Advanced functionalities critical to the project's future are permissioned. DeFi projects on the Liberland chain are not permissioned unless designed by third-party developers on a per-project basis.

This milestone now sets the stage for implementing the quintessential element of all governance systems - the judiciary. We seek to enable dispute resolution and advisory opinions, traditionally offline activities, to take place within this blockchain ecosystem.

## Mission Statement
Our mission is to conceive a blockchain-compatible solution that translates traditional dispute resolution and judiciary functionalities into the digital realm. Our vision includes a system that synergizes the virtues of centralized and decentralized models.

## Problem Definition
### The Current Landscape
As it stands, the blockchain sphere lacks universally acceptable judiciary solutions that can inspire mass adoption. The available solutions, and the broader blockchain environment, often lack the trust-inspiring structures that appeal to the general public and businesses. This is seen as a natural outgrowth of the trustless approach of the blockchain technology, but it is hindering adoption.

To get a clear perspective of this issue, we draw a parallel between blockchain and the user experience within centralized modern communication systems (CCSs). Our focus is specifically on two principal attributes of CCSs - Intentionality and Justice.

### Centralized Communication Systems (CCSs)
CCSs, which include payment systems (banks), social networks, and online governmental operations, operate on principles of Intentionality and Justice - the cornerstone of their operational philosophy.

#### Intentionality 
CCSs operate under the assumption that the real intention of a user is the rightful command to be executed in the system. The intent is to mirror the natural world's experiences and actions as closely as possible within the digital space.

Notable characteristics of this principle include:
- Your actions are subordinate to your intentions.
- Your intentions have the upper hand in the event of a conflict with your actions, given you can prove that they were in place at the time of action.
- The system supports transaction reversibility and replacement.

#### Justice
This principle reflects the system’s ability to distinguish between malicious and good-faith intentions/actions. In instances of conflict, the actions performed in good faith take precedence. Such a system necessitates an authoritative figure and a procedural structure aimed at delivering justice. These systems align the predictability of rulings on which actions are of good faith and which are malicious. We term such systems as Justice.

### Blockchain: Current Challenges and the Need for Reform
#### Irreversibility: The Unforgiving Nature of Blockchain
Blockchain systems, tracing their roots back to Bitcoin (BTC), are characterized by the fundamental principle of irreversibility. In this unforgiving environment, a transaction, once executed, cannot be reversed. Intentions are secondary; only the executed action is acknowledged and accepted as valid user input.

This stringent level of responsibility, however, is not palatable to most individuals. The prevailing practice of third-party organizations matching addresses to human identities is a makeshift solution, an external "patchwork" that contradicts the blockchain's core philosophy. One error can have severe ramifications, potentially causing the loss of millions and wreaking havoc on livelihoods without any recourse within the system.

Please note that we recognize the great benefits of irreversibility; we keep it as the general policy. In certain cases, however, in the context of running a country and public services on the blockchain, it might be constructive to compromise on irreversibility where there is the consent of all parties.

#### Absence of Authority
The current crypto sphere, rife with scams and deceitful actors, offers minimal protection against these malevolent forces. Recourse against hackers, fraudsters, and unscrupulous service providers primarily occurs outside the system, relying on state judiciaries and other external mechanisms.

Crypto represents a landscape of opportunity juxtaposed with significant risk. It's saturated with disclaimers about using the service "as-is" and providers distancing themselves from liability for secondary damages caused by other users. Given this status quo, victims often find themselves in an unforgiving predicament, with limited avenues for seeking justice.

Further aggravating the situation is the inherent bias of these systems towards the astute trickster. With actions taking precedence over intentions and a void of authority, systems inherently favour the cunning over the honest. This perception of built-in injustice deters potential investors, particularly businesses that typically exhibit lower risk tolerance.

### Unfamiliarity: The Cryptic Nature of Current Solutions
Current blockchain judiciary solutions suffer from their highly specialized nature. These systems, primarily designed to handle technical issues, fail to resonate with a broader audience. While solutions like Kleros and Ulex strive for a more generalist approach, they still remain largely alien to the general public.

Relying on complex mathematical algorithms and game theory might be sound in principle, but these concepts are foreign to most individuals. People tend to trust the judgement of "experts" in legal matters rather than abstract mathematical models. Recognizing this gap, we aim to devise a novel solution that bridges the divide.

## Our Solution: An On-Chain Judiciary System
### Outline
Our solution is designed to:
- Develop an on-chain system capable of acting on behalf of a party without their explicit permission in pre-approved ways with mutual consent given in advance.
- Implement a body of norms or laws to regulate the system's operations, thereby eliminating arbitrary decisions and enhancing trust.
- Guarantee decentralization and security while ensuring that the system is operated by professionals who uphold the quality of decisions.
- Retain recognizability by resembling a traditional courtroom rather than a streamlined IT service app.

### Law
The inaugural law guiding this system will be the Law of Liberland. However, the system is law-agnostic, allowing other adopters to implement their own laws, terms & conditions, internal norms, and case law to enhance decision predictability.

### Roles
The system features:
- **Party A**: The applicant, the party submitting an application to the court.
- **Party B**: The defendant, the party being mentioned in the application to the court, usually as an opponent to the claim or to a part of the claim.
- **Judge**: A professional vetted by Liberland (or other users) representing the system's centralized element. The on-chain list of active judges includes their fees, case histories, and success-to-failure ratios.

## Impact
The solution we propose introduces a hybrid entity, central yet decentralized, capable of interpreting intent behind actions within the blockchain. Empowered to regulate transactions by reversing or counteracting them, this entity exercises authority particularly in situations where malicious or bad faith intentions are identified. By introducing a virtual judiciary, any questionable actions can be evaluated and, if necessary, nullified.

This architecture enhances the breadth of on-chain business activity, facilitating enforcement of traditional contract agreements and enabling partial algorithmic execution. In effect, this approach instills confidence that transactions, whether off-chain or on-chain, offline or online, will be enforced. Additionally, it offers an authoritative entity to resolve any disputes arising from the obligations agreed upon by the parties involved.

## Jurisdiction
Agreement to use the judiciary for dispute resolution forms a crucial part of our protocol. This agreement may encompass all relationships or be contract-specific. Parties may nominate the judiciary itself or a particular judge. The judicial system can also function as an oracle, triggering certain contractual clauses or facilitating escrow execution. However, the application of the judiciary is contingent on mutual consent of the involved parties.

A key note to consider: All citizens of Liberland, by virtue of their citizenship, agree to the jurisdiction of the Liberland judiciary as their default court, particularly in disputes involving fellow citizens.

## Court Costs
### Collateral
The collateral signifies the on-chain funds allocated to individuals assisting in the adjudication process: the judges. The court costs, as well as any dues to the victorious party—such as the awarded amount—are to be defined by the judge or judges.

The magnitude of the collateral depends on the mutual agreement between the parties regarding the judge. The collateral can be staked into the contract originating the dispute, be it a contract traditional or smart (refer to the following section), or it can be enforced alongside the award itself. The former scenario is ideal, while the latter is often the practical occurrence. For these instances, mechanisms will be installed to guarantee that the judge and the prevailing party are compensated. These mechanisms will be further explored in the Enforcement section.

### Insurance
Although the previously mentioned mechanisms are in place, managing cases without collaterals remains an undesirable situation for both parties and the judge. We foresee and encourage the emergence of an insurance system. This echoes many real-world attorney insurance cases, such as the Dutch "rechtsbijstand". The insurance guarantees collateral coverage, typically through a smart contract, thereby triggering automatically at the commencement of a court case. The contract is expected to be escrow-based, potentially covered by the judiciary in the rare event of a dispute.

One can procure insurance either as a defendant on a personal basis; or on a per-contract or per-situation basis, e.g. for a larger, or ongoing deal. Contracts or individuals with collaterals in this manner would receive an advantage if they choose to disclose their insurance policy. Disclosure becomes inevitable in certain on-chain cases, for instance, when one's identity as a citizen is revealed for political purposes.

These insurance providers will be entirely private entities, unaffiliated with the government. Nevertheless, we aim to establish a conducive environment for these providers, such that they only require their business prowess and basic programming skills to operate.

## Simple Process
### Outline
The Simple process is employed when all parties involved reach a consensus on the selection of a judge or panel of judges to preside over their case. The selection can be explicit (naming a specific judge) or implicit ("we agree to let the system decide"). The system provides parameters (such as cost, experience level, etc.) for judge selection, with the stipulation that parties are bound by their agreement to accept the system's random selection within the agreed upon parameters.

The Simple process is designed to be:

- Quick, and

- More economical than the contested process.

The intent is to ensure expedient and cost-effective resolution, contrasting with contemporary systems where years can elapse before disputes are resolved. In Liberland, minor disputes could potentially be adjudicated within a day or a few days through the Simple process, and at a significantly reduced cost.

### Mediation
The appointed judge endeavors to segment the case into manageable portions, drafting a mediation solution for each. This proposed solution is then presented to the involved parties. If an agreement is reached, the process concludes without litigation, and the judge is remunerated a flat fee, which is lower than the litigation tariff.

### Litigation
In instances where a mutual agreement is not achieved, the judge drafts a mediation solution and presents it to the involved parties. If an agreement is reached, -> the litigation process is averted, 
-> with the judge remunerated a flat fee that is lower than the tariff payable when Complex Process is used.

## Complex Process
### Outline
The Complex Process acts as a fallback mechanism when the parties cannot concur on the choice of a judge or other terms. A mutual agreement on jurisdiction must be established for any process to occur, but there may exist a level of distrust that prevents a jointly accepted judge. In such circumstances, the system adapts to assign three judges:

- The attorney representing the applicant,

- The attorney representing the respondent, and

- An arbitrator, jointly selected by the two attorneys.

This system, although more involved, remains streamlined for efficiency and cost-effectiveness, maintaining the balance between swiftness and the demands of judicature. The Complex Process is designed to handle intricate issues requiring detailed attention and processual protections for the parties involved. Ultimately, the criminal process of Liberland will adopt the framework of the Complex Process.

### Mediation
1. A user (Party A) alleges that another user (Party B) has violated the standing body of rules (Liberland Law).
2. Party A selects a judge (Attorney A) from the available roster, agrees to their terms, and pays collateral plus a transaction fee.
3. Party B is notified and selects a judge (Attorney B).
4. Party A and Attorney A compile and submit a Case.
5. Party B and Attorney B compile and submit a Response.
6. The Attorneys meet to create a Compromise, dividing the Case into parts and seeking resolution without litigation where possible.
7. Resolved parts of the Case are executed.
8. The unresolved parts proceed to Litigation.

### Litigation
1. Attorneys mutually select a third Judge (the Arbitrator).
2. The Arbitrator delivers a Judgement, analyzing the Application and Response according to Liberland law, resulting in statements of "Party X pays to Party Y," backed by a rationale.
3. If the Parties accept, the judgment is executed. If a Party rejects, the Party pays the appeals fee, and an appeal process commences.

## Appeal
### Outline
An appeal can ensue after either the Simple Process or the Complex Process. It is initiated upon the request of a party, presenting costs to the petitioner and imposing time constraints, namely the period until adjudication, upon the other party. Additionally, the assurance of the first instance's final verdict is jeopardized. Parties may agree in advance to forgo the appeal process, rendering the first instance judgment as the final verdict, anticipated to be prevalent primarily with the Simple Process.

### Steps of an Appeal
1. An Appeal Judge is appointed by the algorithm.
2. The Appeal Judge examines the appeal points and formulates an Appeal Verdict.
3. The final Verdict is executed on the Collateral and the Pooled LLM.

## Functionality: Advisory Opinion
If a party wishes to obtain the Court's opinion on a particular legal, technical or factual matter, even in the absence of a dispute, the system will offer two types of Advisory Opinions:

- **Simple Advisory Opinion**: This is a yes/no binary question. The party formulates the question, provides reasoning, pays a fee, and presents the question to the Judge. They then wait for the Judge's decision and can either accept or reject it. If they reject it, they can pay an additional fee to re-run the game up to three times to view the opinions of three different Juries.
- **Complex Advisory Opinion**: The party pays a higher fee, formulates a complex question, and chooses a Judge. The Judge then formulates the Opinion on the points of the question. The party waits for the Judge's decision and, similar to a Simple Advisory Opinion, they can accept or reject it, paying an additional fee to re-run the game up to three times if they choose to reject it.

## Enactment of Awards
### The Optimal Circumstance
A contract or a case is collateralized such that the collateral is sufficient to cover any additional payments prescribed in the final verdict, beyond the awarded sum and the Court Costs. In this scenario, the collateral serves as a mechanism for execution of the judgement.

### Case with Insufficient Collateral 
#### Seizing LLM
The judge is imbued with the authority to designate an individual's LLM as collateral. Upon such a declaration, an involuntary unpooling of the owing party's LLM stash will ensue, carrying typical ramifications like the forfeit of voting rights associated with that stash. If the full amount is subsequently paid, this directive is withdrawn. However, under circumstances where 

1) there is a violation of the Non Aggression Principle, implicating aggressive conduct against another individual's person or property, or 

2) the damage incurred exceeds one's LLM stash, 

the offender's LLM balance could turn negative, resulting in their listing on Liberland's 'wanted' roster, rendering them a 'persona non grata'. Consequently, they lose their voting rights until the owed amount is fully settled.

#### Enforcement Beyond the Chain
In instances where the judgement cannot be enforced by either of the aforementioned methods, the awarded sum will be incorporated into a conventional contract, or appended as a supplement if the dispute is contract-related. This contract, endorsed by both parties, holds legitimacy outside of Liberland, akin to any other contract. It can be presented to an enforcement agency for execution, even against the unwilling party's resistance.

## Functionality: Traditional Contracts

### Overview
Most contractual relationships in the world aren't currently simple and predictable enough to be run on smart contracts. This is likely to remain so even in the age of AI, at least for a decade or so. In the meantime, dumb contracts, that is, traditional contracts, are what runs the world of business and your everyday life. What is a dumb contract? It is an agreement you make with another human being. It is also a smart contract, in a way, but it runs on the hardware and the OS of your brain.

How will it work? Alice and Bob enter into a traditional contract for the sale of goods. They agree to use the Liberland Blockchain Judiciary system for any potential disputes. They choose a judge from the roster and agree on the collateral and fees. The contract is then recorded on the blockchain. Why should someone want to do this?

### Benefits:
**Efficiency and Speed:** The Liberland Blockchain Judiciary system offers a Simple Process for dispute resolution. If a dispute arises, Alice or Bob can trigger the judge to give a binding opinion. This process is designed to be quick and more economical than traditional legal systems, potentially resolving disputes within a few days.

**Cost-Effectiveness:** The system is designed to be more economical than traditional legal systems. The costs are defined upfront and include the judge's fees and any potential award to the victorious party. This transparency and predictability of costs can make the system more attractive to parties entering into a contract.

**Security and Trust:** The system is built on the blockchain, providing a secure and immutable record of the contract and any subsequent dispute resolution proceedings. This can increase trust between the parties and reduce the risk of fraudulent claims.

**Payment Processing:** The blockchain can also be used to process payments related to the contract. This can be particularly useful in cases where the contract involves regular payments or where the amount of payment is dependent on certain conditions being met. The blockchain can automatically process these payments when the conditions are met, reducing the need for manual intervention and the risk of non-payment.

**Smartification of Traditional Contracts:** While the contract itself may be a traditional contract, the use of the blockchain allows for certain aspects of the contract to be automated. For example, payments can be automatically triggered when certain conditions are met. This can make the contract more efficient and reduce the potential for disputes.\

## Functionality: Advisory Option in State Administration
Beyond dispute resolution and advisory opinions, we plan to extend the use of this system to other areas, such as Administrative Decisions on-chain.

For example, the process of granting or denying citizenship could be complemented with our decentralized system. The Ministry of Internal Affairs, Citizenship Agency would work with the Citizen applicant through steps such as proof of commitment (locked stake), KYC, and Citizenship Interview. 

Afterward, they would create a brief report on the results and a more detailed report on the applicant's background. The Judge would then Confirm or Reject the applicant. A Confirmed applicant becomes a Citizen, while a Rejected one must wait one year before re-applying. 

This is not an exhaustive list of potential applications for our system. We encourage other builders to explore further expansions.

## Functionality: Decentralized Registers
Along with the previous system, we can also decentralize our property register operations. The relevant Ministry would create an entry and add background information, which is generally straightforward or automated. 

The Judge then makes a final Confirmation or Rejection. These decisions will mostly be affirmations. Hence they are considered low-stakes/low gains games.

To make these games more engaging, we could utilize the Complex Advisory Opinion and establish a group of on-chain Registrars who operate the Registry instead of the Ministry. These Registrars could even propose different opinions on what to inscribe, making the games about these matters more interesting.

## Team

### Team Members
- Dorian Stern-Vukotic, Senior Developer
- Kacper Zuk, Senior Developer

### Team LinkedIn Profiles
1. [Dorian Stern-Vukotic](https://www.linkedin.com/in/djstern)
2. [Kacper Zuk](https://www.linkedin.com/in/kacperzuk/)

### Team’s Website
1. [Liberland](www.liberland.org)
2. [Liberland GitHub](https://github.com/liberland/liberland)

### Legal Structure
The project will initially be structured as a Hong Kong-based Limited Liability Company, and later, a Liberland Company will be the entity in charge.

In addition to the internal developer, we are partnered with [Neti](https://www.neti-soft.com/), a blockchain development firm based in Poland.

### GitHub
1. [Main repo](https://github.com/liberland/liberland_substrate)
2. [Docs](https://github.com/liberland/docs/tree/master/blockchain)
3. [Validator doc](https://liberland-1.gitbook.io/wiki/v/public-documents/blockchain/for-validators-nominators-and-stakers)

### Contact
You can reach us at justice@liberland.org

### Intended Language of Development
We will use Rust for the blockchain backend, and Javascript / Angular for the Frontend.

## Milestones
Grand Total
Grant Level: 3;
Funds Required: 99,900 USD.

### Milestone 1: Advisory Opinion & MVP (3 months of Development)
Cost: 30,900 EUR

This milestone aims to:
- Create comprehensive documentation for the solution, detailing all its functionalities.
- Consult extensively with blockchain and game theory experts, academia, and professionals to refine the solution.
- Start implementing the draft in code, further refining the functionality through consultations.
- Create the Judges Roster backend & front end.
- Ultimately, deploy a testnet with the core MVP version of the Advisory Opinion functionality (both simple and complex).

### Milestone 2: Dispute Resolution MVP (2 months of Development)
Cost: 40,000 EUR

This milestone aims to:
- Conduct extensive legal consultations with experts. Some experts will be paid from the grant to audit our ideas on Dispute Resolution and provide improvement suggestions.
- Develop the final on-paper solution.
- Conduct another round of consultations to ensure the solution is viable.
- Program the front end and the back end.
- Deploy the solution on a testnet.
- Engage a team of in-house or outsourced professionals to test the solution extensively.

### Milestone 3: Final Phase (2 months of Development)
Cost: 20,000 EUR

This milestone aims to:
- Conduct further rounds of testing.
- Evaluate feedback from the testers.
- Initiate a phased rollout for select users in a beta program.
- Gather and analyze feedback from the testers.
- Implement the feedback.
- Launch the final product.


