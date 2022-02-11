---
title: "Implementing Dijkstra Algorithm"
description: "Finding the shortest distance"
categories:
  - Graphs
---

### Question

> Given a weighted, undirected and connected graph of V vertices and E edges, Find the shortest distance of all the vertex's from the source vertex S.
```
INPUT:
S = 2
```
![alt text](https://github.com/Abu-thahir/100-days-of-code/blob/main/images/Dijikstra.png?raw=true)
```
OUTPUT:
4 3 0
Explanation:
For nodes 2 to 0, we can follow the path-
2-1-0. This has a distance of 1+3 = 4,
whereas the path 2-0 has a distance of 6. So,
the Shortest path from 2 to 0 is 4.
The other distances are pretty straight-forward.
```
### Code [python]

```python3
import collections
class Solution:
    def dijkstra(self, V, adj, S):
        dist = [float("inf")]*V
        dist[S] = 0
        q = collections.deque()
        q.append(S)
        while q:
            node = q.pop()
            for nei, nei_dist in adj[node]:
                if dist[node] + nei_dist < dist[nei]:
                    dist[nei] = dist[node] + nei_dist
                    q.append(nei)
        return dist

#{ 
#  Driver Code Starts
#Initial Template for Python 3
import atexit
import io
import sys


if __name__ == '__main__':
    test_cases = int(input())
    for cases in range(test_cases):
        V,E = map(int,input().strip().split())
        adj = [[] for i in range(V)]
        for i in range(E):
            u,v,w = map(int,input().strip().split())
            adj[u].append([v,w])
            adj[v].append([u,w])
        S=int(input())
        ob = Solution()
        
        res = ob.dijkstra(V,adj,S)
        for i in res:
            print(i,end=" ")
        print()
# } Driver Code Ends

```

> Time Complexity = O(V^2)

> Space Complexity = O(V^2)
