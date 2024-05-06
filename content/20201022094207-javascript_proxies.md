---
id: c5010eb1-4ce2-4415-8421-7710daecad0a
title: JavaScript Proxies
---

# Introduction

ECMAScript 6 proxies bring intercession to
[JavaScript](20200613170905-javascript). They work as follows. There are
many operations that you can perform on an
[object](20200826201605-objects) obj. For example:

-   Getting the property `prop` of an object `obj` (`obj.prop`)
-   Checking whether an object `obj` has a property `prop`
    (`'prop' in obj`)

Proxies are special objects that allow you customize some of these
operations. A proxy is created with two parameters:

-   `handler`: For each operation, there is a corresponding handler
    method that – if present – performs that operation. Such a method
    *intercepts* the operation (on its way to the target) and is called
    a *trap* (a term borrowed from the domain of operating systems).
-   `target`: If the handler doesn’t intercept an operation then it is
    performed on the target. That is, it acts as a fallback for the
    handler. In a way, the proxy wraps the target.

# Examples

In the following example the handler intercepts the operations `get` and
`has`:

``` javascript
const target = {};
const handler = {
  /** Intercepts: getting properties */
  get(target, propKey, receiver) {
    console.log(`GET ${propKey}`);
    return 123;
  },

  /** Intercepts: checking whether properties exist */
  has(target, propKey) {
    console.log(`HAS ${propKey}`);
    return true;
  },
};
const proxy = new Proxy(target, handler);

console.log(proxy.foo); // 123
console.log("hello" in proxy); // true

proxy.bar = "abc";
console.log(target.bar); // "abc"
```

# Use cases for proxies

## Tracing property acesses (get, set)

``` javascript
function tracePropAccess(obj, propKeys) {
  const propKeySet = new Set(propKeys);
  return new Proxy(obj, {
    get(target, propKey, receiver) {
      if (propKeySet.has(propKey)) {
        console.log("GET " + propKey);
      }
      return Reflect.get(target, propKey, receiver);
    },
    set(target, propKey, value, receiver) {
      if (propKeySet.has(propKey)) {
        console.log("SET " + propKey + "=" + value);
      }
      return Reflect.set(target, propKey, value, receiver);
    },
  });
}

class Point {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
  toString() {
    return `Point(${this.x}, ${this.y})`;
  }
}
// Trace accesses to properties `x` and `y`
let p = new Point(5, 7);
p = tracePropAccess(p, ["x", "y"]);

// GET x
// 4
console.log(p.x);

// SET x=21
// 21
console.log((p.x = 21));

// GET x
// GET y
// Point(21, 7)
console.log(p.toString());
```

## Warning about unknown properties (get,set)

When it comes to accessing properties, JavaScript is very forgiving. For
example, if you try to read a property and misspell its name, you don’t
get an exception, you get the result `undefined`. You can use proxies to
get an exception in such a case. This works as follows. We make the
proxy a prototype of an object.

If a property isn’t found in the object, the `get` trap of the proxy is
triggered. If the property doesn’t even exist in the prototype chain
after the proxy, it really is missing and we throw an exception.
Otherwise, we return the value of the inherited property. We do so by
forwarding the `get` operation to the target (the prototype of the
target is also the prototype of the proxy).

### Unknown Property Examples

1.  Object

    ``` javascript
    const PropertyChecker = new Proxy(
      {},
      {
        get(target, propKey, receiver) {
          if (!(propKey in target)) {
            throw new ReferenceError("Unknown property: " + propKey);
          }
          return Reflect.get(target, propKey, receiver);
        },
      }
    );

    const obj = { __proto__: PropertyChecker, foo: 123 };
    // 123
    console.log(obj.foo);

    // ReferenceError: Unknown property: fo
    obj.fo

    // [object Object]
    obj.toString()
    ```

