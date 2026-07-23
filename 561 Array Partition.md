# Array Partition (LeetCode 561) https://leetcode.com/problems/array-partition/description/

## Problem Statement

Given an integer array `nums` of `2n` integers, group these integers into `n` pairs such that:

```text
(a1, b1), (a2, b2), ..., (an, bn)
```

The score is the sum of the minimum value in each pair.

Return the maximum possible score.

### Example

**Input:**
```text
nums = [1,4,3,2]
```

**Output:**
```text
4
```

**Explanation:**
```text
After sorting: [1,2,3,4]

Pairs:
(1,2) -> min = 1
(3,4) -> min = 3

Score = 1 + 3 = 4
```

---

## Approach

- Sort the array in ascending order.
- Pair adjacent elements after sorting.
- In each pair, the first element is the minimum.
- Sum all elements at even indices (`0, 2, 4, ...`).
- Return the sum.

---

## Code

```python
class Solution:
    def arrayPairSum(self, nums: List[int]) -> int:
        return sum(sorted(nums)[::2])
```

---

## Complexity

- **Time Complexity:** O(n log n)
  - Due to sorting.
- **Space Complexity:** O(n)
  - `sorted()` creates a new array.