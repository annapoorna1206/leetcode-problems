# Build Array from Permutation (LeetCode 1920) https://leetcode.com/problems/build-array-from-permutation/

## Problem Statement

Given a zero-based permutation array `nums` (containing all integers from `0` to `n-1` exactly once), build an array `ans` such that:

```text
ans[i] = nums[nums[i]]
```

Return the array `ans`.

### Example

**Input:**
```text
nums = [0,2,1,5,3,4]
```

**Output:**
```text
[0,1,2,4,5,3]
```

**Explanation:**
```text
ans[0] = nums[nums[0]] = nums[0] = 0
ans[1] = nums[nums[1]] = nums[2] = 1
ans[2] = nums[nums[2]] = nums[1] = 2
ans[3] = nums[nums[3]] = nums[5] = 4
ans[4] = nums[nums[4]] = nums[3] = 5
ans[5] = nums[nums[5]] = nums[4] = 3

Result = [0,1,2,4,5,3]
```

---

## Approach

- Create an empty array `ar`.
- Traverse the array `nums`.
- For each index `i`, append `nums[nums[i]]` to `ar`.
- Return the resulting array.

---

## Code

```python
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        ar = []

        for i in range(len(nums)):
            ar.append(nums[nums[i]])

        return ar
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)