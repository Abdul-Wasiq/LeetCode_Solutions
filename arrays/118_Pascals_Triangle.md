# 118. Pascal's Triangle
## 1. Problem Explain:
- Pascal’s Triangle is a triangle of numbers where:
- First row is [1].
- Each number is sum of the two numbers above it.
- First and last number of every row is always 1.

## 2. Code:
```
Python
class Solution(object):
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        def nCr(n, r):
            from math import factorial
            return factorial(n) // (factorial(r) * factorial(n - r))
        
        triangle = []
        for i in range(numRows):
            eachRow = []
            for j in range(i + 1):
                eachRow.append(nCr(i, j))
            triangle.append(eachRow)
        
        return triangle

```
## 3. Explanation:
```
Row 0:  0C0 = 1  

Row 1:  1C0 = 1, 1C1 = 1  

Row 2:  2C0 = 1, 2C1 = 2, 2C2 = 1  

Row 3:  3C0 = 1, 3C1 = 3, 3C2 = 3, 3C3 = 1  

Row 4:  4C0 = 1, 4C1 = 4, 4C2 = 6, 4C3 = 4, 4C4 = 1  

Row 5:  5C0 = 1, 5C1 = 5, 5C2 = 10, 5C3 = 10, 5C4 = 5, 5C5 = 1  

```
- n (the first number in nCr) increases row by row → 0, 1, 2, 3, 4 …
- r (the second number in nCr) starts at 0 and ends on i.

## 4. Pseudo Code with Example walkthrough:
Example: numRows = 5

#### 1. i = 0:
- j = 0 → C(0,0)=1 → row = [1]
- triangle = [[1]]

#### 2. i = 1:
- j = 0 → C(1,0)=1
- j = 1 → C(1,1)=1
- row = [1,1]
- triangle = [[1],[1,1]]

#### 3. i = 2:
- j = 0 → C(2,0)=1
- j = 1 → C(2,1)=2
- j = 2 → C(2,2)=1
- row = [1,2,1]
- triangle = [[1],[1,1],[1,2,1]]

#### 4. i = 3:
- j = 0 → C(3,0)=1
- j = 1 → C(3,1)=3
- j = 2 → C(3,2)=3
- j = 3 → C(3,3)=1
- row = [1,3,3,1]
- triangle = [[1],[1,1],[1,2,1],[1,3,3,1]]

#### 5. i = 4:
- j = 0 → C(4,0)=1
- j = 1 → C(4,1)=4
- j = 2 → C(4,2)=6
- j = 3 → C(4,3)=4
- j = 4 → C(4,4)=1
- row = [1,4,6,4,1]
- triangle = [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]

#### 6. Loop Overed, now return triangle outside the loop
- return triangle
