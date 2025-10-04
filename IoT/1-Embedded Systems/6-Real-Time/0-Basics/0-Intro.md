
# RTOS
A real-time operating system (RTOS) performs resource management within strict time constraints.

- Deadline guarantee: Correct results within a set time constraint
- Reliability: predictable execution with a guaranteed response.
By being:
- Deterministic: ensure high-priority tasks are executed within a predictable time frame.
- Concurrency management: It allows multiple tasks to run concurrently without interfering with each other.
- Simplified development: by providing standard APIs for task management, making the development process more straight forward.


## RTOS kernel:
Real time operating system (kernel) is a software that extends the basic foreground/background architecture by allowing you to run multiple background loops (called **threads** or **Tasks**) on a single CPU

## Multithreading (Multitasking):
Switching the CPU context frequently form one **Thread** to another to create an illusion that each such Tread has the whole CPU all to itself. 

## Real-Time Embedded
Must respond to requests for service by a deadline relative to request.
Failure to respond prior to deadline results in a system failure


## Tasks
In **real-time operating systems (RTOS)**: A task is like a thread or lightweight process.

In **Linux**: Each thread is represented as a task in the kernel.