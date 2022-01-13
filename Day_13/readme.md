---
title: "Median of Two sorted arrays"
description: "Finding the median - Binary Search"
categories:
  - Coding
---

### Question

> Given two sorted arrays of sizes N and M respectively. The task is to find the median of the two arrays when they get merged. If there are even number of elements in the resulting array, find the floor of the average of two medians.
```
Input:
N = 5, M = 6 
arr[] = {1,2,3,4,5}
brr[] = {3,4,5,6,7,8}
Output: 4
Explanation: After merging two arrays, 
elements will be as 1 2 3 3 4 4 5 5 6 7 8
So, median is 4.
```

### Code [python]

```python3

class Solution:
    
    #Function to find the median of the two arrays when they get merged.
    def findMedianSortedArrays(self,a1, n1, a2, n2):
        INT_MAX = 0xFFFFFFFFFFFFFFFF
        INT_MIN = -INT_MAX
        lo = 0; hi = n1
        while(lo<=hi):
            m1 = (lo+hi)//2
            m2 = (((n1+n2)+1)//2)-m1
            l1 = a1[m1-1] if m1>0 else INT_MIN
            l2 = a2[m2-1] if m2>0 else INT_MIN
            r1 = a1[m1] if m1<n1 else INT_MAX
            r2 = a2[m2] if m2<n2 else INT_MAX
            if(l1>r2):  
                hi = m1-1 
            elif(l2>r1):    
                lo = m1+1
            else:
                if(n1+n2)%2 == 0:  
                    return (max(l1, l2) + min(r1, r2))//2
                return max(l1, l2)

```

> Time Complexity = O(log(max(m,n)))

> Space Complexity = O(1)
