---
publish: true
title: Rust Strings
created: 2020-09-15T15:13:58
---

## Description

The ~String~ type, which is provided by Rust’s standard library rather than coded into the core language, is a growable, mutable, owned, UTF-8 encoded string type. When Rustaceans refer to “strings” in Rust, they usually mean the ~String~ and the string slice ~\&str~ types, not just one of those types. Although this section is largely about ~String~, both types are used heavily in Rust’s standard library, and both ~String~ and string slices are UTF-8 encoded.

## Creating a New String

Many [[Rust Vectors]] are also available for Strings.

```rust
fn main() {
    let mut s = String::new();
}
```

### to\_string

To generate a ~String~ with initial data we can use the [to\_string](https://doc.rust-lang.org/std/string/trait.ToString.html#tymethod.to_string) method:

```rust
fn main() {
    let data = "initial contents";

    let s = data.to_string();

    // the method also works on a literal directly:
    let s = "initial contents".to_string();
}
```

### String::from

The same can be accomplished with ~String::from~:

```rust
fn main() {
    let s = String::from("initial contents");
}
```

## Updating a String

### push\_str

```rust
fn main() {
    let mut s = String::from("foo");
    s.push_str("bar");

    println!("s is {}", s)
}
```

### push

\~push~ adds a single character to a string:

```rust
fn main() {
    let mut s = String::from("lo");
    s.push('l');

    println!("s is {}", s)
}
```

## Concatentation

```rust
fn main() {
    let s1 = String::from("Hello, ");
    let s2 = String::from("world!");
    let s3 = s1 + &s2; // note s1 has been moved here and can no longer be used

    println!("s3 is {}", s3)
}
```

### Concatenate multiple strings

#### With +

```rust
fn main() {
    let s1 = String::from("tic");
    let s2 = String::from("tac");
    let s3 = String::from("toe");

    let s = s1 + "-" + &s2 + "-" + &s3;

    println!("s is {}", s)
}
```

#### With format!

```rust
fn main() {
    let s1 = String::from("tic");
    let s2 = String::from("tac");
    let s3 = String::from("toe");

    let s = format!("{}-{}-{}", s1, s2, s3);

    println!("s is {}", s)
}
```

## Iteration

### Chars

```rust
#![allow(unused)]
fn main() {
    for c in "नमस्ते".chars() {
        println!("{}", c);
    }
}
```

### Bytes

```rust
#![allow(unused)]
fn main() {
    for b in "नमस्ते".bytes() {
        println!("{}", b);
    }
}
```

```
224
164
168
224
164
174
224
164
184
224
165
141
224
164
164
224
165
135
```
