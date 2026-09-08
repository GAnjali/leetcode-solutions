# 1056. Capacity To Ship Packages Within D Days
  
<br>**Problem:** https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-08 09:00 local time

**Runtime:** 168 ms (beats 98.46209999999996%)
**Memory:** 23.9 MB (beats 67.04030000000002%)


<!-- leetgit:submissionId=2134563743 codeHash=d4a45ae206ff0e0278c527eb7725f118b6d3f42d8ed0b33e0c73f3128bb7b98b notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def canShipPackages(self, weights, capacity, days):
        sum, day = 0, 1
        for weight in weights:
            sum+=weight
            if sum <=capacity:
                continue
            else:
                sum = weight
                day += 1
        return day <= days

    def shipWithinDays(self, weights: List[int], days: int) -> int:
        left, right = max(weights), sum(weights)
        ans = left
        while left <= right:
            mid = (left+right) // 2
            if self.canShipPackages(weights, mid, days):
                ans = mid
                right = mid-1
            else:
                left = mid+1
        return ans
```
