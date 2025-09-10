Search algorithms are fundamental techniques in computer science used to find specific elements or conditions in a collection of data. 
These algorithms vary in complexity, efficiency, and application based on the structure and type of data.

### **1. Linear Search**
Linear search examines each element in the array sequentially until the target is found.
**Time Complexity**:
- Worst-case: O(n) (must check every element).
- Best-case: O(1) (if the target is the first element).
**Array**: `[3, 5, 7, 1, 9, 4]`, Target: `9`
**Steps**:
1. Compare `3` with `9` → No match.
2. Compare `5` with `9` → No match.
3. Compare `7` with `9` → No match.
4. Compare `1` with `9` → No match.
5. Compare `9` with `9` → Match found at index 4.

### **2. Binary Search**
Binary search requires a **sorted** array. It divides the array in half, comparing the middle element with the target.
**Time Complexity**:
- Worst-case: O(log ⁡n) (cuts the search space in half at each step).
- Best-case: O(1) (if the target is the middle element).
**Array**: `[1, 3, 5, 7, 9, 11]`, Target: `7`
**Steps**:
1. Array is already sorted.
2. Check the middle element: `5` (middle index 2).
    - `7` is greater than `5`, so search the right half.
3. New search range: `[7, 9, 11]`. Check the middle element: `9`.
    - `7` is smaller than `9`, so search the left half.
4. New search range: `[7]`. Check the middle element: `7`.
    - Match found at index 3.

### **3. Interpolation Search**
Interpolation search works on **sorted** arrays and assumes that the data is evenly distributed. It estimates where the target might be based on the value range.
**Time Complexity**:
- Best-case: O(log ⁡n) (for uniformly distributed data).
- Worst-case: O(n)) (if the distribution is skewed).
**Array**: `[10, 20, 30, 40, 50, 60, 70, 80]`, Target: `50`
**Steps**:
1. Array is already sorted.
2. Calculate estimated position: `pos = 0 + ((50 - 10) * (7 - 0)) / (80 - 10) = 4`.
3. Check element at position 4: `50`.
    - Match found at index 4.

### **4. Jump Search**
Jump search also works on **sorted** arrays. 
It jumps ahead by a fixed number of elements and performs a linear search when the range is narrowed down.
**Time Complexity**:
- Worst-case: O(√n​) (jumps ahead by fixed steps, then linear search within a block).
- Best-case: O(1) (if the first jump lands on the target).
**Array**: `[1, 3, 5, 7, 9, 11, 13, 15, 17, 19]`, Target: `13`
**Steps**:
1. Jump size = √n ​=3. Jump from index 0 to 3: `7`.
    - `13` is greater than `7`, so jump again.
2. Jump from index 3 to 6: `11`.
    - `13` is greater than `11`, so jump again.
3. Jump from index 6 to 9: `17`.
    - `13` is smaller than `17`, so perform linear search between index 6 and 9.
4. Compare `13` with `13` at index 6.
    - Match found at index 6.