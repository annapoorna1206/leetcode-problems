# Intersection of Two Arrays (LeetCode 349) https://leetcode.com/problems/intersection-of-two-arrays/

## Problem Statement

Given two integer arrays `nums1` and `nums2`, return an array of their intersection.

The intersection should contain **unique elements only**.

The order of elements in the result does not matter.

---

## Example 1

**Input:**

```text
nums1 = [1,2,2,1]
nums2 = [2,2]
```

**Output:**

```text
[2]
```

**Explanation:**

The common element between both arrays is:

```text
2
```

Duplicate values are removed.

---

## Example 2

**Input:**

```text
nums1 = [4,9,5]
nums2 = [9,4,9,8,4]
```

**Output:**

```text
[9,4]
```

---

# Approach (Using Set)

### Idea:

- Convert both arrays into sets.
- Sets automatically remove duplicates.
- Find common elements using set intersection:

```python
set1 & set2
```

- Convert the result back into a list.

---

## Code

```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        set1 = set(nums1)
        set2 = set(nums2)

        return list(set1 & set2)
```

---

## Example Walkthrough

Input:

```text
nums1 = [1,2,2,1]
nums2 = [2,2]
```

Convert to sets:

```text
set1 = {1,2}

set2 = {2}
```

Intersection:

```text
{1,2} & {2}

= {2}
```

Convert to list:

```text
[2]
```

---

## Complexity

Let:

- `n` = length of nums1
- `m` = length of nums2

### Time Complexity:

```text
O(n + m)
```

- Creating sets takes O(n) and O(m).
- Intersection takes O(min(n,m)).

### Space Complexity:

```text
O(n + m)
```

- Extra space is used to store the sets.

---

## Pattern

```text
Hash Set Pattern

1. Store elements in a set.
2. Use set operations for:
   - intersection (&)
   - union (|)
   - difference (-)
```

This pattern is useful for problems involving:
- Duplicate removal
- Common elements
- Frequency checking
- Fast lookup operations