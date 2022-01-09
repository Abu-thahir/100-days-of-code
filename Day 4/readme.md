---
title: "Kadane's Algorithm"
description: "Maximum subarray Sum"
categories:
  - Coding
---

### Question

> Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum. A subarray is a contiguous part of an array.

```
Input:
N = 5
Arr[] = {1,2,3,-2,5}
Output:
9
Explanation:
Max subarray sum is 9
of elements (1, 2, 3, -2, 5) which 
is a contiguous subarray.
```

### Code [Python3]

```python
class Solution:
    def maxSubArraySum(self,arr,N):
        max_so_far = arr[0]
        max_ending_here = 0
        for i in range(0, N):
            max_ending_here = max_ending_here + arr[i]
            if (max_so_far < max_ending_here):
                max_so_far = max_ending_here
            if max_ending_here < 0:
                max_ending_here = 0  
        return max_so_far
```

> Time Complexity = O(N)

> Space Complexity = O(1)


