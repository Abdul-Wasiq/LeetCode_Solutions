# 219. Contains Duplicate II 
## 1. Problem Explain:
  Check if the array has duplicates within k indices apart.

## 2. Code:
```
class Solution:
    def containsNearbyDuplicate(self, nums, k):
        seen = {}
        for i, num in enumerate(nums):
            if num in seen and i - seen[num] <= k:
                return True
            seen[num] = i
        return False
```

## 3. Explanation:
- Track last index of each number in a dictionary.

- If a number repeats and its index difference ≤ k, return True.

- Otherwise, return False.

## 4. Pseudo Code with Example walkthrough:
#### nums = [1,2,3,1], k=3 → 1 repeats at indices 0 & 3 → 3-0 ≤ 3 → True 
  
