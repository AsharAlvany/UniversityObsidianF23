Fetch, Retrieve: To get the information back from the database
Traverse, Search, Iteration: Going through the table once
Nested: Going through the second table the number of entries of the first table
SQL is a language which means that a scanner identifies the tokens and the parser checks the syntax of the query
Queries are measured in **block accesses**
Step 1: For a given expression in a query...multiple equivalences exist. A tree of possible combinations will begin to form.
Step 2: Assign a cost value (block access, time, etc) as a quantitative measure
Step 3: Follow each combination to find the cheapest cost
Step 4: Create a list of the best possible combinations (Query Block)
Step 5: Combine Query blocks as terms and files merge.
![[Pasted image 20231107180816.png]]
Nested Loop Join: Cost=blocks in R + (blocks in R)(blocks in S)+JC
