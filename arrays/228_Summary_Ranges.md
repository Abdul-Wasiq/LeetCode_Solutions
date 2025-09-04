# 121. Summary Ranges 
## 1. Problem Explain:
  We just have to write with each element as a set of difference 1
  for example: Input: nums = [0,1,2,4,5,7]
               Output: ["0->2","4->5","7"]

## 2. Code:
```
class Solution(object):
    def summaryRanges(self, nums):
        if (len(nums) < 1):
            return nums
        string = str(nums[0])
        elem = 0
        newArr = []
        for i in range(1,len(nums)):
            if (nums[i-1]+1 != nums[i]):
                if (nums[elem] != nums[i-1]):
                    string = string + "->" + str(nums[i-1])
                newArr.append(string)
                string = str(nums[i])
                elem = i

        if (nums[elem] != nums[-1]):
            string = string + "->" + str(nums[-1])
        newArr.append(string)            
        return newArr                
```

## 3. Explanation:
We want to group numbers that are continuous (difference = 1) into ranges.

- Start from the first number.

- Keep going as long as numbers increase by 1.

- When the chain breaks, close that range and add it to the answer.

- If a range has only one number, just add the number.

## 4. Pseudo Code with Example walkthrough:
#### Input: [0,1,2,4,5,7]

0→1→2 is continuous → "0->2"

4→5 is continuous → "4->5"

7 is alone → "7"

Output: ["0->2","4->5","7"]  
