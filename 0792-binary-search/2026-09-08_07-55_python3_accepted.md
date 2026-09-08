# 792. Binary Search
  
<br>**Problem:** https://leetcode.com/problems/binary-search/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-08 07:55 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 20.6 MB (beats 37.218500000000006%)


<!-- leetgit:submissionId=2134527141 codeHash=904c5f439476b75e071b8b894e32fc75f712f28e7ad581e4b4d54ea7d002e4ec notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left,right = 0, len(nums)-1
        while left<=right:
            mid = (left+right)//2
            if nums[mid] < target:
                left = mid+1
            elif nums[mid] > target:
                right = mid-1
            else:
                return mid
        return -1
```
