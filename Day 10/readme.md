---
title: "Merge Overlapping Intervals"
description: "Overlapping Intervals"
categories:
  - Coding
---

### Question

> Given a collection of Intervals, the task is to merge all of the overlapping Intervals.
```
Input:
Intervals = {{1,3},{2,4},{6,8},{9,10}}
Output: {{1, 4}, {6, 8}, {9, 10}}
Explanation: Given intervals: [1,3],[2,4]
[6,8],[9,10], we have only two overlapping
intervals here,[1,3] and [2,4]. Therefore
we will merge these two and return [1,4],
[6,8], [9,10].
```

### Code [python]

```python3

class Solution:
	def overlappedInterval(self, arr):
        arr.sort(key = lambda x: x[0]) 
        m = []
        s = -10000
        max = -100000
        for i in range(len(arr)):
            a = arr[i]
            if a[0] > max:
                if i != 0:
                    m.append([s,max])
                max = a[1]
                s = a[0]
            else:
                if a[1] >= max:
                    max = a[1]
    
        if max != -100000 and [s, max] not in m:
            m.append([s, max])
        return m 

```

> Time Complexity = O(N log N)

> Space Complexity = O(1)
