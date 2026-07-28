# Degree of an Array (LeetCode 697) https://leetcode.com/problems/degree-of-an-array/

## Problem Statement

Given a non-empty array of non-negative integers `nums`, the **degree** of the array is the maximum frequency of any one of its elements.

Your task is to find the length of the shortest contiguous subarray that has the same degree as the entire array.

### Example

**Input:**
```text
nums = [1,2,2,3,1]
```

**Output:**
```text
2
```

**Explanation:**
```text
Frequency of elements:
1 → 2
2 → 2
3 → 1

Degree of array = 2

Subarrays with degree 2:
[1,2,2,3,1] → length 5
[2,2] → length 2

Shortest length = 2
```

### Example 2

**Input:**
```text
nums = [1,2,2,3,1,4,2]
```

**Output:**
```text
6
```

---

## Approach

- Use three dictionaries:
  - `count` → stores frequency of each number.
  - `first` → stores the first occurrence index.
  - `last` → stores the last occurrence index.
- Traverse the array and update these dictionaries.
- Find the degree of the array using the maximum frequency.
- For every number having the same frequency as the degree:
  - Calculate the subarray length using:

```text
last[num] - first[num] + 1
```

- Return the minimum such length.

---

## Code

```python
class Solution:
    def findShortestSubArray(self, nums: List[int]) -> int:
        count = {}
        first = {}
        last = {}

        for i in range(len(nums)):
            if nums[i] not in first:
                first[nums[i]] = i

            last[nums[i]] = i
            count[nums[i]] = count.get(nums[i], 0) + 1

        degree = max(count.values())
        ans = len(nums)

        for num in count:
            if count[num] == degree:
                ans = min(ans, last[num] - first[num] + 1)

        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
  - One pass to collect frequencies and indices, and one pass through the dictionary.
- **Space Complexity:** O(n)
  - Dictionaries store information about array elements.