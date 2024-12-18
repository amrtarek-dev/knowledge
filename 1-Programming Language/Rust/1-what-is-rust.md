# What is Rust and how to start?

Rust is a modern systems programming language known for its focus on memory safety and performance. It combines low-level control with high-level abstractions, making it suitable for a wide range of applications.

It provides memory safety without the need for garbage collection and allows fine-grained control over system resources. Rust's syntax is similar to C/C++, making it familiar to developers with experience in those languages.

To start with Rust, follow these steps:

## Install Rust

Visit the official Rust website at [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install) and follow the instructions to install Rust on your system. The installation process is straightforward and includes the Rust compiler **(rustc)** and the package manager and build tool called **Cargo**.

Or you can use the Rust online compiler at [https://play.rust-lang.org](https://play.rust-lang.org)

## Hello Rust

Let's start with a simple "Hello, Rust!" example. open your preferred code editor and put the below code in it then save it as file with the name **hello.rs**:

```rust
fn main()
{
    println!("Hello, Rust!");
}
```
To compile the above **crate**, you have two options:
- Using the rustc (rust compiler)
- Using Cargo

But first, let's know what is **crate**

### Crates
hello.rs file called **crate**, it is like a module in C/C++, a crate can be compiled into a binary or a library.

## 1. Rust compiler
Rustc is the compiler that compiles the rust file "hello.rs" to a native runnable file (executable) e.g "hello.exe".
by running
```bash
rustc hello.rs
```

By default, **rustc** will produce a binary from a crate, and it can be edited by **--crate-type** flag to **lib**.
```bash
rustc --crate-type=lib hello.rs
# this will create: libhello.rlib file
```


## 2. Rust Cargo

Cargo is Rust's build system and package manager. To use Cargo, create a new file called Cargo.toml. 
TOML (Tom's Obvious Minimal Language) is a simple format used to specify project configurations.

In **Cargo.toml**, you can specify the project's name, version, and authors:

```toml
[package]
name = "hello_world"
version = "0.0.1"
authors = ["Amr <info@varapps.com>]
```

after making this file you can just run the project by:
``` bash
cargo build
```

This command will create a target directory with a debug folder, containing the compiled executable.

To run the executable using cargo you can run this command:
``` bash
cargo run
```
If the project hasn't been compiled yet, this command will compile it before running.

You can also create a new Rust project with Cargo using the following command:
```bash
cargo new hello_world --bin
```
This will create a new project called **hello_world**, configured as a binary project.


With the basic setup in place, you can continue exploring Rust's features and syntax. Rust has an extensive standard library that provides many useful functionalities. You can also explore Rust's documentation, community resources, and online tutorials to deepen your understanding and learn advanced concepts.