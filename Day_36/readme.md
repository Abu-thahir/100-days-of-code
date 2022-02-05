---
title: "Max Consecutive Ones"
description: "find count of maximum number of consecutive 1’s present in the array."
categories:
  - Arrays
---

### Question

> Given a binary array nums, return the maximum number of consecutive 1's in the array.

```
Input: nums = [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.
```

### Code [python]

```python3

class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        count = 0
        result = 0
        for i in range(0, len(nums)):
            if (nums[i] == 0):
                count = 0
            else:
                count+= 1
                result = max(result, count)
        return result

```

> Time Complexity = O(N)

> Space Complexity = O(1)
