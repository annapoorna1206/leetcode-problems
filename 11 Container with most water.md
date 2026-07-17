# Container With Most Water (LeetCode 11) https://leetcode.com/problems/container-with-most-water/

## Problem Statement

Given an integer array `height` where each element represents the height of a vertical line, find two lines that together with the x-axis form a container that can hold the maximum amount of water.

Return the maximum amount of water the container can store.

### Example

**Input:**
```text
height = [1,8,6,2,5,4,8,3,7]
```

**Output:**
```text
49
```

**Explanation:**
```text
The lines at indices 1 and 8 form a container.
Width = 8 - 1 = 7
Height = min(8, 7) = 7

Area = 7 × 7 = 49
```
## Code

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        left=0
        right=len(height)-1
        ans=0
        
        while left<right:
            area=(right-left)*min(height[left],height[right])
            ans=max(ans,area)

            if height[left]<height[right]:
                left+=1
            else:
                right-=1
        return ans
```

---

## Complexity

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)