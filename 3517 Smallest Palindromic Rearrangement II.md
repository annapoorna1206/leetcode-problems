# Smallest Palindromic Rearrangement I https://leetcode.com/problems/smallest-palindromic-rearrangement-i/

## Problem Statement

You are given a palindromic string `s`.

Return the **lexicographically smallest palindrome** that can be formed using all the characters of `s`.

A palindrome reads the same forward and backward, and a string is lexicographically smaller if it appears earlier in dictionary order.

### Example

**Input:**
```text
s = "daccad"
```

**Output:**
```text
"acddca"
```

**Explanation:**
```text
Character frequencies:
a → 2
c → 2
d → 2

Smallest left half = "acd"
Right half = reverse("acd") = "dca"

Result = "acddca"
```

---

## Approach

- Count the frequency of each character using `Counter`.
- Traverse the characters in sorted order.
- Add half of each character's occurrences to the left half.
- If a character has an odd frequency, place one occurrence in the middle.
- Create the right half by reversing the left half.
- Combine:

```text
left + middle + reversed(left)
```

This produces the lexicographically smallest valid palindrome.

---

## Code

```python
from collections import Counter

class Solution:
    def smallestPalindrome(self, s: str) -> str:
        freq = Counter(s)
        left = ""
        mid = ""

        for ch in sorted(freq):
            left += ch * (freq[ch] // 2)

            if freq[ch] % 2:
                mid = ch

        right = left[::-1]
        return left + mid + right
```

---

## Complexity

- **Time Complexity:** O(n + k log k)
  - `n` = length of the string
  - `k` = number of distinct characters
- **Space Complexity:** O(n)
  - Used for constructing the palindrome string.