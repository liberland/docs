###Politics

All political actions are locked to citizens, who are not currently unpooling, who have at least 5000 politipooled LLM. Attempting any actions as a non citizen should not succeed.

####Voting for congress
Under Voting->Congressional assemble, one can vote for candidates for next congress. There are 2 rows, "Eligible candidates" and "My preference ordered votes"

Eligible candidates can be selected and moved to My preference ordered votes by clicking on the button, and after signing a transaction, verify everything is saved correctly by refreshing the page.

My preference ordered votes can be unvoted, by clicking the x button which will move the candidate into the eligible candidates row, and after signing a transaction, verify everything is saved correctly by refreshing the page.

My preference ordered votes can be shuffled with the buttons, which will change the preference order and after signing a transaction, verify everything is saved correctly by refreshing the page.

####Delegating to congress

You can delegate your votes to acting congressment under Voting->Congressional assembly by clicking the "delegate" button. Signing transaction and refreshing the page should show the 'Delegated' button.

When delegating, it is not possible to vote on Voting->Referendum directly, instead of vote buttons there will be a message to undelegate

When delegating, there will be a message on on Voting->Referendum "Delegating to:<Delegation target>"

(TODO Test)If people are delegating to you (TODO how to see how many people and LLMs?) you votew with the sum of your staked LLM and the sum of staked LLM of everyone delegating into you. Test this 

To stop delegating, on Voting->Referendum click on "undelegate" button. This should reenable referendum voting and congressmen delegation buttons

####Proposing referendums

All referendum proposals will fail if the user is not a full 5000LLM citizen

All referendum proposals will cost 100LLM

In Voting->Referendum Click on propose tp create a legislation proposal referendum, 
fill out the information, and on submit, Voting->Referendum->(scroll down) proposals should have the proposal of a referendum.
Also check that 100LLD has been paid on successful referendum propose

Proposals can be endorsed, but that is a vestigial feature that will be removed, as unlike polkadot all referendum proposals will become referendums.

All proposals will be identified by year and index. Check that every new proposal increments the index, like 2023/1, then 2023/2 etc...

Proposals created through the dApp should have human readable content

It is possible to create 'amend' and 'repeal' proposals directly through legislation browser in legislation tab


####Voting for referenda

See referenda at Voting->Referenda

Referendums should have a Read discussion link, and human readable title and details

When non citizens try to vote, it will result in error/warning

Voting yes will update the aye/nay counter by the same amount as your politipooled LLM

Voting nay will update the aye/nay counter by the same amount as your politipooled LLM

Changing votes is possible and will update the counter accordingly


####Referendum results

When referendum fails nothing happens

When a referendum is successful, it is in dispatch for a while before executing

When referendum to pass a legislation is successful, new legislation will appear in the Legislation tabs

When a referendum to repeal legislation is successful, the legislation will disappear from the legislation tab

When a referendum to amend a legislation is suffessful, the content will change in the legislation tab

All these cases are also valid for individual legislation section.

(TODO referendum percentages for constitution and other limits)

####Vetos

A citizen can cast veto for legislation or legislation section in legislation tab. Doing so will increment the veto number.

A citizen can revert veto for legislation or section he already cast a veto, and doing so will decrease the veto number.

The veto number shows 2 numbers, the first is number of vetos and second is number of total eligible citizens.

(TODO) veto can be executed once more than 50 % of citizens cast veto for a legislation or section.


####Legislation

Legislation can be browsed under the Legislation tab.

Citizens can cast vetos, proposals to repeal and proposals to amend in legislation browser.

Legislation has sections, and each section can be vetoes or repealed or amended individually.
