# Rotate String (LeetCode 796) https://leetcode.com/problems/rotate-string/description/

## Problem Statement

Given two strings `s` and `goal`, return `true` if and only if `s` can become `goal` after some number of left rotations.

A left rotation moves the first character of the string to the end.

### Example 1

**Input:**
```text
s = "abcde"
goal = "cdeab"
```

**Output:**
```text
true
```

**Explanation:**
```text
Rotate "abcde" two times:

abcde → bcdea → cdeab

The result matches goal.
```

### Example 2

**Input:**
```text
s = "abcde"
goal = "abced"
```

**Output:**
```text
false
```

---

## Approach

- First, check if both strings have the same length.
  - If not, return `False`.
- Generate all possible left rotations of `s`.
- For each rotation:
  - Compare it with `goal`.
  - If they match, return `True`.
- If no rotation matches, return `False`.

---

## Code

```python
class Solution:
    def rotateString(self, s: str, goal: str) -> bool:

        if len(s) != len(goal):
            return False

        for i in range(len(s)):
            rotated = s[i:] + s[:i]

            if rotated == goal:
                return True

        return False
```

---

## Complexity

- **Time Complexity:** O(n²)
  - There are `n` rotations, and each rotation takes O(n) time.
- **Space Complexity:** O(n)
  - For storing the rotated string.