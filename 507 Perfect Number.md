# Perfect Number (LeetCode 507)

## Problem Statement

A **perfect number** is a positive integer that is equal to the sum of its positive divisors, excluding the number itself.

Given an integer `num`, return `true` if it is a perfect number; otherwise, return `false`.

### Example

**Input:**
```text
num = 28
```

**Output:**
```text
true
```

**Explanation:**
```text
28 = 1 + 2 + 4 + 7 + 14
```

---

## Approach

- Every number has divisors in pairs.
- Start with `sum_divisors = 1` (since 1 is a divisor of every number greater than 1).
- Check divisors from `2` to `√num`.
- If `i` divides `num`:
  - Add `i`.
  - Add its paired divisor `num // i` (if different).
- Finally, compare the sum with `num`.

---

## Code

```python
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        if num <= 1:
            return False
        total = 1
        for i in range(2, int(num ** 0.5) + 1):
            if num % i == 0:
                total += i
                if i != num // i:
                    total += num // i
        return total == num
```

---

## Complexity

- **Time Complexity:** O(√n)
- **Space Complexity:** O(1)