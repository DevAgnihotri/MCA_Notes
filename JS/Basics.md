# JavaScript Basics

**Table of Contents**

- [1. Introduction to JavaScript](#1-introduction-to-javascript)
  - [What is JavaScript](#what-is-javascript)
  - [History and Evolution](#history-and-evolution)
  - [JavaScript in Browser vs Node.js](#javascript-in-browser-vs-nodejs)
  - [Linking JS with HTML (script tag, defer, async)](#linking-js-with-html-script-tag-defer-async)
  - [JS Syntax, Statements, and Comments](#js-syntax-statements-and-comments)
- [2. Variables and Data Types](#2-variables-and-data-types)
  - [var, let, const](#var-let-const)
  - [Hoisting of variables](#hoisting-of-variables)
  - [Primitive Data Types](#primitive-data-types)
  - [Reference Data Types](#reference-data-types)
  - [Type conversion and type coercion](#type-conversion-and-type-coercion)
  - [typeof operator](#typeof-operator)
- [3. Operators](#3-operators)

  - [Arithmetic Operators](#arithmetic-operators)
  - [Assignment Operators](#assignment-operators)
  - [Comparison Operators](#comparison-operators)
  - [Logical Operators](#logical-operators)
  - [Ternary Operator (?:)](#ternary-operator-)
  - [Bitwise Operators](#bitwise-operators)
  - [Spread and Rest Operators](#spread-and-rest-operators)
  - [Nullish Coalescing Operator (??)](#nullish-coalescing-operator-)
  - [Optional Chaining (?.)](#optional-chaining-)

  - [4. Control Structures](#4-control-structures)
    - [Conditional Statements (if, else if, else, switch)](#conditional-statements-if-else-if-else-switch)
    - [Loops (for, while, do...while)](#loops-for-while-dowhile)
    - [for...in and for...of loops](#forin-and-forof-loops)
    - [break and continue statements](#break-and-continue-statements)
  - [5. Functions](#5-functions)
    - [Function Declaration and Expression](#function-declaration-and-expression)
    - [Anonymous Functions](#anonymous-functions)
    - [Arrow Functions (=>)](#arrow-functions-)
    - [Default Parameters](#default-parameters)
    - [Return Statement](#return-statement)
    - [Function Scope](#function-scope)
    - [Higher-Order Functions](#higher-order-functions)
    - [Callback Functions](#callback-functions)
  - [6. Scope and Closures](#6-scope-and-closures)
    - [Global vs Local Scope](#global-vs-local-scope)
    - [Block Scope](#block-scope)
    - [Lexical Scope](#lexical-scope)
    - [Closure and its use cases](#closure-and-its-use-cases)

---

## 1. Introduction to JavaScript

### What is JavaScript

JavaScript is a high-level, interpreted programming language used to add interactivity to web pages and to build server-side applications with environments like Node.js.

### History and Evolution

Created in 1995 by Brendan Eich, JavaScript has evolved through ECMAScript standards (ES5, ES6/ES2015 and later) adding modules, classes, arrow functions, and async/await.

### JavaScript in Browser vs Node.js

In browsers JS manipulates the DOM, handles events, and works with the BOM; Node.js provides server-side APIs (FS, networking) and runs outside the browser.

### Linking JS with HTML (script tag, defer, async)

Use the `<script>` tag to include JS. `defer` delays execution until after parsing; `async` downloads and runs as soon as ready.

```html
<!-- blocking, executes immediately -->
<script src="script.js"></script>
<!-- non-blocking, executes after parsing -->
<script src="script.js" defer></script>
<!-- executes as soon as downloaded (order not guaranteed) -->
<script src="script.js" async></script>
```

### JS Syntax, Statements, and Comments

Statements are generally terminated by semicolons (optional in many cases). Single-line comments use `//`, multi-line use `/* */`.

```js
// single-line comment
/* multi-line
	 comment */
let x = 5; // statement
```

## 2. Variables and Data Types

### var, let, const

`var` is function-scoped (older), `let` and `const` are block-scoped; `const` creates a read-only binding (object contents can still change).

```js
let a = 1;
const PI = 3.14;
```

### Hoisting of variables

Variable and function declarations are hoisted: declarations move to the top of their scope, but `let`/`const` are not initialized until their declaration (temporal dead zone).

```js
console.log(x); // undefined (var)
var x = 2;

console.log(y); // ReferenceError (let/const)
let y = 3;
```

### Primitive Data Types

Primitives include `String`, `Number`, `Boolean`, `Null`, `Undefined`, `Symbol`, and `BigInt` — they are immutable and compared by value.

### Reference Data Types

Objects, Arrays, and Functions are reference types stored by reference; assigning them copies the reference, not the actual value.

### Type conversion and type coercion

Explicit conversion uses functions like `String()`, `Number()`. Coercion happens automatically in expressions (e.g., `"5" + 3` becomes `'53'`).

```js
"5" + 3; // '53' (string concatenation)
"5" - 3; // 2   (numeric coercion)
```

### typeof operator

`typeof` returns a string describing the type: e.g. `typeof 42` is `'number'`, `typeof null` is `'object'` (historical quirk).

```js
typeof 42; // 'number'
typeof "hello"; // 'string'
typeof null; // 'object'
```

---

## 3. Operators

### Arithmetic Operators

Used for numeric calculations: `+`, `-`, `*`, `/`, `%`, `**` (exponentiation).

```js
2 + 3; // 5
2 ** 3; // 8
```

### Assignment Operators

Assign or update values: `=`, `+=`, `-=`, `*=`, `/=` etc.

```js
let x = 5;
x += 2; // x is now 7
```

### Comparison Operators

Compare values and return boolean: `==`, `!=`, `===`, `!==`, `<`, `>`, `<=`, `>=`.

```js
5 == "5"; // true (loose equality)
5 === "5"; // false (strict equality)
```

### Logical Operators

Operate on booleans: `&&` (AND), `||` (OR), `!` (NOT); used in control flow and expressions.

```js
true && false; // false
!true; // false
```

### Ternary Operator (?:)

Short conditional expression: `condition ? exprIfTrue : exprIfFalse`.

```js
const status = age >= 18 ? "adult" : "minor";
```

### Bitwise Operators

| Operator |                                                                                     Use | Example                                                                  |
| -------- | --------------------------------------------------------------------------------------: | ------------------------------------------------------------------------ | --- | ------------ | -------------- |
| `&`      |                         Bitwise AND — mask bits (only bits set in both operands remain) | `5 & 1 // 1 (0101 & 0001 -> 0001)`                                       |
| `        |                                                                                       ` | Bitwise OR — set bits (bits set in either operand become 1)              | `5  | 1 // 5 (0101 | 0001 -> 0101)` |
| `^`      |                                         Bitwise XOR — toggle bits where operands differ | `5 ^ 1 // 4 (0101 ^ 0001 -> 0100)`                                       |
| `~`      |                                        Bitwise NOT — invert all bits (two's complement) | `~5 // -6 (invert 000...0101 -> 111...1010 => -6)`                       |
| `<<`     |                         Left shift — shift bits left, fill with zeros (multiply by 2^n) | `3 << 1 // 6 (0011 << 1 -> 0110)`                                        |
| `>>`     | Sign-propagating right shift — shift right, preserve sign (divide by 2^n for positives) | `5 >> 1 // 2  ;  -4 >> 1 // -2`                                          |
| `>>>`    |              Zero-fill right shift — shift right, fill left with zeros (unsigned shift) | `5 >>> 1 // 2  ;  -1 >>> 1 // 2147483647 (negative treated as unsigned)` |

### Spread and Rest Operators

The `...` syntax does two related things:

- Spread: expands an iterable (like an array) into individual items.
- Rest: collects multiple function arguments into a single array.

Example (spread and rest) with outputs:

```js
const arr = [1, 2, 3];
const copy = [...arr]; // spread copies items
const extended = [0, ...arr, 4]; // spread inserts items

function sum(...nums) {
  // rest gathers args into `nums`
  return nums.reduce((a, b) => a + b, 0);
}

console.log(copy); // [1, 2, 3]
console.log(extended); // [0, 1, 2, 3, 4]
console.log(sum(1, 2, 3)); // 6
```

### Nullish Coalescing Operator (??)

`a ?? b` returns `b` only when `a` is `null` or `undefined`. It does not treat `0`, `''`, or `false` as missing values (unlike `||`).

Example with outputs:

```js
const a = null ?? "default";
const b = 0 ?? 5; // 0 is not nullish, so it stays
const c = "" ?? "fallback";

console.log(a); // 'default'
console.log(b); // 0
console.log(c); // ''

// Contrast with ||
console.log(0 || 5); // 5 (because 0 is falsy)
```

### Optional Chaining (?.)

Optional chaining lets you access nested properties safely: if any part of the chain is `null` or `undefined`, the expression returns `undefined` instead of throwing an error.

Example and outputs:

```js
const user = { profile: { name: "Ami" } };
console.log(user?.profile?.name); // 'Ami'

const user2 = null;
console.log(user2?.profile?.name); // undefined (no error)

// Using with optional function calls
console.log(user?.getName?.()); // undefined if getName doesn't exist
```

## 4. Control Structures

### Conditional Statements (if, else if, else, switch)

Use `if`, `else if`, and `else` for branching; `switch` is helpful when checking one value against many cases.

```js
const n = 3;
if (n === 1) console.log("one");
else if (n === 2) console.log("two");
else console.log("other"); // 'other'

switch (n) {
  case 1:
    console.log("one");
    break;
  default:
    console.log("other");
}
```

### Loops (for, while, do...while)

`for` is used when you know iteration count; `while` checks condition before each loop; `do...while` runs at least once.

```js
for (let i = 0; i < 3; i++) console.log(i); // 0 1 2
let j = 0;
while (j < 3) {
  console.log(j);
  j++;
} // 0 1 2
let k = 0;
do {
  console.log(k);
  k++;
} while (k < 3); // 0 1 2
```

### for...in and for...of loops

`for...in` iterates enumerable keys of an object; `for...of` iterates values of an iterable (array, string).

```js
const obj = { a: 1, b: 2 };
for (let key in obj) console.log(key); // 'a' 'b'
const arr = [10, 20];
for (let val of arr) console.log(val); // 10 20
```

### break and continue statements

`break` exits the loop early; `continue` skips to the next iteration.

```js
for (let i = 0; i < 5; i++) {
  if (i === 3) break;
  console.log(i);
} // 0 1 2
for (let i = 0; i < 5; i++) {
  if (i % 2 === 0) continue;
  console.log(i);
} // 1 3
```

## 5. Functions

### Function Declaration and Expression

Function declarations (`function name() {}`) are hoisted; function expressions assign a function to a variable.

```js
function add(a, b) {
  return a + b;
}
const mul = function (a, b) {
  return a * b;
};
```

### Anonymous Functions

Anonymous functions have no name and are often used as callbacks or immediately-invoked functions.

```js
setTimeout(function () {
  console.log("delayed");
}, 1000);
(function () {
  console.log("IIFE");
})();
```

### Arrow Functions (=>)

Arrow functions are shorter syntax: they do not bind their own `this` or `arguments`.

```js
const sq = (x) => x * x;
console.log(sq(3)); // 9
```

### Default Parameters

Give parameters default values when omitted by the caller.

```js
function greet(name = "Guest") {
  console.log("Hi", name);
}
greet(); // 'Hi Guest'
```

### Return Statement

`return` exits the function and returns a value; without it a function returns `undefined`.

```js
function f() {
  return 5;
}
console.log(f()); // 5
```

### Function Scope

Variables declared inside a function are local to that function. `let`/`const` are block-scoped.

```js
function scopeTest() {
  let x = 1;
}
console.log(typeof x); // 'undefined'
```

### Higher-Order Functions

Functions that accept other functions as arguments or return functions; useful for abstraction.

```js
const map = (arr, fn) => arr.map(fn);
console.log(map([1, 2], (x) => x * 2)); // [2,4]
```

### Callback Functions

A callback is a function passed into another function to be called later (common in async code).

```js
function fetchData(cb) {
  setTimeout(() => cb("data"), 100);
}
fetchData((result) => console.log(result)); // 'data'
```

---

## 6. Scope and Closures

### Global vs Local Scope

Global variables are accessible anywhere in the program; local variables are defined inside a function and accessible only there.

```js
let globalVar = "g";
function fn() {
  let localVar = "l";
  console.log(globalVar);
}
fn(); // 'g'
console.log(typeof localVar); // 'undefined'
```

### Block Scope

`let` and `const` create block-scoped variables that exist only inside the nearest `{ ... }` block.

```js
if (true) {
  let x = 1;
}
console.log(typeof x); // 'undefined'
```

### Lexical Scope

Functions are defined with access to variables in the scope where they were created — that's lexical scope.

```js
const outer = "out";
function show() {
  console.log(outer);
}
show(); // 'out'
```

### Closure and its use cases

A closure happens when a function retains access to its lexical scope even after the outer function has finished. Useful for data privacy, factories, and callbacks.

```js
function counter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}
const c = counter();
console.log(c()); // 1
console.log(c()); // 2
```

Use cases: private state (like above), partially applied functions, and maintaining state in async callbacks.

---