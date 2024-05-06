---
id: cd472cb3-445c-4c81-a133-d6ef13eec545
title: JavaScript RegExp Named Capture Groups
---

# Introduction

This was introduced in [ES2018](20201030095105-es2018)

# Proposal

RegExp Named Capture Groups[^1]

# Syntax

``` javascript
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const matchObj = RE_DATE.exec("1999-12-31");

console.log(matchObj.groups.year); // 1999
console.log(matchObj.groups.month); // 12
console.log(matchObj.groups.day); // 31
```

## Indexed entries

Named capture groups also created indexed entries, like [numbered
capture
groups](20201104095851-javascript_regexp_numbered_capture_groups)

``` javascript
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const matchObj = RE_DATE.exec("1999-12-31");

console.log(matchObj[1]); // 1999
console.log(matchObj[2]); // 12
console.log(matchObj[3]); // 31
```

## Destructuring

[Destructuring](20201103111746-destructuring_objects) works well with
this:

``` javascript
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

const {groups: {day, year}} = RE_DATE.exec('1999-12-31');
console.log(year); // 1999
console.log(day); // 31
```

## Backreferences

`\k<name>` matches the string that was previously matched by the named
capture group `name`:

``` javascript
const RE_TWICE = /^(?<word>[a-z]+)!\k<word>$/;
RE_TWICE.test("abc!abc"); // true
RE_TWICE.test("abc!ab"); // false
```

Backreference syntax for [numbered capture
groups](20201104095851-javascript_regexp_numbered_capture_groups) works
as well:

``` javascript
const RE_TWICE = /^(?<word>[a-z]+)!\1$/;
RE_TWICE.test('abc!abc'); // true
RE_TWICE.test('abc!ab'); // false
```

Both can be mixed:

``` javascript
const RE_TWICE = /^(?<word>[a-z]+)!\k<word>!\1$/;
RE_TWICE.test("abc!abc!abc"); // true
RE_TWICE.test("abc!abc!ab"); // false
```

## repalce() and named capture groups

[replace()](20201104102343-javascript_regexp_replace_method) supports
named capture groups in two ways:

### Mention names in replacement string

``` javascript
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;
console.log("1999-12-31".replace(RE_DATE, "$<month>/$<day>/$<year>"));
// 12/31/1999
```

### Each replacement function receives an additional parameter that holds an object with data captured via named groups

``` javascript
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

[Rest parameters](20200922162500-rest_parameters) can also be used to
access the last argument:

``` javascript
const RE_DATE = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;
console.log(
  "1999-12-31".replace(RE_DATE, (...args) => {
    const { year, month, day } = args[args.length - 1];
    return month + "/" + day + "/" + year;
  })
);
// 12/31/1999
```

# See also

-   [Numbered Capture
    Groups](20201104095851-javascript_regexp_numbered_capture_groups)

# Footnotes

[^1]: <https://github.com/tc39/proposal-regexp-named-groups>
