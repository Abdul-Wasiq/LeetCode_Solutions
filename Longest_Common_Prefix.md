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
Our logic is to compare each character of the first word with the same character position in all other words.
Steps:

1. Start with an empty string prefix.

2. Loop through each character of the first word.

3. For each character, compare it with the character at the same index in all other words.

4. If a mismatch is found, return the prefix collected so far.

5. If all match, add this character to prefix.

6. If the loop finishes with no mismatches, the entire first word is the prefix.

## 4. Pseudo Code with Example walkthrough:
   Input: ["flower", "flow", "flight"]

1. prefix = ""

2. i = 0 → eachChar = "f"

 - Compare with "f" (flow) → match

 - Compare with "f" (flight) → match
→ add "f" → prefix = "f"

3. i = 1 → eachChar = "l"

 - Compare with "l" (flow) → match

 - Compare with "l" (flight) → match
→ add "l" → prefix = "fl"

4. i = 2 → eachChar = "o"

 - Compare with "o" (flow) → match

 - Compare with "i" (flight) → mismatch → stop.

 Result: "fl"
   
