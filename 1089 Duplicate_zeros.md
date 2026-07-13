# Duplicate Zeros (LeetCode 1089) https://leetcode.com/problems/duplicate-zeros/description/

## Problem Statement

Given a fixed-length integer array `arr`, duplicate each occurrence of `0`, shifting the remaining elements to the right. Elements beyond the original array length are discarded. Modify the array **in-place** and do not return anything.

### Example

**Input:**
```text
arr = [1,0,2,3,0,4,5,0]
```

**Output:**
```text
[1,0,0,2,3,0,0,4]
```

---

## Approach

- Traverse the array using an index `i`.
- Whenever a `0` is encountered:
  - Insert another `0` immediately after it.
  - Remove the last element to maintain the original array length.
  - Skip the duplicated zero by incrementing `i`.
- Continue until the second-last index.

---

## Code

```python
class Solution:
    def duplicateZeros(self, arr: List[int]) -> None:
        """
        Do not return anything, modify arr in-place instead.
        """
        i=0
        while i < len(arr)-1:
            if arr[i]==0:
                arr.insert(i+1,0)
                arr.pop()
                i+=1
            i=i+1

            
            
```

---

## Complexity

- **Time Complexity:** O(n²) *(since `insert()` shifts elements in the array)*
- **Space Complexity:** O(1)