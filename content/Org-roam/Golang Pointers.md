---
publish: true
title: Golang Pointers
created: 2020-08-28T18:09:57
modified: 2026-08-12T09:32:15.606Z
---

# Golang Pointers

## Basics

Go also supports pointers. Default value is always NULL and you can't do pointer arithmetic. Other than that, nothing that will blow your mind here.

```go
package main

import "fmt"

func main() {
	i, j := 42, 2701

	p := &i         // point to i
	fmt.Println(*p) // read i through the pointer
	*p = 21         // set i through the pointer
	fmt.Println(i)  // see the new value of i

	p = &j         // point to j
	*p = *p / 37   // divide j through the pointer
	fmt.Println(j) // see the new value of j
}
```

## Pointers to [[Golang Structs]]

To facilitate lazy people like me Go allows you to lose the `*` when using a pointer to a struct

```go
package main

import "fmt"

type Vertex struct {
	X int
	Y int
}

func main() {
	v := Vertex{1, 2}
	p := &v
	p.X = 123
	fmt.Println(v)
}
```
