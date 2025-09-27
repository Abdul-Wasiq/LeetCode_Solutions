# 628. Maximum Product of Three Numbers
## 1. Problem Explain:
Given an array of integers nums, find the maximum product you can make by multiplying any three numbers.
#### ⚡ Trick:
If numbers are all positive, just pick the top 3.
But negative × negative = positive, so sometimes 2 smallest (most negative) + 1 largest is better.

## 2. Idea:

- Sort the array.
- Option 1: product of last 3 numbers.
- Option 2: product of 2 smallest numbers (negatives) and the largest number.
- Answer is the max of those two.

## 3. Code:
```
class Solution(object):
    def maximumProduct(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums = sorted(nums)

        prod1 = nums[0] * nums[1] * nums[-1] # 2 smallest and 1 lar
        prod2 = nums[-1] * nums[-2] * nums[-3]

        return max(prod1,prod2)
```
## 4. Pseudo Code with Example walkthrough:
#### Example: nums = [ -10, -10, 5, 2 ]

- Sorted: [ -10, -10, 2, 5 ]

- prod1 = (-10) × (-10) × 5 = 500

- prod2 = 5 × 2 × (-10) = -100

- max(500, -100) = 500
##### Answer = 500
