---
publish: true
title: Rust Comments
created: 2020-08-27T19:00:35
modified: 2026-08-12T10:31:55.426Z
---

# Rust Comments

## Basics

In Rust, the idiomatic comment style starts a comment with two slashes, and the comment continues until the end of the line. For comments that extend beyond a single line, you’ll need to include // on each line, like this:

```rust
// So we’re doing something complicated here, long enough that we need
// multiple lines of comments to do it! Whew! Hopefully, this comment will
// explain what’s going on.
```

Comments can also be placed at the end of lines containing code:

```rust
fn main() {
    println!("tralala") // This prints something
}
```

But if you're a sane person you'll comment above the code you're annotating

```rust
// This prints something
fn main() {
    println!("tralala")
}
```

## Documentation comments

### ///

This is like phpdoc, but for Rust. Documentation comments use three slashes ~///~ and support Markdown notation:

````rust
/// Adds one to the number given.
///
/// # Examples
///
/// ```
/// let arg = 5;
/// let answer = my_crate::add_one(arg);
///
/// assert_eq!(6, answer);
/// ```
pub fn add_one(x: i32) -> i32 {
    x + 1
}
````

Run src\_shell{cargo doc} to generate HTML documentation from the comments. src\_shell{cargo doc --open} will open documentation in the browser.

#### Commonly used sections

##### Panics

The scenarios in which the function being documented could panic. Callers of the function who don’t want their programs to panic should make sure they don’t call the function in these situations.

##### Errors

If the function returns a ~Result~, describing the kinds of errors that might occur and what conditions might cause those errors to be returned can be helpful to callers so they can write code to handle the different kinds of errors in different ways.

##### Safety

If the function is ~unsafe~ to call, there should be a section explaining why the function is unsafe and covering the invariants that the function expects callers to uphold.

### //!

This is used for general comments:

````rust
//! # My Crate
//!
//! `my_crate` is a collection of utilities to make performing certain
//! calculations more convenient.

/// Adds one to the number given.
// --snip--
///
/// # Examples
///
/// ```
/// let arg = 5;
/// let answer = my_crate::add_one(arg);
///
/// assert_eq!(6, answer);
/// ```
pub fn add_one(x: i32) -> i32 {
    x + 1
}
````

## Changes

- [[Linking To Items By Name]]
- [[Search Aliases]]
