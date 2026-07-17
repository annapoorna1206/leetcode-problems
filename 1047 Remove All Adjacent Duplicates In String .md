# Remove All Adjacent Duplicates In String (LeetCode 1047)

## Problem Statement

Given a string `s` consisting of lowercase English letters, repeatedly remove adjacent duplicate characters until no more duplicate pairs exist.

Return the final string after all possible removals.

### Example

**Input:**
```text
s = "abbaca"
```

**Output:**
```text
"ca"
```

**Explanation:**
```text
"abbaca" → "aaca" → "ca"
```
## Code

```python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        stack = []
        for ch in s:
            if stack and stack[-1] == ch:
                stack.pop()
            else:
                stack.append(ch)

        return "".join(stack)
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)