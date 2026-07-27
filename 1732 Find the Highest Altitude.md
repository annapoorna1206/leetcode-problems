# Find the Highest Altitude (LeetCode 1732) https://leetcode.com/problems/find-the-highest-altitude/

## Problem Statement

There is a biker going on a road trip. The trip consists of `n + 1` points at different altitudes.

You are given an integer array `gain` where:

```text
gain[i] = altitude difference between points i and i + 1
```

The biker starts at altitude `0`.

Return the highest altitude reached during the trip.

### Example

**Input:**
```text
gain = [-5,1,5,0,-7]
```

**Output:**
```text
1
```

**Explanation:**
```text
Starting altitude = 0

Altitudes:
0
0 + (-5) = -5
-5 + 1 = -4
-4 + 5 = 1
1 + 0 = 1
1 + (-7) = -6

Highest altitude = 1
```

---

## Approach

- Start with altitude `0`.
- Store the current altitude while traversing the `gain` array.
- Keep adding each gain value to the current altitude.
- Store all altitudes in a list.
- Return the maximum altitude reached.

---

## Code

```python
class Solution:
    def largestAltitude(self, gain: List[int]) -> int:
        arr = []
        sums = 0

        arr.append(sums)

        for i in range(len(gain)):
            sums = sums + gain[i]
            arr.append(sums)

        return max(arr)
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(n)