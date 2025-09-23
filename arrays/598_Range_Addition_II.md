# 598: Range Addition II 
## 1. Problem Explain:
- Start with m x n matrix of 0s.
- Each operation [a, b] → add 1 to every cell in rectangle from top-left (0,0) to (a-1, b-1).
- After all operations, find how many cells have the biggest number.

## 2. Idea:
- Every operation [a, b] updates a rectangle from (0,0) to (a-1, b-1).
- The cells that get updated by all operations are exactly inside the overlap of all rectangles.
- That overlap has:
- height = the smallest a among all ops
- width = the smallest b among all ops
- So the number of cells with the maximum value = min_row * min_col.

## 3. Code:
```
class Solution(object):
    def maxCount(self, m, n, ops):
        """
        :type m: int
        :type n: int
        :type ops: List[List[int]]
        :rtype: int
        """
        if (len(ops) == 0):
            return m * n
        
        min_row = m
        min_col = n

        for a,b in ops:
            min_row = min(min_row,a)
            min_col = min(min_col,b)

        return min_row * min_col    
```
## 4. Pseudo Code with Example walkthrough:
Input: m = 3, n = 3, ops = [[2,2],[3,3]]

- if ops is empty:
    return m * n

- min_row = m = 3
- min_col = n = 3

- for each (a, b) in ops:
    min_row = min(min_row, a)
    min_col = min(min_col, b)

# Walkthrough:
- First op (2,2): min_row = min(3,2)=2, min_col = min(3,2)=2
- Second op (3,3): min_row = min(2,3)=2, min_col = min(2,3)=2

return min_row * min_col = 2 * 2 = 4

