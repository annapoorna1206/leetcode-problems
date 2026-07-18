# Reverse Linked List (LeetCode 206) https://leetcode.com/problems/reverse-linked-list/

## Problem Statement

Given the head of a singly linked list, reverse the linked list and return the new head.

### Example

**Input:**
```text
head = [1,2,3,4,5]
```

**Output:**
```text
[5,4,3,2,1]
```

---

## Approach

- Use three pointers:
  - `prev` → stores the previous node.
  - `temp` → current node being processed.
  - `front` → stores the next node before breaking the link.
- Reverse the link of the current node by pointing it to `prev`.
- Move all pointers one step forward.
- Continue until the end of the list.
- Return `prev`, which becomes the new head of the reversed list.

---

## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp=head
        prev=None

        while(temp!=None):
            front=temp.next
            temp.next=prev
            prev=temp
            temp=front

        return prev
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)