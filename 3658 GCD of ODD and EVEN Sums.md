# GCD of Odd and Even Sums https://leetcode.com/problems/gcd-of-odd-and-even-sums/

## Problem Statement

Given an integer `n`:

- `sumOdd` = sum of the first `n` positive odd numbers.
- `sumEven` = sum of the first `n` positive even numbers.

Return the **GCD (Greatest Common Divisor)** of `sumOdd` and `sumEven`.

### Example

**Input:**
```text
n = 3
```

**Output:**
```text
3
```

**Explanation:**
```text
sumOdd  = 1 + 3 + 5 = 9
sumEven = 2 + 4 + 6 = 12

GCD(9, 12) = 3
```

---

## Approach

- The sum of the first `n` odd numbers is:


::contentReference[oaicite:0]{index=0}


- Therefore:
  - `sumOdd = n²`
  - `sumEven = n(n + 1)`
- Compute `gcd(n², n(n+1))` and return the result.

---

## Code

```python
from math import gcd

class Solution:
    def gcdOfOddEvenSums(self, n: int) -> int:

        odd = n * n
        even = n * (n + 1)

        return gcd(odd, even)
```

---

## Complexity

- **Time Complexity:** O(log n)
- **Space Complexity:** O(1)