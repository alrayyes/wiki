---
id: 6fd9af86-8c34-495e-9370-2dd085b2886f
title: TypeScript Template Literal String Type
---

# Description

TypeScript supports template literal strings[^1], with the same syntax
as [JavaScript Template
Literals](20201112100637-javascript_template_literals). There is also an
in progress PR to switch to type alias helpers[^2].

# Syntax

``` typescript
type World = "world";

type Greeting = `hello ${World}`;
// same as
//   type Greeting = "hello world";
```

# Examples

## Unions

With [unions](20200929163219-typescript_union_type) you can mix and
match.

``` typescript
type Color = "red" | "blue";
type Quantity = "one" | "two";

type SeussFish = `${Quantity | Color} fish`;
// same as
//   type SeussFish = "one fish" | "two fish"
//                  | "red fish" | "blue fish";
```

``` typescript
type VerticalAlignment = "top" | "middle" | "bottom";
type HorizontalAlignment = "left" | "center" | "right";

// Takes
//   | "top-left"    | "top-center"    | "top-right"
//   | "middle-left" | "middle-center" | "middle-right"
//   | "bottom-left" | "bottom-center" | "bottom-right"
declare function setAlignment(value: `${VerticalAlignment}-${HorizontalAlignment}`): void;

setAlignment("top-left");   // works!
setAlignment("top-middel"); // error!
setAlignment("top-pot");    // error! but good doughnuts if you're ever in Seattle
```

## Objects

``` typescript
type PropEventSource<T> = {
    on(eventName: `${string & keyof T}Changed`, callback: () => void): void;
};

/// Create a "watched object" with an 'on' method
/// so that you can watch for changes to properties.
declare function makeWatchedObject<T>(obj: T): T & PropEventSource<T>;

let person = makeWatchedObject({
    firstName: "Homer",
    age: 42, // give-or-take
    location: "Springfield",
});    

// error!
person.on("firstName", () => {
});

// error!
person.on("frstNameChanged", () => {
});

// success!
person.on("firstNameChanged", () => {
    console.log(`firstName was changed!`);
});
```

### Inference

Here we made on into a generic method. When a user calls with the string
`'firstNameChanged'`, TypeScript will try to infer the right type for
`K`. To do that, it will match `K` against the content prior to
`"Changed"` and infer the string `"firstName"`. Once TypeScript figures
that out, the `on` method can fetch the type of `firstName` on the
original object, which is `string` in this case. Similarly, when we call
with `"ageChanged"`, it finds the type for the property `age` which is
`number`).

``` typescript
type PropEventSource<T> = {
    on<K extends string & keyof T>
        (eventName: `${K}Changed`, callback: (newValue: T[K]) => void ): void;
};

declare function makeWatchedObject<T>(obj: T): T & PropEventSource<T>;

let person = makeWatchedObject({
    firstName: "Homer",
    age: 42,
    location: "Springfield",
});

// works! 'newName' is typed as 'string'
person.on("firstNameChanged", newName => {
    // 'newName' has the type of 'firstName'
    console.log(`new name is ${newName.toUpperCase()}`);
});

// works! 'newAge' is typed as 'number'
person.on("ageChanged", newAge => {
    if (newAge < 0) {
        console.log("warning! negative age");
    }
})
```

# Helpers

-   [Uppercase](20201123103250-uppercase)
-   [Lowercase](20201123103315-lowercase)
-   [Capitalize](20201123103333-capitalize)
-   [Uncapitalize](20201123103400-uncapitalize)

# Footnotes

[^1]: <https://github.com/microsoft/TypeScript/pull/40336>

[^2]: <https://github.com/microsoft/TypeScript/pull/40580>
