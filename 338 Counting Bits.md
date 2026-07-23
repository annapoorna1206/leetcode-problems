# Counting Bits (LeetCode 338) https://leetcode.com/problems/counting-bits/

## Problem Statement

Given an integer `n`, return an array `ans` of length `n + 1` such that:

```text
ans[i] = number of 1's in the binary representation of i
```

for every `0 <= i <= n`.

### Example

**Input:**
```text
n = 5
```

**Output:**
```text
[0,1,1,2,1,2]
```

**Explanation:**
```text
0 -> 0   -> 0 ones
1 -> 1   -> 1 one
2 -> 10  -> 1 one
3 -> 11  -> 2 ones
4 -> 100 -> 1 one
5 -> 101 -> 2 ones
```

---

## Approach

- Traverse all numbers from `0` to `n`.
- Convert each number to its binary representation.
- Count the number of `'1'` bits in the binary string.
- Store the count in the result array.
- Return the array.

---

## Code

```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        arr = []

        for i in range(0, n + 1):
            num = f"{i:b}"
            b = num.count("1")
            arr.append(b)

        return arr
```

---

## Complexity

- **Time Complexity:** O(n log n)
  - Each number is converted to binary and scanned for `1`s.
- **Space Complexity:** O(n)
  - Result array stores `n + 1` values.