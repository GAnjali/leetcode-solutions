# 1. Two Sum
  
<br>**Problem:** https://leetcode.com/problems/two-sum/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Hash Table<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-02 20:50 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 20.4 MB (beats 60.74249999999999%)


<!-- leetgit:submissionId=2020318024 codeHash=e8b3851ede300b6025d4d2d00d99bdb8fd9e530df6f9019628668db02588fbfa notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        seen = {}
        for i, num in enumerate(nums):
            complement = target-num
            if complement in seen:
                return [seen[complement], i]
            seen[num] = i
        return []

        
```
