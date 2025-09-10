# Rust Operators
Rust arithmetics, bitwise, logical operators

## arithmetics

``` rust
fn operators()
{
    let mut a = 2+3*4; //  will be * (+)
    println!("{}", a);
    a = a + 1; // -- ++ , a++ is not supported
    a += 1; // -= += *= /= %=

    println!("reminder of 13 / 3 = {}", 13 % 3); // 1

    let a_cubed = i32::pow(a, 3); // a * a  * a
    println!(" a cubed = {}", a_cubed);

    let b = 2.5;
    let b_cubed = f64::powi(b, 3);
    let b_to_pi = f64::powf(b, std::f64::consts::PI);
    println!("{} cubed = {}, {}^pi = {}", b, b_cubed, b, b_to_pi);
    // 2.5 cubed = 15.625, 2.5^pi = 17.78956824426224
}
```

## bitwise operations
it is only availabel to the integers in Rust.

``` rust
let c = 1 | 2;           // | OR, & AND, ^ XOR, ! NOR
println!("1|2 = {}", c); // 01 OR 10 == 11 == 3 _10

let two_to_powr_10 =  1 << 10;
println!("2^10 = {}", two_to_powr_10); // 1024
```

## logical

``` rust
// < , <=, >, >=, ==, !=
let pi_less_4 = std::f64::consts::PI < 4.0: // true
let x = 5;
let x_is_5 = x == 5; // true
```
