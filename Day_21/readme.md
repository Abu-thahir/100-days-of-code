---
title: "Next Permutation"
description: "To find  Lexicographically next greater permutation "
categories:
  - Coding
---

### Question

> Implement the next permutation, which rearranges the list of numbers into Lexicographically next greater permutation of list of numbers.
>  If such arrangement is not possible, it must be rearranged to the lowest possible order i.e. sorted in an ascending order. You are given an list of numbers arr[ ] of size N.

```
Input: N = 6
arr = {1, 2, 3, 6, 5, 4}
Output: {1, 2, 4, 3, 5, 6}
Explaination: The next permutation of the 
given array is {1, 2, 4, 3, 5, 6}.
```

### Code [python]

```python3

class Solution:
    def nextPermutation(self, N, arr):
        i = N-1
        while i > 0:
            if arr[i] > arr[i-1]:
                arr[i:N] = sorted(arr[i:N])
                for j in range(i,N):
                    if arr[j] > arr[i-1]:
                        arr[j],arr[i-1] = arr[i-1],arr[j]
                        return arr
            i-=1
        return arr[::-1]  

```

> Time Complexity = O(N)

> Space Complexity = O(1)
