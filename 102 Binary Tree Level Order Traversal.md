# Binary Tree Level Order Traversal (LeetCode 102) https://leetcode.com/problems/binary-tree-level-order-traversal/

## Problem Statement

Given the `root` of a binary tree, return the level order traversal of its nodes' values.

Level order traversal visits nodes level by level from left to right.

### Example

**Input:**
```text
root = [3,9,20,null,null,15,7]
```

**Output:**
```text
[[3],[9,20],[15,7]]
```

**Explanation:**
```text
        3
       / \
      9  20
         / \
        15  7

Level 1: [3]
Level 2: [9,20]
Level 3: [15,7]
```

---

## Approach

- Use a queue (`deque`) to perform Breadth-First Search (BFS).
- Start by adding the root node to the queue.
- Process all nodes at the current level:
  - Remove nodes from the queue.
  - Store their values in a temporary list.
  - Add their left and right children to the queue.
- After processing a level, add the level list to the answer.
- Repeat until the queue becomes empty.

---

## Code

```python
from collections import deque

class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        q = deque()
        ans = []

        if root:
            q.append(root)

        while q:
            level = []

            for i in range(len(q)):
                node = q.popleft()
                level.append(node.val)

                if node.left:
                    q.append(node.left)

                if node.right:
                    q.append(node.right)

            ans.append(level)

        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
  - Each node is visited exactly once.
- **Space Complexity:** O(n)
  - In the worst case, the queue may store an entire level of the tree.