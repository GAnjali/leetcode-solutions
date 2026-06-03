# 167. Two Sum II - Input Array Is Sorted
  
<br>**Problem:** https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Two Pointers, Binary Search<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-03 07:40 local time

**Runtime:** 7 ms (beats 28.958499999999994%)
**Memory:** 20.6 MB (beats 7.677799999999991%)


<!-- leetgit:submissionId=2020713000 codeHash=add521235d94291f4b4fbe66c520fe3221a5c0419a13965a3990356b59ff934c notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        length = len(numbers)
        left, right = 0, length-1
        while left<=right:
            sum = numbers[right]+numbers[left]
            if sum < target:
                left += 1
            elif sum > target:
                right-=1
            else:
                return [left+1, right+1]
```
