## Process
Linux process is an Executable object code that runs on the hardware, normally this object code is encapsulated in (ELF, Executable and Linkable Format)

So it is just a running program in memory.

For process the resources needed are allocated and managed by the kernel through system calls like Timers, Files, Hardware access, etc..

Every Process has a Process ID (pid), you can list is by `ps` command in shell, and every process has its own virtualised processor and virtualised view of memory, which appears to software as its own dedicated CPU/RAM, but it is time shared by the kernel.
### Process ID
every process has its unique pid which is allocated and reused by kernel.
- pid 0 = idle process (one per processor, handles power control)
- pid 1 = init process (initializes system, starts services, launches a login program)

### Start process
`execl()` it is a system call function to start a process, which is going to replace the current process with the new content.
So it will change everything in the current process and it will not return on success, but it will use the current pid, priority, owning user and group.

There is functions do the same with different arguments like:
- execlp(), execle()
- execv(), execvp(), execve()
Which uses different arguments or whether PATH is included.

`fork()` it will create a new process running the same images as the current process, and a new PID as a child process.
Often used to start Daemons (process running in the background)
- The kernel uses `copy on write` technique to do not duplicate the used memory, so when the parent or child process changes the memory then the process will get its own separate copy (memory is shared until modified).

### Zombie process
Happen when a child process dies before the parent, the parent process remains in zombie state until the parent is informed about child terminating.

And this happens when the parent did not waited for the child (did not used `wait()` to obtain information about terminated children),
Or the parent starts multiple children (it needs to wait for all of them).

So the right way to start process is combine (`exec() + fork() + wait()`) which will replacing a process with exec(), then launching a child process with fork() and waiting for completion with wait().

Or use `system()` which going to do all the thing for you but be aware that it will run in shell so it will expands the shell variables like `$HOME` and `$PATH`

``` c
#include <stdlib.h>
int system(const char *command);
```

Every process has a user and group you can change it by `setuid()` and `setgid()` and you can know it by `getuid()` and `getgid()` this will return the Real user and group (who started the process) and to get the effective user and group you can use `geteuid()` and `getegid()`
## PATH Variable
It tells the shell all different place it should search for executables, it is separated list of `:` to enable us call the executable by name rather than path.
``` bash
echo $PATH
```

> **PATH injection** is modifications to your PATH variable to `/home/hacker/ls` rather than `/usr/bin/ls` which will make the executable uses the hacker's one.
> The solution is not using the PATH, and use the absolute path to the executables


### Process Groups
It is a collection of processes

### Sessions
Session is a collection of process groups and it is associated with a controlling terminal `tty` (TeleTypewriter).
ex: A session is created for the login shell on a tty.
- There is only one single foreground process group in a session, but 0 or more background process groups (started with `command &`)

``` bash
ps aux
```
Will list all working processes, processes in brackets are the kernel processes

## Daemons
It is a process which runs in the background, and it does not connect to a controlling terminal.
- Normally it starts at boot time (child of `init`)
- Run as a root
- Often end with d in name.(sshd, crond)

### To create a Daemon
- fork(): to create a new child process which will become the daemon
- exit(): to close the parent process and let the (init) grandparent to continue.
- setsid(): to create a new session (to ensure there is no controlling tty)
- chdir to root (/): to avoid the current directory from being used by the deamon ( can not delete it if you need).
- redirect stdin, stdout, and stderr to /dev/null: to avoid printing to the terminal from the daemon, and use logging like syslog.
## Threads
The process is made of one or more threads, and the thread is a unit of activity within a process.

A process maybe a single-threaded or multithreaded.
Each Thread has its own:
- Stack - which stores local variables
- Processor state and current location
- Memory address space is shared between threads, but it is not shared between processes.


## Memory in Threads/Processes

Each process has its own virtual memory, but each thread inside process shares the same virtual memory and they accessing directly using synchronisation.

But sharing memory access between processes needs an **inter-process Communication (IPC)** 

### Linux Signals
It is a one-way asynchronous notifications sent from:
- kernel to process
- or one process to another process (IPC)
- or A process to itself
And you can handle the signal handlers to control how the process respond to a signal (Ctrl+C (SIGINT) (To stop a process).

### Signals Handlers
They must be a safe functions which are safe to call asynchronously.
- Do not use Global variables for example, because the process code can be interrupted at any time by signals

## IPC (Linux Interprocess Communication)
Allows process to exchange information without using a common global memory space.
Using these mechanism:
- Pipes
- Semaphores
- Message Queues
- Shared Memory