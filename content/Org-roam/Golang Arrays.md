---
publish: true
title: Golang Arrays
created: 2020-08-28T18:23:27
modified: 2026-08-12T10:26:13.169Z
---

# Golang Arrays

Arrays are a thing in Go as well. Once initialized arrays cannot be resized, if you're into _that_ type of thing (no judgement) see [[Golang slices]]

```go
package main

import "fmt"

func main() {
	var a [2]string
	a[0] = "Hello"
	a[1] = "World"
	fmt.Println(a[0], a[1])
	fmt.Println(a)

	primes := [6]int{2, 3, 5, 7, 11, 13}
	fmt.Println(primes)
}
```
