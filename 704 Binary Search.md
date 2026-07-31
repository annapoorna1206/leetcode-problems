# Binary Search (LeetCode 704) https://leetcode.com/problems/binary-search/description/

## Problem Statement

Given an array of integers `nums` sorted in ascending order, and an integer `target`, return the index of `target` if it exists in `nums`.

If `target` does not exist in the array, return `-1`.

You must write an algorithm with:

```text
O(log n)
```

runtime complexity.

### Example 1

**Input:**
```text
nums = [-1,0,3,5,9,12]
target = 9
```

**Output:**
```text
4
```

**Explanation:**
```text
nums[4] = 9
```

---

### Example 2

**Input:**
```text
nums = [-1,0,3,5,9,12]
target = 2
```

**Output:**
```text
-1
```

**Explanation:**
```text
2 is not present in the array.
```

---

## Approach (Binary Search)

- Since the array is sorted, use binary search.
- Maintain two pointers:
  - `low` → starting index
  - `high` → ending index
- Find the middle element:

```text
mid = (low + high) // 2
```

- Compare `nums[mid]` with `target`:
  - If equal → return `mid`.
  - If `nums[mid] < target` → search the right half.
  - Otherwise → search the left half.
- If the loop ends, the target is not found.

---

## Code

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        low = 0
        high = len(nums) - 1

        while low <= high:
            mid = (low + high) // 2

            if nums[mid] == target:
                return mid

            elif nums[mid] < target:
                low = mid + 1

            else:
                high = mid - 1

        return -1
```

---

## Example Walkthrough

**Input:**

```text
nums = [-1,0,3,5,9,12]
target = 9
```

Steps:

```text
low = 0, high = 5

mid = 2
nums[2] = 3

3 < 9 → search right half

low = 3, high = 5

mid = 4
nums[4] = 9

Found target → return 4
```

---

## Complexity

- **Time Complexity:** O(log n)
  - Search space is reduced by half each iteration.
- **Space Complexity:** O(1)
  - Only constant extra variables are used.