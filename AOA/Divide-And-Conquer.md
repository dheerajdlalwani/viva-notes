# Divide and Conquer Approach

  - In divide and conquer approach, the problem in hand, is divided into smaller sub-problems and then each problem is solved independently. When we keep on dividing the subproblems into even smaller sub-problems, we may eventually reach a stage where no more division is possible. Those "atomic" smallest possible sub-problem (fractions) are solved. The solution of all sub-problems is finally merged in order to obtain the solution of an original problem.

  -  Recurrance relation 
   ## T(n)=2T(n/2) + n


  - ## Divide/Break
    - This step involves breaking the problem into smaller sub-problems. Sub-problems should represent a part of the original problem. This step generally takes a recursive approach to divide the problem until no sub-problem is further divisible. At this stage, sub-problems become atomic in nature but still represent some part of the actual problem.

  - ## Conquer/Solve
    - This step receives a lot of smaller sub-problems to be solved. Generally, at this level, the problems are considered 'solved' on their own.

  - ## Merge/Combine
    - When the smaller sub-problems are solved, this stage recursively combines them until they formulate a solution of the original problem. This algorithmic approach works recursively and conquer & merge steps works so close that they appear as one.


- # Merge Sort
  - Merge Sort is a Divide and Conquer algorithm. 
  - It divides the input array into two halves, calls itself for the two halves, and then merges the two sorted halves. 
  - The merge() function is used for merging two halves. The merge(arr, l, m, r) is a key process that assumes that arr [ l..m ] and arr[ m+1..r ] are sorted and merges the two sorted sub-arrays into one.

```
MergeSort(arr[], l,  r)
If r > l
     1. Find the middle point to divide the array into two halves:  
             middle m = l+ (r-l)/2
     2. Call mergeSort for first half:   
             Call mergeSort(arr, l, m)
     3. Call mergeSort for second half:
             Call mergeSort(arr, m+1, r)
     4. Merge the two halves sorted in step 2 and 3:
             Call merge(arr, l, m, r)
```

- ## Time Complexity
  - Sorting arrays on different machines. 
  - Merge Sort is a recursive algorithm and time complexity can be expressed as following recurrence relation. 
  - ## T(n) = 2T(n/2) + θ(n)
  - The above recurrence can be solved either using the Recurrence Tree method or the Master method. 
  - It falls in case II of Master Method and the solution of the recurrence is θ(nLogn). 
  - Time complexity of Merge Sort is  θ(nLogn) in all 3 cases (worst, average and best) as merge sort always divides the array into two halves and takes linear time to merge two halves.
  - Auxiliary Space: O(n)

- ## Drawbacks
  - Slower comparative to the other sort algorithms for smaller tasks.
  - Merge sort algorithm requires an additional memory space of 0(n) for the temporary array.
  - It goes through the whole process even if the array is sorted.




- # Quick Sort
- # Binary Search

