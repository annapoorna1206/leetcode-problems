# Single Number (LeetCode 136) https://leetcode.com/problems/single-number-ii/

## Problem Statement

Given a non-empty integer array `nums`, every element appears twice except for one. Find that single one and return it.

### Example

**Input:**
```text
nums = [4,1,2,1,2]
```

**Output:**
```text
4
```
## Code

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        for i in range(len(nums)):
            if nums.count(nums[i])==1:
                return nums[i]
```

---

## Complexity

- **Time Complexity:** O(n²)
  - `count()` takes O(n) time and is called for each element.
- **Space Complexity:** O(1)