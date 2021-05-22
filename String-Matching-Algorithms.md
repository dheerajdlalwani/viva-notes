# Naive Approach

- compare the characters repeatedly
- if there is a mismatch, go back
- very inefficient because of un necessary repeated comparisons
- time complexity = O(m*n), m = len(pattern), n = len(pattern)

<br>
---
<br>

# Knuth-Morris-Pratt (KMP) Algorithm

- do not backtrack i
- backtrack only j, while parsing the Pie table

Pattern - abcdabc

Prefix - a, ab, abc, abcd, abcda, abcdab, abcdabc
Suffix - c, bc, abc, dabc, cdabc, bcdabc, abcdabc

- ## Base of KMP algorithm
  - Pie Table = Longest Prefix

Pattern - ababd
Pie Table - 
| a | b | a | b | d | <br>
| 0 | 0 | 1 | 2 | 0 |

- time complexity = O(m + n), m = len(pattern), n = len(pattern)
- m - to make table, parse the pattern
- n - parse the string

<br>
---
<br>

# Rabin-Karp Algorithm

- convert the pattern to a numerical value
- use hash function
- compare the hashcode of pattern and a slider window in string of the same length as the pattern
- also called as rolling hash
- if hashes are matched, compare their characters
- disadvantages
  - if hash function is simple, collisions may happen a lot
  - known a spurious hits

  - ## time complexity
    - With spurious hits = O(m*n)
    - Without spurious hits = O(n-m+1)

  - ## Suggested hash function
    -  Rabin finger print function
    





















