# Rust Stack and Heap
How we can use stack and heap memory in rust

## Stack
it is the automatic allocation which happens when you use variables within scope, 
and automatic deallocation when the variable get out of the scope, and it saved in the RAM.

Use of the stack:
- local variable within function.
- functions arguments

```rust 
fn foo()
{
    let a:i32 = 10;
}

fn main()
{
    foo();
}
```

## Heap
It is the manual memory allocation which happens by the program, and deallocated by the program, 
and it saved in the RAM.

To use the heap in Rust you need to use **Box** namespace

```rust
fn main()
{
    let y = Box::new(10);
    // y (in stack) has the address of the value 10 (in heap)

    // so to get the y value
    println!("y = {}", *y);
}
```
The same idea used by vector type in rust

```rust
fn main()
{
    let z = vec![1,2,3];
    // z (in stack) has the address of the vec memory in the heap.
}
``` 

