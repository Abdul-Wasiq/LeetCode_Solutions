# 349. Intersection of two Arrays 
## 1. Problem Explain:
Return the intersection of two arrays → elements that appear in both arrays.

- Result must have unique values.
- Order doesn’t matter.
#### Example: nums1 = [1,2,2,1], nums2 = [2,2] -> Output: [2]

## 2. Code:
```
class Solution(object):
    def intersection(self, nums1, nums2):
        newArr = []
        for i in range(len(nums1)):
            for j in range(len(nums2)):
                if nums1[i] == nums2[j]:
                    if nums1[i] not in newArr:
                        newArr.append(nums1[i])
        return newArr

```

## 3. Idea:
- Compare every element of nums1 with every element of nums2.
- If equal → add to newArr.
- Before adding, check it’s not already there (to keep unique).
- Return newArr.

## 4. Pseudo Code with Example walkthrough:
- newArr = []

- i=0, nums1[0]=1
   compare with nums2 → no match

- i=1, nums1[1]=2
   compare with nums2[0]=2 → match → add 2
   newArr = [2]

- i=2, nums1[2]=2
   compare with nums2 → match but already in newArr → skip

- i=3, nums1[3]=1
   compare with nums2 → no match

- return [2]
