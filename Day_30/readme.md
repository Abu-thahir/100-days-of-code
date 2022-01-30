---
title: "Reverse a linked list"
description: "The task is to reverse this list."
categories:
  - LinkedList
---

### Question

> Given a linked list of N nodes. The task is to reverse this list.

```
Input:
LinkedList: 1->2->3->4->5->6
Output: 6 5 4 3 2 1
Explanation: After reversing the list, 
elements are 6->5->4->3->2->1.

```

### Code [python]

```python3

class Solution:
    #Function to reverse a linked list.
    def reverseList(self, head):
        prev=None
        temp=None
        while(head):
            temp=head.next
            head.next=prev
            prev=head
            head=temp
        head=prev
        return head
 
 class Node:
    def __init__(self, val):
        self.data = val
        self.next = None

# Linked List Class
class Linked_List:
    def __init__(self):
        self.head = None
        self.tail = None

    def insert(self, val):
        if self.head is None:
            self.head = Node(val)
            self.tail = self.head
        else:
            self.tail.next = Node(val)
            self.tail = self.tail.next

def printList(head):
    tmp = head
    while tmp:
        print(tmp.data, end=' ')
        tmp=tmp.next
    print()

if __name__=='__main__':
    for i in range(int(input())):
        n = int(input())
        arr = [int(x) for x in input().split()]
        
        lis = Linked_List()
        for i in arr:
            lis.insert(i)
        
        newHead = Solution().reverseList(lis.head)
        printList(newHead)

# } Driver Code Ends

```

> Time Complexity = O( N )

> Space Complexity = O( 1 )
