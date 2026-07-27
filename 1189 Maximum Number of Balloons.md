# Maximum Number of Balloons (LeetCode 1189) https://leetcode.com/problems/maximum-number-of-balloons/

## Problem Statement

Given a string `text`, return the maximum number of instances of the word:

```text
"balloon"
```

that can be formed using the characters in `text`.

Each character in `text` can be used at most once.

### Example

**Input:**
```text
text = "nlaebolko"
```

**Output:**
```text
1
```

**Explanation:**
```text
The letters can form the word "balloon" exactly once.
```

### Example 2

**Input:**
```text
text = "loonbalxballpoon"
```

**Output:**
```text
2
```

---

## Approach

- Count the occurrences of the required characters:
  - `b`, `a`, `l`, `o`, and `n`.
- Since `"balloon"` contains:
  - 1 `b`
  - 1 `a`
  - 2 `l`
  - 2 `o`
  - 1 `n`
- Divide the counts of `l` and `o` by 2.
- The minimum count among these characters determines how many times `"balloon"` can be formed.

---

## Code

```python
class Solution:
    def maxNumberOfBalloons(self, text: str) -> int:
        b = text.count('b')
        a = text.count('a')
        l = text.count('l') // 2
        o = text.count('o') // 2
        n = text.count('n')

        return min(b, a, l, o, n)
```

---

## Complexity

- **Time Complexity:** O(n)
  - Each `count()` scans the string.
- **Space Complexity:** O(1)
  - Only a few variables are used.