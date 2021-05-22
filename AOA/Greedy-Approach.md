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


- ## Minimum Cost Spanning Trees

  - Spanning-tree is a set of edges forming a tree and connecting all nodes in a graph. 
  - The minimum spanning tree is the spanning tree with the lowest cost (sum of edge weights).
  - Also, it’s worth noting that since it’s a tree, MST is a term used when talking about undirected connected graphs.
 


- ## Prim's Algorithm
  - Prim's (also known as Jarník's) algorithm is a greedy algorithm that finds a minimum spanning tree for a weighted undirected graph.- This means it finds a subset of the edges that forms a tree that includes every vertex, where the total weight of all the edges in the tree is minimized.
  - Basically, Prim’s algorithm is a modified version of Dijkstra’s algorithm. 
  - First, we choose a node to start from and add all its neighbors to a priority queue.
  - After that, we perform multiple steps. In each step, we extract the node that we were able to reach using the edge with the lowest weight. Therefore, the priority queue must contain the node and the weight of the edge that got us to reach this node. Also, it must sort the nodes inside it based on the passed weight.
  - For each extracted node, we add it to the resulting MST and update the total cost of the MST. Also, we add all its neighbors to the queue as well.
  - In order to obtain a better complexity, we can ensure that each node is presented only once inside the queue. For example, we can use a function addOrUpdate that takes the node with the weight and the edge that led us to this node.
  - In case the node was already inside the queue, and the new weight is better than the stored one, the function removes the old node and adds the new one instead. Otherwise, if the node isn’t inside the queue, it simply adds it along with the given weight.
  


- ## Kruskal's Algorithm
  - Kruskal's Algorithm is used to find the minimum spanning tree for a connected weighted graph. 
  - The main target of the algorithm is to find the subset of edges by using which, we can traverse every vertex of the graph
  - The main idea behind the Kruskal algorithm is to sort the edges based on their weight. After that, we start taking edges one by one based on the lower weight.
  - In case we take an edge, and it results in forming a cycle, then this edge isn’t included in the MST. Otherwise, the edge is included in the MST.
  

- ## Prim's VS Kruskal's 

  - K : Offers control over the resulting MST
  - P : Controlling the MST might be a little hard
  - K : Easy to implement
  - P : Hard to implement
  - K : Disjoint sets
  - P : Priority Queue
  - K : TC = O(E.log(V))
  - P : TC = O(E + V.log(V))

- As we can see, the Kruskal algorithm is better to use regarding the easier implementation and the best control over the resulting MST. However, Prim’s algorithm offers better complexity.
