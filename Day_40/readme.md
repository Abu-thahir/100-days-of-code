---
title: "DFS"
description: "Perform a Depth First Traversal of the graph."
categories:
  - Graph
---

### Question

> Given a connected undirected graph. Perform a Depth First Traversal of the graph.
---
INPUT :
---
![alt text](https://github.com/Abu-thahir/100-days-of-code/blob/main/images/download.png?raw=true)

### Code [python]

```python3
class Solution:
    
    #Function to return a list containing the DFS traversal of the graph.
    def dfsOfGraph(self, V, adj):
        def dfs(node, visited, adj, res):
            visited.add(node)
            res.append(node)
            for n in adj[node]:
                if n not in visited:
                    dfs(n, visited, adj, res)
        visited = set()
        res = []
        dfs(0, visited, adj, res)
        return res

#{ 
#  Driver Code Starts
if __name__ == '__main__':
    T=int(input())
    while T>0:
        V,E=map(int,input().split())
        adj=[[] for i in range(V+1)]
        for i in range(E):
            u,v=map(int,input().split())
            adj[u].append(v)
            adj[v].append(u)
        ob=Solution()
        ans=ob.dfsOfGraph(V,adj)
        for i in range(len(ans)):
            print(ans[i],end=" ")
        print()
        T-=1

```

> Time Complexity = O(V + E)

> Space Complexity = O(V)
