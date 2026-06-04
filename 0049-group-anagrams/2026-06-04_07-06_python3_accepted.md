# 49. Group Anagrams
  
<br>**Problem:** https://leetcode.com/problems/group-anagrams/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Hash Table, String, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-04 07:06 local time

**Runtime:** 11 ms (beats 84.12180000000001%)
**Memory:** 24 MB (beats 18.070699999999988%)


<!-- leetgit:submissionId=2021748807 codeHash=04a346e246329d1d5d3b74d5285aa2a75d140fe00d99e47cde973d95a11c01ce notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import defaultdict
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        anagrams = defaultdict(list)
        base = ord('a')
        for word in strs:
            count = [0]*26
            for ch in word:
                count[ord(ch)-base] += 1
            anagrams[tuple(count)].append(word)
        return list(anagrams.values())
```
