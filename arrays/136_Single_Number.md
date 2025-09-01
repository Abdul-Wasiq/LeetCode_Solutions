# 121. Single Number 
## 1. Problem Explain:
Every Element appears twice except one element, return that element.

Example:
Input: nums = [2,2,1] -> output=1

## 2. Code:
```
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        current = nums[0]
        for i in range(1,len(nums)):
            current = current ^ nums[i]
        return current    
```
## 3. Explanation:
Our main goal is to get element which appears only once times,
- we will use XOR concept,
- when same elements then return 0 otherise 1
- for example: 4,1,2,1,2
1. Start = 0

2. 0 ^ 4 = 4

3. 4 ^ 1 = 5

4. 5 ^ 2 = 7

5. 7 ^ 1 = 6

6. 6 ^ 2 = 4
#### The final result is 4 (the single number).

## 4. Pseudo Code with Example walkthrough:
We’ll use nums = [4, 1, 2, 1, 2].

Initial:

current = nums[0] = 4

Loop:

i = 1, nums[1] = 1 \
current = 4 ^ 1 = 5 (100 ^ 001 = 101)

i = 2, nums[2] = 2 \
current = 5 ^ 2 = 7 (101 ^ 010 = 111)

i = 3, nums[3] = 1 \
current = 7 ^ 1 = 6 (111 ^ 001 = 110)

i = 4, nums[4] = 2 \
current = 6 ^ 2 = 4 (110 ^ 010 = 100)
