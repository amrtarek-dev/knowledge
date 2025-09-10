# C and C++ program style

C and C++ program style is the same, so they are using the same syntax and rules.
Another thing you need to know about C is that all this white space is really just there for decoration. It makes the program readable.
```c
// hello.c
#include <stdio.h>
int main( int argc, char ** argv ) {
	printf("Hello, World!\n");
	return 0;
}
```
## White spaces

In other words, We can get rid of these indents and it'll still run just fine.
In fact, we can get rid of all of the white space. except in a few places where it's required.
```c
#include <stdio.h>
int main(int argc,char**argv){printf("Hello, World!\n");return 0;}
```
Obviously it's required between the return and the zero because otherwise you'd be no way to know that these are two different tokens. Likewise, between int and main, but every place else when we need it between **int** and **argc**.
So this. is a perfectly valid C program. I'm gonna save that and we'll compile it and run it and you see it runs just fine. 
Of course, this is not **very readable**. So the reason we have all of these spaces and the indents is to make the code readable. 

## C Writing Style
Now there's different styles of doing this. Some people like to put the curly braces on lines by themselves.
```c
#include <stdio.h>
int main(int argc, char** argv)
{
	return 0;
}
```

Some people like to indent one or both of the curly braces.
```c
#include <stdio.h>
int main(int argc, char** argv)
	{
	return 0;
	}
```

Whatever style you choose just be consistent that style. 
There's no one right way. Of course, if you work with other people, it's often times useful for everybody to agree on a particular style and to stick to that style. 

I tend to use the old K & R style because it's the 1st one that I learned from the original C programming book that came out in the 70s by **Kernighan** and **Richie** often called **K&R**. 
```c
#include <stdio.h>
int main( int argc, char ** argv ) {
	printf("Hello, World!\n");
	return 0;
}
```
So I tend to use a style like that, which is what you see here, but it's not the best. There is no best. The only thing that matters is that you're consistent and that you use the same style consistently so that you can read your code and so that other people can read your code.