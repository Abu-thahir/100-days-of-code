---
title: "Moore Majority Voting Algorithm"
description: "Majority Element i.e the ele occurs more than n/2 times"
categories:
  - Array
---

### Question

> Given an array A of N elements. Find the majority element in the array. A majority element in an array A of size N is an element that appears more than N/2 times in the array.

```
Input:
N = 5 
A[] = {3,1,3,3,2} 
Output:
3
Explanation:
Since, 3 is present more
than N/2 times, so it is 
the majority element.
```

### Code [python]

```python3

class Solution:
    def majorityElement(self, arr, n):
        ele = -1
        counts = 0
        for i in range (n):
            if (counts == 0):
                ele = arr[i]
                counts = 1
            else:
                if (arr[i] == ele):
                    counts += 1
                else:
                    counts -= 1
        count = 0
        for i in range (n):
            if (arr[i] == ele):
                count += 1
             
        if (count > n // 2):
            return ele
        else:
            return -1

```

> Time Complexity = O(N)

> Space Complexity = O(1)
