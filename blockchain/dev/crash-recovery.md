# Chain Crash Recovery Procedure

This procedure should be performed by Liberland Blockchain Dev Team in case of chain failure that led to blocks not being produced or made it impossible to submit extrinsics.

1. Identify the hash of the block that broke the runtime:
   * If finalized, maybe chain explorer has it:
       ```
       query {
         events(first:1,filter:{section:{equalTo:"system"},method:{equalTo:"CodeUpdated"}}, orderBy:BLOCK_NUMBER_DESC) {
           nodes {
             block {
               number,
               hash,
               timestamp
             }
           }
         }
       }
       ```
    * Otherwise look for `system.CodeUpdated` event in recent blocks
2. Update JSONs (both `.raw.json` and normal) with chain specification in `specs/` to include hash of the block with `CodeUpdated` in `badBlocks`. **Notice:** this will revert all changed made in this block and all blocks that came after it, including things like transferring funds! This might cause consistency issues for exchanges, relayers, indexers that already processed these blocks in some way, especially if it was already finalized. Example:
   ```
     "badBlocks": ["0xab1f37b6306b2844320fba83152475efe06ab276cd46177da93e420079598609"],
   ```
3. Perform the standard release process to build new node binary. Remember to also build and publish new Docker image!
4. Instruct all nodes in network (validators, exchanges, bridges, RPC endpoints, users) to perform [Node Update](../for-validators-nominators-and-stakers/update.md).
5. If the removed block was already finalized, in addition to the update instruct all nodes to perform [Resync](../for-validators-nominators-and-stakers/resync.md). Make sure it's not done all at once - there should always be a healthy number of nodes that are not resyncing.
