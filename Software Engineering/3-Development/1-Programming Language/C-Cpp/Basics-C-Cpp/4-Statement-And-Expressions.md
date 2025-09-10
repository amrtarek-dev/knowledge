# C and C++ Statement and Expressions
The C/C++ programming language consists mostly of expressions and statements. In fact, many statements are also expressions and vice versa.

## Statements
```c
#include <stdio.h>
int main(int argc, char ** argv) {
	printf("Hello, World!\n");
	return 0;
}
```

This program will output the constant string "Hello, World!", and every line that is ended with ; is called statement.
```c
printf("Hello, World!\n");
return 0;
```

## Expressions
But actually,
```c
printf("Hello, World!\n");
```
is also expression, because **printf** function is returning a value which is the number of the printed characters.
So let's assign it to a simple integer variable here.
```c
#include <stdio.h>
int main(int argc, char** argv) {
	int x = printf("Hello, World!\n");
	printf("printf retruned %d\n", x);
	return 0:
}
```
x = printf returns an integer value. 
So I can print that with another printf statement, So the output of this program will be
```bash
$ gcc hello.c
$ ./a.out
Hello, World!
printf returned 14
```
So that means the first printf has printed 14 characters.
So the expression is a unit of computation and every expression has a value.
the statement in another hand is a unit of execution and the statement is terminated by a ;

## Compound statement
when multiple statements are grouped together with curly braces. These are called **compound statements**. They're also sometimes called **blocks**.
```c
int main(int argc, char** argv) {
	int x = printf("Hello, World!\n");
	printf("printf retruned %d\n", x);
	return 0:
}
```

every curly braces defining a scope, we will know more about it in the coming topics.