# 88. Merge Sorted Array:

## 1. Problem Explanation

Merge two sorted arrays into nums1.
- nums1 has size m + n (first m elements are valid, last n are 0 placeholders).
- nums2 has n valid elements.
- After merging, nums1 should be a single sorted array.
#### Example:
Input:  nums1 = [1,2,3,0,0,0], m = 3
        nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]

## 2. Code:
```
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        # Place nums2 elements at the end of nums1
        for i in range(n):
            nums1[m + i] = nums2[i]

        # Sort nums1 in-place
        nums1.sort()
```

## 3. Explanation:
Steps:
1. Start placing elements of nums2 into nums1, beginning at index m.
2. After all elements are inserted, sort the entire nums1.
3. The result is nums1 fully merged in sorted order.

## 4. Pseudo Code with Example walkthrough:
  Input 
    nums1 = [1,2,3,0,0,0],m=3
    nums2 = [2,5,6],n=3
- i=0 → nums1[3] = nums2[0] → [1,2,3,2,0,0]

- i=1 → nums1[4] = nums2[1] → [1,2,3,2,5,0]

- i=2 → nums1[5] = nums2[2] → [1,2,3,2,5,6]

- Sort → [1,2,2,3,5,6]

- Return nums1
