---
id: 2a1d0b2f-9f23-4872-a83f-aa01a84756b5
title: Rust Unrecoverable Errors
---

# Unwinding vs Aborting

By default, when a panic occurs, the program starts *unwinding*, which
means Rust walks back up the stack and cleans up the data from each
function it encounters. But this walking back and cleanup is a lot of
work. The alternative is to immediately abort, which ends the program
without cleaning up. Memory that the program was using will then need to
be cleaned up by the operating system. If in your project you need to
make the resulting binary as small as possible, you can switch from
unwinding to aborting upon a panic by adding `panic = 'abort'` to the
appropriate `[profile]` sections in your *Cargo.toml* file. For example,
if you want to abort on panic in release mode, add this:

``` toml
[profile.release]
panic = 'abort'
```

# panic!

When doodie hits the fan and there's no way out, use the
[panic!](https://doc.rust-lang.org/std/macro.panic.html) macro:

``` rust
fn main() {
    panic!("crash and burn");
}
```
