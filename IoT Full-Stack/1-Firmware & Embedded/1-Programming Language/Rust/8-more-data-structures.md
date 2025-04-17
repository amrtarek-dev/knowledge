# More Rust Data structures
Rust supports multiple types of data types here you are going to cover slice, strings, Tuples, pattern matching, and Generics

## slice
A slice is a part of an array, but its size is not known at compile time.

```rust
fn use_slice(slice: &mut [i32])
{
    slice[0] = 321;
    println!("first elem = {}, len = {}", slice[0], slice.len());
    // first elem = 321, len = 3
}
fn slices()
{
    let mut data = [1,2,3,4,5];
    use_slice(&mut data[1..4]);
    println!("{:?}, data");
    // [1, 321, 3, 4, 5]
}
```

## string
It is an vector of characters

```rust
fn strings()
{
    let s:&'static str = "hello there!"; // &str = string slice
    // s = "abc" // error can't reassigned
    // let h = s[0] // error

    // to get the characters
    for c in s.chars()
    {
        println!("{}", c);
    }

    // to check the first character
    if let Some(first_char) = s.chars().nth(0)
    {
        println!("first letter is {}", first_char);
    }

    // Another option is using String which is Heap allocated
    let mut letters = String::new(); // string construct
    let mut a = 'a' as u8;  // casting to u8
    while a <= ('z' as u8)
    {
        letters.push(a as char);
        letters.push_str(",");
        a += 1;
    }
    println!("{}", letters);
    // a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z

    // to convert between them
    let u:&str = &letters; // dereference conversion

    // Concatenation
    // String + str
    let z = letters + &letters;

    let mut abc = Stirng::from("hello world");
    let mut abc = "hello world".to_string();
    abc.remove(0); // will remove h
    abc.push_str("!!");
    println!("{}", abc.replace("ello", "Goodbye"));
    // Goodbye world !!
}
```

## Tuples
It is a combining of any data types. normally used with return from function.

```rust
fn sum_and_product(x:i32, y:i32) -> (i32, i32)
{
    (x+y, x*y)
}

fn tuples()
{
    let x = 3;
    let y = 4;
    let sp = sum_and_product(x,y);

    println!("sp = {:?}", sp);
    // sp = (7, 12)
    println!("{0} + {1} = {2}, {0} * {1} = {3}", x, y, sp.0. sp.1);
    // 3 + 4 = 7, 3 * 4 = 12

    // Destructuring
    let (a,b) = sp;
    println!("a = {}, b = {}", a, b);
    // a = 7, b = 12

    // Tuples of tuples
    let sp2 = sum_and_product(4,7);
    let compined = (sp, sp2);

    println!("{:?}", combined);
    // ((7,12),(11,28))
    println!("last elem = {}", (combined.1).1);
    //last elem = 

    let ((c,d),(e,f)) = combined;
    let foo = (true, 42.0, -1i8);
    println("{:?}", foo);
    // (true, 42, -1)
    
    let meaning = (42);
    println!("{:?}", meaning);
    // 42 -- this is not tuble
    let meaning = (42,);
    println!("{:?}", meaning);
    //(42,)  -- this is tuble
}

```

## Pattern Matching
How to use the pattern matching in rust

```rust

fn how_many(x:i32) -> &'static str
{
    match x
    {
        0 => "no",
        1 | 2 => "one or two",  // 1 or 2
        12 => "a dozen",
        z @ 9...11 => "lots of", // taged range, you can use z as a nornal variable
        _ if (x % 2 == 0) => "even", // conditional default
        _ => "few"
    }
}

fn tuples_match()
{
    let point = (3,4);
    
    match (point)
    {
        (0,0) => println!("origin"),
        (0,y) => println!("x axis, y = {}", y),
        (_,y) => println!("(?,{})", y),
        (x,0) => println!("y axis, x = {}", x),
        (x,y) => println!("({},{})", x, y)
    }
}
```

## Generics

like Option `<T>`

``` rust
struct Points<T,V>
{
    x: T,
    y: V
}

srtuct Point<T>
{
    x: T, y: T
}

struct Line<T>
{
    start: Point<T>,
    end: Point<T>
}

fn generics()
{
    let a: Points<u16, i32> = Points {x: 0, y: 4};
    let b: Points<f64, f64> = Points {x: 1.2, y: 3.4};

    let c: Point = Point {x: 1, y: 2};
    let d: Point = Point {x: 3, y: 4};
    let myline = Line{start:c, end: d};
}



```