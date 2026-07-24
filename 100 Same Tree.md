# Same Tree (LeetCode 100) https://leetcode.com/problems/same-tree/

## Problem Statement

Given the roots of two binary trees `p` and `q`, return `true` if they are the same tree, and `false` otherwise.

Two binary trees are considered the same if:

- They are structurally identical.
- The corresponding nodes have the same values.

### Example

**Input:**
```text
p = [1,2,3]
q = [1,2,3]
```

**Output:**
```text
true
```

### Example 2

**Input:**
```text
p = [1,2]
q = [1,null,2]
```

**Output:**
```text
false
```

---

## Approach

- Compare both trees recursively.
- If both nodes are `None`, they are identical at that position.
- If one node is `None` and the other is not, the trees are different.
- If the node values differ, return `False`.
- Recursively compare:
  - Left subtrees
  - Right subtrees
- The trees are the same only if all corresponding nodes match.

---

## Code

```python
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        if p is None and q is None:
            return True

        if p is None or q is None:
            return False

        if p.val != q.val:
            return False

        return (
            self.isSameTree(p.left, q.left)
            and
            self.isSameTree(p.right, q.right)
        )
```

---

## Complexity

- **Time Complexity:** O(n)
  - Every node is visited once.
- **Space Complexity:** O(h)
  - `h` is the height of the tree due to recursion.
  - Worst case: O(n)
  - Balanced tree: O(log n)