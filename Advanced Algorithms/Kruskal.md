![[Drawing 2023-11-01 18.45.48.excalidraw|1000]]
Step 1:
Sort all edges into an array A in ascending order. Declare an empty array B.
Step 2:
Take all vertices into a 2 dimensional array of vertices, called C where each vertex is its own array
Step 3:
For each element in A,
if the two vertices comprising that edge are in two separate arrays in C, then add that edge into B and merge the two arrays containing the two vertices in A in C
if the two vertices comprising that edge are in the same array, don't do anything and continue to the next element in A
Step 4:
Return A, it now contains the minimum spanning tree for the graph!
### Psuedocode:
![[Pasted image 20231101225648.png]]
Running Time: O(****(V+E)lg*v)