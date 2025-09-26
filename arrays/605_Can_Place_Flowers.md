# 495. Teemo Attacking 
## 1. Problem Explain:
- We have a flowerbed (array of 0s and 1s).
- 1 means a flower is already planted.
- 0 means empty.

- Rule: You cannot plant two flowers next to each other.
- Question: Can we plant n flowers in this flowerbed?

## 2. Code:
```
class Solution(object):
    def canPlaceFlowers(self, flowerbed, n):
        count = 0
        size = len(flowerbed)

        for j in range(size):
            if flowerbed[j] == 0:
                left = (j == 0 or flowerbed[j-1] == 0)
                right = (j == size-1 or flowerbed[j+1] == 0)
                if left and right:
                    flowerbed[j] = 1
                    count += 1
                    if count >= n:   # early exit
                        return True
        return count >= n
```

## 3. Idea:
- Walk through each spot.

- Check if left and right are empty (or out of bounds).

- If yes, plant a flower there (set to 1).

- Count how many planted.

- If count reaches n, return True.

- At end, check if count ≥ n.

## 4. Pseudo Code with Example walkthrough: 
#### Example: flowerbed = [1,0,0,0,1], n = 1
- j=0 → already 1, skip.

- j=1 → left=1 (not empty), skip.

- j=2 → left=0, right=0 → can plant → flowerbed becomes [1,0,1,0,1], count=1.

- Since count ≥ n → return True.
