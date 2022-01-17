---
title: " Set Matrix Zeros"
description: " Set its entire row and col to 0 if an element is 0 "
categories:
  - Matrix
---

### Question

>Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's, and return the matrix.

```
Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
```

### Code [C++]

```C++

class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int col=1 , n=matrix.size() , m=matrix[0].size();
        for(int i=0;i<n;i++){
            if (matrix[i][0]==0)
                col=0;
            for(int j=1;j<m;j++){
                if (matrix[i][j]==0){
                    matrix[i][0]=matrix[0][j]=0;
                }
            }    
        }
        for(int i=n-1;i>=0;i--){
            for(int j=m-1;j>=1;j--){
                if (matrix[0][j]==0 || matrix[i][0]==0)
                    matrix[i][j]=0;
            }
            if (col==0)
                matrix[i][0]=0;   
        }
        
        
    }
};

```

> Time Complexity = O( N*M )

> Space Complexity = O(1)
