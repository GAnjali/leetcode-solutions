# 451. Sort Characters By Frequency
  
<br>**Problem:** https://leetcode.com/problems/sort-characters-by-frequency/<br>

**Difficulty:** Medium<br>
**Topics:** Hash Table, String, Sorting, Heap (Priority Queue), Bucket Sort, Counting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-18 07:54 local time

**Runtime:** 33 ms (beats 9.671000000000017%)
**Memory:** 28.4 MB (beats 9.202799999999977%)


<!-- leetgit:submissionId=2036949026 codeHash=05503a70fefbc2e6e2f741514173f46d38547d66e0b4ec85113a4ba6488e8bdf notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
import heapq
class Solution:
    def frequencySort(self, s: str) -> str:
        freq = {}
        for ch in s:
            freq[ch]=freq.get(ch, 0)+1
        buckets = [[] for _ in range((len(s)+1))]
        for ch,count in freq.items():
            buckets[count].append(ch)
        res = ''
        for i in range(len(buckets)-1, 0, -1):
            for ch in buckets[i]:
                res+=(ch*i)
        return res

        
```
