# Linked List Cycle II (LeetCode 142) https://leetcode.com/problems/linked-list-cycle-ii/description/

## Problem Statement

Given the `head` of a linked list, return the node where the cycle begins. If there is no cycle, return `null`.

A cycle exists if a node can be reached again by continuously following the `next` pointer.

### Example

**Input:**
```text
head = [3,2,0,-4], pos = 1
```

**Output:**
```text
Node with value 2
```

**Explanation:**
```text
The tail connects to the node at index 1,
so the cycle starts at the node with value 2.
```
## Code

```python
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow = head
        fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                slow = head
                while slow != fast:
                    slow = slow.next
                    fast = fast.next
                return slow
        return None
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)