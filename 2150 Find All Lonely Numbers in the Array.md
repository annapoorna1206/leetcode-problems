# Find All Lonely Numbers in the Array (LeetCode 2150) https://leetcode.com/problems/find-all-lonely-numbers-in-the-array/

## Problem Statement

A number `x` is considered **lonely** if:

- It appears exactly once in the array.
- Neither `x - 1` nor `x + 1` exists in the array.

Given an integer array `nums`, return all lonely numbers in the array.

### Example

**Input:**
```text
nums = [10,6,5,8]
```

**Output:**
```text
[10,8]
```

**Explanation:**
```text
10 appears once and neither 9 nor 11 exists.
8 appears once and neither 7 nor 9 exists.
```

---

## Approach

- Use `Counter` to store the frequency of each number.
- Traverse the array:
  - Check if the current number appears exactly once.
  - Check that `num - 1` and `num + 1` are not present in the frequency map.
- If all conditions are satisfied, add the number to the answer list.
- Return the final list.

---

## Code

```python
from collections import Counter

class Solution:
    def findLonely(self, nums: List[int]) -> List[int]:
        freq = Counter(nums)
        ans = []
        for num in nums:
            if freq[num] == 1 and num - 1 not in freq and num + 1 not in freq:
                ans.append(num)
        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)