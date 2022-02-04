---
title: "Floyd’s Cycle-Finding Algorithm "
description: "Detect Loop in linked list"
categories:
  - LinkedList
---

### Question

>Given a linked list of N nodes. The task is to check if the linked list has a loop. Linked list can contain self loop.

```
Input:
N = 3
value[] = {1,3,4}
x = 2
Output: True
Explanation: In above test case N = 3.
The linked list with nodes N = 3 is
given. Then value of x=2 is given which
means last node is connected with xth
node of linked list. Therefore, there
exists a loop.

```

```
Approach : 
* Traverse linked list using two pointers.
* Move one pointer(slow_p) by one and another pointer(fast_p) by two.
* If these pointers meet at the same node then there is a loop. If pointers do not meet then linked list doesn’t have a loop.

```

### Code [python]

```python3

class Solution:
    #Function to check if the linked list has a loop.
    def detectLoop(self, head):
        slow_p = head
        fast_p = head
        while(slow_p and fast_p and fast_p.next):
            slow_p = slow_p.next
            fast_p = fast_p.next.next
            if slow_p == fast_p:
                return 'True'
        return 'False'        

#{ 
#  Driver Code Starts
#Initial Template for Python 3

# Node Class
class Node:
    def __init__(self, data):   # data -> value stored in node
        self.data = data
        self.next = None

# Linked List Class
class LinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
    
    # creates a new node with given value and appends it at the end of the linked list
    def insert(self, val):
        if self.head is None:
            self.head = Node(val)
            self.tail = self.head
        else:
            self.tail.next = Node(val)
            self.tail = self.tail.next
    
    #connects last node to node at position pos from begining.
    def loopHere(self,pos):
        if pos==0:
            return
        
        walk = self.head
        for i in range(1,pos):
            walk = walk.next
        
        self.tail.next = walk

if __name__ == '__main__':
    for _ in range(int(input())):
        n = int(input())
        
        LL = LinkedList()
        for i in input().split():
            LL.insert(int(i))
        
        LL.loopHere(int(input()))
        
        print(Solution().detectLoop(LL.head))
# } Driver Code Ends

```

> Time Complexity = O(N)

> Space Complexity = O(1)
