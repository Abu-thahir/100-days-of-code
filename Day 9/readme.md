---
title: "Juggling Algorithm"
description: "Array Rotation"
categories:
  - Coding
---

### Question

> Given an unsorted array arr[] of size N. Rotate the array to the left (counter-clockwise direction) by D steps, where D is a positive integer. 
```
Input:
N = 10, D = 3
arr[] = {2,4,6,8,10,12,14,16,18,20}
Output: 8 10 12 14 16 18 20 2 4 6
Explanation: 2 4 6 8 10 12 14 16 18 20 
when rotated by 3 elements, it becomes 
8 10 12 14 16 18 20 2 4 6.
```

### Code [Python3]

```python
class Solution:
    #Function to rotate an array by d elements in counter-clockwise direction.
    def rotateArr(self,arr,D,N):
        #arr-array , D-shift , N-size
        g=self.gcd(D%N,N)
        for i in range(g):
            temp=arr[i]
            j=i
            while(1):
                k=j+D
                if k>=N:
                    k=k-N
                if k==i:
                    break
                arr[j]=arr[k]
                j=k
            arr[j]=temp
        return arr
        
    def gcd(self,a,b):
        if b==0:
            return a
        else:
            return self.gcd(b,a%b)    

```

> Time Complexity = O(N)
              
> Space Complexity = O(1)
