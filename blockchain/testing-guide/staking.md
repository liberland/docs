##Staking

Any account with liquid LLD is allowed to stake. dAPP frontent should fully support all necessary staking actions, but block explorer can also be used.

Navigate to "staking" tab in dApp to access staking actions.

"Staking" tab has 2 modes, for validators and nominators. 

###Switching staking mode
Staking mode can be switched by clicking the "Switch to Validator/nominator" button.

Switching from validator to nominator will deactivate the validator.

Switching from nominator to validator requires setting up a validator and having its session keys.

###Adding stake
Click "Add stake". Enter a valid number. After signing the transaction, amount currently staked should increase by amount staked.

Click "Add stake". Enter an invalid number (more than your total LLD). Clicking stake should not do anything.

###Changing rewards destination
Click "change destination". Increase stake will send payout rewards to increase stake, while deposit in account will send payout to liquid LLD rewards in account. 

###Payout rewards
Every couple of eras, staking and validating rewards will be ready. They can be paid out by clicking on "Payout" button.

This may require you to sign multiple transactions, as its paying out every era.

If rewards destination is staked, the Currently staked amount should increase by the amount of LLD rewards pending.

If rewards destinatiion is deposit in account, the Liquid LLD balance in wallet should increased by the amount of LLD rewards pending

###Unstaking
Click "Unstake" and enter the amount you with to unstake. After signing transaction, a new "currently unstaking" section will appear, with the time and amount of unstaking.

TODO what happens when the era is ready? Is it automatic ?

###Nominating
You need to have some currently staked LLD to nominate.

You can select validators you wish to nominate by ticking the "Nominated by me" boxes next to validators. 
After clicking "Update nominations" and signing the transaction, Your nominations should match selected validators. This can be verified by refreshing the page.

Selecting nomination targets as a validator will also deactivate your validator. dAPP should prevent you from updating nominations when running in validator mode.

TODO: What happens if a nominator has max allowed validators and people continue nominating it?

###Commissions

TODO how to test commissions of validators
