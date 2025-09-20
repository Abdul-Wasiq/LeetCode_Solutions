# 575. Distribute Candies:
## 1. Problem Explain:
   Problem is saying that dont return number of candies more than lenght / 2.
   For Example: candyType = [1,1,2,2,3,3], return 3 because person can eat maximum 1,2,3(new taste)
   
## 2. Idea:
- remove all duplicates from the array.
- if lenght of non duplicate elements is more than or equal to length of original array / 2 then return length of length of non duplicate element / 2
- else return length of non duplicate elements.

## 3. Code:
```
class Solution(object):
    def distributeCandies(self, candyType):
        sortedArr = list(set(candyType))

        if (len(sortedArr) >= len(candyType)//2):
            return len(candyType)//2
        else:
            return len(sortedArr)            
```

# 4. Pseudo Code with Example walkthrough: 
   Example: [1,1,2,2,3,3], length = 6
- non Duplicate = [1,2,3], length = 3
- if(3>= 6/2) -> return 3
