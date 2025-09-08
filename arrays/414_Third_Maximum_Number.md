# 414. Third Maximum Number
## 1. Problem Explain:
   Return the third distinct maximum number in the array.
   If it doesn’t exist, return the maximum number.
   #### Input:  nums = [3,2,1]  -> Output: 1
   #### Input:  nums = [1,2] ->  Output: 2  (no 3rd max → return max)

## 2. Code:
```
class Solution(object):
    def thirdMax(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums = list(set(nums))
        nums.sort(reverse=True)

        if (len(nums) >= 3):
            return nums[2]
        else:
            return nums[0]    
```

## 3. Idea:
- Remove duplicates → only distinct numbers matter.

- Sort in descending order.

- If at least 3 numbers → return 3rd one.

- Else → return the largest.

## 4. Pseudo Code with Example walkthrough:
#### Example: nums = [2,2,3,1]
- Remove duplicates → [2,3,1]
- Sort descending → [3,2,1]
- len=3 → return nums[2] = 1
