System programming or system software it is a software that interfacing with the kernel or C library, like GUI, compiler, debugger, web server, database.
Using:
- System Calls (syscalls)
- C Library (libc)
- C Compiler/linker (toolchain)

## Application Vs System software
Application software/ programming uses higher level libraries, and less OS/hardware details. (it is abstracted)

## System Calls (syscalls)
It calls the kernel function invocations from user space (read() write()) Roughly 300 total.
They shared subset of  ~90% implemented by all architectures on linux.

## C Library (libc)
GNU libc (glibc) wrappers for system calls, threading support and applications.

## C Compiler/linker (toolchain)
GCC (GNU C compiler)

## Why system calls
because it is not possible to link your user space application with the linux kernel. (for security and reliability reasons).

So the User space applications calls Posix API library, and then Posix uses trap (a software interrupt) to call Kernel Space.

## API
API is Application Programming Interface, the software that is providing the API is the implementation, which ensure compatibility.
Enables Source can be compiled for different platforms, to work any where as long as it is compiled to the interface.(Portable)
Ex:
C library functions like printf(), strcpy(), etc.., there is exceptions of ~10% of the syscall depend on the architecture.

## ABI
ABI is Application Binary Interface it is talking about binary compatibility, like calling conventions, byte ordering or register use.
It defines and implemented by the kernel and the toolchain, and it defines application interaction with itself, libraries and the kernel

Binary generated after compilation/link (by toolchain) and it is the byte code specific for a hardware types, software/compiler/library revisions, which requires: hardware, software libraries (especially glibc) and compiler

## POSIX
It is a C APIs for Unix-like operating systems, which stands for Portable Operating System Interface, and it had beed standard by IEEE in the late 1980s, as a way to coalesce the "Unix Wars".
Then Open Software Foundation created the Single Unix Specification (SUS) which was free and eventually incorporated the POSIX standard

It defines C code API for many concepts: <stdio.h>, <stdint.h>
- File and directory operations
- Clocks and timers
- Semaphores
- Shared memory
- Threads


## Error handling
Errno and error handling
C library mechanism for reporting errors is errno `<errno.h>`
You can list the errors list by 
``` bash
errno -l
```

EPERM 1 Operation not permitted
ENOENT 2 No such file or directory

``` C
int main () {
	const char *filename = "non-exitsting-file.txt";
	FILE *file = fopen(filename, "rb");
	if (file == NULL) {
		fprintf(stderr, "Value of errno attempting to open file %s: %d\n", filename, errno);
		perror("error returned");
		fprintf(stderr, "Error opening file %s: %s\n", filename, strerror( errno));
	}else{
		fclose(file);
	}
	return 0;
}
```
The output is:
``` bash
Value of errno attempting to open file non-existing.file.txt: 2
perror returned: No such file or directory
Error opening file non-existing-file.txt: No such file or directory
```


> Errno is thread safe.