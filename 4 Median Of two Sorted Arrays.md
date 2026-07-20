# Median of Two Sorted Arrays (LeetCode 4) https://leetcode.com/problems/median-of-two-sorted-arrays/description/

## Problem Statement

Given two sorted arrays `nums1` and `nums2` of sizes `m` and `n`, return the median of the two sorted arrays.

The overall run time complexity should ideally be **O(log(m+n))**, but this solution uses a simpler merge-and-sort approach.

### Example

**Input:**
```text
nums1 = [1,3]
nums2 = [2]
```

**Output:**
```text
2.0
```

**Explanation:**
```text
Merged array = [1,2,3]
Median = 2
```

---

## Approach

- Combine both arrays into a single array.
- Sort the merged array.
- If the length is odd, return the middle element.
- If the length is even, return the average of the two middle elements.

---

## Code

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        a = nums1 + nums2
        a.sort()
        n = len(a)
        if n % 2 == 0:
            return (a[n//2-1] + a[n//2])/2
        else:
            return a[n//2]
```

---

## Complexity

- **Time Complexity:** O((m + n) log(m + n))
  - Due to sorting the merged array.
- **Space Complexity:** O(m + n)
  - Extra space is used for the merged array.