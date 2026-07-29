# Sum of Two Integers (LeetCode 371) https://leetcode.com/problems/sum-of-two-integers/description/

## Problem Statement

Given two integers `a` and `b`, return the sum of the two integers **without using the operators `+` and `-`**.

### Example 1

**Input:**
```text
a = 1, b = 2
```

**Output:**
```text
3
```

### Example 2

**Input:**
```text
a = 2, b = 3
```

**Output:**
```text
5
```

---

## Approach

This solution uses **bit manipulation**:

- `a ^ b` computes the sum without carry.
- `a & b` finds the carry bits.
- `(a & b) << 1` shifts the carry to its correct position.
- Repeat until there is no carry left.
- Use a 32-bit mask to correctly handle negative numbers in Python.

### Bit Operations

```text
XOR (^)
0 ^ 0 = 0
0 ^ 1 = 1
1 ^ 0 = 1
1 ^ 1 = 0
```

```text
AND (&)
0 & 0 = 0
0 & 1 = 0
1 & 0 = 0
1 & 1 = 1
```

---

## Code

```python
class Solution:
    def getSum(self, a: int, b: int) -> int:
        mask = 0xffffffff
        max_int = 0x7fffffff

        while b:
            carry = (a & b) << 1
            a = (a ^ b) & mask
            b = carry & mask

        if a <= max_int:
            return a
        else:
            return ~(a ^ mask)
```

---

## Example Walkthrough

**Input:**

```text
a = 1
b = 2
```

**Iteration 1**

```text
a = 01
b = 10

a ^ b = 11  -> 3
a & b = 00
carry = 00
```

Since carry becomes `0`, the answer is:

```text
3
```

---

## Complexity

- **Time Complexity:** O(1)
  - At most 32 iterations for 32-bit integers.
- **Space Complexity:** O(1)