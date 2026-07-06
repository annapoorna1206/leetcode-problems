# Move Zeroes (LeetCode 283) https://leetcode.com/problems/move-zeroes/description/

## Problem Statement

Given an integer array `nums`, move all the `0`s to the end while maintaining the relative order of the non-zero elements.

**Note:**
- Modify the array **in-place**.
- Do not use an extra array.

### Example

**Input:**
```text
nums = [0,1,0,3,12]
```

**Output:**
```text
[1,3,12,0,0]
```

---

## Approach

- Use two pointers: `i` and `j`.
- `i` traverses the array.
- `j` keeps track of the position where the next non-zero element should be placed.
- Whenever a non-zero element is found, swap it with the element at `j` and increment `j`.

---



```python code
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:

        j = 0

        for i in range(len(nums)):
            if nums[i] != 0:
                nums[j], nums[i] = nums[i], nums[j]
                j += 1
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)
