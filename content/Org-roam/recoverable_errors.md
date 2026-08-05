---
publish: true
title: Rust Recoverable Errors
created: 2020-09-16T16:37:37
modified: 2026-08-05T10:26:50.513Z
---

# Rust Recoverable Errors

- [match](#match)
  - [Ditching match altogether](#ditching-match-altogether)
- [Panic on Error shortcuts](#panic-on-error-shortcuts)
  - [unwrap](#unwrap)
  - [expect](#expect)
- [Propagating Errors](#propagating-errors)

# match

In Rust we use the \[Rust Pattern Syntax]\(Rust Pattern Syntax) expression to check for errors in the \[\[https://doc.rust-lang.org/std/result/enum.Result.html]\[Result]]:

```rust
use std::fs::File;

fn main() {
    let f = File::open("hello.txt");

    let f = match f {
        Ok(file) => file,
        Err(error) => panic!("Problem opening the file: {:?}", error),
    };
}
```

Generally speaking you want to perform different actions depending on the error type:

```rust
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let f = File::open("hello.txt");

    let f = match f {
        Ok(file) => file,
        Err(error) => match error.kind() {
            ErrorKind::NotFound => match File::create("hello.txt") {
                Ok(fc) => fc,
                Err(e) => panic!("Problem creating the file: {:?}", e),
            },
            other_error => panic!("Problem opening the file: {:?}", other_error),
        },
    };
}
```

## Ditching match altogether

A more elegant way of writing the above:

```rust
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let f = File::open("hello.txt").unwrap_or_else(|error| {
        if error.kind() == ErrorKind::NotFound {
            File::create("hello.txt").unwrap_or_else(|error| {
                panic!("Problem creating the file: {:?}", error);
            })
        } else {
            panic!("Problem opening the file: {:?}", error);
        }
    });
}
```

# Panic on Error shortcuts

## unwrap

If the ~Result~ value is ~Ok~, \[\[https://doc.rust-lang.org/std/option/enum.Option.html#method.unwrap]\[unwrap]] will return the value inside the ~Ok~. If the ~Result~ is of the ~Err~ variant, unwrap will call the ~panic!~ macro

```rust
use std::fs::File;

fn main() {
    let f = File::open("hello.txt").unwrap();
}
```

## expect

\[\[https://doc.rust-lang.org/std/option/enum.Option.html#method.expect]\[expect]] is almost the same as unwrap, the only difference being that it allws us to choose the panic! error message:

```rust
use std::fs::File;

fn main() {
    let f = File::open("hello.txt").expect("Failed to open hello.txt");
}
```

# Propagating Errors

When you’re writing a function whose implementation calls something that might fail, instead of handling the error within this function, you can return the error to the calling code so that it can decide what to do. This is known as propagating the error and gives more control to the calling code, where there might be more information or logic that dictates how the error should be handled than what you have available in the context of your code.

```rust
#![allow(unused)]
fn main() {
    use std::fs::File;
    use std::io;
    use std::io::Read;

    fn read_username_from_file() -> Result<String, io::Error> {
        let f = File::open("hello.txt");

        let mut f = match f {
            Ok(file) => file,
            Err(e) => return Err(e),
        };

        let mut s = String::new();

        match f.read_to_string(&mut s) {
            Ok(_) => Ok(s),
            Err(e) => Err(e),
        }
    }
}
```

This can of course be refactored to something nicer:

```rust
#![allow(unused)]
fn main() {
    use std::fs::File;
    use std::io;
    use std::io::Read;

    fn read_username_from_file() -> Result<String, io::Error> {
        let mut f = File::open("hello.txt")?;
        let mut s = String::new();
        f.read_to_string(&mut s)?;
        Ok(s)
    }
}
```

And this can be refactored even more:

```rust
#![allow(unused)]
fn main() {
    use std::fs::File;
    use std::io;
    use std::io::Read;

    fn read_username_from_file() -> Result<String, io::Error> {
        let mut s = String::new();

        File::open("hello.txt")?.read_to_string(&mut s)?;

        Ok(s)
    }
}
```
