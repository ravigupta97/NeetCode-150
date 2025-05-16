


## 🧠 Problem: Best Time to Buy and Sell Stock (LeetCode #121)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)


### ❓ Problem Statement:
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

 

Example 1:

- Input: prices = [7,1,5,3,6,4]
- Output: 5
- Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
- Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

Example 2:

- Input: prices = [7,6,4,3,1]
- Output: 0
- Explanation: In this case, no transactions are done and the max profit = 0.
 

Constraints:

- 1 <= prices.length <= 105
- 0 <= prices[i] <= 104
---

### ✅ Solution (Python):
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # update min_price and max_profit
        min_price = prices[0]
        max_profit = 0
        
        for price in prices:
            # Calculate profit on this day
            profit = price - min_price

            # Update max_profit if this profit is greater
            max_profit = max(max_profit, profit)

            # Update min_price seen so far
            min_price = min(min_price, price)
        
        return max_profit
       
```
### 🧠 Explanation:

- Update min_price with first element and max_profit as 0 
- Iterate through the prices list and calculate the profit on this day
- Update the max_profit if profit is greater
- Update the min_price seen so far

---

⏱️ Time Complexity:

- Time : O(n)
---

### ✅ Solution (Kadane's Algorithm) (Python):
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # Update buy_price and profit
        buy_price = prices[0]
        profit = 0

        for price in prices:
            # check if the current price is less than buy_price and update if true
            if price < buy_price:
                buy_price = price
            
            # Update the profit if the difference of current price and buy_price is positive
            elif price - buy_price > profit:
                profit = price - buy_price
        return profit
```
---

### 🧠 Explanation:

- Update buy_price with first element and profit as 0
- Iterate through the list and check if the current price is less than buy_price and update if true
- Update the profit if the difference of current price and buy_price is positive

---

⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
