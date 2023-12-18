# Senate guide

This is a guide for Senators on how to perform senate actions.

## Propose motion

### Spend from treasury

1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/extrinsics)
2. Go to Developer -> Extrinsics -> `senate` -> `propose(...)`
    * `threshold`: 51% * number of senate members, round up. Examples:
        * 3 senate members - threshold = 2
        * 4 senate members - threshold = 3
        * 5 senate members - threshold = 3
    * `proposal`:
        * `llm` `treasuryLlmTransferToPolitipool(...)` (or `treasuryLlmTransfer` for liquid LLM or `treasuryLldTransfer` for LLD)
        * `toAccount`: recipient of LLM
        * `amount`: LLM in grains, so 1 LLM = `1000000000000` (12 zeros)
    * `lengthBound`: `54`
 
### Cancel referendum
 
1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/extrinsics)
2. Developer -> Extrinsics -> `senate` -> `propose(...)`
    * `threshold`: 51% * number of senate members, round up
    * `proposal`:
        * `democracy` `emergencyCancel`
        * `refIndex`: index of referendum to cancel
    * `lengthBound`: `10`

### Cancel proposal
 
1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/extrinsics)
2. Developer -> Extrinsics -> `senate` -> `propose(...)`
    * `threshold`: 51% * number of senate members, round up
    * `proposal`:
        * `democracy` `cancelProposal`
        * `refIndex`: index of referendum to cancel
    * `lengthBound`: `7`

## Voting on motions

### Get hash of proposal

1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/chainstate)
2. Developer -> Chain state -> `senate` -> `proposals()`
3. Click `+` button
4. The hash is the string that starts with `0x`.

### Check details

1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/chainstate)
2. Developer -> Chain state -> `senate` -> `proposalOf(h256)`
    * Put the hash from previous step.
3. Click `+` button
4. Make sure the section, method and args match what you expect.

### Vote

1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/extrinsics)
2. Developer -> Extrinsics -> `senate` -> `vote(...)`
    * `proposal`: hash from previous step
    * `index`: `0`
    * `approve`: `yes`

## Execution

After at least `threshold` number of senators voted yes, anyone can execute the motion:

1. Visit [Polkadot.js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fmainnet.liberland.org#/extrinsics)
2. Developer -> Extrinsics -> `senate` -> `close(...)`
    * `proposalHash`: hash from previous step
    * `index`: `0`
    * `proposalWeightBound`
        * `refTime`: `1307232`
        * `proofSize`: `0`
    * `lengthBound`: same as in Propose motion section