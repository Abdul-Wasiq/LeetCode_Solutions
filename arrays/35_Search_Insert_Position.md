# 35 Search Insert Position
## 1. Problem Explain:
Find target index in sorted array. If not found, return where it should be inserted.
nums = [1,3,5,6], target = 5, output -> 2

## 2. Code:
```
Python
class Solution(object):
    def searchInsert(self, nums, target):
        for i in range(len(nums)):
            if target <= nums[i]:
                return i
        return len(nums)  # target bigger than all
```
## 3. Explanation:
Logic is to check each number in array with target.

1. Start from first element.

2. If target <= nums[i], return index i.

3. Continue until end.

4. If no element ≥ target, return array length.
   
## 4. Pseudo Code with Example walkthrough:Input: nums = [1,3,5,6], target = 5

- i = 0 → 5 ≤ 1? → no

- i = 1 → 5 ≤ 3? → no

- i = 2 → 5 ≤ 5? → yes → return 2

- Result: 2
