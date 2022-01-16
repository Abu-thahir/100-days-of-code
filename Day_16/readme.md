---
title: " Spiral Matrix "
description: " Spiral Matrix Traversal"
categories:
  - Matrix
---

### Question

>Given a matrix of size N x M. You have to find the Kth element which will obtain while traversing the matrix spirally starting from the top-left corner of the matrix.

```
Input: 
N = 3, M = 3, K = 4
A[] = {{1, 2, 3}, 
       {4, 5, 6}, 
       {7, 8, 9}}
Output: 
6
Explanation: Spiral traversal of matrix: 
{1, 2, 3, 6, 9, 8, 7, 4, 5}. Fourth element
is 6.

```

### Code [python]

```python3

class Solution:
    def findK(self, a, n, m, k):
        ans=[]
        l,up,down,r,c=0,0,n-1,m-1,0
        while(len(ans)<n*m):
            for i in range(l,r+1):
                c+=1
                ans.append(a[up][i])
                if c==k:
                    return ans[c-1]
            for j in range(up+1,down+1):
                c+=1
                ans.append(a[j][r])
                if c==k:
                   return ans[c-1]
            if up!=down:
                for i in range(r-1,l-1,-1):
                    c+=1
                    ans.append(a[down][i])
                    if c==k:
                        return ans[c-1]
            if l!=r:
                for i in range(down-1,up,-1):
                    c+=1
                    ans.append(a[i][l])
                    if c==k:
                        return ans[c-1]
            up,r=up+1,r-1
            down,l=down-1,l+1
        return ans[k-1] 

```

> Time Complexity = O(n*m )

> Space Complexity = O(1)
