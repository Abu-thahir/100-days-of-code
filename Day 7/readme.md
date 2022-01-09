---
title: "Nth Natural Number"
description: "Base 9"
categories:
  - Coding
---

### Question

> Given a positive integer N. You have to find Nth natural number after removing all the numbers containing digit 9.

```
Input:
N = 9
Output:
10
Explanation:
After removing natural numbers which contains
digit 9, first 9 numbers are 1,2,3,4,5,6,7,8,10
and 9th number is 10.
```

### Code [Python3]

```python
class Solution:
    def findNth(self,N):
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
