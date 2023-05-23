# Liberland Blockchain - the Judiciary

## Introduction
### Liberland Smart Chain
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

#### Absence of Authority
The current crypto sphere, rife with scams and deceitful actors, offers minimal protection against these malevolent forces. Recourse against hackers, fraudsters, and unscrupulous service providers primarily occurs outside the system, relying on state judiciaries and other external mechanisms.

Crypto represents a landscape of opportunity juxtaposed with significant risk. It's saturated with disclaimers about using the service "as-is" and providers distancing themselves from liability for secondary damages caused by other users. Given this status quo, victims often find themselves in an unforgiving predicament, with limited avenues for seeking justice.

Further aggravating the situation is the inherent bias of these systems towards the astute trickster. With actions taking precedence over intentions and a void of authority, systems inherently favour the cunning over the honest. This perception of built-in injustice deters potential investors, particularly businesses that typically exhibit lower risk tolerance.

### Unfamiliarity: The Cryptic Nature of Current Solutions
Current blockchain judiciary solutions suffer from their highly specialized nature. These systems, primarily designed to handle technical issues, fail to resonate with a broader audience. While solutions like Kleros and Ulex strive for a more generalist approach, they still remain largely alien to the general public.

Relying on complex mathematical algorithms and game theory might be sound in principle, but these concepts are foreign to most individuals. People tend to trust the judgement of "experts" in legal matters rather than abstract mathematical models. Recognizing this gap, we aim to devise a novel solution that bridges the divide.

## Our Solution: An On-Chain Judiciary System

### Goals
Our solution is designed to:
- Develop an on-chain system capable of acting on behalf of a party without their explicit permission.
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
- **Jury**: Cryptographically anonymized users who vote on the merit of arguments based on game theory, aiming to align with the majority vote (Schelling point), representing the system's decentralized element.

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

## Impact and Functionality

### Impact
With our solution, we're introducing a centralized-decentralized entity capable of determining the intentions behind actions. This entity will have the power to overturn transactions by reversing them or creating opposing transactions. In situations involving malicious or bad faith intentions, the judiciary will evaluate and, if necessary, counteract such actions.

### Tokenomics
Our Judges will be professionals whose fees are determined by the Collateral - the loser pays. In cases divided into several Claims, the loser of each claim pays.

For those wishing to participate in a Jury, they can convert their LLD and liquid LLM into LJT (Liberland Jury Tokens). Jurors will "bet" JT based on the Focal Point game, with majority voters receiving the bets of the losing minority, distributed proportionately.

JTs will be locked and can only be converted back into LLD / LLM on the 15th of each month (the Ides). Users must designate prior to the Ides which of their JT they wish to transfer.

### Functionality: Advisory Opinion
If a party wishes to obtain the Court's opinion on a particular legal, technical or factual matter, even in the absence of a dispute, the system will offer two types of Advisory Opinions:

- **Simple Advisory Opinion**: This is a yes/no binary question. The party formulates the question, provides reasoning, pays a fee, and presents the question to the Jury. They then wait for the Jury's decision and can either accept or reject it. If they reject it, they can pay an additional fee to re-run the game up to three times to view the opinions of three different Juries.
- **Complex Advisory Opinion**: The party pays a higher fee, formulates a complex question, and chooses a Judge. The Judge then formulates the Opinion on the points of the question. The party waits for the Jury's decision and, similar to a Simple Advisory Opinion, they can accept or reject it, paying an additional fee to re-run the game up to three times if they choose to reject it.

## Applications and Extensions
Beyond dispute resolution and advisory opinions, we plan to extend the use of this system to other areas, such as Administrative Decisions on-chain.

For example, the process of granting or denying citizenship could be complemented with our decentralized system. The Ministry of Internal Affairs, Citizenship Agency would work with the Citizen applicant through steps such as proof of commitment (locked stake), KYC, and Citizenship Interview. 

Afterward, they would create a brief report on the results and a more detailed report on the applicant's background. The Jury would then Confirm or Reject the applicant. A Confirmed applicant becomes a Citizen, while a Rejected one must wait one year before re-applying. 

This is not an exhaustive list of potential applications for our system. We encourage other builders to explore further expansions.

## Decentralized Registers
Along with the previous system, we can also decentralize our property register operations. The relevant Ministry would create an entry and add background information, which is generally straightforward or automated. 

The Jury then makes a final Confirmation or Rejection. These decisions will mostly be affirmations. Hence they are considered low-stakes/low gains games.

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


