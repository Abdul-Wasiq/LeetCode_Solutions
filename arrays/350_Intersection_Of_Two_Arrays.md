# 350. Intersection Of Two Arrays 
## 1. Problem Explain:
   Return the intersection of two arrays, but this time(the minimum count):

 - Each element in the result should appear as many times as it shows in both arrays.
 - Order doesn’t matter.
#### Example nums1 = [1,2,2,1], nums2 = [2,2] -> Output: [2,2]

## 2. Code:
```
class Solution(object):
    def intersect(self, nums1, nums2):
        newArr = []
        for i in nums1:
            if (i in nums2):
                newArr.append(i)
                nums2.remove(i)                

        return newArr        
```
## 3. Idea:
- Loop through nums1.

- If number also exists in nums2 → add it to result.

- Remove that number from nums2 so it won’t count extra.

- Continue until done.

## 4. Pseudo Code with Example walkthrough:
  Example: nums1 = [1,2,2,1], nums2 = [2,2]
newArr = []

- i=1 → not in nums2 → skip
- i=2 → in nums2 → add 2, remove from nums2
   newArr = [2], nums2 = [2]
- i=2 → in nums2 → add 2, remove from nums2
   newArr = [2,2], nums2 = []
- i=1 → not in nums2 → skip

- return [2,2]
  
