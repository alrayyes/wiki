---
publish: true
title: Search Aliases
created: 2020-11-19T17:07:10
---

# Search Aliases

## Description

\~#\[doc(alias = "<alias>")]~ can be specified on items to add search aliases when searching through [[rustdoc]] UI. See the PR[^PR] for more information.

## Syntax

```rust
#[doc(alias = "bar")]
struct Foo;
```

## Footnotes

[^PR]: https://github.com/rust-lang/rust/pull/75740/
