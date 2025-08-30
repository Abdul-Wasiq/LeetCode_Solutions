# 26. Pascal's Triangle II:
## 1. Problem Explain:
We have to return the row on the given integer.
Example: n=5, output= [1 4 6 4 1]

## 2. Code:
```
Python
import math
class Solution(object):
    def getRow(self, rowIndex):
        """
        :type rowIndex: int
        :rtype: List[int]
        """
        def nCr(n,r):
            from math import factorial
            # nCr = n! / r!(n-r)!
            return factorial(n) / (factorial(r) * factorial(n-r))

        triangle = []
        for n in range(rowIndex+1):
            currRow = []
            for r in range(n+1):
                val = nCr(n,r)
                currRow.append(val)

            if (n == rowIndex):
                return currRow
                exit()
```
## 3. Explanation:
Our main goal is that when n in loop equals to rowIndex then return the current Row,
```
Row 0:  0C0 = 1  

Row 1:  1C0 = 1, 1C1 = 1  

Row 2:  2C0 = 1, 2C1 = 2, 2C2 = 1  

Row 3:  3C0 = 1, 3C1 = 3, 3C2 = 3, 3C3 = 1  

Row 4:  4C0 = 1, 4C1 = 4, 4C2 = 6, 4C3 = 4, 4C4 = 1  

Row 5:  5C0 = 1, 5C1 = 5, 5C2 = 10, 5C3 = 10, 5C4 = 5, 5C5 = 1  
```
we will run loop needed Row + 1 then use condition that n = needed Row then return the current Row
# 4. Pseudo Code with Example walkthrough:
Example rowIndex = 3
#### 1. n=0,r=0 -> currRow = [1]
#### 2. n=1,r=0 -> currRow = [1]
- n=1,r=1 -> currRow = [1,1]
#### 3. n=2,r=0 -> currRow = [1]
  - n=2,r=1 -> currRow = [1,2]
  - n=2,r=2 -> currRow = [1,2,1]
#### 4. n=3,r=0 -> currRow = [1]
  - n=3,r=1 -> currRow = [1,3]
  - n=3,r=2 -> currRow = [1,3,3]
  - n=3,r=3 -> currRow = [1,3,3,1]
#### 5. if(n(3) == RowIndex(3)) => return [1,3,3,1]
