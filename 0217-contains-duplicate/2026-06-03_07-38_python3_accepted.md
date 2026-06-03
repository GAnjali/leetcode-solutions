# 217. Contains Duplicate
  
<br>**Problem:** https://leetcode.com/problems/contains-duplicate/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Hash Table, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-03 07:38 local time

**Runtime:** 11 ms (beats 65.9178%)
**Memory:** 32.1 MB (beats 48.29629999999997%)


<!-- leetgit:submissionId=2020711991 codeHash=6ea06468faf2ed792e893178ae4e58c57184fbff1f27f7f1f8d35891d8423792 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False
        
```
