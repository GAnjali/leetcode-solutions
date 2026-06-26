# 152. Maximum Product Subarray
  
<br>**Problem:** https://leetcode.com/problems/maximum-product-subarray/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Dynamic Programming<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-26 08:08 local time

**Runtime:** 6 ms (beats 45.6023%)
**Memory:** 19.7 MB (beats 97.10900000000002%)


<!-- leetgit:submissionId=2046319132 codeHash=93e48317670524f13c9761c768320a3a07ea528de722ca6f939bd4a7f86a24c3 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        if len(nums) == 0: return 1
        if len(nums) == 1: return nums[0]
        maxP = 1
        result = 0
        minP = 1
        for num in nums:
            candidates = (num, maxP*num, minP*num)
            maxP = max(candidates)
            minP = min(candidates)
            result = max(result, maxP)
        return result

        
```
