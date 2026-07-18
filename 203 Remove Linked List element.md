# Remove Linked List Elements (LeetCode 203) https://leetcode.com/problems/remove-linked-list-elements/

## Problem Statement

Given the head of a linked list and an integer `val`, remove all nodes of the linked list that have `Node.val == val`, and return the new head.

### Example

**Input:**
```text
head = [1,2,6,3,4,5,6]
val = 6
```

**Output:**
```text
[1,2,3,4,5]
```
## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        while head and head.val == val:
            head = head.next

        temp = head

        while(temp!=None and temp.next!=None):
            front = temp.next
            if front.val==val:
                front = front.next
                temp.next = front
            else:
                temp = temp.next
        return head
        
```
---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)