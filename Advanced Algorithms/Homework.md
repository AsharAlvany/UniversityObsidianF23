1. Check to see if the diagonal matrix goes below zero
3. edge disjoint paths, find the maximum flow, run maximum flow algorithm
4. Transform each vertex to multiple edges (each vertex will become two edges of capacity n each). Construct a new graph with additional vertices and edges. If the max flow is at least m then the escape is possible. Ford-Fulkerson's algorithm