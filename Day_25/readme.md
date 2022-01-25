---
title: "Find All Four Sum Numbers "
description: " Find all the unique quadruple = SUM "
categories:
  - Binary Search
---

### Question

> Given an array of integers and another number. Find all the unique quadruple from the given array that sums up to the given number.

```
Input:
N = 7, K = 23
A[] = {10,2,3,4,5,7,8}
Output: 2 3 8 10 $2 4 7 10 $3 5 7 8 $
Explanation: Sum of 2, 3, 8, 10 = 23,
sum of 2, 4, 7, 10 = 23 and sum of 3,
5, 7, 8 = 23.

```

### Code [python]

```python3

class Solution:
    def fourSum(self, arr, k):
        li = set()
        n = len(arr)
        arr.sort()
        for i in range(n-3):
            for j in range(i+1, n-2):
                l = j + 1
                r = n - 1
                while(l < r):
                    s = arr[i] + arr[j] + arr[l] + arr[r]
                    if (s == k):
                        li.add((arr[i], arr[j], arr[l], arr[r]))
                        l += 1
                        r -= 1
                    elif (s < k):
                        l += 1
                    else :
                        r -= 1
        return sorted(li) 

```

> Time Complexity = O( N^3 )

> Space Complexity = O( N^2 )
