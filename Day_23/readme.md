---
title: "Merge Without Extra Space "
description: "Merge two sorted arrays with space complexity O(1)"
categories:
  - Arrays
---

### Question

> Given two sorted arrays arr1[] and arr2[] of sizes n and m in non-decreasing order. Merge them in sorted order without using any extra space. 
> Modify arr1 so that it contains the first N elements and modify arr2 so that it contains the last M elements.

```
Input: 
n = 2, arr1[] = [10, 12] 
m = 3, arr2[] = [5 18 20]
Output: 
arr1[] = [5 10]
arr2[] = [12 18 20]
Explanation:
After merging two sorted arrays 
we get 5 10 12 18 20.
```

### Code [PYTHON]

```python3
class Solution:
    def nextGap(self,gap):
        if (gap <= 1):
            return 0
        return (gap // 2) + (gap % 2)
    
    def merge(self,arr1,arr2,n,m):
        gap = n + m
        gap = self.nextGap(gap)
        while gap > 0:
            i = 0
            while i + gap < n:
                if (arr1[i] > arr1[i + gap]):
                    arr1[i], arr1[i + gap] = arr1[i + gap], arr1[i]
                i += 1
            j = gap - n if gap > n else 0
            while i < n and j < m:
                if (arr1[i] > arr2[j]):
                    arr1[i], arr2[j] = arr2[j], arr1[i]
                i += 1
                j += 1
            if (j < m):
                j = 0
                while j + gap < m:
                    if (arr2[j] > arr2[j + gap]):
                        arr2[j], arr2[j + gap] = arr2[j + gap], arr2[j]
                    j += 1
            gap = self.nextGap(gap)


```


> Time Complexity = O(N log N)

> Space Complexity = O(1)
