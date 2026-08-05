---
publish: true
title: Golang Functions
created: 2020-08-26T15:13:37
modified: 2026-08-05T07:58:56.683Z
---

# Golang Functions

- [Arguments](#arguments)
  - [Basics](#basics)
  - [Variadic](#variadic)
- [Returns](#returns)
  - [Multiple results](#multiple-results)
  - [Named return values](#named-return-values)
  - [Function values](#function-values)
  - [Function closures](#function-closures)
- [Implementing an Interface](#implementing-an-interface)

# Arguments

## Basics

A function can take zero or more arguments. \[\[https://blog.golang.org/declaration-syntax]\[Argument type comes after the variable name]].

```go
package main

import "fmt"

func add(x int, y int) int {
	return x + y
}

func main() {
	fmt.Println(add(42, 13))
}
```

When two or more consecutive named function parameters share a type, you can omit the type from all but the last

```go
package main

import "fmt"

func add(x, y int) int {
	return x + y
}

func main() {
	fmt.Println(add(42, 13))
}
```

## Variadic

Go also supports \[\[https://gobyexample.com/variadic-functions]\[variadic functions]], ie functions with any number of trailing arguments:

```go
package main

import "fmt"

func sum(nums ...int) {
    fmt.Print(nums, " ")
    total := 0
    for _, num := range nums {
        total += num
    }
    fmt.Println(total)
}

func main() {

    sum(1, 2)
    sum(1, 2, 3)

    nums := []int{1, 2, 3, 4}
    sum(nums...)
}
```

# Returns

## Multiple results

A function can return any number of results

```go
package main

import "fmt"

func swap(x, y string) (string, string) {
	return y, x
}

func main() {
	a, b := swap("hello", "world")
	fmt.Println(a, b)
}
```

## Named return values

Go's return values may be named. If so, they are treated as variables defined at the top of the function. These names shoudl be used to document the meaning of the return values. A `return` statement without arguments returns the named return values. This is known as a "naked" return. Naked return statements should be used only short functions as they can harm readability in longer functions.

```go
package main

import "fmt"

func split(sum int) (x, y int) {
	x = sum * 4 / 9
	y = sum - x
	return
}

func main() {
	fmt.Println(split(17))
}
```

## Function values

Like in [JavaScript](JavaScript) functions can be passed around

```go
package main

import (
	"fmt"
	"math"
)

func compute(fn func(float64, float64) float64) float64 {
	return fn(3, 4)
}

func main() {
	hypot := func(x, y float64) float64 {
		return math.Sqrt(x*x + y*y)
	}
	fmt.Println(hypot(5, 12))

	fmt.Println(compute(hypot))
	fmt.Println(compute(math.Pow))
}
```

## Function closures

Like [JavaScript](JavaScript) function closures are supported in Go as well

```go
package main

import "fmt"

func adder() func(int) int {
	sum := 0
	return func(x int) int {
		sum += x
		return sum
	}
}

func main() {
	pos, neg := adder(), adder()
	for i := 0; i < 10; i++ {
		fmt.Println(
			pos(i),
			neg(-2*i),
		)
	}
}
```

0 0
1 -2
3 -6
6 -12
10 -20
15 -30
21 -42
28 -56
36 -72
45 -90

# Implementing an Interface

Here is an example of a function implementing an \[Golang interfaces]\(Golang interfaces):

```go
type BlindAlerter interface {
	ScheduleAlertAt(duration time.Duration, amount int)
}

// BlindAlerterFunc allows you to implement BlindAlerter with a function
type BlindAlerterFunc func(duration time.Duration, amount int)

// ScheduleAlertAt is BlindAlerterFunc implementation of BlindAlerter
func (a BlindAlerterFunc) ScheduleAlertAt(duration time.Duration, amount int) {
	a(duration, amount)
}
```
