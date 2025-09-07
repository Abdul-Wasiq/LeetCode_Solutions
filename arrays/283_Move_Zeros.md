# 283. Move Zeros 
## 1. Problem Explain:
   Move all 0s to the end. Keep order of other numbers.
  #### Example: [0,1,0,3,12] → [1,3,12,0,0] 

## 2. Code:
```
class Solution(object):
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        arr1 = []
        arr2 = []

        for i in range(len(nums)):
          if (nums[i] == 0):
            arr2.append(nums[i])
          else:
            arr1.append(nums[i])

        num = 0
        for j in range(len(arr1)):
          nums[j] = arr1[num]
          num = num + 1

        num = len(arr1)
        for k in range(len(arr2)):
          nums[num] = arr2[k]
          num = num + 1
        
```
## 3. Explanation:
1- Create two arrays:

- arr1 → stores non-zero numbers.
- arr2 → stores zeros.

2- Copy arr1 first into nums.

3- Then copy arr2 (all zeros) after it.    

## 4. Pseudo Code with Example walkthrough:
#### Example: [0, 1, 0, 3, 12]
- arr1 = []        
- arr2 = []        

- for each num in nums: \
     if num == 0 → put in arr2 \
     else → put in arr1 

- arr1 = [1, 3, 12]
- arr2 = [0, 0]

- nums = arr1 + arr2
- nums = [1, 3, 12, 0, 0]
