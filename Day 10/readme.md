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

### Pseudocode 
```
1) Sort all intervals in increasing order of start time.
2) Traverse sorted intervals starting from first interval, 
   do following for every interval.
      a) If current interval is not first interval and it 
         overlaps with previous interval, then merge it with
         previous interval. Keep doing it while the interval
         overlaps with the previous one.         
      b) Else add current interval to output list of intervals.
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