2.  Class

    If we turn `PropertyChecker` into a constructor, we can use it for
    [classes](20201008090316-class_notation) via extends:

    ``` javascript
    function PropertyChecker() {}
    PropertyChecker.prototype = new Proxy(/*···*/);

    class Point extends PropertyChecker {
      constructor(x, y) {
        super();
        this.x = x;
        this.y = y;
      }
    }

    const p = new Point(5, 7);
    console.log(p.x); // 5
    console.log(p.z); // ReferenceError
    ```

## Negative Array indices (get)

Some [array prototype
methods](20201009090331-javascript_array_prototype_methods) let you
refer to the last element via -1, to the second-to-last element via -2,
etc. For example:

``` javascript
console.log(["a", "b", "c"].slice(-1)); // ['c']
```

Alas, that doesn’t work when accessing elements via the bracket operator
(\[\]). We can, however, use proxies to add that capability. The
following function createArray() creates Arrays that support negative
indices. It does so by wrapping proxies around Array instances. The
proxies intercept the get operation that is triggered by the bracket
operator.

``` javascript
function createArray(...elements) {
  const handler = {
    get(target, propKey, receiver) {
      // Sloppy way of checking for negative indices
      const index = Number(propKey);
      if (index < 0) {
        propKey = String(target.length + index);
      }
      return Reflect.get(target, propKey, receiver);
    },
  };
  // Wrap a proxy around an Array
  const target = [];
  target.push(...elements);
  return new Proxy(target, handler);
}

const arr = createArray("a", "b", "c");
console.log(arr[-1]); // c
```

## Data binding (set)

``` javascript
function createObservedArray(callback) {
    const array = [];
    return new Proxy(array, {
        set(target, propertyKey, value, receiver) {
            callback(propertyKey, value);
            return Reflect.set(target, propertyKey, value, receiver);
        }
    });    
}
const observedArray = createObservedArray(
    (key, value) => console.log(`${key}=${value}`));
observedArray.push('a');

```

## Accessing a restful web service

``` javascript
function httpGet(url) {
  return new Promise((resolve, reject) => {
    const request = new XMLHttpRequest();
    Object.assign(request, {
      onload() {
        if (this.status === 200) {
          // Success
          resolve(this.response);
        } else {
          // Something went wrong (404 etc.)
          reject(new Error(this.statusText));
        }
      },
      onerror() {
        reject(new Error("XMLHttpRequest Error: " + this.statusText));
      },
    });
    request.open("GET", url);
    request.send();
  });
}

function createWebService(baseUrl) {
  return new Proxy(
    {},
    {
      get(target, propKey, receiver) {
        // Return the method to be called
        return () => httpGet(baseUrl + "/" + propKey);
      },
    }
  );
}

const service = createWebService("http://example.com/data");
// Read JSON data in http://example.com/data/employees
service.employees().then((json) => {
  const employees = JSON.parse(json);
});
```

## Recoverable references

*Revocable references* work as follows: A client is not allowed to
access an important resource (an object) directly, only via a reference
(an intermediate object, a wrapper around the resource). Normally, every
operation applied to the reference is forwarded to the resource. After
the client is done, the resource is protected by revoking the reference,
by switching it off. Henceforth, applying operations to the reference
throws exceptions and nothing is forwarded, anymore.

In the following example, we create a revocable reference for a
resource. We then read one of the resource’s properties via the
reference. That works, because the reference grants us access. Next, we
revoke the reference. Now the reference doesn’t let us read the
property, anymore.

``` javascript
function createRevocableReference(target) {
  const handler = {}; // forward everything
  const { proxy, revoke } = Proxy.revocable(target, handler);
  return { reference: proxy, revoke };
}

const resource = { x: 11, y: 8 };
const { reference, revoke } = createRevocableReference(resource);

// Access granted
console.log(reference.x); // 11

revoke();

// Access denied
console.log(reference.x); // TypeError: Revoked
```

# See also

-   [Metaprogramming](20201022095438-javascript_metaprogramming)
