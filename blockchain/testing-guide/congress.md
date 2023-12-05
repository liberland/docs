###Congress

####Applying for congress
If user is a citizen who is not in the congress, user can apply for congress in Congress tab and clicking Apply for congress.

If a non citizen applies for congress, the request will fail.

If a citizen applies for congress, he will appear as an eligible candidate under the Voting -> Congressional assembly tab.


####Congress actions
Congress members can propose congress motions. Some of these are easy to make in the frontend.

As a congressman, under Congress->Overview, there should be buttons to propose international treaty, referendum, and create spending.

Clicking on propose international treaty and referendum will open a legislation proposal. Submitting a congress legislation proposal will create a congress motion that can be seen in Congress -> Motions tab.

Clicking on Create new spending and submitting a spending proposal will create a congress spending motion, that can be seen in Congress -> Motions tab.

Motions can be seen under Congress-> Motions tab. Congressmen can vote aye or nay for a motion. The one who proposed the motion automatically votes aye.

If congressman has voted aye already, voting nay will remove his vote from the aye counter and add a vote in the nay counter

If congressman didnt vote already, he can vote aye or nay and this will increase the number of respective aye or nay votes.

If number of aye votes reaches a sufficient number, a motion can be executed

TODO (how to execute motions)

If number of nay votes reaches a sufficient number, motion can be struck down

TODO (how to strike down motions)

(TODO not sure)If a legislation motion is passed, it will create a referendum that can be seen under Voting->Referenda

(TODO not sure)If an international treaty is passed, it will automatically create a new legislation that can be seen under Legislation->International Treaties

(TODO NOT SURE)If a spending motion is passed, the LLM funds will be moved from congress account into the account specified in motion. 
You can check congress account finances before and after passing the motion under Offices->Government finances. Also check the destination account.
If send to politipool is selected instead of send liquid, the funds will arrive in politipooled form.

(TODO not sure) LLD treasury how is it filled?

Congress can send LLD from treasury. Under Congress -> LLD Treasury, clicking on propose spend and submitting destination and amount will create a motion.

(TODO not sure)If LLD spend motion is passed, the funds are moved from treasury into the destination/beneficiary account immediately

(TODO not sure) what happens at the end of the spend period ?

It is possible to create legislation 'amend' and 'repeal' congress motions directly through legislation browser in legislation tab. Passing this motion will create a referendum to repeal or amend respectively
