# Check If Two String Arrays are Equivalent (LeetCode 1662) https://leetcode.com/problems/check-if-two-string-arrays-are-equivalent/

## Problem Statement

Given two string arrays `word1` and `word2`, return `True` if the two arrays represent the same string, and `False` otherwise.

A string is represented by concatenating all the strings in the array in order.

---

## Example 1

**Input:**

```text
word1 = ["ab", "c"]
word2 = ["a", "bc"]
```

**Output:**

```text
True
```

**Explanation:**

```text
word1 → "ab" + "c" = "abc"
word2 → "a" + "bc" = "abc"

Both strings are equal.
```

---

## Example 2

**Input:**

```text
word1 = ["a", "cb"]
word2 = ["ab", "c"]
```

**Output:**

```text
False
```

**Explanation:**

```text
word1 → "acb"
word2 → "abc"

The strings are different.
```

---

## Approach

- Create two empty strings `s1` and `s2`.
- Concatenate all strings in `word1` into `s1`.
- Concatenate all strings in `word2` into `s2`.
- Compare the two resulting strings.
- Return `True` if they are equal; otherwise return `False`.

---

## Code

```python
class Solution:
    def arrayStringsAreEqual(self, word1: List[str], word2: List[str]) -> bool:
        s1 = ""
        s2 = ""

        for ch in word1:
            s1 += ch

        for ch in word2:
            s2 += ch

        if s1 == s2:
            return True
        else:
            return False
```

---

## Example Walkthrough

**Input:**

```text
word1 = ["ab", "c"]
word2 = ["a", "bc"]
```

Build the strings:

```text
s1 = "ab" + "c"
   = "abc"

s2 = "a" + "bc"
   = "abc"
```

Compare:

```text
"abc" == "abc" ✓
```

Return:

```text
True
```

---

## Complexity

- **Time Complexity:** O(n + m)
  - `n` = total length of all strings in `word1`
  - `m` = total length of all strings in `word2`

- **Space Complexity:** O(n + m)
  - Two additional strings are created.

---

## Better Python Approach

Python provides `join()` to concatenate strings efficiently:

```python
class Solution:
    def arrayStringsAreEqual(self, word1: List[str], word2: List[str]) -> bool:
        return "".join(word1) == "".join(word2)
```

- **Time Complexity:** O(n + m)
- **Space Complexity:** O(n + m)

---

## Pattern

```text
String Concatenation + Comparison

1. Join all strings in the first array.
2. Join all strings in the second array.
3. Compare the resulting strings.
```

This is a simple **String Manipulation** problem that tests concatenation and comparison of strings.