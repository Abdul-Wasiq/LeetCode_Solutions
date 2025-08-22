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

        # Store the common prefix
        prefix = ""

        # Loop through each character index of the first word
        for i in range(len(strs[0])):
            eachChar = strs[0][i] # character from first word

            # Compare with the same position in other words
            for j in range(1, len(strs)):
                if (i >= len(strs[j]) or eachChar != strs[j][i] ):  # mismatch → stop
                    return prefix
                    exit()                    
            # If matched in all → add to prefix
            prefix = prefix + eachChar

        # If no mismatch → full first word is the prefix
        return prefix

         
```
