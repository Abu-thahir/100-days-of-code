---
title: "SUM OF QUERY"
description: "Sum of given range"
categories:
  - Coding
---

### Question

> You are given an array arr[] of n integers and q queries in an array queries[] of length 2*q containing l, r pair for all q queries. You need to compute the following sum over q queries.

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


