---
publish: true
title: ready
created: 2020-11-20T11:11:57
modified: 2026-08-12T09:44:58.347Z
---

# ready

## Description

readcy[^documentation] creates a future that is immediately ready with a value.

Futures created through this function are functionally similar to those created through ~async {}~. The main difference is that futures created through this function are named and implement ~Unpin~.

## Declaration

```rust
pub fn ready<T>() -> Ready<T>
```

## Notable traits

```rust
impl<T> Future for Ready<T>
    type Output = T;
```

## Examples

```rust
use core::future;

let a = future::ready(1);
assert_eq!(a.await, 1);
```

## Footnotes

[^documentation]: https://doc.rust-lang.org/std/future/fn.pending.html
