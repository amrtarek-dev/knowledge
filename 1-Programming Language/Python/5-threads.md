@Title: Threads
@Description: Thread in python is a lightweight, independently executing sequence of instructions that can run concurrently with other threads.
@Author: Amr Abdelghafar
@Category: Python
@img: python.jpg
++++++++++

Threads are a way to achieve parallelism and can be used to perform multiple tasks simultaneously. Python provides a built-in module called **threading** to work with threads.

There are two ways to use threads in python:
- Inherit the Thread Class
- Passing a target function to the **Thread** constructor 

### Inherit the Thread class

Importing the **threading** module and creating a thread by subclassing the **Thread** class from the **threading** module and overriding the **run()** method:

```python
import threading

class MyThread(threading.Thread):
    def run(self):
        # Code to be executed in the thread
        print("Thread is running")

# Creating an instance of the custom thread
my_thread = MyThread()

# Starting the thread
my_thread.start()

# Waiting for the thread to finish (optional)
my_thread.join()

print("Main thread continues")
```


### Thread Function

You can also create a thread by passing a target function to the Thread constructor:

```python
import threading

def my_function():
    print("Thread is running")

# Creating a thread with a target function
my_thread = threading.Thread(target=my_function)

# Starting the thread
my_thread.start()

# Waiting for the thread to finish (optional)
my_thread.join()

print("Main thread continues")
```

## Thread Synchronization

When multiple threads are working with shared resources, it's important to synchronize access to avoid data corruption. Python provides the **Lock** class for this purpose:

```python
import threading

# Shared resource
shared_data = {"counter": 0}
shared_data_lock = threading.Lock()

def increment_counter(data, lock):
    for _ in range(100000):
        with lock:
            data["counter"] += 1

# Creating two threads and passing the shared data and lock as arguments
thread1 = threading.Thread(target=increment_counter, args=(shared_data, shared_data_lock))
thread2 = threading.Thread(target=increment_counter, args=(shared_data, shared_data_lock))

# Starting the threads
thread1.start()
thread2.start()

# Waiting for the threads to finish
thread1.join()
thread2.join()

print("Counter value:", shared_data["counter"])
```

## Daemon Thread

Daemon threads are threads that run in the background and are terminated when the main program finishes:

```python
import threading
import time

def daemon_function():
    while True:
        print("Daemon thread is running")
        time.sleep(1)

# Creating a daemon thread
daemon_thread = threading.Thread(target=daemon_function)
daemon_thread.daemon = True

# Starting the daemon thread
daemon_thread.start()

# Main thread continues
time.sleep(3)
print("Main thread continues")
```

## Thread Pooling

Thread pooling is a technique where a fixed number of threads are created and reused to execute tasks:

```python
import concurrent.futures

def task_function(task_number):
    print(f"Task {task_number} is running")
    return f"Task {task_number} is complete"

# Creating a thread pool with 3 threads
with concurrent.futures.ThreadPoolExecutor(max_workers=3) as executor:
    # Submitting tasks to the thread pool
    futures = [executor.submit(task_function, i) for i in range(5)]

    # Retrieving results as they become available
    for future in concurrent.futures.as_completed(futures):
        result = future.result()
        print(result)
```

These examples cover the basics of working with threads in Python.

> Keep in mind that Python's **Global Interpreter Lock** (GIL) can limit the effectiveness of threads in certain scenarios, especially in CPU-bound tasks. 
> For **CPU-bound tasks**, consider using the **multiprocessing** module for parallelism.
