# Maximum Number of Vowels in a Substring of Given Length (LeetCode 1456) https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/

## Problem Statement

Given a string `s` and an integer `k`, return the maximum number of vowel letters present in any substring of length `k`.

Vowels are: `a`, `e`, `i`, `o`, and `u`.

### Example

**Input:**
```text
s = "abciiidef"
k = 3
```

**Output:**
```text
3
```

**Explanation:**
```text
The substring "iii" contains 3 vowels.
```

---

## Approach

- Use the **Sliding Window** technique.
- Count the vowels in the first window of size `k`.
- Slide the window one character at a time:
  - Remove the contribution of the outgoing character.
  - Add the contribution of the incoming character.
- Keep track of the maximum vowel count seen.

---

## Code

```python
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        vowels='aeiou'
        count=0

        for i in range(k):
            if s[i] in vowels:
                count+=1

        ans=count

        for i in range(k,len(s)):
            if s[i-k] in vowels:
                count-=1
            if s[i] in vowels:
                count+=1
            ans=max(ans,count)
        return ans
            
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)