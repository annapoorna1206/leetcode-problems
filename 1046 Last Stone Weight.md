# Last Stone Weight (LeetCode 1046) https://leetcode.com/problems/last-stone-weight/

## Problem Statement

You are given an array `stones` where `stones[i]` is the weight of the `iᵗʰ` stone.

Each turn:

- Choose the two heaviest stones `x` and `y` (`x ≤ y`).
- If `x == y`, both stones are destroyed.
- If `x != y`, the stone with weight `x` is destroyed, and the stone with weight `y - x` remains.

Return the weight of the last remaining stone. If no stones remain, return `0`.

### Example

**Input:**
```text
stones = [2,7,4,1,8,1]
```

**Output:**
```text
1
```

**Explanation:**
```text
8 and 7 -> 1      => [2,4,1,1,1]
4 and 2 -> 2      => [2,1,1,1]
2 and 1 -> 1      => [1,1,1]
1 and 1 -> 0      => [1]

Last remaining stone = 1
```

---

## Approach

- While more than one stone remains:
  - Sort the array.
  - Remove the two heaviest stones.
  - If their weights are different, insert the difference back into the array.
- When only one stone (or none) remains, return its weight.

---

## Code

```python
class Solution:
    def lastStoneWeight(self, stones: List[int]) -> int:
        while len(stones) > 1:
            stones.sort()
            x = stones.pop()
            y = stones.pop()
            if x != y:
                stones.append(x - y)
        if stones:
            return stones[0]
        return 0
```

---

## Complexity

- **Time Complexity:** O(n² log n)
  - The list is sorted repeatedly after each smash operation.
- **Space Complexity:** O(1)