---
publish: true
title: Rust control flow
created: 2020-08-27T19:04:43
modified: 2026-08-05T10:26:50.514Z
---

# Rust control flow

- [Branching](#branching)
  - [If](#if)
- [Loops](#loops)
  - [Loop](#loop)
  - [While](#while)
  - [For](#for)

# Branching

## If

```rust
fn main() {
    let number = 3;

    if number < 5 {
        println!("condition was true");
    } else {
        println!("condition was false");
    }
}
```

Because Rust is expressive we can use an `if` expression on the right side of a `let` statement:

```rust
fn main() {
    let condition = true;
    let number = if condition { 5 } else { 6 };

    println!("The value of number is: {}", number);
}
```

# Loops

## Loop

This will loop forever

```rust
fn main() {
    loop {
        println!("again!");
    }
}
```

Loops can also return values:

```rust
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2;
        }
    };

    println!("The result is {}", result);
}
```

## While

Rust also supports while loops:

```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{}!", number);

        number -= 1;
    }

    println!("LIFTOFF!!!");
}
```

## For

For loops are supported as well

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];

    for element in a.iter() {
        println!("the value is: {}", element);
    }
}
```
