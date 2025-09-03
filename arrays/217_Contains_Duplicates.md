# 217. Contains Duplicates 
## 1. Problem Explain:
Check if the array contains any duplicates.

## 2. Code:
```
class Solution:
    def containsDuplicate(self, nums):
        return len(nums) != len(set(nums))
```

## 3. Explanation:
- Convert the list to a set → removes duplicates.

- If lengths change → duplicates exist → return True; else → False.

## 4. Pseudo Code with Example walkthrough:
nums = [1,2,3,1] → set → {1,2,3} → lengths differ → True 
