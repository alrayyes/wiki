---
publish: true
title: JavaScript RegExp Replace Method
created: 2020-11-04T10:23:43
modified: 2026-08-05T07:58:56.692Z
---

# JavaScript RegExp Replace Method

replace\[fn:replace] is a nice way to use regexps to replace text:

```js
console.log("papa".replace("p", "m"));
console.log("Borobudur".replace(/[ou]/, "a"));
console.log("Borobudur".replace(/[ou]/g, "a"));
```

You can also use awk like syntax to switch things around:

```js
console.log(
  "Liskov, Barbara\nMcCarthy, John\nWadler, Philip"
    .replace(/(\w+), (\w+)/g, "$2 $1"));
```

You can even pass a function to replace:

```js
let s = "the cia and fbi";
console.log(s.replace(/\b(fbi|cia)\b/g,
            str => str.toUpperCase()));
```

```js
let stock = "1 lemon, 2 cabbages, and 101 eggs";
function minusOne(match, amount, unit) {
  amount = Number(amount) - 1;
  if (amount == 1) { // only one left, remove the 's'
    unit = unit.slice(0, unit.length - 1);
  } else if (amount == 0) {
    amount = "no";
  }
  return amount + " " + unit;
}
console.log(stock.replace(/(\d+) (\w+)/g, minusOne));
```

# Footnotes

\[fn:replace]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/replace
