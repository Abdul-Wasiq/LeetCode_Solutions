# 66. LONGEST COMMON PREFIX
## 1. Problem Explain:
You are given a list of digits that represents a number. Add 1 to this number and return the result as a new list. 

Example: [1,2,3] → 123 + 1 = [1,2,4]

## 2. Code:
```
Python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """

        digToStr = ""
        #We have to change digits to String
        for eachDig in digits:
            digToStr = digToStr + str(eachDig)

        addOne = int(digToStr) + 1
        newStr = str(addOne)

        newList = []

        for eachChar in newStr:
            newList.append(int(eachChar))

        return newList           
```
## 3. Explanation:
Our logic is to treat the digit list as a full number, add 1, then split back into digits.
Steps:

1. Convert digit list to a string.

2. Convert string to integer.

3. Add 1.

4. Convert back to string.

5. Split into digits and return.
   (Reminder: you have to be good in converstion(int to str or str to int))
## 4. Pseudo Code with Example walkthrough:
  Input: [1,2,3]

1. numStr = ""

2. numStr = "123"

3. num = 123 + 1 = 124

4. str(num) = "124"

5. result = [1,2,4]

6. Output: [1,2,4]
