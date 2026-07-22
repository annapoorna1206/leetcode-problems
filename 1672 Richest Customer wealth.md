# Richest Customer Wealth (LeetCode 1672) https://leetcode.com/problems/richest-customer-wealth/description/

## Problem Statement

You are given an `m x n` integer matrix `accounts` where:

- `accounts[i][j]` represents the amount of money the `iᵗʰ` customer has in the `jᵗʰ` bank.

Return the wealth of the richest customer.

A customer's wealth is the sum of money they have in all their bank accounts.

### Example

**Input:**
```text
accounts = [[1,2,3],[3,2,1]]
```

**Output:**
```text
6
```

**Explanation:**
```text
Customer 1 wealth = 1 + 2 + 3 = 6
Customer 2 wealth = 3 + 2 + 1 = 6

Maximum wealth = 6
```

---

## Approach

- Traverse each customer's accounts.
- Calculate the total wealth by summing all bank balances.
- Keep track of the maximum wealth encountered.
- Return the maximum wealth.

---

## Code

```python
class Solution:
    def maximumWealth(self, accounts: List[List[int]]) -> int:
        maxwealth = 0
        for i in range(len(accounts)):
            sum1 = 0
            for j in range(len(accounts[i])):
                sum1 += accounts[i][j]
            if sum1 > maxwealth:
                maxwealth = sum1
        return maxwealth
```

---

## Complexity

- **Time Complexity:** O(m × n)
  - `m` = number of customers
  - `n` = number of bank accounts per customer
- **Space Complexity:** O(1)