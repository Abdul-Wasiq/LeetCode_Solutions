# 485. Max Consecutive Ones 
## 1. Problem Explain:
  We want the maximum number of 1s in a row inside the array.
  #### Example: nums = [1,1,0,1,1,1] return 3 because longest streak of 1 is 3

## 2. Code:
```
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        newArr = []
        num = 0

        for i in range(len(nums)):
            if (nums[i] == 1):
                num = num + 1
            else:
                newArr.append(num)
                num = 0

        newArr.append(num)
        newArr.sort()
        return newArr[len(newArr)-1] 
```

## 3. Idea:
- Loop through all elements in an array
- we will make variable(lets say 'num')
- if element detected is 1 then add 1
- if element detected is 0 then add num in new Array and make num = 0
- sort the new Array
- return the last element of new Array

## 4. Pseudo Code with Example walkthrough: 
  #### Example: [1,1,0,1,1,1]
-1 newArr = [], num = 0
- i=0, newArr= [], num = 0
  nums[0] = 1 -> num = 1
- i=1, newArr=[], num = 2
  num[1] = 1 -> num = 2
- i=2, newArr=[], num = 2
  num[2] = 0 -> newArr=[2], num = 0
- i=3, newArr=[2], num = 0
  num[3] = 1 -> num = 1
- i=4, newArr=[2], num = 1
  num[4] = 1 -> num = 2      
- i=5, newArr=[2], num = 2
  num[5] = 1 -> num = 3
- Loop Overed: newArr=[2,3]
- sort newArr
- return 3 (last Element in sorted newArr)     
  
