# Longest Substring Without Repeating Characters (LeetCode 3)

## Problem Statement

Given a string `s`, find the length of the longest substring without repeating characters.

### Example

**Input:**
```text
s = "abcabcbb"
```

**Output:**
```text
3
```

**Explanation:**
```text
The longest substring without repeating characters is "abc",
which has a length of 3.
```
## Code

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        a = set()
        left = 0
        ans = 0

        for right in range(len(s)):
            while s[right] in a:
                a.remove(s[left])
                left += 1

            a.add(s[right])
            ans = max(ans, right - left + 1)

        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(min(n, m))
  - `m` = size of the character set