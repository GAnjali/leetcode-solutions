# 3. Longest Substring Without Repeating Characters
  
<br>**Problem:** https://leetcode.com/problems/longest-substring-without-repeating-characters/<br>

**Difficulty:** Medium<br>
**Topics:** Hash Table, String, Sliding Window<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-22 23:57 local time

**Runtime:** 11 ms (beats 77.10099999999998%)
**Memory:** 19.4 MB (beats 30.107200000000027%)


<!-- leetgit:submissionId=2042558488 codeHash=e18e1a98395d138a56dcc5a47a9706a02a00262f631dbfe4583f19461f8c0cef notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        left = 0
        seen = set()
        maxLen = 0
        for right in range(len(s)):
            while s[right] in seen:
                seen.remove(s[left])
                left+=1
            seen.add(s[right])
            maxLen = max(maxLen, right-left+1)
        return maxLen
        
```
