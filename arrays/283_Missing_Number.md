# 283. Missing Number
## 1. Problem Explain:
  We just have to return value which is missing in the sequence.
  For Example: nums = [3,0,1]
               Output: 2

## 2. Code:
```
class Solution(object):
    def missingNumber(self, nums):
        nums = sorted(nums)
        for i in range(len(nums)):
            if(i != nums[i]):
                return i
        return len(nums)
```

## 3. Explanation:
- We have to run the loop(from 0 to n)
- if one by one loop value is not equal to sorted array
- then return i of loop
- if all elements are available sequentially then return last element which is length of an array.

## 4. Pseudo Code with Example walkthrough:
- sorted(nums) => [0,1,3]
.1 i=0
-  if(0!=0) => False
.2 i=1
-  if(1!=1) => False
.3 i=2
-  if(2!=3) return 2         
