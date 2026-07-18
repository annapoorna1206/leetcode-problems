# Remove Duplicates from Sorted List (LeetCode 83)

## Problem Statement

Given the head of a sorted linked list, delete all duplicates such that each element appears only once.

Return the linked list sorted as well.

### Example

**Input:**
```text
head = [1,1,2,3,3]
```

**Output:**
```text
[1,2,3]
```
## Code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp = head
        while(temp!=None and temp.next!=None):
            front = temp.next
            if temp.val == front.val:
                front = front.next 
                temp.next = front
            else:
                front= front.next
                temp = temp.next
        return head
        
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)