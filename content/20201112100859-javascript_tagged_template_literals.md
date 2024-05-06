---
id: 6e8147d7-6328-4509-ba82-3f906aedf6cf
title: JavaScript Tagged Template Literals
---

# Description

Function calls whose parameters are provided via [template
literals](20201112100637-javascript_template_literals).

# Syntax

``` javascript
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
