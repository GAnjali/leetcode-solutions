# 81. Search in Rotated Sorted Array II
  
<br>**Problem:** https://leetcode.com/problems/search-in-rotated-sorted-array-ii/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-09-09 07:15 local time

**Runtime:** 3 ms (beats 7.579599999999994%)
**Memory:** 19.7 MB (beats 32.34660000000002%)


<!-- leetgit:submissionId=2135731257 codeHash=ec65600cec738db4136d5463d98bab96c46c8e6ea8809a07f1441df9f5253dcc notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums)-1
        while left<=right:
            mid = (left+right)//2
            print("mid:", mid)
            print("nums[left], nums[mid]:",nums[left], nums[mid])
            if nums[mid] ==target:
                return True
            elif nums[left]==nums[mid]==nums[right]:
                left+=1
                right-=1
                continue
            elif nums[left]<=nums[mid]:
                if  nums[left] <=target<=nums[mid]:
                    right = mid-1
                else:
                    left=mid+1
            else:
                if  nums[mid] <=target<=nums[right]:
                    left = mid+1
                else:
                    right=mid-1
            print("left, right:", left, right)
        return False
        
```
