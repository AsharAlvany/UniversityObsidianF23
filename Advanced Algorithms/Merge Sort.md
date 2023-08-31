Merge Sort uses the technique of [[Divide, Conquer, and Combine]] to decrease the time taken.
**Divide** by splitting into two subarrays A\[p...q\] and A\[q +1 ... r\], where q is the halfway point of A\[p...r]
**Conquer** by recursively sorting the two subarrays
**Combine** by merging the two sorted arrays to produce a single sorted array. To accomplish this step, we'll define a subprocedure MERGE(A, p, q, r) 
1. Keep splitting the array until you have reached the base case size of 1
2. Merge with neighbor array to create a sorted array by comparing the first element of both arrays and incrementing the pointer to the array that is smaller and adding that element into the new merged array until a final sorted merged array has been created 