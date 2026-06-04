# 347. Top K Frequent Elements
  
<br>**Problem:** https://leetcode.com/problems/top-k-frequent-elements/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Hash Table, Divide and Conquer, Sorting, Heap (Priority Queue), Bucket Sort, Counting, Quickselect<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-04 07:26 local time

**Runtime:** 8 ms (beats 32.676300000000005%)
**Memory:** 22.7 MB (beats 81.94169999999998%)


<!-- leetgit:submissionId=2021755849 codeHash=45eb7b2db5f58c0333fab0a4162729f5d55d58197d3b6ae927f638f0eabe9a37 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import defaultdict
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        frequency = defaultdict(int)
        for num in nums:
            frequency[num] += 1
        arr = sorted(frequency.items(), key=lambda x:x[1], reverse=True)
        return [num for num, count in arr[:k]]
```
