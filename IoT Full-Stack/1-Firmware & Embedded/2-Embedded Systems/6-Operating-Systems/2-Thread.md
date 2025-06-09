A **thread** is the smallest sequence of programmed instructions that can be managed independently. Threads are often called **lightweight processes**.

It has:
- **Shares memory space** with other threads in the same process
- **Owns** its own stack, program counter, and registers
- Enables **parallel execution** inside a process

## Types
- **User-level threads** (managed by user libraries)
- **Kernel-level threads** (managed by the OS)
- **Multithreading**: Multiple threads in a process

## LifeCycle
- **Ready**: ready to run and waiting for the CPU time in the Que
- **Running**: It isn running by the CPU
- **Suspended**: The thread is inactive and will not be scheduled until explicitly resumed.

### Context Switching
Is the process of storing the state of a currently running thread and restoring the state of the next thread to be executed by the CPU.