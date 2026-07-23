# Sort Array By Parity (LeetCode 905) https://leetcode.com/problems/sort-array-by-parity/description/

## Problem Statement

Given an integer array `nums`, move all the even integers to the beginning of the array, followed by all the odd integers.

Return any array that satisfies this condition.

### Example

**Input:**
```text
nums = [3,1,2,4]
```

**Output:**
```text
[2,4,3,1]
```

**Explanation:**
```text
All even numbers appear before all odd numbers.
Other valid outputs are also possible.
```

---

## Approach

- Create an empty list `ans`.
- Traverse the array and append all even numbers to `ans`.
- Traverse the array again and append all odd numbers.
- Return the resulting array.

---

## Code

```python
class Solution:
    def sortArrayByParity(self, nums: List[int]) -> List[int]:
        ans = []

        for num in nums:
            if num % 2 == 0:
                ans.append(num)

        for num in nums:
            if num % 2 != 0:
                ans.append(num)

        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)