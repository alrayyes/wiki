---
id: f739a5a0-36a6-4a06-8890-91ec5fa84585
title: Linking To Items By Name
---

# Description

[rustdoc](20201119165454-rustdoc) has syntax to specifiy that you're
trying to link to a type, and it will generate URLs for you. No more
relative linking with all the issues it brings.

# Syntax

## Pre 1.48

``` rust
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

## 1.48

``` rust
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

# External documentation

-   Linking to items by name[^1]
-   Feature history[^2]

# Footnotes

[^1]: <https://doc.rust-lang.org/stable/rustdoc/linking-to-items-by-name.html>

[^2]: <https://blog.rust-lang.org/inside-rust/2020/09/17/stabilizing-intra-doc-links.html>
