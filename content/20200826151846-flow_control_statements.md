---
id: db553cc1-625c-4ddf-8d3c-cc0bba7b4345
title: Golang flow control statements
---

# For

Go has no \`while\`, \`do\` or \`until\` keywords for iteration, only
\`for\`

``` go
package main

import "fmt"

func main() {
    sum := 0
    for i := 0; i < 10; i++ {
        sum += i
    }
    fmt.Println(sum)
}
```

Init and post statements are optional:

``` go
package main

import "fmt"

func main() {
    sum := 1
    for ; sum < 1000; {
        sum += sum
    }
    fmt.Println(sum)
}
```

For is Go's "while":

``` go
package main

import "fmt"

func main() {
    sum := 1
    for sum < 1000 {
        sum += sum
    }
    fmt.Println(sum)
}
```

Infinite loops are possible as well:

``` go
package main

func main() {
    for {
    }
}
```

Iterate over [Golang Arrays](20200828182327-arrays) & [Golang
slices](20200828182546-slices) with \`range\`:

``` go
package main

import (
    "fmt"
)

func main() {
    var numbers = []int{1,2,3,4,5}
    var sum = 0

    for _, number := range numbers {
        sum += number
    }

    fmt.Println("%s", sum)
}
```

# If

Like for, the if statement can start with a short statement to execute
before the condition.

Variables declared by the statement are only in scope until the end of
the if.

``` go
package main

import (
    "fmt"
    "math"
)

func pow(x, n, lim float64) float64 {
    if v := math.Pow(x, n); v < lim {
        return v
    }
    return lim
}

func main() {
    fmt.Println(
        pow(3, 2, 10),
        pow(3, 3, 20),
    )
}
```

Variables declared inside an if short statement are also available
inside any of the else blocks.

``` go
package main

import (
    "fmt"
    "math"
)

func pow(x, n, lim float64) float64 {
    if v := math.Pow(x, n); v < lim {
        return v
    } else {
        fmt.Printf("%g >= %g\n", v, lim)
    }
    // can't use v here, though
    return lim
}

func main() {
    fmt.Println(
        pow(3, 2, 10),
        pow(3, 3, 20),
    )
}
```

# Switch

Go's switch is like the one in C, C++, Java, JavaScript, and PHP, except
that Go only runs the selected case, not all the cases that follow. In
effect, the break statement that is needed at the end of each case in
those languages is provided automatically in Go. Another important
difference is that Go's switch cases need not be constants, and the
values involved need not be integers.

``` go
package main

import (
    "fmt"
    "runtime"
)

func main() {
    fmt.Print("Go runs on ")
    switch os := runtime.GOOS; os {
    case "darwin":
        fmt.Println("OS X.")
    case "linux":
        fmt.Println("Linux.")
    default:
        // freebsd, openbsd,
        // plan9, windows...
        fmt.Printf("%s.\n", os)
    }
}
```

Switch without a condition is the same as switch true. This construct
can be a clean way to write long if-then-else chains.

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    t := time.Now()
    switch {
    case t.Hour() < 12:
        fmt.Println("Good morning!")
    case t.Hour() < 17:
        fmt.Println("Good afternoon.")
    default:
        fmt.Println("Good evening.")
    }
}
```

Type switches are also a thing:

``` go
package main

import "fmt"

func do(i interface{}) {
    switch v := i.(type) {
    case int:
        fmt.Printf("Twice %v is %v\n", v, v*2)
    case string:
        fmt.Printf("%q is %v bytes long\n", v, len(v))
    default:
        fmt.Printf("I don't know about type %T!\n", v)
    }
}

func main() {
    do(21)
    do("hello")
    do(true)
}
```

# Defer

A defer statement defers the execution of a function until the
surrounding function returns. The deferred call's arguments are
evaluated immediately, but the function call is not executed until the
surrounding function returns.

``` go
package main

import "fmt"

func main() {
    defer fmt.Println("world")

    fmt.Println("hello")
}
```

Deferred function calls are pushed onto a stack. When a function
returns, its deferred calls are executed in last-in-first-out order.

``` go
package main

import "fmt"

func main() {
    fmt.Println("counting")

    for i := 0; i < 10; i++ {
        defer fmt.Println(i)
    }

    fmt.Println("done")
}
```
