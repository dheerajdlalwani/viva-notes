# DFS

- Complete -  No: fails in infinite-depth spaces (Can modify to avoid repeated states along path)
- Time - O(bm) with m=maximum depth : terrible if m is much larger than d
- but if solutions are dense, may be much faster than breadth-first
- Space - O(bm), i.e., linear space! (we only need to remember a single path + expanded unexplored nodes)
- Optimal - No (It may find a non-optimal goal first) 

<br>
---
<br>

# BFS

- Complete -  Yes it always reaches goal (if b is finite)
- Time -  1+b+b^2+b^3+… +b^d + ( b^(d+1) - b )) = O(bd+1) (this is the number of nodes we generate)
- Space - O(b^d+1) (keeps every node in memory, either in fringe or on a path to fringe).
- Optimal - Yes (if we guarantee that deeper solutions are less optimal, e.g. step-cost=1).
- Space is the bigger problem (more than time)
