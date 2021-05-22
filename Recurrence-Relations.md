# Recurrence Relation
- A recurrence is an equation or inequality that describes a function in terms of its values on smaller inputs. 
- To solve a Recurrence Relation means to obtain a function defined on the natural numbers that satisfy the recurrence.

- For Example, the Worst Case Running Time T(n) of the MERGE SORT Procedures is described by the recurrence.

  - ## There are four methods for solving Recurrence:
    - Substitution Method
    - Iteration Method
    - Recursion Tree Method
    - Master Method


- ## Recursion Tree Method

- Recursion Tree Method is a pictorial representation of an iteration method which is in the form of a tree where at each level nodes are expanded.

- In general, we consider the second term in recurrence as root.

- It is useful when the divide & Conquer algorithm is used.

- It is sometimes difficult to come up with a good guess. In Recursion tree, each root and child represents the cost of a single subproblem.

- We sum the costs within each of the levels of the tree to obtain a set of pre-level costs and then sum all pre-level costs to determine the total cost of all levels of the recursion.

- A Recursion Tree is best used to generate a good guess, which can be verified by the Substitution Method.



- ## Master Method 

- [Master-Method](https://www.programiz.com/dsa/master-theorem)