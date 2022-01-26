---
title: " Largest subarray with 0 sum  "
description: " compute the length of the largest subarray with sum 0  "
categories:
  - Arrays
  - hash-map
---

### Question

> Given an array having both positive and negative integers. The task is to compute the length of the largest subarray with sum 0.

```
Input:
N = 8
A[] = {15,-2,2,-8,1,7,10,23}
Output: 5
Explanation: The largest subarray with
sum 0 will be -2 2 -8 1 7.

```

### Code [python]

```python3

class Solution:
    def maxLen(self, n, arr):
        hash_map = {}
        max_len = 0
        c_sum = 0
        for i in range(n):
            c_sum += arr[i]
            if arr[i] is 0 and max_len is 0:
                max_len = 1
            if c_sum is 0:
                max_len = i + 1
            if c_sum in hash_map:
                max_len = max(max_len, i - hash_map[c_sum] )
            else:
                hash_map[c_sum] = i
        return max_len

```

> Time Complexity = O(N)

> Space Complexity = O(N)
