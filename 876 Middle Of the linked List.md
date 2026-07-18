# Middle of the Linked List (LeetCode 876) https://leetcode.com/problems/middle-of-the-linked-list/

## Problem Statement

Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.

### Example

**Input:**
```text
head = [1,2,3,4,5]
```

**Output:**
```text
[3,4,5]
```

**Input:**
```text
head = [1,2,3,4,5,6]
```

**Output:**
```text
[4,5,6]
```
## Code

```python
c# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        count=0
        temp = head
        while temp:
            count+=1
            temp = temp.next

        if count%2!=0:
            x = (count+1)//2

        else:
            x = (count+2)//2

        temp=head
        
        for i in range(1,x):
            temp=temp.next
        return temp



        # Fast and Slow Pointer Approach
        
        # slow=head
        # fast=head

        # while fast and fast.next:
        #     slow=slow.next
        #     fast=fast.next.next

        # return slow
---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

---

## Optimized Approach (Fast & Slow Pointers)

- Use two pointers:
  - `slow` moves one step at a time.
  - `fast` moves two steps at a time.
- When `fast` reaches the end, `slow` will be at the middle node.

```python
slow = head
fast = head

while fast and fast.next:
    slow = slow.next
    fast = fast.next.next

return slow
```

### Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

This approach finds the middle in a single traversal.