---
publish: true
title: JavaScript Generators
created: 2020-09-11T15:59:47
---

## ES6

### Introduction

Generators are processes that you can pause and resume. Generators are defined with ~function\*~.

```js
const foo = function* () {
  yield 'a';
  yield 'b';
  yield 'c';
};

let str = '';
for (const val of foo()) {
  str = str + val;
}

console.log(str);
```

### Generator Kinds

#### Generator function declarations

```js
function* genFunc() { }
const genObj = genFunc();
```

#### Generator function expressions

```js
const genFunc = function* () { };
const genObj = genFunc();
```

#### Generator method definitions in object literals

```js
const obj = {
    * generatorMethod() {
    }
};
const genObj = obj.generatorMethod();
```

#### Generator method definitions in class definitions

```js
class MyClass {
    * generatorMethod() {
    }
}
const myInst = new MyClass();
const genObj = myInst.generatorMethod();
```

## Examples

### Iterables

```js
function* objectEntries(obj) {
    const propKeys = Reflect.ownKeys(obj);

    for (const propKey of propKeys) {
        // `yield` returns a value and then pauses
        // the generator. Later, execution continues
        // where it was previously paused.
        yield [propKey, obj[propKey]];
    }
}

const jane = { first: 'Jane', last: 'Doe' };
for (const [key,value] of objectEntries(jane)) {
    console.log(`${key}: ${value}`);
}

// Output:
// first: Jane
// last: Doe
```

### Async Iterables

```js
async function* createAsyncIterable(syncIterable) {
  for (const elem of syncIterable) {
    yield elem;
  }
}
```

### Asynchronous code

```js
const fetchJson = co.wrap(function* (url) {
    try {
        let request = yield fetch(url);
        let text = yield request.text();
        return JSON.parse(text);
    }
    catch (error) {
        console.log(`ERROR: ${error.stack}`);
    }
});

fetchJson('http://example.com/some_file.json')
.then(obj => console.log(obj));
```

## Also see

- [[JavaScript Iterables]]
- [[JavaScript Promises]]
