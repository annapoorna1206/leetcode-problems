# Merge Two Sorted Lists (LeetCode 21) https://leetcode.com/problems/merge-two-sorted-lists/

## Problem Statement

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one sorted linked list and return its head.

### Example

**Input:**
```text
list1 = [1,2,4]
list2 = [1,3,4]
```

**Output:**
```text
[1,1,2,3,4,4]
```
## Code

```python
class Solution:
    def mergeTwoLists(
        self,
        list1: Optional[ListNode],
        list2: Optional[ListNode]
    ) -> Optional[ListNode]:

        if not list1 or not list2:
            return list1 or list2

        if list1.val <= list2.val:
            list1.next = self.mergeTwoLists(list1.next, list2)
            return list1
        else:
            list2.next = self.mergeTwoLists(list1, list2.next)
            return list2
```

---

## Complexity

- **Time Complexity:** O(m + n)
  - `m` and `n` are the lengths of the two lists.
- **Space Complexity:** O(m + n)
  - Due to the recursive call stack.