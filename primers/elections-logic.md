# Liberland Congress Elections Logic

## Congress

Liberland congress elections use Phragmen's algorithm. This is the same algorithm used for choosing Liberland Blockchain validators and their stakes. The takes Liberland merits (LLM) into account and fills the empty eats while trying to:

1. Maximize the total amount of LLM backing all winners.
2. Maximize the LLM behind the last elected congresspeople.
3. Minimize the variance of the LLM backing the winners.

Phragmen's is complex and hard to predict using "common sense", but important aspects of Phragmen's in the case of Liberland are:

1. The **order of votes does not matter** for winning a congress seat. If one votes for Candidate A and Candidate B, they express an equal preference of either candidate being elected to Liberland congress,
2. If one votes with 5000 LLM for three candidates (Candidates A, B and C), but one of them (Candidate B) doesn't get elected to congress, the LLM is split among the candidates that were elected (A & C). This allows more freedom in which candidates are chosen as it leaves no reason to not vote for candidates that are unlikely to win, and votes aren't "wasted" the way voters feel they are "wasted" in traditional first-past-the-post systems.
3. The algorithm tries to minimize the LLM variance backing each candidate, and so it chooses how to split the votes. If one votes with 5000 LLM and two of the selected are elected, the algorithm might choose to allocate 1000 LLM to Candidate B and 4000 LLM to Candidate C - whatever is better to minimize the variance and maximize the LLM behind the last congressperson to be elected. 

There are detailed documents on [Phragmen's available here](https://wiki.polkadot.network/docs/learn-phragmen).

Voters have no say in this allocation, however it does mean that Phragmen's algorithm is not ideal for choosing the Prime Member.

## Prime Member

Prime member is chosen using a [weighted Borda Count](https://en.wikipedia.org/wiki/Borda_count).

Here, the order of votes matters. If one votes for Candidate C as first preference and Candidate A as second preference (i.e. a ranked ballot), Candidate C will receive 16 times this voter's LLM vote, and Candidate A will receive 15 times this voter's LLM vote. The candidate with highest score is elected Prime Member.