````markdown
# JavaScript Basics — Part 3

**Table of Contents**

- [16. Advanced Concepts](#16-advanced-concepts)
  - [Hoisting (Variable and Function)](#hoisting-variable-and-function)
  - [this keyword in different contexts](#this-keyword-in-different-contexts)
  - [Closures in detail](#closures-in-detail)
  - [Prototype Chain](#prototype-chain)
  - [Shadowing](#shadowing)
  - [IIFE (Immediately Invoked Function Expression)](#iife-immediately-invoked-function-expression)
  - [Currying](#currying)
  - [Debouncing and Throttling](#debouncing-and-throttling)
  - [Memoization](#memoization)
  - [Module Pattern](#module-pattern)
  - [Factory Function](#factory-function)
- [17. Local Storage and Cookies](#17-local-storage-and-cookies)
  - [localStorage, sessionStorage, cookies](#localstorage-sessionstorage-cookies)
  - [Difference between them](#difference-between-them)
  - [CRUD operations on storage](#crud-operations-on-storage)
  - [Storage events](#storage-events)
- [20. Modules](#20-modules)
  - [ES6 Modules (import, export)](#es6-modules-import-export)
  - [CommonJS and AMD](#commonjs-and-amd)
  - [Default and Named Exports](#default-and-named-exports)
  - [Bundlers (Webpack, Vite, etc.)](#bundlers-webpack-vite-etc)
- [21. Regular Expressions](#21-regular-expressions)
  - [Syntax and Patterns](#syntax-and-patterns)
  - [Flags (g, i, m)](#flags-g-i-m)
  - [Common RegEx Methods (match, replace, test, exec)](#common-regex-methods-match-replace-test-exec)
- [22. Memory Management](#22-memory-management)
  - [Garbage Collection](#garbage-collection)
  - [Memory leaks and prevention](#memory-leaks-and-prevention)
- [23. Security](#23-security)
  - [XSS (Cross-Site Scripting)](#xss-cross-site-scripting)
  - [CSRF (Cross-Site Request Forgery)](#csrf-cross-site-request-forgery)
  - [Input sanitization](#input-sanitization)

---

## 16. Advanced Concepts

Advanced concepts help you write better and faster JavaScript. They explain how the language works under the hood.
Each subtopic below has a short explanation, the syntax, a tiny example, and the output.

### Hoisting (Variable and Function)

Hoisting means JavaScript moves declarations to the top before running code. Declarations exist before you reach them, but values do not.

Syntax/example:

```js
console.log(x); // undefined (declaration hoisted, value not)
var x = 5;

foo(); // works because function declarations are hoisted
function foo() {
  console.log("called");
}
```

Output:

```txt
undefined
called
```

### this keyword in different contexts

`this` points to the object that called the function. In the global scope it points to global (or undefined in strict mode). Arrow functions do not have their own `this`.

Syntax/example:

```js
const obj = {
  name: "Amy",
  get() {
    return this.name;
  },
};
console.log(obj.get()); // 'Amy'
const arrow = () => this; // uses surrounding this
```

Output:

```txt
Amy
```

### Closures in detail

A closure happens when a function remembers the variables from the place it was created, even after that place finished running.

Syntax/example:

```js
function makeCounter() {
  let count = 0;
  return function () {
    count += 1;
    return count;
  };
}
const c = makeCounter();
console.log(c()); // 1
console.log(c()); // 2
```

Output:

```txt
1
2
```

### Prototype Chain

Objects can inherit from other objects. The prototype chain is how JavaScript finds a property by walking up linked prototypes.

Syntax/example:

```js
function Person(n) {
  this.name = n;
}
Person.prototype.say = function () {
  return "Hi " + this.name;
};
const p = new Person("Zoe");
console.log(p.say()); // 'Hi Zoe'
```

Output:

```txt
Hi Zoe
```

### Shadowing

Shadowing is when an inner variable has the same name as an outer variable. The inner one hides the outer one inside its scope.

Syntax/example:

```js
let x = 5;
function f() {
  let x = 10; // shadows outer x inside f
  console.log(x);
}
f();
console.log(x);
```

Output:

```txt
10
5
```

### IIFE (Immediately Invoked Function Expression)

An IIFE runs as soon as it is created. It is useful to make a private scope.

Syntax/example:

```js
(function () {
  const secret = "hide";
  console.log("IIFE runs");
})();
```

Output:

```txt
IIFE runs
```

### Currying

Currying turns a function with many arguments into many functions each with one argument. It helps make reusable small functions.

Syntax/example:

```js
function add(a) {
  return function (b) {
    return a + b;
  };
}
console.log(add(2)(3)); // 5
```

Output:

```txt
5
```

### Debouncing and Throttling

Debounce delays a function until actions stop; throttle limits how often a function runs. Both help with heavy events like resize or scroll.

Syntax/example (debounce simple):

```js
function debounce(fn, wait) {
  let t;
  return function (...args) {
    clearTimeout(t);
    t = setTimeout(() => fn.apply(this, args), wait);
  };
}
// Usage: const debounced = debounce(() => console.log('run'), 200);
```

Output (concept):

```txt
Only one 'run' printed after the user stops triggering the event.
```

### Memoization

Memoization stores results of a function so repeated calls with the same inputs are fast.

Syntax/example:

```js
function memoize(fn) {
  const cache = {};
  return (n) => (cache[n] ??= fn(n));
}
const fib = memoize((n) => (n < 2 ? n : fib(n - 1) + fib(n - 2)));
console.log(fib(6)); // 8
```

Output:

```txt
8
```

### Module Pattern

Module pattern creates a private scope and exports only what you need. It protects internal data.

Syntax/example:

```js
const MyModule = (function () {
  let count = 0;
  return {
    inc() {
      count += 1;
      return count;
    },
  };
})();
console.log(MyModule.inc()); // 1
```

Output:

```txt
1
```

### Factory Function

A factory function returns objects. It is an easy alternative to classes for making many similar objects.

Syntax/example:

```js
function makeUser(name) {
  return {
    name,
    greet() {
      return "Hi " + name;
    },
  };
}
const u = makeUser("Nikki");
console.log(u.greet()); // 'Hi Nikki'
```

Output:

```txt
Hi Nikki
```

---

## 17. Local Storage and Cookies

Browser storage helps keep small pieces of data on the user side. Use them to remember settings or small app state.
This section shows the simple differences and how to do CRUD with storage.

### localStorage, sessionStorage, cookies

- `localStorage`: keeps data until cleared (no expiry).
- `sessionStorage`: keeps data for that browser tab only.
- `cookies`: small data sent to server and can have expiry.

Syntax/example:

```js
localStorage.setItem("color", "blue");
console.log(localStorage.getItem("color")); // 'blue'
sessionStorage.setItem("tab", "1");
document.cookie = "user=Sam; path=/;";
```

Output:

```txt
blue
```

### Difference between them

localStorage keeps data forever (until cleared). sessionStorage clears when the tab closes. Cookies are sent to the server and can expire.

### CRUD operations on storage

Create/Read/Update/Delete examples for `localStorage`:

```js
// Create / Update
localStorage.setItem("name", "Rohit");
// Read
console.log(localStorage.getItem("name")); // 'Rohit'
// Delete
localStorage.removeItem("name");
// Clear all
localStorage.clear();
```

Output (example read):

```txt
Rohit
```

### Storage events

The `storage` event fires on other windows when storage changes in one window. Useful to sync state across tabs.

Syntax/example:

```js
// In one tab: localStorage.setItem('x', '1');
// In another tab:
window.addEventListener("storage", (e) => {
  console.log("changed", e.key, e.newValue);
});
```

Output (concept):

```txt
changed x 1
```

---

## 18. Fetch and AJAX

Fetch and AJAX let your page talk to servers to get or send data. Modern code uses `fetch()` which returns Promises.

### XMLHttpRequest basics

Old way to do AJAX is `XMLHttpRequest`. It works but is more code than `fetch()`.

Syntax/example:

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', '/data');
xhr.onload = () => console.log(xhr.responseText);
xhr.send();
```

Output (concept):

```txt
prints server response text when ready
```

### Fetch API (fetch())

`fetch()` is simpler and returns a Promise that resolves to a Response object.

Syntax/example:

```js
fetch('/data')
  .then((res) => res.text())
  .then((txt) => console.log(txt));
```

Output (concept):

```txt
server response text
```

### Async/Await with Fetch

Use `async`/`await` to write fetch code that looks like normal, synchronous code.

Syntax/example:

```js
async function getData() {
  const res = await fetch('/data');
  const json = await res.json();
  console.log(json);
}
getData();
```

Output (concept):

```txt
{ ...parsed JSON... }
```

### Handling JSON data

Call `res.json()` to parse JSON from the response; it also returns a Promise.

Syntax/example:

```js
fetch('/user').then((r) => r.json()).then((u) => console.log(u.name));
```

Output (concept):

```txt
prints user name from JSON
```

### Error handling in Fetch

Check `res.ok` and use `.catch()` or `try/catch` with `await` to handle network errors.

Syntax/example:

```js
fetch('/bad-url')
  .then((r) => {
    if (!r.ok) throw new Error('Network error');
    return r.json();
  })
  .catch((e) => console.error('Fetch failed', e.message));
```

Output (concept):

```txt
Fetch failed Network error
```

### Axios overview

Axios is a popular library that wraps `fetch`/XHR and gives a simpler API and automatic JSON parsing.

Syntax/example:

```js
// using axios (needs library)
axios.get('/data').then((res) => console.log(res.data));
```

Output (concept):

```txt
server data (parsed)
```

---

## 19. Object-Oriented JavaScript (OOPs in JS)

OOP in JavaScript means creating objects that hold data and behavior. You can use constructor functions or ES6 classes.

### Constructor Functions

Old-style way to make many similar objects using `new` and prototypes.

Syntax/example:

```js
function Person(name) {
  this.name = name;
}
Person.prototype.greet = function () { return 'Hi ' + this.name; };
const p = new Person('Joe');
console.log(p.greet()); // 'Hi Joe'
```

Output:

```txt
Hi Joe
```

### ES6 Classes

Classes are nicer syntax over constructor functions; they still use prototypes under the hood.

Syntax/example:

```js
class Car {
  constructor(model) { this.model = model; }
  info() { return this.model; }
}
const c = new Car('Fiat');
console.log(c.info()); // 'Fiat'
```

Output:

```txt
Fiat
```

### Inheritance (extends, super)

Use `extends` and `super()` to inherit from another class and call the parent constructor.

Syntax/example:

```js
class Animal { constructor(name) { this.name = name; } }
class Dog extends Animal { bark() { return 'woof ' + this.name; } }
const d = new Dog('Max');
console.log(d.bark()); // 'woof Max'
```

Output:

```txt
woof Max
```

### Encapsulation and Abstraction

Encapsulation hides details inside objects. Use closures or private fields (`#`) to keep data private.

Syntax/example:

```js
class Secret {
  #val = 1;
  inc() { this.#val += 1; return this.#val; }
}
const s = new Secret();
console.log(s.inc()); // 2
```

Output:

```txt
2
```

### Polymorphism in JS

Polymorphism means different objects can use the same method name in their own way. Methods can be overridden.

Syntax/example:

```js
class A { speak() { return 'A'; } }
class B extends A { speak() { return 'B'; } }
console.log(new A().speak(), new B().speak()); // 'A' 'B'
```

Output:

```txt
A B
```

### Static Methods and Properties

Static methods belong to the class itself, not to instances.

Syntax/example:

```js
class MathUtil { static sum(a,b){ return a+b; } }
console.log(MathUtil.sum(2,3)); // 5
```

Output:

```txt
5
```


## 20. Modules

Modules help split code into small files that can import and export only what they need.
Use modules to keep code organized and reusable.

### ES6 Modules (import, export)

ES6 modules use `export` and `import` keywords. They work in modern browsers and Node (with module settings).

Syntax/example:

```js
// math.js
export function sum(a, b) {
  return a + b;
}

// app.js
import { sum } from "./math.js";
console.log(sum(2, 3)); // 5
```

Output:

```txt
5
```

### CommonJS and AMD

CommonJS (`require`, `module.exports`) is used by Node.js. AMD is older for browsers. CommonJS loads synchronously, ES modules load differently.

Syntax/example (CommonJS):

```js
// math.cjs
module.exports = { sum: (a, b) => a + b };
// app.cjs
const m = require("./math.cjs");
console.log(m.sum(1, 2)); // 3
```

Output:

```txt
3
```

### Default and Named Exports

You can export a default value (one per file) and named exports (many per file).

Syntax/example:

```js
// default export
export default function () {
  return "ok";
}
// named
export const x = 1;
```

### Bundlers (Webpack, Vite, etc.)

Bundlers bundle many module files into one or a few files for the browser. Tools like Webpack, Vite, and Rollup are common.

Example (concept):

```txt
You write many small files, the bundler creates one fast file for production.
```

---

## 21. Regular Expressions

Regular expressions (RegEx) help find patterns in text, like test, match, replace, or extract parts.
They are powerful but can look cryptic at first.

### Syntax and Patterns

RegEx uses special characters to match text (e.g., `\d` for digits, `\w` for word chars, `.` for any char).

Syntax/example:

```js
const re = /\d+/; // one or more digits
console.log("a1b2".match(re)); // ['1']
```

Output:

```txt
['1']
```

### Flags (g, i, m)

Flags change behavior: `g` for global (all matches), `i` case-insensitive, `m` multiline.

Syntax/example:

```js
const re = /a/gi;
console.log("AaA".match(re)); // ['A','a','A']
```

Output:

```txt
['A','a','A']
```

### Common RegEx Methods (match, replace, test, exec)

- `test()` returns true/false
- `match()` returns matches
- `replace()` replaces matched text
- `exec()` returns capture groups and position

Syntax/example:

```js
const r = /foo(\d)/;
console.log(r.test("foo1")); // true
console.log("foo2".replace(/foo/, "bar")); // 'bar2'
```

Output:

```txt
true
bar2
```

---

## 22. Memory Management

JavaScript automatically frees memory you don't use, but you must avoid patterns that keep memory alive by accident.
Understanding garbage collection helps prevent memory leaks in long-running apps.

### Garbage Collection

The engine finds values that cannot be reached from running code and frees their memory (garbage collection). You don't free memory manually.

Example (concept):

```txt
If no code can reach an object, it becomes eligible for collection.
```

### Memory leaks and prevention

Leaks happen when code keeps references to unused objects (e.g., global caches, forgotten timers). Remove listeners, clear timers, and avoid large globals.

Simple prevention tips:

```txt
- remove event listeners when not needed
- clearInterval / clearTimeout when done
- avoid growing global arrays forever
```

---

## 23. Security

Web security prevents attackers from running bad code or stealing data. Key topics: XSS, CSRF, and input sanitization.
Follow simple rules: never trust user input, escape output, and use safe headers.

### XSS (Cross-Site Scripting)

XSS happens when attackers put script in pages that other users see. Always escape or sanitize HTML from users.

Syntax/example (unsafe):

```js
const html = "<img src=x onerror=alert(1)>";
container.innerHTML = html; // unsafe
```

Safe approach:

```js
container.textContent = html; // treats as text, not HTML
```

### CSRF (Cross-Site Request Forgery)

CSRF tricks a user's browser to send requests they did not intend. Use anti-CSRF tokens or SameSite cookies to protect endpoints.

Concept/example:

```txt
Server includes a secret token in the page, client must send it back with requests.
```

### Input sanitization

Always validate and sanitize input on server-side (and client-side for UX). Use libraries to escape dangerous characters before using input in HTML or database queries.

Simple example:

```js
function escapeHtml(s) {
  return s.replace(
    /[&<>"']/g,
    (c) =>
      ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[
        c
      ])
  );
}
console.log(escapeHtml("<b>hi</b>"));
```

Output:

```txt
&lt;b&gt;hi&lt;/b&gt;
```

---
