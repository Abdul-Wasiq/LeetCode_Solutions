# 108. Convert Sorted Array to Binary Search Tree

We will cover two examples to know that how conversion works
## Example (Odd Length Array)

   nums = [-10, -3, 0, 5, 9] (length = 5)

### Step 1: Pick the middle element
Mid index = 5 // 2 = 2 → nums[2] = 0 → 0 becomes the root
Left subarray = [-10, -3], Right subarray = [5, 9]

### Step 2: Build left subtree
Mid of [-10, -3] = 1 → -3 becomes left child of 0
Remaining left = [-10] → -10 becomes left child of -3

### Step 3: Build right subtree
Mid of [5, 9] = 1 → 9 becomes right child of 0
Remaining left = [5] → 5 becomes left child of 9
