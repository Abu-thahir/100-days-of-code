---
title: "Minimum Platforms "
description: "Minimum Number of Platforms Required for a Railway Station"
categories:
  - Greedy Technique
---

### Question

> Your task is to complete the function findPlatform() which takes the array arr[] (denoting the arrival times), array dep[] 
(denoting the departure times) and the size of the array as inputs and returns the minimum number of platforms required at the railway station such that no train waits.

```
Input: n = 6 
arr[] = {0900, 0940, 0950, 1100, 1500, 1800}
dep[] = {0910, 1200, 1120, 1130, 1900, 2000}
Output: 3
Explanation: 
Minimum 3 platforms are required to 
safely arrive and depart all trains.
```

### Code [python]

```python3

class Solution:    
    #Function to find the minimum number of platforms required at the
    #railway station such that no train waits.
    def minimumPlatform(self,n,arr,dep):
        arr.sort()
        dep.sort()
        need = 1
        result = 1
        i = 1
        j = 0
        while (i < n and j < n):
            if (arr[i] <= dep[j]):
                need += 1
                i += 1
            elif (arr[i] > dep[j]):
                need -= 1
                j += 1
            if (need > result):
                result = need
        return result

```

> Time Complexity = O(nLogn)

> Space Complexity = O(n)
