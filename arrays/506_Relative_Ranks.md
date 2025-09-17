# 506. Relative Ranks
## 1. Problem Explain:
   We have to give ranks to each person(index) that what is its rank.
   score = [10,3,8,9,4] rank is ["Gold", "5th", "Bronze", "Silver", "4"]

## 2. Idea:
- First we will get copy the original array in descending order.
- then we will give it rank in dictionary form
- for example: dictionary= [10:"Gold",9: "Silver",8:"Bronze",4:"4",3:"5"]
- now loop through score(original array)
- and add values of score
- like score = [10,3,8,9,4] -> 10= Gold (newArr = ["Gold Medal"])
                            -> 3 = "5" (newArr = ["Gold Medal", "5")
                            -> 8 = "Bronze" (newArr = ["Gold Medal", "5", "Bronze"]
                            -> 9 = "Silver" (newArr = ["Gold Medal", "5", "Bronze", "Silver"]
                            -> 4 = "4" (newArr = ["Gold Medal", "5", "Bronze", "Silver", "4"]
- return newArr

## 2. Code:
```
class Solution(object):
    def findRelativeRanks(self, score):
        """
        :type score: List[int]
        :rtype: List[str]
        """
        descending = sorted(score, reverse=True)
        medals = ["Gold Medal", "Silver Medal", "Bronze Medal"]
        hashMap = {}
        for i in range(len(descending)):
            if (i < 3):
                hashMap[descending[i]] = medals[i]
            else:
                hashMap[descending[i]] = str(i+1)

        newArr = []

        for s in score:
            newArr.append(hashMap[s])

        return newArr                               
```
