# 349. Find All Numbers Disappeared in an Array
## 1. Problem Explain:
   Return all the numbers in [1..n] that are not present in nums.

## 2.Code:
```
class Solution(object):
    def findDisappearedNumbers(self, nums):
        return list(set(range(1, len(nums)+1)) - set(nums))
```

## 3. Idea:
- range(1, n+1) → all numbers that should be there.

- Convert to set for easy comparison.

- Subtract the set(nums) (numbers that actually appear).

- Whatever is left = missing numbers.

## 4. Pseudo Code with Example walkthrough:
####  Example: nums = [4,3,2,7,8,2,3,1]
#### n = 8
#### expected = {1,2,3,4,5,6,7,8}
#### present  = {1,2,3,4,7,8}
#### missing  = expected - present = {5,6}

#### return [5,6]

