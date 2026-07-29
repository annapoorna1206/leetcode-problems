# Missing Number (LeetCode 268) https://leetcode.com/problems/missing-number/

## Problem Statement

Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

### Example 1

**Input:**
```text
nums = [3,0,1]
```

**Output:**
```text
2
```

**Explanation:**
```text
Numbers from 0 to 3 are:
0, 1, 2, 3

The missing number is 2.
```

### Example 2

**Input:**
```text
nums = [0,1]
```

**Output:**
```text
2
```

### Example 3

**Input:**
```text
nums = [9,6,4,2,3,5,7,0,1]
```

**Output:**
```text
8
```

---

## Approach

- Sort the array.
- Traverse the array from index `0`.
- If the value at any index does not match the index itself, that index is the missing number.
- If all indices match their values, then the missing number is `n` (the length of the array).

---

## Code

```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        nums.sort()

        for i in range(len(nums)):
            if nums[i] != i:
                return i

        return len(nums)
```

---

## Complexity

- **Time Complexity:** O(n log n)
  - Due to sorting.
- **Space Complexity:** O(1)