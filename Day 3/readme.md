---
title: "N meetings Greedy Approach"
description: "To find the maximum no. of meeting that can be accomodated in the same room"
categories:
  - Coding
---

### Question

> There is one meeting room in a firm. There are N meetings in the form of (start[i], end[i]) where start[i] is start time of meeting i and end[i] is finish time of meeting i.Find the maximum no. of meeting that can hold in a room.

### Code [python]

```
python3
class Solution:
    
    def maximumMeetings(self,n,start,end):
        n = len(start)
        l = []
        for i in range(n):
            l.append(meeting(start[i], end[i], i))
        ans = []
        l.sort(key = lambda x: x.end)
        ans.append(l[0].pos)
        time_limit = l[0].end
     
        for i in range(1, n):
            if l[i].start > time_limit:
                ans.append(l[i].pos)
                time_limit = l[i].end
        return len(ans)
```

> Time Complexity =  O(N*LogN)

> Space Complexity = O(N)

```
