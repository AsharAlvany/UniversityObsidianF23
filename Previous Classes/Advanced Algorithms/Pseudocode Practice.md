1. Write in pseudocode an algorithm with a best efficiency to insert an integer element into a sorted integer array?
``` pcode
insertIntoSortedArray(A, x, l)
	// A is the arrray, x is the element to be inserted and l is the length
	begin = 0
	end = l
	midpoint = l/2
	currentIndex = midpoint
	while (A[currentIndex + 1] >= x AND A[curentIndex - 1] <= x)
		if(A[currentIndex] > x)
			end = currentIndex
			currentIndex = (end - begin)/2 + begin
		else
			begin = currentIndex
			currentIndex = (end - begin)/2 + begin
	currentValue = x
	declare temp
	for i = currentIndex, i < l AND A[i - 1] != EMPTY, i++
		temp = A[i]
		A[i] = currentValue
		currentValue = temp
	
```
