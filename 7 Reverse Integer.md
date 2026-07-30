# Reverse Integer (LeetCode 7) https://leetcode.com/problems/reverse-integer/

## Problem Statement

Given a signed 32-bit integer `x`, return `x` with its digits reversed.

If reversing `x` causes the value to go outside the signed 32-bit integer range:

```text
[-2³¹, 2³¹ - 1]
```

return `0`.

### Example 1

**Input:**
```text
x = 123
```

**Output:**
```text
321
```

### Example 2

**Input:**
```text
x = -123
```

**Output:**
```text
-321
```

### Example 3

**Input:**
```text
x = 120
```

**Output:**
```text
21
```

**Explanation:**
```text
Leading zeros are removed after reversal.
```

---

## Approach

- Store the sign of the number.
- Convert the number to its absolute value.
- Extract digits one by one using `% 10`.
- Build the reversed number using:

```text
rev = rev * 10 + digit
```

- Restore the original sign.
- Check whether the result is within the 32-bit signed integer range.
- If not, return `0`.

---

## Code

```python
class Solution:
    def reverse(self, x: int) -> int:
        sign = -1 if x < 0 else 1
        x = abs(x)

        rev = 0

        while x:
            digit = x % 10
            rev = rev * 10 + digit
            x = x // 10

        rev = sign * rev

        if rev < -2**31 or rev > 2**31 - 1:
            return 0

        return rev
```

---

## Example Walkthrough

**Input:**

```text
x = 123
```

Steps:

```text
rev = 0

digit = 3 → rev = 3
digit = 2 → rev = 32
digit = 1 → rev = 321
```

Result:

```text
321
```

---

## Complexity

- **Time Complexity:** O(log₁₀ n)
  - One iteration per digit.
- **Space Complexity:** O(1)