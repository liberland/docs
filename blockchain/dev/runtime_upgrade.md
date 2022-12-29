## How to upgrade the chain

Prerequirements:  
Read substrate official documentation     
Read about webassembly and utilize "subwasm"   
Watch Alex's runtime migrations video:  https://www.youtube.com/watch?v=MQgDV37JrIY    
Read about runtime migrations: https://github.com/apopiak/substrate-migrations  

# Step 1
Add your changes to the code repository and make sure your pallets are included in the runtime. Increment the spec_version by adding +1.

Compile your node


# Step 2
Go over modifed changes made to the storage and apply storage migrations to convert the old types to the new once in the `on_runtime_upgrade` function

Note: Failing to migrate important storage changes will have a negative effect on the chain   
Note: use logging to display what migrations kicked in

# Step 3
Verify that the compiled wasm file looks good with subwasm and srtool(https://github.com/paritytech/srtool).  

# Step 4  
Compile the node locally and use the current spec_version that is deployed on chain(check polkadot.js for last upgrade in chainstate)    
Push the runtime upgrade either with as Sudo Call or as a democracy vote on your local instance.
If all is well and the pallet's interact good after the upgrade, go ahead to the next step

# Step 5 
Prep a release page for the node with the output from srtool and the hashes of the binary files, upload the wasm file aswell to the releases page.

# Step 6  
Push the upgrade on-chain  


## Links:  
https://develop--substrate-docs.netlify.app/how-to-guides/v3/storage-migrations/basics/       
https://docs.substrate.io/build/runtime-storage/           
https://docs.substrate.io/build/upgrade-the-runtime/          
