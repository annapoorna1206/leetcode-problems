# Maximum Ice Cream Bars (LeetCode 1833) https://leetcode.com/problems/maximum-ice-cream-bars/

## Problem Statement

You are given an array `costs` where `costs[i]` is the cost of the `iᵗʰ` ice cream bar, and an integer `coins` representing the number of coins you have.

Return the maximum number of ice cream bars you can buy with the available coins.

### Example

**Input:**
```text
costs = [1,3,2,4,1]
coins = 7
```

**Output:**
```text
4
```

**Explanation:**
```text
After sorting: [1,1,2,3,4]

Buy ice cream bars costing:
1 + 1 + 2 + 3 = 7

Total bars purchased = 4
```

---

## Approach

- Sort the `costs` array in ascending order.
- Start buying the cheapest ice cream bars first.
- Keep a running sum of costs.
- If the total cost does not exceed `coins`, increase the count.
- Return the total number of bars purchased.

---

## Code

```python
class Solution:
    def maxIceCream(self, costs: List[int], coins: int) -> int:
        costs.sort()

        sum = 0
        count = 0

        for i in range(len(costs)):
            sum = sum + costs[i]

            if sum <= coins:
                count += 1

        return count
```

---

## Complexity

- **Time Complexity:** O(n log n)
  - Due to sorting the array.
- **Space Complexity:** O(1)