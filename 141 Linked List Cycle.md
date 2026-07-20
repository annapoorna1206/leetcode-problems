# Linked List Cycle (LeetCode 141) https://leetcode.com/problems/linked-list-cycle/

## Problem Statement

Given the `head` of a linked list, determine if the linked list has a cycle in it.

A cycle exists if a node can be reached again by continuously following the `next` pointer.

Return `true` if there is a cycle; otherwise, return `false`.

### Example

**Input:**
```text
head = [3,2,0,-4], pos = 1
```

**Output:**
```text
true
```

**Explanation:**
```text
The tail connects to the node at index 1,
forming a cycle in the linked list.
```

---

## Approach

- Use two pointers:
  - `slow` moves one step at a time.
  - `fast` moves two steps at a time.
- If there is a cycle, the two pointers will eventually meet.
- If `fast` reaches the end (`None`), the list does not contain a cycle.

This is known as **Floyd’s Cycle Detection Algorithm (Tortoise and Hare)**.

---

## Code

```python
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

            if slow == fast:
                return True

        return False
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)