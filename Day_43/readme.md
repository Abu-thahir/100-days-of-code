---
title: "Balancing Paranthesis"
description: "verify the validity of Paranthesis"
categories:
  - Stack
---

### Question

> Given a string S, composed of different combinations of '(' , ')', '{', '}', '[',']'. The task is to verify the validity of the arrangement.
```
Input:
S = ()[]{}
Output: 1
Explanation: The arrangement is valid.

Input:
S = ())({}
Output: 0
Explanation: Arrangement is not valid.
```

### Code [python]

```python3

class Solution:
    def valid(self, s): 
        v = 0
        for i in s:
            if i in {'(', '[', '{'} :
                v=v+1
            else:
                v=(v - 1)
            if v < 0:
                return 0
        if v:
            return 0
        else:
            return 1

```

> Time Complexity = O(N)

> Space Complexity = O(N)
