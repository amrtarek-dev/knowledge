# Rust Functions
When you need several operations to execute one after another we put these operations into a functions
## Function
The function is a block of code limited by curly braces, which contains a couple of instructions that can do by the machine.

To make a function in Rust you have to use the **fn** keyword then the function name then round brackets
```rust 
fn functions()
{
    
}
```

## Call a function
```rust
fn main() {
    functions();
}
```

## Arguments (By value)
It is the values that the functions take

``` rust
fn print_value(x: i32)
{
    println!("value = {}", x);
}

fn main()
{
    print_value(33);
    // value = 33
}
```

## Change Arguments (By reference)

``` rust
fn increase(x: &mut i32)
{
    *x += 1; // dereference  the x value
}

fn main()
{
    let mut z = 1;
    increase(&mut z);
}
```

## Return value
``` rust
fn product(x: i32, y: i32) -> i32
{
    x * y   // without the semicolone
}

fn main()
{
    let a = 3;
    let b = 5;
    let p = product(a, b);
    println!("{} * {} = {}", a, b, p);
}
```

## Methods
The method is a container function, so in rust, the container is the struct data type.

``` rust
struct Point
{
    x: f64,
    y: f64
}

struct Line
{
    start: Point,
    end: Point
}

impl Line
{
    fn len(&self) -> f64
    {
        let dx = self.start.x - self.end.x;
        let dy = self.start.y - self.end.y;
        (dx*dx + dy*dy).sqrt()
    }
}

fn methods()
{
    let p = Point { x: 3.0, y: 4.0};
    let p2 = Point { x: 5.0, y: 10.0};
    let myline = Line { start: p, end: p2 };

    println!("length = {}", myline.len());
}
```

## Closures
It is creating a function and store it in a variable

``` rust
fn say_hello() {println!("hello");}

fn main()
{
    let sh = say_hello;
    sh();
    // hello
}
```
The syntax for closure 
``` rust
fn closures()
{
    let plus_one = |x:i32| -> i32 { x + 1};
    let a = 6;
    println!("{} + 1 = {}", a, plus_one(a));

    let mut two = 2;
    {   // make scope for the closure
        let plus_two = |x|
        {
            let mut z = x;
            z += two;
            z
        };
        println!("{} + 2 = {}", 3, plus_two(3));
    }
    let barrow_two = &mut two;
}
```
