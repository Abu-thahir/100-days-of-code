---
title: "Merge two sorted linked lists "
description: "The task is to merge both of the list"
categories:
  - LinkedList
---

### Question

> Given two sorted linked lists consisting of N and M nodes respectively. The task is to merge both of the list (in-place) and return head of the merged list.

```
Input:
N = 4, M = 3 
valueN[] = {5,10,15,40}
valueM[] = {2,3,20}
Output: 2 3 5 10 15 20 40
Explanation: After merging the two linked
lists, we have merged list as 2, 3, 5,
10, 15, 20, 40.

```

### Code [python]

```python3

def sortedMerge(head1, head2):
    if head1 is None: return head2 
    elif head2 is None: return head1
    else:
        t1 = head1
        t2 = head2
        if t1.data <= t2.data:
            head = t1
            curr = t1
            t1 = t1.next
        else:
            head = t2
            curr = t2
            t2 = t2.next
        prev = curr
        while t1 is not None and t2 is not None:
            if t1.data <= t2.data:
                curr = t1
                t1 = t1.next
            else:
                curr = t2
                t2 = t2.next
            prev.next = curr
            prev = curr
        curr.next = t2 if t1 is None else t1
        return head

```

> Time Complexity = O( N )

> Space Complexity = O( 1 )
