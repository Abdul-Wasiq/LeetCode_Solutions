# 455. Assign Cookies 
## 1. Problem Explain:
  You are a father, and you have children and cookies,
  your goal is to feed greed child first and you also dont have to feed over,
  For Example: greed = [1,2,3], size Of Cookie = [1,1] so output should be 1 because you    are able to feed only one greediest children.

## 2. Code:
```
class Solution(object):
    def findContentChildren(self, g, s):
        g.sort()
        s.sort()

        i = 0
        j = 0

        while (i<len(s) and j<len(g)):
            if (s[i] >= g[j]):
                j=j+1
            i=i+1
        return j        
```

## 3. Idea:
- Our main goal is to check g and s that if sth element is greater than gth element then check then move elements of g further and compare normally and other wise move s elements further if s element is not greater than g elememnt and in the end return how much further gth index has gone. but be careful that index dont go out of range.

## 4. Pseudo Code with Example walkthrough:
- g = sorted(7,8,9,10) and s = sorted(5,6,7,8)
- i=0,j=0 -> if(5>=7) False -> i=1
- i=1,j=0 -> if(6>=7) False -> i=2
- i=2,j=0 -> if(7>=7) True -> j=1
- i=2,j=1 -> if(7>=8) False -> i=3
- i=3,j=1 -> if(8>=8) True -> j=2
- i=3,j=2 -> if(8>=9) False -> i=4
- i=4,j=2 -> while(4<4 and 2<4) -> False -> Loop Stopped
- return j which is 2
  As a father I have to feed to two greediest children(cookie size=7,  feed to greediest level = 7 and cookie size = 8, feed to greed level child = 8)

    These problems will be easy once you understand Two Pointers technique or greedy pointers.
