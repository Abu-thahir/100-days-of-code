---
title: "Two Pointer Technique"
description: "Dam of Candies"
categories:
  - Coding
---

### Question

> Given an array of heights of books ,the task is to find out the area between two books that can hold the maximum candies without changing the original position of selected books. 

### Code [python]

```python3

class Solution:
    def maxCandy(self, height, n): 
        maxcandy = 0
        i = 0 
        j = len(height) - 1
        while i < j:
            maxcandy = max(maxcandy, min(height[i],height[j]) * (j-i-1) )
            if height[i] > height[j]:
                j -= 1
            else:
                i += 1
        return maxcandy

```

> Time Complexity = O(N)

> Space Complexity = O(1)
