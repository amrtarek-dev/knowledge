# Strategy Design Pattern
The strategy pattern is a behavioural design pattern that defines a family of algorithms, encapsulates each algorithm, and makes them interchangeable. 

## Benefit
It allows the client to choose an algorithm at runtime without modifying the client code.

## When
This pattern is particularly useful when you have a family of algorithms and want to make them easily swappable.

## Example Problem
Suppose you have a program that needs to sort a list of numbers, and you want to support multiple sorting algorithms (e.g., bubble sort, merge sort, quicksort).

## Solution
Instead of hardcoding a specific sorting algorithm in your code, you can use the strategy pattern.

### OO Principles

- Define the Changing code part and encapsulate it.
- Program to interface, not implementation.
- Favour Composition over inheritance.

### Step 1
Implement the first OO principles (Encapsulation):

The changing code part is the Sort Algoritm, so encapsulate it in multiple classes
```md
+------------+
| BubbleSort |
+------------+
| + sort()   |
+------------+

+------------+
| MergeSort  |
+------------+
| + sort()   |
+------------+

+------------+
| QuickSort  |
+------------+
| + sort()   |
+------------+
```  

### Step 2
Implement the second OO principles:

Program to interface, so make an interface for the Sorting Strategy

```md
+------------+          +------------------+
| BubbleSort |          |  <<interface>>   |
+------------+.......|> | SortingStrategy  |
| + sort()   |    .     +------------------+
+------------+    .     | + sort()         |
                  .     +------------------+
+------------+    .
| MergeSort  |.....
+------------+    .
| + sort()   |    .
+------------+    .
                  .  
+------------+    .
| QuickSort  |.....
+------------+
| + sort()   |
+------------+
```

### Step 3
Implement the third OO principles:

Use the **SortingStrategy** inertface as dependency (Composition relation)

```md
+--------------------------------+
| SortingContext                 |           +------------------+
+--------------------------------+           |  <<interface>>   |
| - SortingStrategy SS           |<>-------> | SortingStrategy  |
+--------------------------------+           +------------------+
| + setSort(SortingStrategy ss){ |           | + sort()         |
|        this.SS = ss;           |           +------------------+
|   }                            |  
|                                |
| + useSort(){                   |
|        this.SS.sort();         |
|   }                            |          
+--------------------------------+
```

## To use it
The client now can use the **SortingContext** class and set the sorting algoritm in run time.

With this pattern we have achived the flixability of adding new sort algorithm without changing the code, and the user could change the used algorithm in the run time.