# Operations and control flow
After knowing variable types, let's start to know more about Python operators, and how you can control the execution flow of your code.

## Operations

There is a quite number of operation available in Python

### Mathematical operations

#### Adding
```python
>>> 10 + 1020
>>> 10 + 10.020.0
```

#### Subtraction
```python
>>> 10 - 55
>>> 10 - 5.05.0
```

#### Multiplication
```python
>>> 10 * 550
>>> 10 * 5.050.0
# Power
>> 2 ** 532
```

#### Division
```python
>>> 10 / 3 
3.3333333333333335
>>> 10 // 3
3
# Reminder
>>> 5 % 3
2
```

### Relational operation
```python
>>> Num = 10
>>> Num == 10
True
>>> Num != 10
False
>>> Num < 11
True
>>> Num > 9
True
>>> Num >= 10 
True
>>> Num <= 10 
True
```

## Control flow

### If conditions

It is a branch execution based on a value expiration
```python
if True:
    print("It's true")
else:
    pass
```

### Loops

#### While loop

While loop is a block of code that will be executed while a condition is True, and stops when it becomes False
```python
count = 5
while count != 0:
    print(count)
    count -= 1
```

You can end a loop on another condition by **break** keyword
```python
x = 10
while True:
    x -= 1
    if x == 0:
        break
```

#### For loop

For loop is a loop for each item in the loop block (iterable object)
```python
>>> names = ["amr", "tarek", "hassan", "abdelghafar"]
>>> for name in names:
...    print(name)
...
amrtarekhassanabdelghafar
```

Incremental for loop
```python
>>> for i in range(0,3):
...    print(I)
...
012
```

decrement for loop (reversed)
```python
>>> for i in range(3,0,-1):
...    print(I)
...
321
```

enumerate
```python
>>> t = [6, 12, 30 , 20]
>>> for i in enumerate(t):
...    print(i)
...
(0, 6)
(1, 12)
(2, 30)
(4, 20)
```

So now you can start with python modularity and more deep python stuff.