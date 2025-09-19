# 566. Reshape the Matrix
## 1. Problem Explain:
   We have to convert the matrix array in the required rows and cols.
   For Example: [[1,2],[3,4]], r = 1, c = 4, output = [1,2,3,4]

## 2. Idea:
- We will make new empty 2D Array,
- we will put element one by one using nested loops
- nested loop depends on 'r' and 's'(required matrix)
- and make row = 0, and col = 0
- it looks like this: newArr[i][j] = mat[row][col]
- in this loop body, we have to detect that col doesnt go out of index
- so we will put condition which says that if col == length of array 'mat' then incremenet 1 in row and start col from 0.
We learn in maths that we cant reshape of the matrix if required matrix doesnt have same rows and cols as matrix which we will change.

## 3. Code:
```
class Solution(object):
    def matrixReshape(self, mat, r, c):
        newArr = [[0]*c for _ in range(r)]  
        rowOfMat = len(mat)
        colOfMat = len(mat[0])

        if (r*c != rowOfMat * colOfMat):
            return mat
        row = 0
        col = 0

        for i in range(r):
            for j in range(c):
                newArr[i][j] = mat[row][col] 
                col = col + 1

                if (col == colOfMat):
                    col = 0
                    row = row + 1

        return newArr             
```

# 4. Pseudo Code with Example walkthrough: 
   Example: mat = [[1,2],[3,4]], r = 1, c = 4 
#### 1. i=0, j=0, row=0, col=0:
- newArr[0][0] = mat[0][0] -> newArr = [[1]], if(col==2){False(col=1)} 
#### 2. i=0, j=1, row=0, col=1:
- newArr[0][1] = mat[0][1] -> newArr = [[1,2]], if(col==2){row=1,col=0} 
#### 3. i=0, j=2, row=1, col=0:
- newArr[0][2] = mat[1][0] -> newArr = [[1,2,3]], if(col==2){False(col=1)} 
#### 4. i=0,j=3, row=1, col=1:
- newArr[0][3] = mat[1][1] -> newArr = [[1,2,3,4]], 
#### 5. Loop Overed:
- return newArr(1,2,3,4)      
