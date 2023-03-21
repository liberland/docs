# Company registrar
## Purpose
1. Have a registry capable of storing data on the blockchain.
2. Enable the storage of company data, such as
2. a. Company Name and Trade Names,
2. b. Purpose,
2. c. Address,
2. d. Principals (Directors) and the data on them,
2. e. Founders and the data on them,
2. f. Ultimate Beneficiary Owners and the data on them,
2. g. Shareholders and the data on them.
3. Encrypt the data, and enable the following persons to see and change it:
3. a. Principals, and
3. b. Liberland Government, later, decentralized registrar.
## Blockchain
We built a new pallet that handles registrars and companies, similar to the identity pallet.
Registrars can ‘sign up’ as a registrar and can be either wallets or collectives.
Liberlands official registry will have an ID of X, whatever the ID of the official registrar when registering it with the registry pallet
Companies (wallets, collectives, DAOs) can ask to register companies with their data and request confirmation from one or more registrars.
Companies can also give edit permissions to registrars. This may be off-chain-required to be mandatory before being marked as registered (“knownGood” equivalent) by the registrar.
Company address and, optionally the registrar have edit permissions.
There are two main fields containing JSON data, “knownGood” and "requested. New company creations and edits by the company or registrar go to requested, and the registrar may copy requested data to “knownGood” after the checkup process off-chain.
Off-chain
We build a Frontend with many necessary or optional fields for company registration.
Fields can be set to “encrypted,” where the data will be saved in encrypted form, and the registrar and the company creator will share the newly generated encryption key.
Encryption key will be stored securely.
The data is stored in JSON form, like

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

Once the data is entered, it can be sent to the chain.
Registrar can confirm data on chain
There is a way to read chain data and allow edits
Land and assets
Purpose
Assets: Have a registry of real-life and metaverse assets as movable and immovable property.
Land: Have a land registry connected to the metaverse and the real-life land coordinates.
NFT-based assets and land coordinates are NFTs.
Function: Single source of truth for land ownership, real and metaverse, and for property owners.
Blockchain
Uniques collections are a set of similar NFTs, like a bored ape yacht club or “Land in Liberland”
Land and assets are NFTs of a certain collection with certain metadata on the uniques pallet.
Registrars can be wallets or possibly collectives
Collections have the registrar set as authority
Registrar can set metadata or attributes of any NFT in the collection. For example, land NFTs are grouped together into plots, and the registrar can change the “plot” attribute/metadata of the NFT.
Selling is done as normally in the uniques pallet, with the possible exception that, for example, to sell land, you can only sell TO citizens.
These functions are mostly already supported by the uniques pallet, so major code can only be written if requirements change.
Merging NFTs into a single NFT is a requirement and may need to be done via an intermediary pallet. 
There may or may not be a new land registry pallet that keeps track of plots, depending on how coding goes; see below. There may be a need for an intermediate pallet that forwards valid calls from collectives etc to the NFTs pallet
Off-chain
The frontend should read your NFTs and recognize them as land, vehicles, etc.
Users can ask the registry to register a new NFT, such as a new car, which the registry needs to mint and assign to the user. There should be a UI for this eventually.
The land registry mints initial NFTs that have grid coordinates
The land registry keeps track of which NFTs belong to which plots - data is persisted and read on the blockchain
The land registry can split NFTs by changing the coordinates of one NFT and minting another from the reduced coordinates of the other and persist that on the blockchain.
Keeping track that coordinates do not overlap is the responsibility of the land registry off-chain.
Plot ids and ownership of plots may be done off-chain or on-chain through land registry. Every NFT must belong to a user on-chain, but plots are a quality-of-life feature, so we don't have to make a pallet for it officially, but it may be a preferred solution.
There should be an API middleware that can read chain data and format them for metaverse
The Metaverse will get merged plot coordinates and other utility API endpoints
