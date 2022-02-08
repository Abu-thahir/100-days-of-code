---
title: "Median in a row-wise sorted Matrix"
description: " find the median of the matrix."
categories:
  - Matrix
---

### Question

> Given a row wise sorted matrix of size RxC where R and C are always odd, find the median of the matrix.
```
Input:
R = 3, C = 3
M = [[1, 3, 5], 
     [2, 6, 9], 
     [3, 6, 9]]

Output: 5

Explanation:
Sorting matrix elements gives us 
{1,2,3,3,5,6,6,9,9}. Hence, 5 is median.
```

### Code [python]

```python3

class Solution:
    def median(self, matrix, r, c):
    	for i in range(1, r):
    	    matrix[0] += matrix[i]
    	for i in range(1,r):
    	    matrix.pop()
    	
    	matrix[0].sort()
    	
    	l = len(matrix[0])
        
        if l%2 == 0:
            a1 = l-1//2
            a2 = a1 + 1
            median = (matrix[0][a1]+matrix[0][a2]/2)
            return median
        else:
            median = matrix[0][l//2]
            return median

```

> Time Complexity = O(N)

> Space Complexity = O(1)
