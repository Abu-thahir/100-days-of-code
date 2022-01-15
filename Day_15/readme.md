---
title: " First and last occurrences of X "
description: " First and last occurrences of X in an array - Binary Search"
categories:
  - Divide and Conquer
---

### Question

>Given a sorted array having N elements, find the indices of the first and last occurrences of an element X in the given array

```
Input:
N = 2 , X = 3
arr[] = { 1, 3, 3, 4 }
Output:
1 2
Explanation:
For the above array, first occurence
of X = 3 is at index = 1 and last
occurence is at index = 2.

```

### Code [python]

```python3

class Solution: 
    def firstAndLast(self, arr, n, x): 
        if x not in arr:
            return [-1]  
        first = self.getFirstLastIndex(arr,0,n-1,x,True)
        last = self.getFirstLastIndex(arr,0,n-1,x,False)
        return [first,last]
       
      
    def getFirstLastIndex(self, arr,low,high,x,bool):   
        ans = -1
        while low <= high:
            mid = low +(high -low)//2 #midex index of array
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
