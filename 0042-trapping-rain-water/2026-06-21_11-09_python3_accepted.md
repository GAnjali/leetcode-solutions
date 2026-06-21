# 42. Trapping Rain Water
  
<br>**Problem:** https://leetcode.com/problems/trapping-rain-water/<br>

**Difficulty:** Hard<br>
**Topics:** Array, Two Pointers, Dynamic Programming, Stack, Monotonic Stack<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-21 11:09 local time

**Runtime:** 27 ms (beats 5.019800000000007%)
**Memory:** 22.8 MB (beats 7.364499999999999%)


<!-- leetgit:submissionId=2040606394 codeHash=3502063a4b23e1d0486ee29637118ebfa84eb98d772ca0959dc1b3d86440c7ed notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)
        prefixMax, suffixMax = {0: height[0]}, {n-1:height[n-1]}
        for i in range(1, n):
            prefixMax[i] = max(prefixMax[i-1], height[i])
        for i in range(n-2, -1, -1):
            suffixMax[i] = max(suffixMax[i+1], height[i])
        total=0
        for i, n in enumerate(height):
            total += min(prefixMax[i], suffixMax[i]) - n
        return total
```
