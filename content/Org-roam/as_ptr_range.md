---
publish: true
title: as_ptr_range
created: 2020-11-20T09:57:39
modified: 2026-08-12T10:26:13.158Z
---

# as\_ptr\_range

## Description

as\_ptr\_range[^documentation] returns the two raw pointers spanning the slice.

The returned range is half-open, which means that the end pointer points one /past/ the last element of the slice. This way, an empty slice is represented by two equal pointers, and the difference between the two pointers represents the size of the slice.

This function is useful for interacting with foreign interfaces which use two pointers to refer to a range of elements in memory, as is common in C++.

## Declaration

```rust
pub fn as_ptr_range(&self) -> Range<*const T>
```

## Traits for Range<A>

```rust
impl<A> Iterator for Range<A> where
    A: Step,     type Item = A;
```

## Syntax

```rust
#![allow(unused)]
fn main() {
    let a = [1, 2, 3];
    let x = &a[1] as *const _;
    let y = &5 as *const _;

    assert!(a.as_ptr_range().contains(&x));
    assert!(!a.as_ptr_range().contains(&y));
}
```

## Footnotes

[^documentation]: https://doc.rust-lang.org/std/primitive.slice.html#method.as_ptr_range
