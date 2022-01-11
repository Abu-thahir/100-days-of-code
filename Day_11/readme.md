---
title: "Trapping Rain Water"
description: " compute how much water can be trapped between the blocks "
categories:
  - Coding
---

### Question

> Given an array arr[] of N non-negative integers representing the height of blocks. If width of each block is 1, compute how much water can be trapped between the blocks during the rainy season. 

```
Input:
N = 4
arr[] = {7,4,0,9}
Output:
10
Explanation:
Water trapped by above 
block of height 4 is 3 units and above 
block of height 0 is 7 units. So, the 
total unit of water trapped is 10 units.
```

### Code [python]

```python3


class Solution:
    def trappingWater(self, arr,n):
        result = 0
        left_max = 0
        right_max = 0
        low = 0
        high= n-1
        while(low <= high):
            if(arr[low] < arr[high]):
                if(arr[low] > left_max):
                    left_max = arr[low]
                else:
                    result += left_max - arr[low]
                    low+= 1
            else:
                if(arr[high] > right_max):
                    right_max = arr[high]
                else:
                    result += right_max - arr[high]
                    high-= 1
        return result

```

> Time Complexity = O(N)

> Space Complexity = O(1)
