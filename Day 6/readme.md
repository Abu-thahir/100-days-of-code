---
title: "Rearrange the array without using temp"
description: "Rearrange the array with space complexity of O(1)"
categories:
  - Coding
---

### Question

> Given an array of size n where all elements are distinct and in range from 0 to n-1, change contents of arr[] so that arr[i] = j is changed to arr[j] = i
### Code [Python3]

```python
class Solution:
    def prank(self, a, n):
        for i in range(0,n):
            a[i]=a[i]+(a[a[i]]%n)*n
        for i in range(0,n):
            a[i]=int(a[i]/n)
        return a
```

> Time Complexity = O(N)
> Space Complexity = O(1)


