# Coin Change (LeetCode 322) https://leetcode.com/problems/coin-change/

## Problem Statement

You are given an integer array `coins` representing different coin denominations and an integer `amount` representing a total amount of money.

Return the **fewest number of coins** needed to make up that amount.

If it is not possible to make up the amount using the given coins, return `-1`.

### Example 1

**Input:**
```text
coins = [1,2,5]
amount = 11
```

**Output:**
```text
3
```

**Explanation:**
```text
11 = 5 + 5 + 1

Number of coins = 3
```

### Example 2

**Input:**
```text
coins = [2]
amount = 3
```

**Output:**
```text
-1
```

**Explanation:**
```text
It is impossible to form amount 3 using coin 2.
```

---

## Approach (Dynamic Programming)

- Create a DP array where:
  - `dp[i]` = minimum coins needed to make amount `i`.
- Initialize all values as infinity (`inf`).
- Set:

```text
dp[0] = 0
```

because zero coins are needed to make amount `0`.

- For each amount from `1` to `amount`:
  - Try every coin.
  - If the coin can contribute to the current amount:
  
```text
dp[i] = min(dp[i], dp[i - coin] + 1)
```

- If `dp[amount]` remains infinity, return `-1`.
- Otherwise return `dp[amount]`.

---

## Code

```python
class Solution:
    def coinChange(self, coins: List[int], amount: int) -> int:
        dp = [float('inf')] * (amount + 1)
        dp[0] = 0

        for i in range(1, amount + 1):
            for coin in coins:
                if i - coin >= 0:
                    dp[i] = min(dp[i], dp[i - coin] + 1)

        if dp[amount] != float('inf'):
            return dp[amount]
        else:
            return -1
```

---

## Example Walkthrough

**Input:**

```text
coins = [1,2,5]
amount = 11
```

DP array updates:

```text
dp[0] = 0
dp[1] = 1
dp[2] = 1
dp[3] = 2
...
dp[11] = 3
```

Result:

```text
11 = 5 + 5 + 1
Answer = 3
```

---

## Complexity

- **Time Complexity:** O(amount × number_of_coins)
- **Space Complexity:** O(amount)