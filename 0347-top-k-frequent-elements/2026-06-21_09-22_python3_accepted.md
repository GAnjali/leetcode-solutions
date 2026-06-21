# 347. Top K Frequent Elements
  
<br>**Problem:** https://leetcode.com/problems/top-k-frequent-elements/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Hash Table, Divide and Conquer, Sorting, Heap (Priority Queue), Bucket Sort, Counting, Quickselect<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-21 09:22 local time

**Runtime:** 3 ms (beats 89.3208%)
**Memory:** 22.7 MB (beats 81.28659999999998%)


<!-- leetgit:submissionId=2040515647 codeHash=9eb34db413b662ea11ee5db61f2acc0d2c47115463399a73ecc4bb8c1e83d7a6 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        for num in nums:
            count[num] = count.get(num, 0)+1
        return sorted(count, key = lambda x:-count[x])[:k]
        

        
```
