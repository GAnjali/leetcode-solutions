# 215. Kth Largest Element in an Array
  
<br>**Problem:** https://leetcode.com/problems/kth-largest-element-in-an-array/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Divide and Conquer, Sorting, Heap (Priority Queue), Quickselect<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-18 08:00 local time

**Runtime:** 127 ms (beats 10.198799999999999%)
**Memory:** 31.4 MB (beats 12.525700000000008%)


<!-- leetgit:submissionId=2036951896 codeHash=ba2deed87b3705ad43dbe18fdf26a3d06156acb865ba50db413a3f78de691ad3 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
import heapq
class Solution:
    def findKthLargest(self, nums: List[int], k: int) -> int:
        heap = []
        for num in nums:
            heapq.heappush(heap, -num)
        for i in range(k-1):
            heapq.heappop(heap)
        return -heapq.heappop(heap)
        
```
