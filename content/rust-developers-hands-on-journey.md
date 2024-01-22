+++
title = "Learning Rust: A Developer's Hands-On Journey"
date = 2024-01-22

[taxonomies]
categories = ["Learning"]
tags = ["Rust"]

+++

# Learning Rust: A Developer's Hands-On Journey

Let's dive into coding with the quintessential "Hello, World!" program. <!-- more -->

Before we go further, let's talk about cargo. It's Rust's package manager and build system, bundled into one. With cargo, we'll be managing dependencies, building projects, and more. But for now, we've used it to run our simple program. We can create new Rust project by using **cargo new** command

```bash
$ cargo new hello_cargo
$ cd hello_cargo
```

The first command creates a new directory and project called hello_cargo. We’ve named our project hello_cargo, and Cargo creates its files in a directory of the same name.

You can learn more about cargo [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)

```rust
fn main() {
    println!("Hello, Rust World!");
}
```

Save the file and head to your terminal. Navigate to the directory containing your Rust file and type:

```bash
$ cargo run
```

Behold! Your first Rust program is alive and kicking. The println! macro is Rust's way of printing to the console, and the semicolon at the end of the line indicates the end of the statement.



## Exploring Rust Syntax: Variables 

Let's take a closer look at Rust's syntax by exploring variables. In Rust, variables are immutable by default, promoting a safer coding practice. Let's declare a variable and see what Rust has to offer:

```rust
fn main() {
    let my_variable = 42;  // Immutable variable
    println!("The value of my variable is: {}", my_variable);

    // Uncomment the line below to see Rust's reaction to a mutable variable
    // my_variable = 24;  // This will throw an error since my_variable is immutable
}
```
Run this code with cargo run. Notice that if you try to reassign a value to my_variable, Rust will complain. You can make it mutable by using the mut keyword:
```rust
fn main() {
    let mut my_variable = 42;  // Mutable variable
    println!("The value of my variable is: {}", my_variable);

    my_variable = 24;  // This works now
    println!("Now it's: {}", my_variable);
}
```

## Ownership Concepts: A Deeper Dive

As we progress in our Rust journey, it's crucial to understand ownership concepts. Rust's ownership system ensures memory safety without a garbage collector. The concepts of ownership, borrowing, and lifetimes can be a bit tricky at first, but they play a pivotal role in writing safe and efficient code.

Here's a brief overview:

- **Ownership:** Each value in Rust has a variable that is its "owner." There can only be one owner at a time. When the owner goes out of scope, Rust will clean up the memory.
- **Borrowing:** Rather than transferring ownership, Rust allows you to borrow references to a value. Borrowing can be either mutable or immutable, and it's enforced at compile time.
- **Lifetimes:** Lifetimes ensure that references in Rust are valid and don't lead to dangling pointers. They specify the scope for which a reference is valid.

Let's briefly touch on borrowing:

```rust
fn main() {
    let original_value = String::from("Hello, Rust!");
    let borrowed_value = borrow_string(&original_value);

    println!("Original value: {}", original_value);
    println!("Borrowed value: {}", borrowed_value);
}

fn borrow_string(s: &String) -> String {
    // Do something with the borrowed reference
    // We're not allowed to modify s, just read from it

    s.clone()  // Return a new String, since we can't return a reference to the original String
}
```
This function borrow_string borrows a reference to a String. Notice that we had to clone the string before returning it because we can't return a reference to the original string due to Rust's ownership rules.

## Cargo: More Than Just a Build Tool

Now that we've been using `cargo` to run our programs, let's explore some more of its capabilities. With `cargo`, you can:

- **Build Your Project:** Use `cargo build` to compile your code. The resulting binary will be in the `target/debug` directory.
- **Run Tests:** Add tests to your code and run them with `cargo test`.
- **Create a Release Build:** Optimize your code for release with `cargo build --release`. The resulting binary will be in the `target/release` directory.

## Wrapping Up

Phew! That was quite a bit to digest, but Rust rewards us with a robust and safe programming environment. As we proceed further into the Rust's realm, we'll encounter more challenges and triumphs. Until next time, happy coding!