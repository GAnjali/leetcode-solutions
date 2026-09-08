# 907. Koko Eating Bananas
  
<br>**Problem:** https://leetcode.com/problems/koko-eating-bananas/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-08 10:18 local time

**Runtime:** 157 ms (beats 88.11309999999982%)
**Memory:** 20.5 MB (beats 81.9253%)


<!-- leetgit:submissionId=2134632507 codeHash=26d3617f59e0a1e0b2f1e4e0fd3c9008e24c115ddd1733be2c9c72294e0100d5 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
import math
class Solution:
    def canEatAll(self, piles, capacity, hours):
        totalHours = 0
        for pile in piles:
            totalHours += math.ceil(pile/capacity)
        return totalHours<=hours
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        left, right = 1, max(piles)
        ans = left
        while left<=right:
            mid = (right+left)//2
            if self.canEatAll(piles, mid, h):
                right = mid-1
                ans = mid
            else:
                left = mid+1
        return ans

```
