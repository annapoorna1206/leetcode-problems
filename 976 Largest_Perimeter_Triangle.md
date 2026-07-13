# Largest Perimeter Triangle (LeetCode 976)

## Problem Statement

Given an integer array `nums`, return the **largest perimeter** of a triangle with a non-zero area that can be formed using any three side lengths. If no such triangle can be formed, return `0`.

### Example

**Input:**
```text
nums = [2,1,2]
```

**Output:**
```text
5
```

---

## Approach

- Sort the array in **ascending order**.
- Traverse the array from the end.
- For every three consecutive elements, check the triangle condition:
  - `nums[i-2] + nums[i-1] > nums[i]`
- If the condition is satisfied, return their sum as the largest perimeter.
- If no valid triangle exists, return `0`.

---

## Code

```python
class Solution:
    def largestPerimeter(self, nums: List[int]) -> int:
        nums.sort()
        sum=0
        for i in range(len(nums)-2):
            if(nums[i]+nums[i+1]>nums[i+2] and nums[i+1]+nums[i+2]>nums[i] and nums[i]+nums[i+2]>nums[i+1]):
                sum=nums[i]+nums[i+1]+nums[i+2]
        return sum
```

---

## Complexity

- **Time Complexity:** O(n log n) *(sorting)*
- **Space Complexity:** O(1)