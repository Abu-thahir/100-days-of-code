---
title: "Dutch National Flag Algorithm"
description: "Sort an array of 0's , 1's and 2's"
categories:
  - Coding
---

### Question

> Given an array A[] consisting 0s, 1s and 2s. The task is to write a function that sorts the given array. The functions should put all 0s first, then all 1s and all 2s in last using efficient time complexity. 

```
Input: 
N = 5
arr[]= {0 2 1 2 0}
Output:
0 0 1 2 2
Explanation:
0s 1s and 2s are segregated 
into ascending order.
```

### Code [python]

```python3

class Solution:
    def sort012(self,arr,n):
        low = 0
        mid=0
        high = n-1
        while(mid<=high):
            if (arr[mid]==0):
                arr[mid],arr[low] = arr[low],arr[mid]
                mid+=1
                low+=1
            elif(arr[mid]==1):
                mid+=1
            else:
                arr[mid],arr[high]=arr[high],arr[mid]
                high-=1

```

> Time Complexity = O(N)

> Space Complexity = O(1)
