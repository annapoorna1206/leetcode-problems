# Max Consecutive Ones (LeetCode 485) https://leetcode.com/problems/max-consecutive-ones/description/

## Problem Statement

Given a binary array `nums`, return the maximum number of consecutive `1`s in the array.

### Example

**Input:**
```text
nums = [1,1,0,1,1,1]
```

**Output:**
```text
3
```

---

## Approach

- Traverse the array while maintaining a count of consecutive `1`s.
- Increment the count when a `1` is encountered.
- Reset the count to `0` when a `0` is encountered.
- Keep track of the maximum count throughout the traversal.

---

## Code

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        count=0
        ans=0
        for i in range(len(nums)):
            if nums[i]==1:
                count=count+1
                ans=max(ans,count)
            else:
                count=0
        return ans        
                
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)