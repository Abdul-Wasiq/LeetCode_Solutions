# 500. Keyboard Row 
## 1. Problem Explain:
   return the word in the array which all alphabets are in same row
   American Keyboard: qwertyuiop (Row1)
                      asdfghjkl (Row2)
                      zxcvbnm (Row3)

   For Example: 
         words = ["Hello","Alaska","Dad","Peace"] 
         return Alaska and Dad because all Alaska alphabets are in same Row(Row2) and Dad also in Row2

## 3. Idea:
- We will compare each element's alphabet with keyboard array
- If all hello alphabets in same row then add in new array otherwise not.

## 2. Code:
```
class Solution(object):
    def findWords(self, words):
        keyboard = ["qwertyuiop", "asdfghjkl", "zxcvbnm"]
        newArr = []
        for word in words:
            for key in keyboard:
                all_in_row = True
                for ch in word: # Hello
                    if (ch.lower() not in key):
                       all_in_row = False

                if (all_in_row):
                    newArr.append(word)
                    break
        return newArr                 
```

## 4. Pseudo Code with Example walkthrough:
1. word = Hello:
- Hello is not in qwertyuiop (False)
- Hello is not in asdfghjkl (False)
- Hello is not in zxcvbnm (False)

2. word = Alaska: 
- Alaska is not in qwertyuiop (False)
- Alaska is in asdfghjkl (True) -> newArr = ["Alaska"]

3. word = Dad:
- Dad is not in qwertyuiop (False)
- Dad is in asdfghjkl (True) -> newArr = ["Alaska", "Dad"]

4. word = Peace:
- Peace is not in qwertyuiop (False)
- Peace is not in asdfghjkl (False)
- Peace is not in zxcvbnm (False)

5. Loop Finished:
- return newArr which is Alaska Dad
