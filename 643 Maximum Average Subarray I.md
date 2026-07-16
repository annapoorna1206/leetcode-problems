# Maximum Average Subarray I (LeetCode 643) https://leetcode.com/problems/maximum-average-subarray-i/description/

## Problem Statement

Given an integer array `nums` and an integer `k`, find the contiguous subarray of length `k` that has the maximum average value and return that average.

### Example

**Input:**
```text
nums = [1,12,-5,-6,50,3]
k = 4
```

**Output:**
```text
12.75000
```

**Explanation:**
```text
Subarray = [12,-5,-6,50]
Average = (12 - 5 - 6 + 50) / 4 = 51 / 4 = 12.75
```

---

## Approach

- Use the **Sliding Window** technique.
- Calculate the sum of the first `k` elements.
- Slide the window one element at a time:
  - Add the new element entering the window.
  - Remove the element leaving the window.
- Keep track of the maximum window sum.
- Return `max_sum / k`.

---

## Code

```python
class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:
        maxvalue=sum(nums[:k])
        ans=maxvalue

        for i in range(k,len(nums)):
            maxvalue+=nums[i]
            maxvalue-=nums[i-k]
            ans=max(maxvalue,ans)
        newans=ans/k
        return newans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)
