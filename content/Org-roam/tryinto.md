---
publish: true
title: TryInto
created: 2020-11-19T17:12:45
modified: 2026-08-05T10:26:50.519Z
---

# TryInto

# Description

TryInto\[fn:documentation] is an attempted conversion that consumes self, which may or may not be expensive.

# Delcaration

pub trait TryInto<T> {
type Error;
fn try\_into(self) -> Result\<T, Self::Error>;
}

# Implementors

impl\<T, U> TryInto<U> for T
where
U: TryFrom<T>,

# Footnotes

\[fn:documentation]https://doc.rust-lang.org/std/convert/trait.TryInto.html
