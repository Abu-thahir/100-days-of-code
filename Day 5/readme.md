---
title: "SUM OF QUERY"
description: "Sum of given range"
categories:
  - Coding
---

### Question

> You are given an array arr[] of n integers and q queries in an array queries[] of length 2*q containing l, r pair for all q queries. You need to compute the following sum over q queries.

```
Input: n = 4
arr = {1, 2, 3, 4}
q = 2
queries = {1, 4, 2, 3}
Output: 10 5
Explaination: In the first query we need sum 
from 1 to 4 which is 1+2+3+4 = 10. In the 
second query we need sum from 2 to 3 which is 
2 + 3 = 5.
```

### Code [Python3]

```python
class Solution:
    def querySum(self, n, arr, q, queries):
        # code here
        def tot(arr,l,r):
           s=0
           for i in range(l-1,r):
               s=s+arr[i]
           return s
           
        res=[]
        for i in range(q):
            res.append(tot(arr,queries[i*2],queries[i*2+1]))
        return res
```

> Time Complexity = O(n+q)

> Space Complexity = O(n)


