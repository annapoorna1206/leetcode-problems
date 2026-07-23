# Next Greater Element I (LeetCode 496) https://leetcode.com/problems/next-greater-element-i/submissions/2078054352/

## Problem Statement

You are given two distinct integer arrays `nums1` and `nums2`, where `nums1` is a subset of `nums2`.

For each element in `nums1`, find the first greater element that appears to its right in `nums2`.

If no such element exists, return `-1` for that element.

### Example

**Input:**
```text
nums1 = [4,1,2]
nums2 = [1,3,4,2]
```

**Output:**
```text
[-1,3,-1]
```

**Explanation:**
```text
For 4, there is no greater element to its right → -1
For 1, the next greater element is 3
For 2, there is no greater element to its right → -1
```

---

## Approach

- For each element in `nums1`:
  - Find its index in `nums2`.
  - Traverse the elements to its right in `nums2`.
  - Find the first element greater than the current number.
  - If found, store it; otherwise, store `-1`.
- Return the resulting array.

---

## Code

```python
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        ans = []

        for num in nums1:
            ind = nums2.index(num)
            greater = -1

            for i in range(ind + 1, len(nums2)):
                if nums2[i] > num:
                    greater = nums2[i]
                    break

            ans.append(greater)

        return ans
```

---

## Complexity

- **Time Complexity:** O(m × n)
  - `m` = length of `nums1`
  - `n` = length of `nums2`
- **Space Complexity:** O(1) (excluding output array)