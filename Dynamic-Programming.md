# Dynamic Programming

- find all approaches, pick best one
- more time consuming than greedy
- recursive formulas, not recursion
- mostly iteration
- both methods use stored results to build the final solutiom

- ## Principal of optimality
  - A problem can be solved by taking sequence of decisions
  - A problem is said to satisfy the Principle of Optimality if the subsolutions of an optimal solution of the problem are themesleves optimal solutions for their subproblems.

- ## Tabulation vs Memoizatiom
 
  - ### Memoization
    - Memoization ensures that a method doesn't run for the same inputs more than once by keeping a record of the results for the given inputs (usually in a hash map).
    - for example, a simple recursive method for computing the nth Fibonacci number
    - top down 
    - recursive

  - ### Tablulation
    - Rather than starting from the main problem, we start solving the sub-problems and move our way up. The tabulation approach is done by filling up a table of n-dimension, hence the name tabulation.
    - for example, an iterative method to for computing Fibonacci number.
    - bottom-up approach
    - tabulation avoids recursion, iterative approach


- ## Multistage Graph
  - directed, weighted graph
  - resource allocation
  - minimum cost, [minimization problem]
  - tabulation
  - cost(i,j) = min { c(j,l) + cost(i+1, l) }
  - i = stage
  - j = vertex number

- ## All pairs shortest path
  - Floyd-Warshall algorithm is used to find all pair shortest path problem from a given weighted graph. As a result of this algorithm, it will generate a matrix, which will represent the minimum distance from any node to all other nodes in the graph.
  - Time Complexity = O(n^3), n = number of vertices

```
Begin
   for k := 0 to n, do
      for i := 0 to n, do
         for j := 0 to n, do
            if cost[i,k] + cost[k,j] < cost[i,j], then
               cost[i,j] := cost[i,k] + cost[k,j]
         done
      done
   done
   display the current cost matrix
End
```





































