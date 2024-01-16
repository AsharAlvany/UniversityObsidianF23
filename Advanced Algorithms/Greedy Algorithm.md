Similar to dynamic programming and is used for optimization. Optimize sub-problems to optimize the main problem
Choose an activity that leaves the resource available for as many other activities as possible

If a subproblem $S_k$ is non empty and let $a_m$ be the activity that has the earliest finish time in $S_k$ then $a_m$ is included in some optimal solution

Let $A_k$ be a maximum size subset of mutually compatible activities of $S_k$

In solutions $A_k$ let $a_j$ be the activity with the earliest finish time

### 0-1 Knapsack Algorithm
Greedy choice does not always work, for this problem we would use something similar to the rod-cutting algorithm (dynamic programming)

### Fractional Knapsack Algorithm
Greedy choice DOES work and it is more efficient than the dynamic algorithm problem

### Huffman Codes
Form a priority queue, delete the 2 minimum and put them into a binary tree with the root being the sum of the two minimum, add it back into the priority queue