# 34. Find First and Last Position of Element in Sorted Array
  
<br>**Problem:** https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-08 08:09 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 20.5 MB (beats 61.252400000000016%)


<!-- leetgit:submissionId=2134534128 codeHash=9fe54343329f029c0d09a8773130c45cf28e02128885861c19500e9a3c6d4259 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        ans = [-1, -1]
        left,right = 0, len(nums)-1
        while left<=right:
            mid = (left+right)//2
            if nums[mid] < target:
                left = mid+1
            elif nums[mid] > target:
                right = mid-1
            else:
                ans[0] = mid
                right = mid-1
        left,right = 0, len(nums)-1
        while left<=right:
            mid = (left+right)//2
            if nums[mid] < target:
                left = mid+1
            elif nums[mid] > target:
                right = mid-1
            else:
                ans[1] = mid
                left = mid+1
        return ans
```
