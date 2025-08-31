# 121. Best Time to Buy and Sell Stock 
## 1. Problem Explain:
We just have to return when to sell stock(trying to get maximum profit), We can't sell stock before buying it.

Example: prices = [7,1,5,3,6,4], output = 5 \
Remember: cant buy on day 2(1) and sell it on day 1(7)

## 2. Code:
```
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        profit = 0
        max_profit = 0
        mini = prices[0]
        for i in range(1,len(prices)):
            if (mini > prices[i]):
                mini = prices[i]
            else:
                profit = prices[i] - mini # profit 
                max_profit = max(profit, max_profit) # comparing previous profit with current Profit to get maximum profit
        
        return max_profit
```
## 3. Explanation:
1. Check that stock is miminm than current stock? 
2. if yes then save it in variable'mini'
3. if not then subtract the current maximum stock with current minimum stock
4. then compare this answer with previous maximum profit
5. when loop will be overed then return maximum profit

## 4. Pseudo Code with Example walkthrough:
   Example: [7,1,5,3,6,4]
#### 1. i = 0:
- if(7>1) => min=1
#### 2. i = 1:
- if(1>5): False
- else: profit=5-1 => 4
        max_profit = (4,0)=>4
#### 3. i = 2:  
- if(1>3): False
- else: profit=3-1 => 2
        max_profit = (2,4)=>4
#### 4. i = 3:  
- if(1>6): False
- else: profit=6-1 => 5
        max_profit = (5,4)=>5
#### 3. i = 4:  
- if(1>4): False
- else: profit=4-1 => 3
        max_profit = (3,5)=>5
#### 4. Loop Overed
- return max_profit which is 5
