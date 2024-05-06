---
id: 1324afaa-085a-401c-9757-df93b6c51423
title: Rust functions
---

# Functions

## Case

Rust uses [snake case](https://en.wikipedia.org/wiki/Snake_case) for
function and variable names. Functions always start with fn

``` rust
fn main() {
    println!("Hello, world!");

    another_function();
}

fn another_function() {
    println!("Another function.");
}
```

## Parameters

In rust you **must** declare parameter types

``` rust
fn main() {
    another_function(5);
}

fn another_function(x: i32) {
    println!("The value of x is: {}", x);
}
```

## Rust is expressive

Rust is an expressive language, so you have to do stuff like this:

``` rust
fn main() {
    let _x = 5;

    let y = {
        let x = 3;
        x + 1
    };

    println!("The value of y is: {}", y);
}
```

## Return values

Unless you add a return statement, most functions return the last
expression implicitly:

``` rust
fn five() -> i32 {
    5
}

fn main() {
    let x = five();

    println!("The value of x is: {}", x);
}
```
