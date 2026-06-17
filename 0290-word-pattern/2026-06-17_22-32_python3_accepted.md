# 290. Word Pattern
  
<br>**Problem:** https://leetcode.com/problems/word-pattern/<br>

**Difficulty:** Easy<br>
**Topics:** Hash Table, String<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 22:32 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.2 MB (beats 68.38929999999999%)


<!-- leetgit:submissionId=2036646468 codeHash=1783f6f39989b0396d95ff101dbe1b588ae849f80ba0adf20ee0875af98c3125 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        def encode(string):
            mapping = {}
            encoded = []
            count = 0
            for ch in string:
                if ch not in mapping:
                    mapping[ch] = count
                encoded.append(mapping[ch])
                count+=1
            return encoded
        return encode(pattern) == encode(s.split(' '))
        
```
