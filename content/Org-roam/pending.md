---
publish: true
title: pending
created: 2020-11-20T11:08:42
modified: 2026-08-05T07:58:56.701Z
---

# pending

# Description

pending\[fn:documentation] creates a future which never resovles, representing a computation that never finishes.

# Declaration

pub fn pending<T>() -> Pending<T>

# Notable traits

impl<T> Future for Pending<T>
type Output = T;

# Examples

use core::future;

let future = future::pending();
let () = future.await;
unreachable!();

# Footnotes

\[fn:documentation]https://doc.rust-lang.org/std/future/fn.pending.html
