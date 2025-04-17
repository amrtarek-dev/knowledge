There are many different sorting algorithms, each with unique properties and performance characteristics. Here are the most common sorting algorithms, along with examples for each:

## 1. **Bubble Sort**
Bubble Sort is a simple comparison-based algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. 

This process continues until the list is sorted.
- **Time Complexity**: O(n²) (not very efficient for large datasets)
- **Example**: Sorting `[5, 3, 8, 4, 2]`
    1. Compare `5` and `3`, swap → `[3, 5, 8, 4, 2]`
    2. Compare `5` and `8`, no swap → `[3, 5, 8, 4, 2]`
    3. Compare `8` and `4`, swap → `[3, 5, 4, 8, 2]`
    4. Compare `8` and `2`, swap → `[3, 5, 4, 2, 8]`
    5. Continue until no swaps are needed.


## 2. **Selection Sort**
Selection Sort divides the list into two parts: the sorted part on the left and the unsorted part on the right. 

It repeatedly selects the smallest element from the unsorted part and moves it to the sorted part.
- **Time Complexity**: O(n²)
- **Example**: Sorting `[29, 10, 14, 37, 13]`
    1. Find the minimum (`10`), swap it with the first element → `[10, 29, 14, 37, 13]`
    2. Find the next minimum (`13`), swap → `[10, 13, 14, 37, 29]`
    3. Continue this process until the list is sorted.


## 3. **Insertion Sort**
Insertion Sort builds the sorted array one element at a time by repeatedly picking the next element from the unsorted part and inserting it into the correct position within the sorted part.
- **Time Complexity**: O(n²)
- **Example**: Sorting `[7, 3, 5, 1]`
    1. Start with the second element, compare `3` with `7`, and insert → `[3, 7, 5, 1]`
    2. Compare `5` with `7`, and insert before it → `[3, 5, 7, 1]`
    3. Insert `1` in the correct position → `[1, 3, 5, 7]`.

## 4. **Merge Sort**
Merge Sort is a **divide-and-conquer** algorithm. 

It divides the array into two halves, recursively sorts each half, and then merges the sorted halves back together.
- **Time Complexity**: O(n log n) (more efficient for large datasets)
- **Example**: Sorting `[38, 27, 43, 3, 9, 82, 10]`
    1. Divide the array into two halves: `[38, 27, 43]` and `[3, 9, 82, 10]`.
    2. Recursively split the subarrays until each array contains one element: `[38] [27] [43] [3] [9] [82] [10]`.
    3. Merge the subarrays step by step: `[27, 38, 43]` and `[3, 9, 10, 82]`.
    4. Finally, merge the two sorted halves into `[3, 9, 10, 27, 38, 43, 82]`.

## 5. **Quick Sort**
Quick Sort is another **divide-and-conquer** algorithm that selects a "pivot" element from the array and partitions the other elements into two subarrays:

those less than the pivot and those greater than the pivot. It then recursively sorts the subarrays.
- **Time Complexity**: O(n log n) on average, but O(n²) in the worst case (e.g., when the pivot is consistently the smallest or largest element).
- **Example**: Sorting `[9, 7, 5, 11, 12, 2, 14, 3, 10, 6]`
    1. Choose a pivot (e.g., `9`).
    2. Partition the array into elements less than `9` and elements greater than `9`: `[7, 5, 2, 3, 6] [9] [11, 12, 14, 10]`.
    3. Recursively apply Quick Sort to the subarrays.
    4. Result: `[2, 3, 5, 6, 7, 9, 10, 11, 12, 14]`.