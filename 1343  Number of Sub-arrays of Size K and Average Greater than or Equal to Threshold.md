# Number of Sub-arrays of Size K and Average Greater than or Equal to Threshold (LeetCode 1343) https://leetcode.com/problems/number-of-sub-arrays-of-size-k-and-average-greater-than-or-equal-to-threshold/

## Problem Statement

Given an integer array `arr` and two integers `k` and `threshold`, return the number of contiguous subarrays of size `k` whose average is greater than or equal to `threshold`.

### Example

**Input:**
```text
arr = [2,2,2,2,5,5,5,8]
k = 3
threshold = 4
```

**Output:**
```text
3
```

**Explanation:**
```text
Subarrays [2,5,5], [5,5,5], and [5,5,8]
have averages 4, 5, and 6 respectively.
```

## Code

```python
class Solution:
    def numOfSubarrays(self, arr: List[int], k: int, threshold: int) -> int:

        sub_arr=sum(arr[:k])
        count=0
        if sub_arr/k>=threshold:
            count+=1

        for i in range(k,len(arr)):
            sub_arr+=arr[i]
            sub_arr-=arr[i-k]

            if sub_arr/k>=threshold:
                count+=1
        return count
```
---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)