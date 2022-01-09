---
title: "Count all possible paths"
description: "Dynamic Programming"
categories:
  - Coding
---

### Question

> The task is to count all the possible paths from top left to bottom right of a m X n matrix with the constraints that from each cell you can either move only to right or down.

```
Input: m = 3, R = 3
Output: 6
Explanation: Six possible ways are
RRDD, DDRR, RDDR, DRRD, RDRD, DRDR.
```

### Code [Python3]

```python
class Solution:
	def numberOfPaths(self, p, q):
		count = [[0 for x in range(n)] for y in range(m)]
		for i in range(m):
            count[i][0] = 1;
        for j in range(n):
            count[0][j] = 1;
        for i in range(1, m):
            for j in range(1, n):             
                count[i][j] = count[i-1][j] + count[i][j-1]
        return count[m-1][n-1]%(pow(10,9)+7)        

```

> Time Complexity = O(m*n)
              
> Space Complexity = O(m*n)
