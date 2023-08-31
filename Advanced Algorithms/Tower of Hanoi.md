Uses [[Divide, Conquer, and Combine]]
1. Must only move one disc at a time
2. Must place the disc on tower
3. Must place the disc such that no smaller disc is below it
#### Pseudocode
```python
def Hanoi(n, src, dst, temp){
	if (n > 0)
		Hanoi(n-1,src,tmp,dst)
		Move disc n from src to dst
		Hanoi(n-1,tmp,dst,src)
}
```
---
#### Analyzing
1. How many recursive calls are there in the algorithm?
	- 2
2. What are the problem sizes of each recursive call?
	- n-1, n-1
4. How much time is spent on dividing?
	- We don't divide or combine the problem
5. How much time is spent combining the problem?
$$T(n) = 2T(n-1) + O(1)$$
---
