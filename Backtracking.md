# Backtracking

- uses DFS
- brute force method
- generate a state space tree
- recursive method
- bounding function helps limit the number of nodes to be checked

  - ## Live node 
    - is a generated node for which all of the children have not been generated yet

  - ## E-node 
    - is a live node whose children are currently being generated or explored
  - ## Dead node 
    - is a generated node that is not to be expanded any further
    - all the children of a dead node are already generated
    - live nodes are killed using a bounding function to make them dead nodes
  - ## State Space Tree
    - We assume that a solution to the problem can be constructed from component solutions, xi. 
    - So the solution can be expressed as (x1, x2,...,xn) and a partial solution is (x1, x2,...,xi) where i < n. A state-space tree is the tree of the construction of the solution from partial solution starting with the root with no component solution (...).
    - The tree is typically search depth first and the nodes are implicit meaning they are generated as need. A node is said to be promising if the partial solution is still feasible. 
    - Any time the partial node becomes infeasible the node, called non-promising the branch will no longer be pursued. 
    - So, the algorithm backtracks to the first promising node and explores the other branches of the state-space tree.


```
Algorithm Backtrack(X[1...i])
    if X[1...i] is a solution then write X[1...i]; exit
    else
        for each X[1...i+1] that is promising do
            Backtrack(X[1...i+1])
```



- ## N-Queens Problem 

  - The problem is to configure n queens on an nxn checkered board so that no queen can attack another queen. 
  - Naturally each queen must be on a unique row, call the queen 1 the queen on row 1. We recursively place the queens on the next square on its row. 
  - The efficiency of backtracking relies on pruning tree. Sometimes symmetry in the problem can eliminate branches early. 
  - For example, in the n-queen, problem we only need consider the first n/2 positions.

Illustrate with 4 queens 

Another trick is to trick is to presort the set in the subset sum problem.

 

Another trick is to pre-assign values in the partial solution as we did in the Hamiltonian circuit problem.


- ## Sum of Subsets
  - Subset sum problem is to find subset of elements that are selected from a given set whose sum adds up to a given number K. 
  - We are considering the set contains non-negative values. 
  - It is assumed that the input set is unique (no duplicates are presented).


- ## Graph Coloring [mColoring decision problem]
  - time complexity without bounding function = number of nodes generated = (colors)^(n+1)
  - time complexity with bounding function = (colors)^(n)
  - Minimum colors to be used - [mColoring Optimization Problem]
- ## Hamiltonian Cycle
  - start at any vertex
  - visit all vertices
  - but strictly once
  - return back to the starting vertex
  - NP Hard problem (Exponential Time taking problem)
  - must not have articulation points
  - must not have pendant vertex
  - time complexity = n^n
  - ### bounding function
    - no duplicates
    - must have an edge back from previous vertex
    - if on last vertex, must have edge to first
