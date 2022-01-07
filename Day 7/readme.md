---
title: "Nth Natural Number"
description: "Base 9"
categories:
  - Coding
---

### Question

> Given a positive integer N. You have to find Nth natural number after removing all the numbers containing digit 9.

### Code [Python3]

```python
class Solution:
    def findNth(self,N):
        #code here
        ans=0
        p=1
        n=N
        
        while(n>0):
            ans += p*(n%9)
            n//=9
            p*=10
        return ans            

```

> Time Complexity = O(log N)
              
> Space Complexity = O(1)


