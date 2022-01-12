---
title: "Find the repeating and the missing"
description: " two equations using sum and sum of squares "
categories:
  - Coding
---

### Question

> Given an unsorted array Arr of size N of positive integers. One number 'A' from set {1, 2, …N} is missing and one number 'B' occurs twice in array. Find these two numbers.

```
Input: 
Input:
N = 2
Arr[] = {2, 2}
Output: 2 1
Explanation: Repeating number is 2 and 
smallest positive missing number is 1.
```

```
Approach:

Let x be the missing and y be the repeating element.
Let N is the size of array.
Get the sum of all numbers using formula S = N(N+1)/2
Get the sum of square of all numbers using formula Sum_Sq = N(N+1)(2N+1)/6
Iterate through a loop from i=1….N
S -= A[i]
Sum_Sq -= (A[i]*A[i])
It will give two equations 
x-y = S – (1) 
x^2 – y^2 = Sum_sq 
x+ y = (Sum_sq/S) – (2) 
```
### Code [python]

```python3

class Solution:
    def findTwoElement( self,A,n): 
        s = (n* (n+ 1)) // 2
        sum_sq = ((n * (n + 1) * (2 * n + 1)) // 6)
        missingNumber, repeating = 0, 0
        for i in range(len(A)):
            s -= A[i]
            sum_sq -= A[i] * A[i]
        missingNumber = (s + sum_sq // s) // 2
        repeating = missingNumber - s
        ans = []
        ans.append(repeating)
        ans.append(missingNumber)
        return ans
        
```

> Time Complexity = O(N)

> Space Complexity = O(1)
