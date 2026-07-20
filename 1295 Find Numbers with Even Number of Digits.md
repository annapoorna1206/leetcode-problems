# Find Numbers with Even Number of Digits (LeetCode 1295)

## Problem Statement

Given an array `nums` of integers, return the number of integers that contain an even number of digits.

### Example

**Input:**
```text
nums = [12,345,2,6,7896]
```

**Output:**
```text
2
```

**Explanation:**
```text
12 contains 2 digits (even)
345 contains 3 digits (odd)
2 contains 1 digit (odd)
6 contains 1 digit (odd)
7896 contains 4 digits (even)

Therefore, the answer is 2.
```
## Code

```python
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        count = 0
        for i in range(len(nums)):
            num = nums[i]
            digits=0
            while num>0:
                digits+=1
                num=num//10
            if digits%2==0:
                count+=1
        return count
```

---

## Complexity

- **Time Complexity:** O(n × d)
  - `n` = number of elements
  - `d` = number of digits in each number
- **Space Complexity:** O(1)