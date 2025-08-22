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

## 4. Pseudo Code with Example walkthrough:
   lets say we have an array strs = ["flower","flow","flight"]
   now lets do operation of each line in the code,

   strs = ["flower", "flow", "flight"]
   prefix = ""
   for (i=0 to 5) {
      eachChar = strs[0][0] means eachChar = "f"
      for (j = 1 to 2) {
         if ("f"(eachChar) != "f"(strs[1][0]) it is not True {
             print the prefix(it is empty now)
             and stop the loop by exit() function }      
      prefix "" = prefix "" + "f"
      }
      now for (j = 2 to 2) {
      if ("f"(eachChar) != "f"(strs[2][0]) it is not true {
          print the prefix(it is empty here)
          and stop the loop by exit() function }
   print the prefix if main loop is overed(but not overed yet_

   now main loop has completed, let it run again:

   for (i=1 to 5) {
      eachChar = "l"
      for (j = 1 to 2):
         if ("l" != strs[j(1)][i(1)]("l")) NOT TRUE{
            print the prefix 
            and exit the function
         now if ("l" != strs[j(2)[i(1)"l") NOT TRUE {
            print the prefix
            and exit the function
      prefix"f" = prefix"f" + "l"
      }

  for (i=2 to 5) {
      eachChar = "o"
      for (j=1 to 2) {
         if ("o" != strs[j(1)[i(2)]("o") NOT TRUE {
            print the prefix which is "fl"
            and exit the function }
      for (j=2 to 2) {
         if ("o" != strs[j(2)[i(2)]("i") TRUE {
            print the prefix which is "fl"
            and exit the function
}
   
