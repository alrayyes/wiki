---
publish: true
title: as_mut_ptr_range
created: 2020-11-20T10:10:47
---

# as\_mut\_ptr\_range

## Description

Returns the two unsafe mutable pointers spanning the slice.

The returned range is half-open, which means that the end pointer points one /past/ the last element of the slice. This way, an empty slice is represented by two equal pointers, and the difference between the two pointers represents the size of the slice.

This function is useful for interacting with foreign interfaces which use two pointers to refer to a range of elements in memory, as is common in C++.

## Declaration

```rust
pub fn as_mut_ptr_range(&mut self) -> Range<*mut T>
```

## Traits for Range<A>

```rust
impl<A> Iterator for Range<A> where
    A: Step,     type Item = A;
```

## Footnotes

https://doc.rust-lang.org/std/primitive.slice.html#method.as\_mut\_ptr\_range
