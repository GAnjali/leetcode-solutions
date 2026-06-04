# 49. Group Anagrams
  
<br>**Problem:** https://leetcode.com/problems/group-anagrams/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Hash Table, String, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-04 06:58 local time

**Runtime:** 11 ms (beats 84.12180000000001%)
**Memory:** 22 MB (beats 66.98619999999998%)


<!-- leetgit:submissionId=2021746016 codeHash=2f7b0048804532ce7247b65b9c634293f7ad8d4c8d4403b601082abcfb476350 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import defaultdict
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        anagrams = defaultdict(list)
        for st in strs:
            group = ''.join(sorted(st))
            anagrams[group].append(st)
        return list(anagrams.values())
```
