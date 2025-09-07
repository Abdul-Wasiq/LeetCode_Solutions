# 303. Range Sum Query-Immutable
## 1. Problem Explain:
   Return sum of numbers from index left to right.
   #### Example: nums = [-2,0,3,-5,2,-1], Output: [null, 1, -1, -3]

## 2. Code:
```
class NumArray(object):
    def __init__(self, nums):
        self.nums = nums

    def sumRange(self, left, right):
        result = 0
        for i in range(left, right+1):
            result += self.nums[i]
        return result
```

## 3. Idea:
- Save the array.

- Loop from left → right.

- Add numbers and return sum.

## 4. Pseudo Code with Example walkthrough:
   Example: nums = [-2,0,3,-5,2,-1] and sumRange(0,2)
- result = 0

- i = 0: result = result + nums[0] = 0 + (-2)  => result = -2
- i = 1: result = result + nums[1] = -2 + 0    => result = -2
- i = 2: result = result + nums[2] = -2 + 3    => result = 1

- return 1

## 5. Leetcode Perspect of view:
LeetCode runs your class like this

- nums = [-2, 0, 3, -5, 2, -1]
- obj = NumArray(nums)
- obj.sumRange(0, 2)   # → 1
- obj.sumRange(2, 5)   # → -1
- obj.sumRange(0, 5)   # → -3


