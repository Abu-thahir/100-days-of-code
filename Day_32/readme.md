---
title: " Equilibrium Point "
description: "Finding Equilibrium using Prefix Sum"
categories:
  - Arrays
---

### Question

>Given an array A of n positive numbers. The task is to find the first Equilibium Point in the array. 
>Equilibrium Point in an array is a position such that the sum of elements before it is equal to the sum of elements after it. 

```
Input: 
n = 5 
A[] = {1,3,5,2,2} 
Output: 3 
Explanation: For second test case 
equilibrium point is at position 3 
as elements before it (1+3) = 
elements after it (2+2). 

```

### Code [python]

```python3
class Solution:

    def equilibriumPoint(self,arr, N):
        l= []
        r= []
        l.append(arr[0])
        r.append(arr[N-1])
        for i in range(1,N):
            l.append(l[i-1]+arr[i])
            r.append(r[i-1]+arr[N-1-i])
                
        for i in range(N):
            if(l[i] == r[N - 1 - i ]):
                return(i+1)
        return -1

```

> Time Complexity = O(N)

> Space Complexity = O(N)
