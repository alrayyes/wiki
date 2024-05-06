---
id: 9a604084-80a1-4868-be7b-950e7f43b65d
title: Rust variables
---

# Mutability

By default variables in Rust are immutable. To make a variable mutable
one must explicity add \`mut\` in front of it

``` rust
fn main() {
    let mut x = 5;
    println!("The value of x is: {}", x);
    x = 6;
    println!("The value of x is: {}", x);
}
```

# Constants

Constatns are values that are bound to a name and are not allowed to
change. Some differences with variables:

-   You can't use \`mut\` with constants
-   Constants are delared with \`const\` keyword instead of \`let\`
-   Type value must be annotated
-   Constants can be declared in any scope
-   Constants may only be set to a constant expression, not the result
    of a function call of any other value that could only be computed at
    runtime

``` rust
#![allow(unused_variables)]
fn main() {
const MAX_POINTS: u32 = 100_000;
}
```

# Shadowing

You can declare a new variable with the same value as a previous
variable. The new variable "shadows" the previous variable

``` rust
fn main() {
    let x = 5;

    let x = x + 1;

    let x = x * 2;

    println!("The value of x is: {}", x);
}
```

Shadowing is different from marking a variable as mut, because we’ll get
a compile-time error if we accidentally try to reassign to this variable
without using the let keyword. By using let, we can perform a few
transformations on a value but have the variable be immutable after
those transformations have been completed.

The other difference between mut and shadowing is that because we’re
effectively creating a new variable when we use the let keyword again,
we can change the type of the value but reuse the same name. For
example, say our program asks a user to show how many spaces they want
between some text by inputting space characters, but we really want to
store that input as a number:

``` rust
fn main() {
    let spaces = "   ";
    let spaces = spaces.len();

    println!("There are {} spaces in the string", spaces)
}
```

# Data types

## Tuple

Tuple elements can be accessed directly by using a period.

``` rust
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);

    println!("These are the tuple values {} {} {}", tup.0, tup.1, tup.2)
}
```

## Array

In Rust every element of an array must have the same type. They also
have a fixed length, like tuples.

``` rust
fn main() {
    let _a = [1, 2, 3, 4, 5];
}
```

You would write an array’s type by using square brackets, and within the
brackets include the type of each element, a semicolon, and then the
number of elements in the array, like so:

``` rust
#![allow(unused_variables)]
fn main() {
    let a: [i32; 5] = [1, 2, 3, 4, 5];
}
```

You can also easily initialize an array that contains the same value for
each element:

``` rust
#![allow(unused_variables)]
fn main() {
    let a = [3; 5];
}
```

Accessing array elements is also straightforward:

``` rust
#![allow(unused_variables)]
fn main() {
    let a = [1, 2, 3, 4, 5];

    let first = a[0];
    let second = a[1];
}
```

## Destructuring

Rust also supports destructuring

``` rust
fn main() {
    let tup = (500, 6.4, 1);

    let (x, y, z) = tup;

    println!("The value of x is: {}", x);
    println!("The value of y is: {}", y);
    println!("The value of z is: {}", z);
}
```
