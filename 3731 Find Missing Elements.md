# Find Missing Elements (Leetcode Problem 3731) https://leetcode.com/problems/find-missing-elements/description/?envType=daily-question&envId=2026-08-04

## Problem Statement

Given an integer array `nums`, return a list of all the missing integers between the **minimum** and **maximum** values (inclusive) of the array.

The missing numbers should be returned in ascending order.

---

## Example 1

**Input:**

```text
nums = [1, 3, 5, 6]
```

**Output:**

```text
[2, 4]
```

**Explanation:**

The numbers between `1` and `6` are:

```text
1, 2, 3, 4, 5, 6
```

The numbers missing from the array are:

```text
2, 4
```

---

## Example 2

**Input:**

```text
nums = [7, 8, 9]
```

**Output:**

```text
[]
```

**Explanation:**

All numbers between `7` and `9` are present.

---

# Approach

### Idea:

- Find the smallest and largest elements in the array.
- Traverse every number from `min_num` to `max_num`.
- For each number:
  - Check if it is present in the array.
  - If not, add it to the answer list.
- Return the list of missing numbers.

---

## Code

```python
class Solution:
    def findMissingElements(self, nums: List[int]) -> List[int]:
        min_num = min(nums)
        max_num = max(nums)

        arr = []

        for i in range(min_num, max_num + 1):
            if i not in nums:
                arr.append(i)

        return arr
```

---

## Example Walkthrough

**Input:**

```text
nums = [1, 3, 5, 6]
```

Find the range:

```text
min_num = 1
max_num = 6
```

Check each number:

```text
1 → Present ✓
2 → Missing ✗ → Add
3 → Present ✓
4 → Missing ✗ → Add
5 → Present ✓
6 → Present ✓
```

Result:

```text
[2, 4]
```

---

## Complexity

### Your Solution

- **Time Complexity:** O(n × r)

Where:

- `n` = size of the array
- `r` = `max(nums) - min(nums) + 1`

This is because each `i not in nums` performs a linear search through the array.

- **Space Complexity:** O(k)

Where `k` is the number of missing elements stored in the result list.

---

## Optimized Approach

Convert the array to a **set** for faster lookups.

```python
class Solution:
    def findMissingElements(self, nums: List[int]) -> List[int]:
        num_set = set(nums)

        min_num = min(nums)
        max_num = max(nums)

        ans = []

        for i in range(min_num, max_num + 1):
            if i not in num_set:
                ans.append(i)

        return ans
```

### Complexity

- **Time Complexity:** O(n + r)
- **Space Complexity:** O(n)

Using a set reduces the lookup time from **O(n)** to **O(1)** on average.

---

## Pattern

```text
Range Traversal + Membership Check

1. Find minimum and maximum values.
2. Traverse the complete range.
3. Check whether each value exists.
4. Collect missing values.
```

This pattern is commonly used in problems involving:
- Missing numbers
- Consecutive sequences
- Range validation
- Hash Set optimization