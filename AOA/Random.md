# Iteration vs Recursion

- R : A program is called recursive when an entity calls itself.
- I : A program is call iterative when there is a loop (or repetition)
- R : Finding the Time complexity of Recursion is more difficult than that of Iteration. Time complexity of recursion can be found by finding the value of the nth recursive call in terms of the previous calls. Thus, finding the destination case in terms of the base case, and solving in terms of the base case gives us an idea of the time complexity of recursive equations.
- I : Time complexity of iteration can be found by finding the number of cycles being repeated inside the loop.
- R : short code, huge time complexity
- I : Long code, smaller time complexity





# Dijkstra VS Floyd Warshall 


- Dijkstra’s Algorithm is one example of a single-source shortest or SSSP algorithm, i.e., given a source vertex it finds shortest path from source to all other vertices.

- Floyd Warshall Algorithm is an example of all-pairs shortest path algorithm, meaning it computes the shortest path between all pair of nodes.

## Time Complexities :

- Time Complexity of Dijkstra’s Algorithm: O(E log V)
- Time Complexity of Floyd Warshall: O(V^3)

## Other Points:

- We can use Dijskstra’s shortest path algorithm for finding all pair shortest paths by running it for every vertex. But time complexity of this would be O(VE Log V) which can go (V3 Log V) in worst case.
- Another important differentiating factor between the algorithms is their working towards distributed systems. Unlike Dijkstra’s algorithm, Floyd Warshall can be implemented in a distributed system, making it suitable for data structures such as Graph of Graphs (Used in Maps).
- Lastly Floyd Warshall works for negative edge but no negative cycle, whereas Dijkstra’s algorithm don’t work for negative edges.


# Optimal Algorithm

- An algorithm can be said to be optimal if the function that describes its time complexity in the worst case is a lower bound of the function that describes the time complexity in the worst case of a problem that the algorithm in question solves.




# Dynamic Programming VS Dynamic Programming

- Divide and Conquer works by dividing the problem into sub-problems, conquer each sub-problem recursively and combine these solution

- Dynamic Programming is a technique for solving problems with overlapping subproblems. Each sub-problem is solved only once and the result of each sub-problem is stored in a table ( generally implemented as an array or a hash table) for future references. These sub-solutions may be used to obtain the original solution and the technique of storing the sub-problem solutions is known as memoization.



## Dynamic Programming Prerequisites/Restrictions
As we’ve just discovered there are two key attributes that divide and conquer problem must have in order for dynamic programming to be applicable:

- Optimal substructure — optimal solution can be constructed from optimal solutions of its subproblems

- Overlapping sub-problems — problem can be broken down into subproblems which are reused several times or a recursive algorithm for the problem solves the same subproblem over and over rather than always generating new subproblems

Once these two conditions are met we can say that this divide and conquer problem may be solved using dynamic programming approach.



##  Greedy versus dynamic programming
- Because the optimal-substructure property is exploited by both greedy and dynamic-programming strategies, one might be tempted to generate a dynamic-programming solution to a problem when a greedy solution suffices, or one might mistakenly think that a greedy solution works when in fact a dynamic-programming solution is required. 
- To illustrate the subtleties between the two techniques, let us investigate two variants of a classical optimization problem.

- The 0-1 knapsack problem is posed as follows. A thief robbing a store finds n items; the ith item is worth vi dollars and weighs wi pounds, where vi and wi are integers. 
- He wants to take as valuable a load as possible, but he can carry at most W pounds in his knapsack for some integer W. What items should he take? (This is called the 0-1 knapsack problem because each item must either be taken or left behind; the thief cannot take a fractional amount of an item or take an item more than once.)

- In the fractional knapsack problem, the setup is the same, but the thief can take fractions of items, rather than having to make a binary (0-1) choice for each item. 
- You can think of an item in the 0-1 knapsack problem as being like a gold ingot, while an item in the fractional knapsack problem is more like gold dust.

- Both knapsack problems exhibit the optimal-substructure property. For the 0-1 problem, consider the most valuable load that weighs at most W pounds. 

- If we remove item j from this load, the remaining load must be the most valuable load weighing at most W - wj that the thief can take from the n - 1 original items excluding j. 

- For the comparable fractional problem, consider that if we remove a weight w of one item j from the optimal load, the remaining load must be the most valuable load weighing at most W - w that the thief can take from the n - 1 original items plus wj - w pounds of item j.

- Although the problems are similar, the fractional knapsack problem is solvable by a greedy strategy, whereas the 0-1 problem is not. 

- To solve the fractional problem, we first compute the value per pound vi/wi for each item. Obeying a greedy strategy, the thief begins by taking as much as possible of the item with the greatest value per pound. 

- If the supply of that item is exhausted and he can still carry more, he takes as much as possible of the item with the next greatest value per pound, and so forth until he can't carry any more. 

- Thus, by sorting the items by value per pound, the greedy algorithm runs in O(n1gn) time. The proof that the fractional knapsack problem has the greedy-choice property is left as Exercise 17.2-1.

To see that this greedy strategy does not work for the 0-1 knapsack problem, consider the problem instance illustrated in Figure 17.2(a). There are 3 items, and the knapsack can hold 50 pounds. Item 1 weighs 10 pounds and is worth 60 dollars. Item 2 weighs 20 pounds and is worth 100 dollars. Item 3 weighs 30 pounds and is worth 120 dollars. Thus, the value per pound of item 1 is 6 dollars per pound, which is greater than the value per pound of either item 2 (5 dollars per pound) or item 3 (4 dollars per pound). The greedy strategy, therefore, would take item 1 first. As can be seen from the case analysis in Figure 17.2(b), however, the optimal solution takes items 2 and 3, leaving 1 behind. The two possible solutions that involve item 1 are both suboptimal.

For the comparable fractional problem, however, the greedy strategy, which takes item 1 first, does yield an optimal solution, as shown in Figure 17.2 (c). Taking item 1 doesn't work in the 0-1 problem because the thief is unable to fill his knapsack to capacity, and the empty space lowers the effective value per pound of his load. In the 0-1 problem, when we consider an item for inclusion in the knapsack, we must compare the solution to the subproblem in which the item is included with the solution to the subproblem in which the item is excluded before we can make the choice. The problem formulated in this way gives rise to many overlapping subproblems--a hallmark of dynamic programming, and indeed, dynamic programming can be used to solve the 0-1 problem.



# Bellman Ford

- 
