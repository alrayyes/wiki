---
publish: true
title: Golang Packages
created: 2020-08-26T14:27:55
modified: 2026-08-12T10:26:13.170Z
---

# Golang Packages

## Basics

Every Go program is made up of packages. Programs start running in package `main`.

By convention the pacckage name is the same as the last element of the import path. For instance, the `math/rand` package comprises files that begin with the statement `package rand`.

```go
package main

import (
	"fmt"
	"math/rand"
)

func main() {
	fmt.Println("My favorite number is", rand.Intn(10))
}
```

## Imports

It's best practice to convert multiple import statements to a "factored" import statement:

```go
package main

import "fmt"
import "math"

func main() {
	fmt.Printf("This uses multiple import statements\n")
	fmt.Printf("Now you have %g problems.\n", math.Sqrt(7))
}
```

should be

```go
package main

import (
	"fmt"
	"math"
)

func main() {
	fmt.Printf("This uses a parenthesized \"factored\" import statement\n")
	fmt.Printf("Now you have %g problems.\n", math.Sqrt(7))
}
```

## Exported names

In Go, a name is exported if it begins with a capital letter. When importing a package, you can refer only to its exported names. Any "unexported" names are not accessible from outside the package.
