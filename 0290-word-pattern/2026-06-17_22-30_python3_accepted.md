# 290. Word Pattern
  
<br>**Problem:** https://leetcode.com/problems/word-pattern/<br>

**Difficulty:** Easy<br>
**Topics:** Hash Table, String<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 22:30 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.3 MB (beats 68.38929999999999%)


<!-- leetgit:submissionId=2036644232 codeHash=dba3a1090fa89ba4073411d4ac5fd2b199b160b4806f7dccb2205462af0de81d notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        def encode(string, type):
            mapping = {}
            encoded = []
            count = 0
            if type=='string':
                for ch in string:
                    if ch not in mapping:
                        mapping[ch] = count
                    encoded.append(mapping[ch])
                    count+=1
            else:
                for word in string.split(' '):
                    if word not in mapping:
                        mapping[word] = count
                    encoded.append(mapping[word])
                    count+=1
            return encoded
        return encode(pattern, 'string') == encode(s, 'sentence')
        
```
