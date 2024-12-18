# Rust Variables
To make a variables in rust we need to use **let** keyword, by default the variable is immutable so you can't change its value once assigned, but you can use **mut** keyword to make it `mmutable`.


## Fundamental data types
These are the primitive data types.

### integers

we have i8, i16, i32, i64 for signed int, and 
        u8, u16, u32, u64 for unsigned int.

```rust
let a:u8 = 123; //8-bits -- unsigned 0..255 -- can't reassigned
println!("a = {}", a);
a = 2; // error
let mut b:i8 = 0;
b = 42;
println!("b = {}", b);
```
So **let** keyword here has bind the value 123 to memory name 'a',

You can avoid to write the i8, u8, and let the compiler automatic figure out the data type.

```rust
let mut a = 123456789; // 32-bit signed i32

```

To print the size of the variable you can use **std::mem** namespace

```rust
use std::mem;
let mut a = 123456789;
println!("a = {}, size = {} bytes", a , mem::size_of_val(&a));
```

### word size
we have isize and usize which is the word size in the memory or the pointer size, 
so in case of 32-bit system it will be 32-bit and 64-bit system it will be 64-bit.
Important use for usize and isize is as index of array or vector

```rust
let z:isize = 123; // word size
let size_of_z = mem::size_of_val(&z); // this will be in bytes
pritnln!("z = {}, takes up {} bytes, {}-bit OS", z, size_of_z, size_of_z * 8 );

let idx:usize = 0;
let a = [1,2,3];
println!("a[0] = {}", a[idx]);
// a[0] = 1
```

### character

```rust
let d:char = 'a'; // 4 bytes
let c = 'x';
```

### real numbers

we have f8, f16, f32, f64 for float
```rust
let e = 2.5; //8 bytes
```

### boolean
```rust
let g = false; // will print false
let g > 0;  // will print true
```

