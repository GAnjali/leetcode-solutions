# 33. Search in Rotated Sorted Array
  
<br>**Problem:** https://leetcode.com/problems/search-in-rotated-sorted-array/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-09 07:06 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.5 MB (beats 10.440299999999993%)


<!-- leetgit:submissionId=2135727284 codeHash=b4f196c79e2b7f335c3e5a793fe990767626d30d87141510fadb47ede5d8ef64 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums)-1
        while left<=right:
            mid = (left+right)//2

            if nums[mid] ==target:
                return mid
            elif nums[left]<=nums[mid]:
                if  nums[left] <=target<=nums[mid]:
                    right = mid-1
                else:
                    left=mid+1
            elif nums[mid]<=nums[right]:
                if  nums[mid] <=target<=nums[right]:
                    left = mid+1
                else:
                    right=mid-1
        return -1
        
```
