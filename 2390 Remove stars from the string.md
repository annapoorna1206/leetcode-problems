# Removing Stars From a String (LeetCode 2390) https://leetcode.com/problems/removing-stars-from-a-string/

## Problem Statement

You are given a string `s` containing lowercase letters and stars (`*`).

In one operation, a star removes itself and the closest non-star character to its left.

Return the resulting string after all stars have been removed.

### Example

**Input:**
```text
s = "leet**cod*e"
```

**Output:**
```text
"lecoe"
```

**Explanation:**
```text
"leet**cod*e"
→ "lee*cod*e"
→ "lecod*e"
→ "lecoe"
```

---

## Approach

- Use a **stack** to keep track of characters.
- Traverse the string:
  - If the current character is `*`, remove the top character from the stack.
  - Otherwise, push the character onto the stack.
- After processing all characters, join the stack to form the final string.

---

## Code

```python
class Solution:
    def removeStars(self, s: str) -> str:
        stack = []

        for ch in s:
            if ch == "*":
                stack.pop()
            else:
                stack.append(ch)

        ans = "".join(stack)
        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)