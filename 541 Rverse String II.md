# Reverse String II (LeetCode 541) https://leetcode.com/problems/reverse-string-ii/

## Problem Statement

Given a string `s` and an integer `k`, reverse the first `k` characters for every `2k` characters counting from the start of the string.

Rules:

- If there are fewer than `k` characters left, reverse all of them.
- If there are at least `k` but fewer than `2k` characters left, reverse only the first `k` characters.

Return the modified string.

### Example

**Input:**
```text
s = "abcdefg"
k = 2
```

**Output:**
```text
"bacdfeg"
```

**Explanation:**
```text
"ab" -> "ba"
"cd" remains the same
"ef" -> "fe"
"g" remains the same

Result = "bacdfeg"
```

---

## Approach

- Convert the string into a list because strings are immutable.
- Traverse the string in steps of `2 * k`.
- For each block, reverse the first `k` characters using slicing.
- Convert the list back to a string and return it.

---

## Code

```python
class Solution:
    def reverseStr(self, s: str, k: int) -> str:
        s = list(s)

        for i in range(0, len(s), 2 * k):
            s[i:i + k] = reversed(s[i:i + k])

        return "".join(s)
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)