---
id: 11d0fefd-c11e-400b-80fd-ba40e94b2a47
title: JavaScript RegExp Replace Method
---

replace[^1] is a nice way to use regexps to replace text:

``` javascript
console.log("papa".replace("p", "m"));
console.log("Borobudur".replace(/[ou]/, "a"));
console.log("Borobudur".replace(/[ou]/g, "a"));
```

You can also use awk like syntax to switch things around:

``` javascript
console.log(
  "Liskov, Barbara\nMcCarthy, John\nWadler, Philip"
    .replace(/(\w+), (\w+)/g, "$2 $1"));
```

You can even pass a function to replace:

``` javascript
let s = "the cia and fbi";
console.log(s.replace(/\b(fbi|cia)\b/g,
            str => str.toUpperCase()));
```

``` javascript
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

[^1]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/replace>
