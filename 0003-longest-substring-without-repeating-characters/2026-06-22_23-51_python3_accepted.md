# 3. Longest Substring Without Repeating Characters
  
<br>**Problem:** https://leetcode.com/problems/longest-substring-without-repeating-characters/<br>

**Difficulty:** Medium<br>
**Topics:** Hash Table, String, Sliding Window<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-22 23:51 local time

**Runtime:** 327 ms (beats 5.008200000000019%)
**Memory:** 19.1 MB (beats 92.57300000000002%)


<!-- leetgit:submissionId=2042551127 codeHash=911ba2b0667394539bea439d25cfa89273d9b95bfbfbf294f10397af518d5713 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        maxLen = 0
        for i in range(len(s)):
            seen = set()
            for j in range(i, len(s)):
                if s[j] in seen:
                    break
                seen.add(s[j])
                maxLen = max(maxLen, j-i+1)
        return maxLen
        
```
