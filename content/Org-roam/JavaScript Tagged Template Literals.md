---
publish: true
title: JavaScript Tagged Template Literals
created: 2020-11-12T10:08:59
modified: 2026-08-12T10:26:13.184Z
---

# JavaScript Tagged Template Literals

## Description

Function calls whose parameters are provided via [[JavaScript Template Literals]].

## Syntax

```js
let person = 'Mike';
let age = 28;

function myTag(strings, personExp, ageExp) {
  let str0 = strings[0]; // "That "
  let str1 = strings[1]; // " is a "

  // There is technically a string after
  // the final expression (in our example),
  // but it is empty (""), so disregard.
  // let str2 = strings[2];

  let ageStr;
  if (ageExp > 99){
    ageStr = 'centenarian';
  } else {
    ageStr = 'youngster';
  }

  // We can even return a string built using a template literal
  return `${str0}${personExp}${str1}${ageStr}`;
}

let output = myTag`That ${ person } is a ${ age }`;

console.log(output);
// That Mike is a youngster
```
