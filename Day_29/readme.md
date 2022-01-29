---
title: "Find middle of LinkedList"
description: "Finding middle element in a linked list"
categories:
  - LinkedList
---

### Question

> Given a singly linked list of N nodes. The task is to find the middle of the linked list. 
> For example, if the linked list is 1-> 2->3->4->5, then the middle node of the list is 3. If there are two middle nodes(in case, when N is even), print the second middle element.

```
Input:
LinkedList: 1->2->3->4->5
Output: 3 
Explanation: 
Middle of linked list is 3.

```

### Code [python]

```python3

class Solution:
    #  Should return data of middle node. If linked list is empty, then  -1
    def findMid(self, head):
        count=0
        self.head=head
        iter=self.head
        while iter:
            count+=1
            iter=iter.next
        mid=0
        iter=self.head
        while iter:
            if mid==count//2:
                return iter.data
            mid+=1
            iter=iter.next

```

> Time Complexity = O( N )

> Space Complexity = O( 1 )
