# 26. Remove Duplicates from Sorted Array:
## 1. Problem Explain:
Keep only the unique numbers in the sorted array by overwriting duplicates and return how many unique numbers exist.
Example: [1, 1, 2, 3, 3, 4] -> [1,2,3,4,3,4] and return 4 because there are three unique numbers

## 2. Code:
```
Python
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        j = 0  
        for i in range(1, len(nums)):  # loop through array starting from 2nd element
            if nums[j] != nums[i]:  # if current element is different from the last unique element
                j = j + 1  # move pointer j forward (new spot for unique number)
                nums[j] = nums[i]  # place the unique element at position j
        return j + 1  # length of array with unique elements
```
## 3. Explanation:
Our main goal is to put unique elements in first place and put duplicate in last:
1. Start with pointer j = 0 (position of last unique element).

2. Loop i from the 2nd element to the end.

3. Compare nums[j] with each nums[i]

4. If they are different, it means nums[i] is a new unique number.

5. Move j one step forward and copy nums[i] to nums[j].

6. Continue until the loop ends.

7. Return j + 1, which represents how many unique numbers we placed at the beginning of the array.

## 4. Pseudo Code with Example walkthrough:
  Input: [1, 1, 2, 3, 3, 4]

  1. j = 0
  2. i = 1, j = 0
     .) if (1 != 1) skipped
  3. i = 2, j = 0
     .) if (1 != 2) {j = 1 and nums[1]=2 => [1,2...]
  4. i = 3, j = 1
     .) if (2 != 3) {j = 2 and nums[2]=3 => [1,2,3...]
  5. i = 4, j = 2
     .) if (3 != 3) Skipped
  6. i = 5, j = 2
     .) if (3 != 4) {j = 3 and nums[3]=4 => [1,2,3,4,3,4]
  7. Loop Completed:
     return how many unieque element:
     return j+1        
