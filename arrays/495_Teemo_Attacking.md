# 495. Teemo Attacking 
## 1. Problem Explain:
   Teemo attacks. Each attack poisons Ashe for duration seconds.
   If next attack comes before poison ends, don’t double count.

## 2. Code:
```
class Solution(object):
    def findPoisonedDuration(self, timeSeries, duration):
        total = 0
        for i in range(len(timeSeries)-1):
            total += min(duration, timeSeries[i+1] - timeSeries[i])
        return total + duration
```

## 3. Idea:
- Go through all attacks.

- If another attack comes soon, only count the gap.

- At the end, add last attack duration.

## 4. Pseudo Code with Example walkthrough: 
#### Example: timeSeries = [1, 2], duration = 2

- i=0 → gap = 2-1=1 → add min(2,1)=1 → total=1
- after loop add duration → total=1+2=3
- Answer = 3 
