# 169 Majority Element
## 1. Problem Explain:
   We have to get the element which appears more than length of an array times.

## 2. Code:   
```
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums = sorted(nums)
        return nums[len(nums) // 2]
```

## 3. Explanation:
1- Our logic to get majority number is:
- We will make new Array/List with a sorted version of original Array
- then we will get center element of the sorted array
- and this will be our majority element

## 3. Explanation:
        
