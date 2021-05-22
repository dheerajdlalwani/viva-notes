# Greedy Approach

- locally optimal solution, hoping collectively it will give an optimal solution
- greedy algorithms do not always yield optimal solutions
- but for many problems they do.





- ## Dijkstra

  - Given a graph and a source vertex in the graph, find shortest paths from source to all vertices in the given graph.
  - Dijkstra’s algorithm is very similar to Prim’s algorithm for minimum spanning tree.
  - Like Prim’s MST, we generate a SPT (shortest path tree) with given source as root. 
  - We maintain two sets, one set contains vertices included in shortest path tree, other set includes vertices not yet included in shortest path tree. 
  - At every step of the algorithm, we find a vertex which is in the other set (set of not yet included) and has a minimum distance from the source.
  - Below are the detailed steps used in Dijkstra’s algorithm to find the shortest path from a single source vertex to all other vertices in the given graph. 

- ### Algorithm 
  - Create a set sptSet (shortest path tree set) that keeps track of vertices included in shortest path tree, i.e., whose minimum distance from source is calculated and finalized.Initially, this set is empty. 
  - Assign a distance value to all vertices in the input graph. Initialize all distance values as INFINITE. Assign distance value as 0 for the source vertex so that it is picked first. 
  - While sptSet doesn’t include all vertices 
    - Pick a vertex u which is not there in sptSet and has minimum distance value. 
    - Include u to sptSet.
    - Update distance value of all adjacent vertices of u. To update the distance values, iterate through all adjacent vertices. 
    - For every adjacent vertex v, if sum of distance value of u (from source) and weight of edge u-v, is less than the distance value of v, then update the distance value of v. 

- ## Time complexity
  - O(V^2)
  - O(E log V)

- ## Drawbacks
  - Dijkstra’s algorithm doesn’t work for graphs with negative weight cycles, it may give correct results for a graph with negative edges. 
  - For graphs with negative weight edges and cycles, Bellman–Ford algorithm can be used

