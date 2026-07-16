# Maximum Number of Words Found in Sentences (LeetCode 2114)

## Problem Statement

A sentence is a list of words separated by a single space.

Given an array of strings `sentences`, where each element represents a sentence, return the **maximum number of words** that appear in a single sentence.

### Example

**Input:**
```text
sentences = ["alice and bob love leetcode",
             "i think so too",
             "this is great thanks very much"]
```

**Output:**
```text
6
```

---

## Approach

- Traverse each sentence in the array.
- Split the sentence using spaces (`split()`).
- Count the number of words in the sentence.
- Keep track of the maximum count found.

---

## Code

```python
class Solution:
    def mostWordsFound(self, sentences: List[str]) -> int:
        maxvalue=0
        for sentence in sentences:
            maxvalue=max(maxvalue,len(sentence.split()))
        return maxvalue
```

---

## Complexity

- **Time Complexity:** O(n × m)
  - `n` = number of sentences
  - `m` = average length of a sentence
- **Space Complexity:** O(m)