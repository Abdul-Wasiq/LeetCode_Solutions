# 561. Array Partition
## 1. Problem Explain:
    We want to maximize the sum of the smaller numbers when forming pairs from the array.
    For Example: nums = [1,4,3,2]

    Pair them as (1,2) and (3,4)

    Sum of minimums = 1 + 3 = 4
    Output: 4

## 2. Code:
```
class Solution(object):
    def arrayPairSum(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums = sorted(nums)
        maxi = min(nums[0], nums[1])
        i = 0

        while (i < len(nums) - 2):
            maxi = maxi + min(nums[i+2], nums[i+3])
            i = i + 2

        return maxi
```
