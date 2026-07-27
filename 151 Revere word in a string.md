# Reverse Words in a String (LeetCode 151) https://leetcode.com/problems/reverse-words-in-a-string/

## Problem Statement

Given an input string `s`, reverse the order of the words.

A word is defined as a sequence of non-space characters.

The returned string should:

- Contain words in reverse order.
- Have only a single space separating words.
- Not contain leading or trailing spaces.

### Example

**Input:**
```text
s = "the sky is blue"
```

**Output:**
```text
"blue is sky the"
```

### Example 2

**Input:**
```text
s = "  hello world  "
```

**Output:**
```text
"world hello"
```

**Explanation:**
```text
Leading and trailing spaces are removed.
```

---

## Approach

- Use `split()` to separate the string into words.
  - `split()` automatically removes extra spaces.
- Reverse the list of words.
- Join the words using a single space.
- Return the resulting string.

---

## Code

```python
class Solution:
    def reverseWords(self, s: str) -> str:
        w = s.split()
        w.reverse()
        joint = " ".join(w)
        return joint
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)