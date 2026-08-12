---
publish: true
title: TryInto
created: 2020-11-19T17:12:45
modified: 2026-08-12T09:32:15.640Z
---

# TryInto

## Description

TryInto[^documentation] is an attempted conversion that consumes self, which may or may not be expensive.

## Delcaration

```rust
pub trait TryInto<T> {
    type Error;
    fn try_into(self) -> Result<T, Self::Error>;
}
```

## Implementors

```rust
impl<T, U> TryInto<U> for T
where
    U: TryFrom<T>,
```

## Footnotes

[^documentation]: https://doc.rust-lang.org/std/convert/trait.TryInto.html
