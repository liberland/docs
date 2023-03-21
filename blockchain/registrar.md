# Company registry
## Purpose
1. Have a registry capable of storing data on the blockchain.
2. Enable the storage of company data, such as   
   a. Company Name and Trade Names,  
   b. Purpose,  
   c. Address,  
   d. Principals (Directors) and the data on them,  
   e. Founders and the data on them,  
   f. Ultimate Beneficiary Owners and the data on them,  
   g. Shareholders and the data on them.  
3. Encrypt the data, and enable the following persons to see and change it:   
   a. Principals, and  
   b. Liberland Government, later, decentralized registrar.  
## Blockchain
4. We built a new pallet that handles registrars and companies, similar to the identity pallet.
5. Registrars can ‘sign up’ as a registrar and can be either wallets or collectives.
6. Liberlands official registry will have an ID of X, whatever the ID of the official registrar when registering it with the registry pallet
7. Companies (wallets, collectives, DAOs) can ask to register companies with their data and request confirmation from one or more registrars.
8. Companies can also give edit permissions to registrars. This may be off-chain-required to be mandatory before being marked as registered (“knownGood” equivalent) by the registrar.
9. Company address and, optionally the registrar have edit permissions.
10. There are two main fields containing JSON data, “knownGood” and "requested. New company creations and edits by the company or registrar go to requested, and the registrar may copy requested data to “knownGood” after the checkup process off-chain.
## Off-chain
11. We build a Frontend with many necessary or optional fields for company registration.
12. Fields can be set to “encrypted,” where the data will be saved in encrypted form, and the registrar and the company creator will share the newly generated encryption key.
13. Encryption key will be stored securely.
14. The data is stored in JSON form, like

{
	companyName: {
	Value: “Company LTD”
	Encrypted: false
},
ultimateBeneficiaries: [
	{
		Name: John Doe
		WalletAddress: blablabla
		Encrypted: false
},
{
		Name: fwrtreyter564fdyrytuh
		WalletAddress: 6543b6bhgrfuiikyuyurty
		Encrypted: true
}
]
}

15. Once the data is entered, it can be sent to the chain.
16. Registrar can confirm data on chain
17. There is a way to read chain data and allow edits
# Land and assets Registry
## Purpose
18. **Assets:** Have a registry of real-life and metaverse assets as movable and immovable property.
19. **Land:** Have a land registry connected to the metaverse and the real-life land coordinates.
20. NFT-based assets and land coordinates are NFTs.
21. Function: Single source of truth for land ownership, real and metaverse, and for property owners.
## Blockchain
22. Uniques collections are a set of similar NFTs, like a bored ape yacht club or “Land in Liberland”
23. Land and assets are NFTs of a certain collection with certain metadata on the uniques pallet.
24. Registrars can be wallets or possibly collectives
25. Collections have the registrar set as authority
26. Registrar can set metadata or attributes of any NFT in the collection. For example, land NFTs are grouped together into plots, and the registrar can change the “plot” attribute/metadata of the NFT.
27. Selling is done as normally in the uniques pallet, with the possible exception that, for example, to sell land, you can only sell TO citizens.
28. These functions are mostly already supported by the uniques pallet, so major code can only be written if requirements change.
29. Merging NFTs into a single NFT is a requirement and may need to be done via an intermediary pallet. 
30. There may or may not be a new land registry pallet that keeps track of plots, depending on how coding goes; see below. There may be a need for an intermediate pallet that forwards valid calls from collectives etc to the NFTs pallet
## Off-chain
31. The frontend should read your NFTs and recognize them as land, vehicles, etc.
32. Users can ask the registry to register a new NFT, such as a new car, which the registry needs to mint and assign to the user. There should be a UI for this eventually.
33. The land registry mints initial NFTs that have grid coordinates
34. The land registry keeps track of which NFTs belong to which plots - data is persisted and read on the blockchain
35. The land registry can split NFTs by changing the coordinates of one NFT and minting another from the reduced coordinates of the other and persist that on the blockchain.
36. Keeping track that coordinates do not overlap is the responsibility of the land registry off-chain.
37. Plot ids and ownership of plots may be done off-chain or on-chain through land registry. Every NFT must belong to a user on-chain, but plots are a quality-of-life feature, so we don't have to make a pallet for it officially, but it may be a preferred solution.
38. There should be an API middleware that can read chain data and format them for metaverse
39. The Metaverse will get merged plot coordinates and other utility API endpoints
