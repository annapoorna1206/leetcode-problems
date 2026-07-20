# How Many Numbers Are Smaller Than the Current Number (LeetCode 1365)

## Problem Statement

Given the array `nums`, for each element `nums[i]`, find out how many numbers in the array are smaller than it.

Return the answer as an array.

### Example

**Input:**
```text
nums = [8,1,2,2,3]
```

**Output:**
```text
[4,0,1,1,3]
```

**Explanation:**
```text
For 8, there are 4 numbers smaller than it.
For 1, there are 0 numbers smaller than it.
For 2, there is 1 number smaller than it.
For 2, there is 1 number smaller than it.
For 3, there are 3 numbers smaller than it.
```

---

## Approach

- For each element in the array:
  - Compare it with every other element.
  - Count how many numbers are smaller than the current element.
- Store the count in the result array.
- Return the result array.

---

## Code

```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]: 
        ans=[]
        for i in range(len(nums)):
            count=0
            for j in range(len(nums)):
                if nums[j]<nums[i]:
                    count+=1
            ans.append(count)
        return ans
```
---

## Complexity

- **Time Complexity:** O(n²)
- **Space Complexity:** O(n)