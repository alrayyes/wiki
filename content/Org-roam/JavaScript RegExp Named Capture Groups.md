---
publish: true
title: JavaScript RegExp Named Capture Groups
created: 2020-11-04T10:04:31
modified: 2026-08-12T10:31:55.411Z
---

# JavaScript RegExp Named Capture Groups

## Introduction

This was introduced in [[ES2018]]

## Proposal

RegExp Named Capture Groups[^capture-groups]

## Syntax

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const matchObj = RE_DATE.exec("1999-12-31");

console.log(matchObj.groups.year); // 1999
console.log(matchObj.groups.month); // 12
console.log(matchObj.groups.day); // 31
```

### Indexed entries

Named capture groups also created indexed entries, like [[JavaScript RegExp Numbered Capture Groups]]

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const matchObj = RE_DATE.exec("1999-12-31");

console.log(matchObj[1]); // 1999
console.log(matchObj[2]); // 12
console.log(matchObj[3]); // 31
```

### Destructuring

[[Destructuring Objects]] works well with this:

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const {groups: {day, year}} = RE_DATE.exec('1999-12-31');
console.log(year); // 1999
console.log(day); // 31
```

### Backreferences

\~\k<name>~ matches the string that was previously matched by the named capture group ~name~:

```js
const RE_TWICE = /^(?<word>[a-z]+)!\k<word>$/;
RE_TWICE.test("abc!abc"); // true
RE_TWICE.test("abc!ab"); // false
```

Backreference syntax for [[JavaScript RegExp Numbered Capture Groups]] works as well:

```js
const RE_TWICE = /^(?<word>[a-z]+)!\1$/;
RE_TWICE.test('abc!abc'); // true
RE_TWICE.test('abc!ab'); // false
```

Both can be mixed:

```js
const RE_TWICE = /^(?<word>[a-z]+)!\k<word>!\1$/;
RE_TWICE.test("abc!abc!abc"); // true
RE_TWICE.test("abc!abc!ab"); // false
```

### repalce() and named capture groups

[[JavaScript RegExp Replace Method]] supports named capture groups in two ways:

#### Mention names in replacement string

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;
console.log("1999-12-31".replace(RE_DATE, "$<month>/$<day>/$<year>"));
// 12/31/1999
```

#### Each replacement function receives an additional parameter that holds an object with data captured via named groups

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;
console.log(
  "1999-12-31".replace(
    RE_DATE,
    (
      g0,
      y,
      m,
      d,
      offset,
      input,
      { year, month, day } // (A)
    ) => month + "/" + day + "/" + year
  )
);
// 12/31/1999
```

[[JavaScript Rest Parameters]] can also be used to access the last argument:

```js
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;
console.log(
  "1999-12-31".replace(RE_DATE, (...args) => {
    const { year, month, day } = args[args.length - 1];
    return month + "/" + day + "/" + year;
  })
);
// 12/31/1999
```

## See also

- [[JavaScript RegExp Numbered Capture Groups]]

## Footnotes

[^capture-groups]: https://github.com/tc39/proposal-regexp-named-groups
