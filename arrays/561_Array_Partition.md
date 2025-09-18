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

## 3. Explanation:
- Sort the array first, because sorted pairs give the maximum possible sum.
- Take elements in pairs: (nums[0], nums[1]), (nums[2], nums[3]), …
- From each pair, add the smaller number (since problem says sum of mins).
- Continue until all elements are used.
- Return the total sum.

## 4. Pseudo Code with Example walkthrough:
#### Example: nums = [6,2,6,5,1,2]

- Sorted = [1,2,2,5,6,6]
- Take pairs: (1,2), (2,5), (6,6)
- Sum = 1 + 2 + 6 = 9

#### Step by step:

- i=0 → min(1,2)=1 → sum=1
- i=2 → min(2,5)=2 → sum=3
- i=4 → min(6,6)=6 → sum=9
- Return 9
