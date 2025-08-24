# 27 Remove Element
## 1. Problem Explain: 
Remove all occurrences of val from the array and return the count of the remaining elements.
Example: nums = [3,2,2,3], val = 3, output should be k=2 because there are two non 'val' numbers in first way

## 2. Code:
```
Python
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """ 
        k = 0
        # Iterate through all elements in nums
        for i in range(len(nums)):
            # If current element is not equal to val, keep it
            if nums[i] != val:
                nums[k] = nums[i]   # Place the non-val element at index k
                k += 1              # Move k forward for the next position
        return k  # k represents the count of non-val elements
```
## 3. Explanation:
Our logic is to move all numbers that are not equal to val to the front of the array. Steps:

1. Start with a pointer k = 0 (this will mark the position for the next non-val number).

2. Loop through each element in the array nums.

3. If the current element is not equal to val, copy it to index k and increase k by 1.

4. If the element is equal to val, skip it (do nothing).

5. After the loop ends, k will represent how many numbers are left in the array that are not equal to val.

6. Return k.

👉 Note: LeetCode checks only the first k elements of the array. That’s why returning k is enough — it shows how many non-val elements remain, and all val elements are effectively ignored.   

## 4. Pseudo Code with Example walkthrough:
Input: nums = [3,2,2,3], val = 3
k = 0

i = 0 → nums[0] = 3  
Check: (3 != 3) → false → skip  

i = 1 → nums[1] = 2  
Check: (2 != 3) → true → nums[0] = 2 → nums = [2,2,2,3]  
k = 1  

i = 2 → nums[2] = 2  
Check: (2 != 3) → true → nums[1] = 2 → nums = [2,2,2,3]  
k = 2  

i = 3 → nums[3] = 3  
Check: (3 != 3) → false → skip  

End of loop → return k = 2
