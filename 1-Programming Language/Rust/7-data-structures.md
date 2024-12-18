# Rust Data structures
Rust supports multiple types of data types here you are going to cover struct, enums, Option, Arrays, and Vectors

## struct

``` rust
// struct of primitive types
struct Point
{
    x: f64,
    y: f64
}

// struct of structs
struct line
{
    start: Point,
    end: Point
}

fn structures()
{
    let p = Point { x: 3.0, y: 4.0};
    println!("point p is at ({}, {})", p.x, p.y);
    // point p is at (3.0, 4.0)

    let p2 = Point { x: 5.0, y: 10.0 };

    let myline = Line { start: p, end: p2 };
    println!("Myline starts at ({}, {}) and ends at ({}, {})",
            myline.start.x, myline.start.y, myline.end.x, myline.end.y);
    // Myline starts at (3.0, 4.0) and ends at (5.0, 4.0)
}
```

## Enums
Enums is a data structures hold integers, by default starts by 0
```rust
enum Color
{
    Red,
    Green,
    Blue,
    RGBColor(u8, u8, u8),  // tuple format, you can't give them names.
    RGBAColor{red:u8, green:u8, blue:u8, alpha:u8}  // struct format
}

fn enums()
{
    let c:Color = Color::Red;
    // this will check for c variable
    // let c:Color = Color::RGBColor(0,0,0);
    // let c:color = Color::RGBAColor{red: 0, green: 255, blue:0, alpha:255};
    match c
    {
        // if it has Red color
        Color::Red => println!("Red"),
        Color::Green => println!("Green"),
        Color::Blue => println!("Blue"),
        Color::RGBColor(0,0,0) => println!("Black"),
        Color::RGBColor(r,g,b) => println!("rgb({},{},{})", r,g,b),
        Color::RGBAColor{red:_, green:_, blue:_, alpha:0} => println!("black"),
        _ => () // this to catch the rest of matches and do nothing :).
    }
}
```

## Option `<T>`
**Option** data type is a special type from enum, which defined like
``` rust
pub enum Option<T> {
    None,
    Some(T),
}
```
Which means it has only two values:
- **None** which represent that there is no value.
- **Some(T)** which represent that there is a value with type **T** which can take any type.

We can use this data structure in case there are two value for return or for a variable (None for no value), and Some(data) for any other data.
```rust
let a = None;  // a has None
let b = Some(10); // b Has data type called Some of 10 Some(10)
```
A function return or not returning.
```rust
fn option()
{
    let x = 3.0;
    let y = 2.0;

    let result:Option<f64> = 
        if y != 0.0 {Some(x/y)} else {None};
    
    // {:?} called debug kind
    println!("{:?}", result);
    // Soms(1.5)
    
    match result
    {
        Some(z) => println!("{}/{} = {}", x, y, z),
        None => println!("cannot divide {} by {}", x, y)
    }
    // 3.0/2.0 = 1.5

    if let Some(z) = result { println!("z = {}", z); }
    // z = 1.5
}
```

## Arrays
Arrays is a fixed length container for the same data type

```rust
use std::mem;

fn arrays()
{
    let mut a:[i32;5] = [1,2,3,4,5];

    println!("a has {} elements, first is {}", a.len(), a[0]);
    a[0] = 321;
    println!("a[0] = {}", a[0]);
    // a[0] = 321
    println!("{:?}", a);
    // [321, 2, 3, 4, 5]

    if a == [321, 2, 3, 4, 5]
    {
        println!("match");
    }

    let b = [1u16; 10]; 
    for i in 0..b.len()
    {
        println!("{}", b[i]);
        // 1
        // 1
        // 1
        // ...  ten times
        // 1
    }
    println!("b took up {} bytes", mem::size_of_val(&b));
    // b took up 20 bytes

    let mtx:[[f32;3]; 2] = 
    [
        [1.0, 2.0, 3.0],
        [4.0, 5.0, 6.0]
    ];
    println!("{:?}", mtx);
    // [[1, 2, 3], [4, 5, 6]]

    for i in 0..mtx.len()
    {
        for j in 0..mtx[i].len()
        {
            // print the diagonal
            if i == j
            {
                println!("mtx[{}][{}] = {}", i, j, mtx[i][j]);
                // mtx[0][0] = 1
                // mtx[1][1] = 5
            }
        }
    }
}
```

## Vectors
It is a dynamic length array and treated as Stack memory

```rust
fn vectors()
{
    //It must be mutable
    let mut a = Vec::new();
    a.push(1);
    a.push(2);
    a.push(3);
    println!("a = {:?}", a);
    // a = [1, 2, 3]

    let idx:usize = 0;
    a[idx] = 312;
    println!("a[0] = {}", a[idx]);
    // a[0] = 312

    println!("a[11] = {}", a[11]); // Panic, this is out of boundaries
    // to make a safe access to vector use get()

    match a.get(3) // return Option<T>
    {
        Some(x) => println!("a[3] = {}", x),
        None => println!("error, no such element")
    }

    // to remove element from Vec use pop()
    let last_elem = a.pop();  // return Option<T>
    println!("last elem is {:?}, a = {:?}", last_elem, a);
    // last elem is Soms(3), a = [312, 2, 3]

    while let Some(x) = a.pop()
    {
        println!("{}", x);
        // 312
        // 2
        // 3
    }
}
```


