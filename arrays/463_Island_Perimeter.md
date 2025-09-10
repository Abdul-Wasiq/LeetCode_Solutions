# 463. Island Perimeter  
## 1. Problem Explain:
   We have a grid: 1 = land, 0 = water.
   Find the border of land (total outer sides touching water or grid edg

## 2. Code:
```
class Solution(object):
    def islandPerimeter(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        rows = len(grid)
        cols = len(grid[0])
        per = 0
        for i in range(rows):
          for j in range(cols):
             if grid[i][j] == 1:
               if i == 0 or grid[i-1][j] == 0:
                 per = per + 1
               if j == 0 or grid[i][j-1] == 0:        
                 per = per + 1
               if j == cols-1 or grid[i][j+1] == 0:    
                 per = per + 1
               if i == rows - 1 or grid[i+1][j] == 0:    
                 per = per + 1

        return per         
```

## 3. Idea:
- First we have to check that detected 1 is on first or last row, or first or last column if yes then add 1
- then we will check that left ,right, upper and lower side of detected 1 has 0 then add 1 in permeter variable

## 4. Pseudo Code with Example walkthrough:
   #### grid = [[0,1,0,0],[1,1,1,0],[0,1,0,0],[1,1,0,0]] 
1- Row1,Col1(0,1,0,0):
   Row1 is first then add 1
   
   
