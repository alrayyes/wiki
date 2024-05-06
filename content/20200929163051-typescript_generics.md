---
id: aacdac15-4e00-4d75-9888-79b23bb47498
title: TypeScript Generics
---

# Examples

## Function level

``` typescript
function reverse<T>(items: T[]): T[] {
    var toreturn = [];
    for (let i = items.length - 1; i >= 0; i--) {
        toreturn.push(items[i]);
    }
    return toreturn;
}

var sample = [1, 2, 3];
var reversed = reverse(sample);
console.log(reversed); // 3,2,1

// Safety!
reversed[0] = '1';     // Error!
reversed = ['1', '2']; // Error!

reversed[0] = 1;       // Okay
reversed = [1, 2];     // Okay
```

## Class level

``` typescript
/** A class definition with a generic parameter */
class Queue<T> {
  private data = [];
  push(item: T) { this.data.push(item); }
  pop(): T | undefined { return this.data.shift(); }
}

/** Again sample usage */
const queue = new Queue<number>();
queue.push(0);
queue.push("1"); // ERROR : cannot push a string. Only numbers allowed
```

## Member functions

``` typescript
class Utility {
  reverse<T>(items: T[]): T[] {
      var toreturn = [];
      for (let i = items.length - 1; i >= 0; i--) {
          toreturn.push(items[i]);
      }
      return toreturn;
  }
}
```
