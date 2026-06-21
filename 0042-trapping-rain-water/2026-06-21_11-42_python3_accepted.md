# 42. Trapping Rain Water
  
<br>**Problem:** https://leetcode.com/problems/trapping-rain-water/<br>

**Difficulty:** Hard<br>
**Topics:** Array, Two Pointers, Dynamic Programming, Stack, Monotonic Stack<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-21 11:42 local time

**Runtime:** 3 ms (beats 95.1075%)
**Memory:** 21 MB (beats 48.6969%)


<!-- leetgit:submissionId=2040639780 codeHash=b2b3086c6882ae6a725a7f2c859bcb3c78cc75c54a00ce97603b1ce2ac152ff2 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)
        l,r= 0, n-1
        leftMax, rightMax = 0,0
        total = 0
        while l<r:
            if height[l] <= height[r]:
                leftMax = max(leftMax, height[l])
                total+=leftMax-height[l]
                l+=1
            else:
                rightMax = max(rightMax, height[r])
                total+=rightMax-height[r]
                r-=1
        return total
```
