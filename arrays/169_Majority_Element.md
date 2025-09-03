# 169 Majority Element
## 1. Problem Explain:
   Find the element that appears more than n/2 times in an array.

## 2. Code:   
```
class Solution:
    def majorityElement(self, nums):
        return sorted(nums)[len(nums)//2]
```

## 3. Explanation:
- Sort the array.

- The majority element always appears at the middle index.

## 4. Pseudo Code with Example walkthrough:
#### nums = [3,2,3] → sorted → [2,3,3] → middle nums[1] = 3 



        
