# Binary Tree Preorder Traversal (LeetCode 144) https://leetcode.com/problems/binary-tree-preorder-traversal/

## Problem Statement

Given the `root` of a binary tree, return the preorder traversal of its nodes' values.

In **Preorder Traversal**, nodes are visited in the following order:

```text
Root → Left → Right
```

### Example

**Input:**
```text
root = [1,null,2,3]
```

**Output:**
```text
[1,2,3]
```

**Explanation:**
```text
    1
     \
      2
     /
    3

Preorder Traversal:
1 → 2 → 3
```

---

## Approach

- Use a recursive helper function.
- If the current node is `None`, return.
- Visit the root node and add its value to the result array.
- Recursively traverse the left subtree.
- Recursively traverse the right subtree.
- Return the final traversal array.

---

## Code

```python
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        arr = []
        def pre(root):
            if not root:
                return None
            arr.append(root.val)
            pre(root.left)
            pre(root.right)
        pre(root)
        return arr
```

---

## Complexity

- **Time Complexity:** O(n)
  - Each node is visited exactly once.
- **Space Complexity:** O(h)
  - `h` is the height of the tree due to the recursion stack.
  - Worst case: O(n)
  - Balanced tree: O(log n)