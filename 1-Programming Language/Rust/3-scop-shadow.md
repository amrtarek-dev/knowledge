# Rust Variables scope and shadowing
Any variable declared inside a function will be scoped only to its function, more generic rule: any variable declared inside { } curl braces.

``` rust
fn scope_and_shadowing()
{
    let a = 123;

    let a = 777; // this only allowed in Rust and a value will be the last one.
    {
        let b = 2;
        println!("b = {}", b);

        let a = 555;
        // a is shadowing the global variable a .
        println!("a = {}", a); // a = 555

    }

    // a is decleared here
    println!("a = {}", a); // a = 777
    // b is not decleared here
    println!("b = {}", b); // error "unresolved name 'b'
}
```

### GLobals

You have two ways to make a global variables in Rust
- using **const** keywoard
- using **static** keywoard

#### const
It does not reserve an address for the variable.

``` rust
const A_GLOBALE:u8 = 42; // has to have the type (can't be auto), and it has not address.
                         // It uses a text replacement wherever it is used.
                         
fn main()
{
    println!("{}", A_GLOBAL); // It will just replace the A_GLOBAL with 42.
}
```

#### static
It reserves an address for the variable.

``` rust
static A_GLOBAL:u8 = 42; // It has an address.
static mut B_GLOBAL:u8 = 10;
       
fn main()
{
    println!("{}", A_GLOBAL); // It will use the variable it self, so if it is mutable, it will be changed every were.
    unsafe
    {
        B_GLOBAL = 15;
        pritnln!("{}",  B_GLOBAL);
    }
}
```
The safety of the language will try to avoid you from doing a mutable global varible,
but you can promisse that you will be careful by adding the **unsafe** tag for the use of the variable.
