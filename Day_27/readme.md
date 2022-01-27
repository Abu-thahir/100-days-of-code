---
title: " Length of the longest substring  "
description: " find the length of the longest substring without repeating characters.   "
categories:
  - Arrays
---

### Question

> Given a string S, find the length of the longest substring without repeating characters.

```
Input:
S = "geeksforgeeks"
Output:
7
Explanation:
Longest substring is
"eksforg".

```

### Code [python]

```python3

class Solution:
    def longestUniqueSubsttr(self, S):
        visited = {}
        max_len = 0
        s = 0
        for i in range(len(S)):
            if S[i] in visited:
                s = max(s, visited[S[i]] + 1)
            visited[S[i]] = i
            max_len = max(max_len, i-s + 1)
        return max_len

```

> Time Complexity = O( N + K)

> Space Complexity = O( K )
