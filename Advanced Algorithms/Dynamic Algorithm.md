AVOID RECURSION
Memoization of Fibonacci
compute but don't recompute. Recursion computes a lot of the same steps many times. Memoization stores a list of known answers so there is no need to compute a recursive call seen for the second time, just look up the index.

[[Divide, Conquer, and Combine]] is best for recursive calls that do not repeat, but dynamic algorithms are best for recursion with repeated steps