---
publish: true
title: rustdoc
created: 2020-11-19T16:54:54
modified: 2026-08-05T07:58:56.708Z
---

# rustdoc

# Description

Rustdoc\[fn:rustdoc] is the built in library documentation tool included in the Rust distribution and allows you to write documentation in Markdown\[fn:markdown].

# Syntax

pub mod foo {
/// Some docs for `Foo`
///
/// You may want to use `Foo` with \[`Bar`].
///
/// \[`Bar`]: ../bar/struct.Bar.html
pub struct Foo;
}

pub mod bar {
/// Some docs for `Bar`
///
/// You may want to use `Bar` with \[`Foo`].
///
/// \[`Foo`]: ../foo/struct.Foo.html
pub struct Bar;
}

# Footnotes

\[fn:markdown]https://en.wikipedia.org/wiki/Markdown
\[fn:rustdoc]https://doc.rust-lang.org/rustdoc/index.html
