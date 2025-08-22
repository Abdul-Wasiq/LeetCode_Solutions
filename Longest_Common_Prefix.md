# LONGEST COMMON PREFIX
## 1. Explanation:
Find the longest starting part (prefix) that is common in all words of the array.  
Example: ["flower", "flow", "flight"] → common prefix = "fl"

## 2. Code:
``` 
Python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """

        prefix = ""

        for i in range(len(strs[0])):
            eachChar = strs[0][i]

            for j in range(1, len(strs)):
                if (i >= len(strs[j]) or eachChar != strs[j][i] ):
                    return prefix
                    exit()                    
        
            prefix = prefix + eachChar
        
        return prefix

         
```
