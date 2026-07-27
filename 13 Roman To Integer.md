# Roman to Integer (LeetCode 13) https://leetcode.com/problems/roman-to-integer/description/

## Problem Statement

Roman numerals are represented by seven symbols:

```text
I = 1
V = 5
X = 10
L = 50
C = 100
D = 500
M = 1000
```

Given a Roman numeral string `s`, convert it into an integer.

### Example

**Input:**
```text
s = "III"
```

**Output:**
```text
3
```

**Explanation:**
```text
I + I + I = 3
```

### Example 2

**Input:**
```text
s = "IV"
```

**Output:**
```text
4
```

**Explanation:**
```text
I comes before V, so 1 is subtracted from 5.

5 - 1 = 4
```

---

## Approach

- Store the value of each Roman numeral in a dictionary.
- Traverse the string from left to right.
- If the current numeral is smaller than the next numeral:
  - Subtract its value from the answer.
- Otherwise:
  - Add its value to the answer.
- Return the final integer value.

---

## Code

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        roman = {
            "I": 1,
            "V": 5,
            "X": 10,
            "L": 50,
            "C": 100,
            "D": 500,
            "M": 1000
        }
        ans = 0
        for i in range(len(s)):
            if i < len(s) - 1 and roman[s[i]] < roman[s[i + 1]]:
                ans = ans - roman[s[i]]
            else:
                ans = ans + roman[s[i]]
        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
  - Each character is processed once.
- **Space Complexity:** O(1)
  - The Roman numeral dictionary has a fixed size.