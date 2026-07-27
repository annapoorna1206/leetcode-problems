# Maximum Product of Two Elements in an Array (LeetCode 1464)

## Problem Statement

Given an integer array `nums`, choose two different indices `i` and `j` such that:

```text
(nums[i] - 1) * (nums[j] - 1)
```

is maximized.

Return the maximum value of this expression.

### Example

**Input:**
```text
nums = [3,4,5,2]
```

**Output:**
```text
12
```

**Explanation:**
```text
Choose 5 and 4.

(5 - 1) × (4 - 1)
= 4 × 3
= 12
```

---

## Approach

- Sort the array in ascending order.
- The two largest elements will produce the maximum product.
- Take the last two elements of the sorted array.
- Compute:

```text
(nums[-1] - 1) × (nums[-2] - 1)
```

- Return the result.

---

## Code

```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        nums.sort()
        a = (nums[-1] - 1) * (nums[-2] - 1)
        return a
```

---

## Complexity

- **Time Complexity:** O(n log n)
  - Due to sorting.
- **Space Complexity:** O(1)