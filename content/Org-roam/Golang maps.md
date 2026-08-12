---
publish: true
title: Golang maps
created: 2020-08-28T19:20:34
modified: 2026-08-12T10:31:55.401Z
---

# Golang maps

## Basics

A map maps keys to values, ie: associative arrays. Zero value of a map is ~nil~. ~make~ function returns a new ~map~.

```go
package main

import "fmt"

type Vertex struct {
	Lat, Long float64
}

var m map[string]Vertex

func main() {
	m = make(map[string]Vertex)
	m["Bell Labs"] = Vertex{
		40.68433, -74.39967,
	}
	fmt.Println(m["Bell Labs"])
}
```

## Map literals

These are essentially the same as [[Golang Structs]], keys are required.

```go
package main

import "fmt"

type Vertex struct {
	Lat, Long float64
}

var m = map[string]Vertex{
	"Bell Labs": Vertex{
		40.68433, -74.39967,
	},
	"Google": Vertex{
		37.42202, -122.08408,
	},
}

func main() {
	fmt.Println(m)
}
```

If top-level type is just a type name, it can be omitted from literal elements. Saves some typing.

```go
package main

import "fmt"

type Vertex struct {
	Lat, Long float64
}

var m = map[string]Vertex{
	"Bell Labs": {40.68433, -74.39967},
	"Google":    {37.42202, -122.08408},
}

func main() {
	fmt.Println(m)
}
```

## Mutating maps

Nothing shocking here either. Map elements can be added/deleted/modified/etc.

```go
package main

import "fmt"

func main() {
	m := make(map[string]int)

	m["Answer"] = 42
	fmt.Println("The value:", m["Answer"])

	m["Answer"] = 48
	fmt.Println("The value:", m["Answer"])

	delete(m, "Answer")
	fmt.Println("The value:", m["Answer"])

	v, ok := m["Answer"]
	fmt.Println("The value:", v, "Present?", ok)
}
```

## Types

A ~type~ can be declared as a thin wrapper around a ~map~:

```go
import "fmt"

type Dictionary map[string]string

func (d Dictionary) Search(word string) string {
	return d[word]
}

func main() {
	d := Dictionary{"key": "This is the value"}
	fmt.Println(d.Search("key"))
}
```
