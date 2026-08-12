---
publish: true
title: Linking To Items By Name
created: 2020-11-19T17:02:37
modified: 2026-08-12T10:26:13.187Z
---

# Linking To Items By Name

## Description

[[rustdoc]] has syntax to specifiy that you're trying to link to a type, and it will generate URLs for you. No more relative linking with all the issues it brings.

## Syntax

### Pre 1.48

```rust
pub mod foo {
    /// Some docs for `Foo`
    ///
    /// You may want to use `Foo` with [`Bar`].
    ///
    /// [`Bar`]: ../bar/struct.Bar.html
    pub struct Foo;
}

pub mod bar {
    /// Some docs for `Bar`
    ///
    /// You may want to use `Bar` with [`Foo`].
    ///
    /// [`Foo`]: ../foo/struct.Foo.html
    pub struct Bar;
}
```

### 1.48

```rust
pub mod foo {
    /// Some docs for `Foo`
    ///
    /// You may want to use `Foo` with [`Bar`](crate::bar::Bar).
    pub struct Foo;
}

pub mod bar {
    /// Some docs for `Bar`
    ///
    /// You may want to use `Bar` with [`crate::foo::Foo`].
    pub struct Bar;
}
```

## External documentation

- Linking to items by name[^linking]
- Feature history[^history]

## Footnotes

[^history]: https://blog.rust-lang.org/inside-rust/2020/09/17/stabilizing-intra-doc-links.html

[^linking]: https://doc.rust-lang.org/stable/rustdoc/linking-to-items-by-name.html
