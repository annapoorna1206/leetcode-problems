# Excel Sheet Column Number (LeetCode 171) https://leetcode.com/problems/excel-sheet-column-number/

## Problem Statement

Given a string `columnTitle` representing the column title as it appears in an Excel sheet, return its corresponding column number.

### Examples

**Input:**
```text
columnTitle = "A"
```

**Output:**
```text
1
```

**Input:**
```text
columnTitle = "AB"
```

**Output:**
```text
28
```
## Code

```python
class Solution:
    def titleToNumber(self, columnTitle: str) -> int:
        ans=0
        for ch in columnTitle:
            v=ord(ch)-ord('A')+1
            ans=ans*26+v
        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)