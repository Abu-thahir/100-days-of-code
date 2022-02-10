---
title: "Detect Cycle in a Directed Graph"
description: "Using DFS"
categories:
  - Graphs
---

### Question

> Given a Directed Graph with V vertices (Numbered from 0 to V-1) and E edges, check whether it contains any cycle or not.

```
Input:
```
![alt text](https://github.com/Abu-thahir/100-days-of-code/blob/main/images/detect%20cycle.png?raw=true)
```
Output: 1
Explanation: 3 -> 3 is a cycle
```
### Code [Python3]

```python
class Solution:
    
    def isCyclic(self, V, adj):
        viz = [False]*V
        dfsviz = [False]*V
        for i in range(V):
            if not viz[i]:
                if self.dfs(adj, i, viz, dfsviz):
                    return True
        return False
    
    def dfs(self, adj, start, viz, dfsviz):
        viz[start] = True
        dfsviz[start] = True
        for x in adj[start]:
            if not viz[x]:
                if self.dfs(adj, x, viz, dfsviz):
                    return True
            elif dfsviz[x]:
                return True
        dfsviz[start] = False
        return False
#{ 
#  Driver Code Starts
#Initial Template for Python 3

import sys
sys.setrecursionlimit(10**6)
        
if __name__ == '__main__':
    t = int(input())
    for i in range(t):
        V,E = list(map(int, input().strip().split()))
        adj = [[] for i in range(V)]
        for i in range(E):
            a,b = map(int,input().strip().split())
            adj[a].append(b)
        ob = Solution()
        
        if ob.isCyclic(V, adj):
            print(1)
        else:
            print(0)
# } Driver Code Ends
```

> Time Complexity = O(V+E)

> Space Complexity = O(V)


