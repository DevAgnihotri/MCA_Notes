# JavaScript Basics — Part 4

**Table of Contents**

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

_Notes:_ Sections 20–23 added in the same simple style. I kept explanations short and examples with outputs. Tell me if you want any section simplified further or expanded with exercises.
