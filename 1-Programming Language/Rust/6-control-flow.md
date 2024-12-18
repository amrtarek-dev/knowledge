# Rust Control flow
Rust Control flow if statement, while, loop, for, match.

## if statement

``` rust
fn if_statement()
{
    let temp = 35;
    if temp > 30
    {
        println!("really hot outside!");
    } else if temp < 10
    {
        println!("really called!");
    } else
    {
        println!("temperature is ok");
    }

    let day = if temp > 20 {"sunny"} else {"cloudy"};
    println!("today is {}", day); // will print sunny

    println!("is it {}", 
    if temp > 20 {"hot"} else if temp < 10 {"cold"} else {"OK"});

    println!("it is {}",
    if temp > 20 {
        if temp > 30 {"very hot"} else {"hot"}
    } else if temp < 10 {"cold"} else {"OK"});
}

```

## While and loop

``` rust
fn  while_and_loop()
{
    let mut x = 1;
    while x < 1000
    {
        x *=2;
        if x == 64 { continue; }
        println!("x is {}", x);
    }

    let mut y = 1;
    loop // while true (loop forever)
    {
        y *= 2;
        println!("y = {}", y);
        
        if y == 1<<10 { break; }
    }

}
```

## for

``` rust
fn for_loop()
{
    for x in 1..11 // x from 1 to 10
    {
        if x == 3 { continue; }
        if x == 8 { break; }
        println!("x = {}", x);
    }

    for (pos,y) in (30..41).enumerate() // (exclusive range)
    {
        println!("{}: {}", pos, y);
        // 0: 30
        // 1: 31
        // ...
        // 9: 39
        //10: 40
    }
}
```

## match
it is like swith case, but it will force you to cover all cases by default.

``` rust
fn match_statement()
{
    let country_code = 44;
    let country = match country_code
    {
        44 => "UK",
        46 => "Sweden",
        7  => "Russia",
        1...999 => "unknown", // any range from 1 to 999 (inclusive range)
        _  => "invalid" // Any other value.
    };

    println!("the country with code {} is {}", country_code, country);
    // the country with code 44 is UK
    // the country with code 777 is unknown
    // the country with code 999 is unknown
    // the country with code 5555 is invalid
}

