---
publish: true
title: ready
created: 2020-11-20T11:11:57
modified: 2026-08-05T07:58:56.705Z
---

# ready

# Description

readcy\[fn:documentation] creates a future that is immediately ready with a value.

Futures created through this function are functionally similar to those created through ~async {}~. The main difference is that futures created through this function are named and implement ~Unpin~.

# Declaration

pub fn ready<T>() -> Ready<T>

# Notable traits

impl<T> Future for Ready<T>
type Output = T;

# Examples

use core::future;

let a = future::ready(1);
assert\_eq!(a.await, 1);

# Footnotes

\[fn:documentation]https://doc.rust-lang.org/std/future/fn.pending.html
