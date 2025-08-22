# LONGEST COMMON PREFIX
## 1. Problem Explain:
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
## 3. Explanation:
    Our logic is to compare each character in FIRST word with all other characters of OTHER words.
    so first thing we will do is that we will make variable of prefix and let it be empty string,
    we have to take the loop which runs from first character to last character of first word,
    and we will make variable with connected loop which gets character one by one,
    now we have to make an other loop inside the main loop for getting other words in array except first word to compare,
    then we will put condition that if each Character in first word is not equal to each character in other words(one by one),
    if we will find that each character in first word is not equal to characters of other words then return the remaining prefix and then stop the loop, 
    if character is matched then add in prefix variable(Remember we talked about 'prefix' empty String variable in starting?)

   now this logic will work only when condition is true means that if there is no or less prefix I mean not complete prefix like full word then it is applicable other wise it will not return anything when whole first word is prefix.

## 3. Pseudo Code with Example walkthrough:
    lets say we have an array
   
