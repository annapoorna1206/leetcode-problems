# Count Odd Numbers in an Interval Range (LeetCode 1523) https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/

## Problem Statement

Given two non-negative integers `low` and `high`, return the count of odd numbers between `low` and `high` (inclusive).

### Example 1

**Input:**
```text
low = 3, high = 7
```

**Output:**
```text
3
```

**Explanation:**
```text
Odd numbers in the range [3, 7] are:
3, 5, 7

Count = 3
```

### Example 2

**Input:**
```text
low = 8, high = 10
```

**Output:**
```text
1
```

**Explanation:**
```text
Odd numbers in the range [8, 10] are:
9

Count = 1
```

---

## Approach

- The number of integers in the range is:

```text
high - low + 1
```

- If either `low` or `high` is odd, the count of odd numbers is:

```text
(high - low) // 2 + 1
```

- Otherwise:

```text
(high - low + 1) // 2
```

---

## Correct Code

```python
class Solution:
    def countOdds(self, low: int, high: int) -> int:
        count=(high-low)//2
        if low%2!=0 or high%2!=0:
                count+=1     
        return count
```

---

## Complexity

- **Time Complexity:** O(1)
- **Space Complexity:** O(1)