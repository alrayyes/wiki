---
publish: true
title: Rust Closures
created: 2020-09-23T14:40:22
modified: 2026-08-12T09:44:58.348Z
---

# Rust Closures

## Syntax

### Long

```rust
fn main() {
    let double_closure = |num: u32| -> u32 { 2 * num };

    println!("2 times 3 = {}", double_closure(3));
}
```

### Abbreviated

```rust
fn main() {
    let double_closure = |num| 2 * num;

    println!("2 times 3 = {}", double_closure(3));
}
```

## Closure variable scope

Unlike [[Rust functions]] Closures can capture their environment and access variables from the scope in which they're defined:

```rust
fn main() {
    let x = 4;

    let equal_to_x = |z| z == x;

    let y = 4;

    assert!(equal_to_x(y));
}
```
