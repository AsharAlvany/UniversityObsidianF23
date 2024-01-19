**Dijkstra**'s - Node to node. Single source, shortest paths to all the destinations (only positive edges, greedy algorithm, priority queue, cloud of the known)
1. Start node has a cost of 0
2. Pick all the closest unknown vertices and add them to the “cloud” of known vertices
3. Update distances for nodes with edges from v
4. Go to the node with the shortest total path, mark it as known and start from 2

Example:
![[Pasted image 20231024103405.png]]
**Bellman Ford** - Node to node. Single source, shortest paths to all the destinations (both positive and negative edges)
![[Pasted image 20231024103534.png]]![[Pasted image 20231024103552.png]]