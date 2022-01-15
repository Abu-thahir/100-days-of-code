---
title: "Number of occurrence"
description: "Find the no. occurence of an element- Binary Search"
categories:
  - Divide and Conquer
---

### Question

>Given a sorted array Arr of size N and a number X, you need to find the number of occurrences of X in Arr.

```
Input:
N = 7, X = 2
Arr[] = {1, 1, 2, 2, 2, 2, 3}
Output: 4
Explanation: 2 occurs 4 times in the
given array.
```

### Code [python]

```python3

class Solution:

	def count(self,arr, n, x):
        if x not in arr:
            return 0  
        first = self.getFirstLastIndex(arr,0,n-1,x,True)
        last = self.getFirstLastIndex(arr,0,n-1,x,False)
        return last-first+1
       
      
    def getFirstLastIndex(self, arr,low,high,x,bool):   
        ans = -1
        while low <= high:
            mid = low +(high -low)//2
            if x < arr[mid]:
                high = mid -1
            elif x > arr[mid]:
                low = mid +1
            else:
                ans = mid
                if bool:
                    high = mid - 1
                else:
                    low = mid + 1
        return ans

```

> Time Complexity = O(log N )

> Space Complexity = O(1)
