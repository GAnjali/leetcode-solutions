# 121. Best Time to Buy and Sell Stock
  
<br>**Problem:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Dynamic Programming<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-02 20:57 local time

**Runtime:** 45 ms (beats 62.90820000000002%)
**Memory:** 28.5 MB (beats 75.686%)


<!-- leetgit:submissionId=2020324584 codeHash=9c0202a532798f64a96c91852b85ed459f10db2ff4ced69da12b193537af4de9 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        minPrice = prices[0]
        maxProfit = 0
        for price in prices:
            minPrice = min(minPrice, price)
            profit = price - minPrice
            maxProfit = max(maxProfit, profit)
        return maxProfit
        
```
