# 347. Top K Frequent Elements
  
<br>**Problem:** https://leetcode.com/problems/top-k-frequent-elements/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Hash Table, Divide and Conquer, Sorting, Heap (Priority Queue), Bucket Sort, Counting, Quickselect<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-21 09:25 local time

**Runtime:** 7 ms (beats 51.9095%)
**Memory:** 22.9 MB (beats 61.28569999999998%)


<!-- leetgit:submissionId=2040519776 codeHash=144b5993d5f20e363b19d2bc5b0d59695c0b7eb46465fa5a9e3e8f4db282f818 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
import heapq
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        for num in nums:
            count[num] = count.get(num, 0)+1
        heap = []
        for num, freq in count.items():
            heapq.heappush(heap, (freq,num))
            if len(heap) > k:
                heapq.heappop(heap)
        return [num for freq,num in heap]
        

        
```
