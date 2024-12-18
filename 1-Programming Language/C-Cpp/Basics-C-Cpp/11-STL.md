# C++ Standard Template Library (STL)

C++ added its own library which depends on **Templates** and called it **STL** or **Standard Template Library**, It is a part of the  ANSI/ISO C++ standard, so it is part of the C++ standard.

It consists of many components and utilities, the components can be split into three types:
- Containers
- Iterators
- Algorithms

## Containers
They are template classes that can be used to manipulate the data in a standard way, and they are 3 categories:
- Sequential Containers
	- Array, Vector, List, Forward List, Pair
- Associative Containers
	- Set, MultiSet, unordered_set, unordered_multiset
- Adapter Containers
	- Stack, Queue, Deque, priority Queue
### Sequential
#### Array
Arrays are used to store multiple values of similar data types in a single variable in contiguous memory allocation.
```cpp
#include <array>
//std::array<data_type, no_of_elements> nameOfArray;
std::array<int, 3> a = {1,2,3};
```
> Array has a fixed size, and it can not be changed, and the initial value for it is a garbage value, so it is a good practice to assign value to it at initialisation.

#### Vector
Vectors are used to store multiple values of similar data types in contiguous memory allocation, and size does not need to be known in advance, and easy access to a specific item or all of them.

```cpp
#include <vector>

//std::vector<data_type> nameOfVector;
std::vector<int> v = {1,2,3};
std::vector<int> iv(3, 100); // {100, 100, 100}

std::cout << v.size(); // 3
v.capacity(); // size of vector + the extra size that can be added.
std::cout << v.front(); // 1
std::cout << v.back(); // 3

// range-base iterator (C++11)
for (int& vec: v) {
    cout << vec << " ";
}

// insert in the middle of vector
v.insert(v.begin() + 1, 5); // 1,5,2,3
v.push_back(4); // 1,5,2,3,4
v.insert(v.end(), 5); // 1,5,2,3,4,5
v.emplace(v.end(), 6); // 1,5,2,3,4,5,6
v.emplace_back(7); // 1,5,2,3,4,5,6,7

// To initialized from c-array
const static int size = 10;
int ia[size] = { 1, 2, 3, ,4, 5, 6, 7, 8, 9, 10};
vector<int> iv2(ia, ia+size);


// To initialized from argc/argv list
 // argv : argument value. argc : argument count.
vector<string> args(argv, argv_argc);

```

- When you need fast random access to elements.
- When you primarily add or remove elements at the end of the collection.
- When the number of elements does not change frequently.

> Unlike arrays, the size of a vector can grow dynamically, but if the capacity is exceeded, the vector reallocates its storage to a large contiguous block.
> Which copying all elements to the new block and it is time and memory expensive.

Properties:
> Add or delete from back =  O(1)
> Add or delete from middle or front = O(n) (because of the shift needed)
> Access [], or at()  = o(1)
> find    = O(Log(n)) ( and it needs to be ordered)

#### List
List is a double linked list (Each element in the list contains a pointer to next and previous node), which allow efficient insertion and deletions from anywhere in the list, including both the front, and back.
```cpp
#include <list>

std::list<int> l;
l.push_back(1);
l.push_back(2);
l.push_back(3); // {1, 2, 3}
l.push_front(4); // {4, 1, 2, 3}

// Insert in middle
std::list<int>::iterator it = l.begin();
std::advance(it, 2);
l.insert(it, 5); // {4, 1, 5, 2, 3}

// You can not use [] or at() to access list element
for (const auto& elem : l) { 
	std::cout << elem << " "; 
}

```


### Simple
#### Pair
Is a type of container that receive two elements
```cpp
#include <utility>
pair<string, int>p = make_pair("Amr", 20);
pair<string, int>p2 = {"Tarek", 10};
pair<string, int>p3{"Hassan", 1};

// For accessing
cout<< p.first() << ":"<< p.second() << endl;
```

### Associative
#### Set
Set is a immutable, sorted, and unique data type

```cpp
#include <set>
std::set<int>s;
s.insert(4); // insert at the end
s.emplace(5); insert but faster

std::set<int, greater<int>s{12,3,4,5,6,23,121}; // sort descending
```

#### MultiSet
Multiset is the same of set but it can hold duplicated value (use it when you just want the sorting).
```cpp
#include <multiset>

std::multiset<int> ms;
ms.emplace(1);
ms.count(1); // check how many 1 in the set.
```

#### Map
Map is the array of pair data type plus it has a unique and sorted keys but not values.
it has a fast insertion, search o(log n), removal o(1)
```cpp
#include <map>
std::map<int, std::string> myMap; 
myMap[1] = "One"; 
myMap[2] = "Two"; 
// Search for key 1 auto 
it = myMap.find(1); 
if (it != myMap.end()) { 
	std::cout << "Key 1 found with value: " << it->second << std::endl; 
} else { 
	std::cout << "Key 1 not found" << std::endl; 
}
```
### Adapter 
#### Queue (FIFO)
is a FIFO (first in, first out), where elements are added to the back and removed from the front
```cpp
#include <queue>
std::queue<int> q;
q.push(1); // will push to front (FI)
q.push(2);
q.push(3);  // {3,2,1}

q.pop() // remove the front element (1) (FO)
q.back(); // 3
q.front(); // 1
```

#### Deque
Double ended queue, allows insertion and deletion at both ends.
```cpp
#include <deque>
std::deque<int> dq;
dq.push_back(1);
dq.push_back(2);
dq.push_front(3); {3, 1, 2}

dq.pop_front(); // Remove the front element (3) 
dq.pop_back(); // Remove the back element (2)
```

- When you need efficient insertion and deletion at both ends of the collection.
- When you do not need strict contiguous memory layout.
- When the number of elements changes frequently at both ends.

> Queue and Deque are not contiguous they are saving the data in memory chunks, so it can grow and shrink more efficiently than `vector`

#### Stack (FILO)
``` cpp 
#include <stack>
std::stack<int> stack;

// Add (push) elements to the stack
stack.push(10);
stack.push(20);
stack.push(30);

// Get (pop) elements from the stack
std::cout << "Popping elements from stack: \n";

while (!stack.empty()) {
	// Get the top element
	std::cout << stack.top() << std::endl;
	// Remove the top element
	stack.pop();
}
```


Properties:
> Add or delete from back or front =  O(1)
> Add or delete from middle = O(n) (because of the shift needed)
> Access [], or at()  = o(1)
> find = O(n) (slow search)

## Templates
maybe you have noticed the <> in vectors, these are the template type operator, so the vector class is using template to handle different types of data types, so do the algorithm functions **sort** and **count**.
And actually, the template approach is using the **operator overloading** to work, you already use it to add two strings with the + sign, which is operator overloading for the plus sign to handle the different data types.