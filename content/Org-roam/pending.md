---
publish: true
title: pending
created: 2020-11-20T11:08:42
---

# pending

## Description

pending[^documentation] creates a future which never resovles, representing a computation that never finishes.

## Declaration

```rust
pub fn pending<T>() -> Pending<T>
```

## Notable traits

```rust
impl<T> Future for Pending<T>
    type Output = T;
```

## Examples

```rust
use core::future;

let future = future::pending();
let () = future.await;
unreachable!();
```

## Footnotes

[^documentation]: https://doc.rust-lang.org/std/future/fn.pending.html
