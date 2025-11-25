# JavaScript Basics — Part 2

**Table of Contents**

- [7. Objects](#7-objects)
  - [Object Literals](#object-literals)
  - [Accessing and Modifying Object Properties](#accessing-and-modifying-object-properties)
  - [this keyword behavior](#this-keyword-behavior)
  - [Object Methods (Object.keys(), Object.values(), Object.entries())](#object-methods-objectkeys-objectvalues-objectentries)
  - [Object Destructuring](#object-destructuring)
  - [Shallow vs Deep Copy](#shallow-vs-deep-copy)
  - [Prototype and Prototypal Inheritance](#prototype-and-prototypal-inheritance)
- [8. Arrays](#8-arrays)
  - [Array Declaration and Access](#array-declaration-and-access)
  - [Common Array Methods](#common-array-methods)
  - [Array Destructuring](#array-destructuring)
  - [Spread and Rest in Arrays](#spread-and-rest-in-arrays)
- [9. Strings](#9-strings)
  - [String Literals and Template Strings](#string-literals-and-template-strings)
  - [String Methods (length, indexOf, substring, replace, split, etc.)](#string-methods-length-indexof-substring-replace-split-etc)
  - [Template Literals and Interpolation](#template-literals-and-interpolation)
- [12. ES6+ (Modern JavaScript)](#12-es6-modern-javascript)
  - [let, const vs var](#let-const-vs-var)
  - [Template Literals](#template-literals)
  - [Destructuring (Array & Object)](#destructuring-array--object)
  - [Default Parameters](#default-parameters-1)
  - [Spread and Rest Operators](#spread-and-rest-operators-1)
  - [Arrow Functions](#arrow-functions-1)
  - [Modules (import / export)](#modules-import--export)
  - [Classes and Inheritance](#classes-and-inheritance)
  - [Promises](#promises)
  - [Async/Await](#asyncawait)
  - [Generators (function\*)](#generators-function)
  - [Iterators](#iterators)
  - [Symbols](#symbols)
  - [Sets and Maps](#sets-and-maps)
- [13. Error Handling](#13-error-handling)
  - [try, catch, finally](#try-catch-finally)
  - [throw statement](#throw-statement)
  - [Error objects (name, message, stack)](#error-objects-name-message-stack)
  - [Custom Errors](#custom-errors)
- [14. Asynchronous JavaScript](#14-asynchronous-javascript)
  - [Synchronous vs Asynchronous Execution](#synchronous-vs-asynchronous-execution)
  - [Callbacks](#callbacks)
  - [Callback Hell](#callback-hell)
  - [Promises (resolve, reject, then, catch, finally)](#promises-resolve-reject-then-catch-finally)
  - [Async/Await](#asyncawait-1)
  - [Promise Chaining](#promise-chaining)
  - [Parallel Execution (Promise.all, Promise.race)](#parallel-execution-promiseall-promiserace)
- [15. Event Loop and Execution Context](#15-event-loop-and-execution-context)
  - [Call Stack](#call-stack)
  - [Event Loop mechanism](#event-loop-mechanism)
  - [Web APIs](#web-apis)
  - [Microtask and Macrotask Queues](#microtask-and-macrotask-queues)
  - [Job Queue](#job-queue)

---

## 7. Objects

Objects hold named values (properties) and are used to group related data.
They are like real-world objects with attributes and behaviors.

### Object Literals

An object literal is a simple way to create an object using `{}` and key:value pairs.

Syntax:

```js
const obj = { key: value };
```

Example and output:

```js
const person = { name: "Sam", age: 20 };
console.log(person); // { name: 'Sam', age: 20 }
```

### Accessing and Modifying Object Properties

You can get or set properties using dot `.` or bracket `[]` notation.
Brackets let you use variables or keys with spaces.

Syntax:

```js
obj.key;
obj["key"];
obj.key = newValue;
```

Example and output:

```js
person.name = "Samir";
console.log(person.name); // 'Samir'
person["city"] = "Pune";
console.log(person.city); // 'Pune'
```

### this keyword behavior

`this` refers to the object that is calling the function; in plain functions it depends on how the function is called.
Arrow functions do NOT have their own `this` — they use the surrounding `this`.

Syntax/Example:

```js
const obj = {
  x: 1,
  getX() {
    return this.x;
  },
};
console.log(obj.getX()); // 1
```

### Object Methods (Object.keys(), Object.values(), Object.entries())

These methods help list keys, values, or both as arrays for easy iteration.

Syntax and example:

```js
console.log(Object.keys(person)); // ['name','age','city']
console.log(Object.values(person)); // ['Samir',20,'Pune']
console.log(Object.entries(person)); // [['name','Samir'], ['age',20], ['city','Pune']]
```

### Object Destructuring

Destructuring extracts properties into variables with simple syntax and less code.

Syntax and example:

```js
const { name, age } = person;
console.log(name, age); // 'Samir' 20
```

### Shallow vs Deep Copy

A shallow copy copies top-level properties; nested objects still share references. A deep copy clones nested data too.

Example and output (shallow):

```js
const a = { v: { n: 1 } };
const b = { ...a }; // shallow copy
b.v.n = 2;
console.log(a.v.n); // 2 (changed because inner object is shared)
```

Quick deep copy (simple data) using JSON (note: not for functions or special objects):

```js
const deep = JSON.parse(JSON.stringify(a));
deep.v.n = 3;
console.log(a.v.n); // 2 (original unchanged)
```

### Prototype and Prototypal Inheritance

Objects inherit properties from their prototype; this allows sharing methods across many objects.

Syntax and example:

```js
function Person(name) {
  this.name = name;
}
Person.prototype.greet = function () {
  return "Hi " + this.name;
};
const p = new Person("Ria");
console.log(p.greet()); // 'Hi Ria'
```

---

## 8. Arrays

Arrays store ordered lists of values and are zero-indexed (first item is at index 0).
They are useful for collections like lists of names or numbers.

### Array Declaration and Access

Create arrays with `[]` and access items by their numeric index.

Syntax and example:

```js
const arr = [10, 20, 30];
console.log(arr[0]); // 10
arr[1] = 25; // modify
console.log(arr); // [10,25,30]
```

### Common Array Methods:

Below are short examples for common methods; outputs are shown as comments.

- `push()`, `pop()`, `shift()`, `unshift()` — add/remove items at ends.

```js
const a = [1, 2];
a.push(3);
console.log(a); // [1,2,3]
a.pop();
console.log(a); // [1,2]
a.unshift(0);
console.log(a); // [0,1,2]
a.shift();
console.log(a); // [1,2]
```

- `map()`, `filter()`, `reduce()` — transform and combine arrays.

```js
const nums = [1, 2, 3];
console.log(nums.map((x) => x * 2)); // [2,4,6]
console.log(nums.filter((x) => x % 2)); // [1,3]
console.log(nums.reduce((s, x) => s + x, 0)); // 6
```

- `forEach()`, `find()`, `some()`, `every()` — iterate and search.

```js
nums.forEach((x) => console.log(x)); // prints 1 2 3
console.log(nums.find((x) => x > 1)); // 2
console.log(nums.some((x) => x > 2)); // true
console.log(nums.every((x) => x > 0)); // true
```

- `includes()`, `indexOf()`, `slice()`, `splice()` — check and change arrays.

```js
console.log(nums.includes(2)); // true
console.log(nums.indexOf(2)); // 1
console.log(nums.slice(0, 2)); // [1,2]
const b = nums.splice(1, 1, 9); // remove 1 item at idx1, insert 9
console.log(nums); // [1,9,3]
```

### Array Destructuring

Extract values from arrays into variables in one line.

Syntax and example:

```js
const [x, y] = [5, 6];
console.log(x, y); // 5 6
```

### Spread and Rest in Arrays

Use `...` to copy or expand arrays (spread) and to gather remaining items (rest).

Example and output:

```js
const arr1 = [1, 2];
const arr2 = [...arr1, 3];
console.log(arr2); // [1,2,3]
const [first, ...rest] = arr2;
console.log(first, rest); // 1 [2,3]
```

---

## 9. Strings

Strings hold text. Use single, double, or backticks (for templates).
They are used for names, messages, and any text data.

### String Literals and Template Strings

Template strings (backticks) let you put variables inside with `${}` and write multi-line text.

Syntax and example:

```js
const name = "Mira";
const msg = `Hello ${name}`;
console.log(msg); // 'Hello Mira'
```

### String Methods (length, indexOf, substring, replace, split, etc.)

Strings have helpful methods to check length, find text, cut parts, replace text, and split into arrays.

Examples:

```js
const s = "hello world";
console.log(s.length); // 11
console.log(s.indexOf("o")); // 4
console.log(s.substring(0, 5)); // 'hello'
console.log(s.replace("world", "JS")); // 'hello JS'
console.log(s.split(" ")); // ['hello','world']
```

### Template Literals and Interpolation

Template literals let you build strings with variables and expressions easily using backticks.

Syntax and example:

```js
const a = 2,
  b = 3;
console.log(`sum is ${a + b}`); // 'sum is 5'
```

---

## 12. ES6+ (Modern JavaScript)

Modern JavaScript (ES6+) added many features that make code shorter and easier to read.
These features are now commonly used in web apps and Node.js.

### let, const vs var

`var` is function-scoped and hoisted; `let` and `const` are block-scoped and safer. Use `const` for values that don't change.

```js
var a = 1;
let b = 2;
const c = 3;
// c = 4; // error: cannot reassign const
console.log(a, b, c); // 1 2 3
```

### Template Literals

Backticks let you include variables and expressions inside strings with `${}` and write multi-line text.

```js
const name = "Jay";
console.log(`Hello, ${name}!`); // 'Hello, Jay!'
```

### Destructuring (Array & Object)

Extract values from arrays or objects into variables with short syntax.

Array example:

```js
const [x, y] = [10, 20];
console.log(x, y); // 10 20
```

Object example:

```js
const { name, age } = { name: "Tia", age: 21 };
console.log(name, age); // 'Tia' 21
```

### Default Parameters

Set default values for function parameters when callers omit them.

```js
function greet(name = "Guest") {
  return `Hi ${name}`;
}
console.log(greet()); // 'Hi Guest'
```

### Spread and Rest Operators

`...` spreads items from arrays/objects or collects remaining items into an array (rest).

```js
const a = [1, 2];
const b = [...a, 3];
console.log(b); // [1,2,3]
function sum(...nums) {
  return nums.reduce((s, n) => s + n, 0);
}
console.log(sum(1, 2, 3)); // 6
```

### Arrow Functions

Short function syntax using `=>`. Arrow functions do not bind their own `this`.

```js
const sq = (n) => n * n;
console.log(sq(4)); // 16
```

### Modules (import / export)

Use `export` to share code and `import` to load code from other files (ES modules).

```js
// a.js: export const pi = 3.14;
// b.js: import { pi } from './a.js'; console.log(pi);
```

### Classes and Inheritance

`class` gives a clearer way to create constructor functions and use `extends` for inheritance.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }
}
class Dog extends Animal {
  bark() {
    return "woof";
  }
}
const d = new Dog("Max");
console.log(d.name, d.bark()); // 'Max' 'woof'
```

### Promises

A Promise represents a value that may arrive later; use `.then()` to get result and `.catch()` for errors.

```js
const p = new Promise((resolve) => setTimeout(() => resolve("done"), 100));
p.then((r) => console.log(r)); // 'done'
```

### Async/Await

`async` functions let you use `await` to pause until a Promise finishes, making async code look synchronous.

```js
async function run() {
  const r = await p;
  console.log("awaited", r);
}
run(); // 'awaited done'
```

### Generators (function\*)

Generators can pause (`yield`) and resume execution; defined with `function*`.

```js
function* gen() {
  yield 1;
  yield 2;
}
const g = gen();
console.log(g.next().value, g.next().value); // 1 2
```

### Iterators

Iterators provide a way to loop over data; arrays are iterable and work with `for...of`.

```js
for (const v of [1, 2, 3]) console.log(v); // 1 2 3
```

### Symbols

Symbols are unique values used as keys to avoid name collisions on objects.

```js
const s = Symbol("id");
const o = { [s]: 123 };
console.log(o[s]); // 123
```

### Sets and Maps

`Set` stores unique values; `Map` stores key-value pairs with any type of key.

```js
const sset = new Set([1, 2, 2]);
console.log([...sset]); // [1,2]
const m = new Map();
m.set("a", 1);
console.log(m.get("a")); // 1
```

---

## 13. Error Handling

Error handling lets a program catch problems and respond instead of crashing.
Use `try/catch` to handle errors and `throw` to raise them when needed.

### try, catch, finally

Wrap risky code with `try`; handle errors in `catch`; `finally` runs always (cleanup).

```js
try {
  throw new Error("oops");
} catch (e) {
  console.log("caught", e.message);
} finally {
  console.log("done");
}
// Output: 'caught oops' then 'done'
```

### throw statement

Use `throw` to raise an error when something is wrong; catch it with `try/catch`.

```js
function check(x) {
  if (!x) throw "Missing";
}
try {
  check(null);
} catch (e) {
  console.log(e);
} // 'Missing'
```

### Error objects (name, message, stack)

Error objects carry `name`, `message`, and `stack` to help debugging.

```js
const e = new Error("bad");
console.log(e.name, e.message); // 'Error' 'bad'
```

### Custom Errors

Make custom error types by extending `Error` for clearer handling.

```js
class MyError extends Error {
  constructor(msg) {
    super(msg);
    this.name = "MyError";
  }
}
try {
  throw new MyError("fail");
} catch (e) {
  console.log(e.name, e.message);
} // 'MyError' 'fail'
```

---

Asynchronous JavaScript lets work happen later without blocking the main program.
It helps handle slow tasks like network calls or timers.

### Synchronous vs Asynchronous Execution

Synchronous code runs top-to-bottom and waits; asynchronous code starts tasks and continues.

Example and output:

```js
console.log("start");
setTimeout(() => console.log("later"), 0);
console.log("end");
// Output: 'start' then 'end' then 'later'
```

### Callbacks

A callback is a function passed into another function to run later.
Common with timers and older APIs.

Syntax/example:

```js
function greet(cb) {
  cb("Hi");
}
greet((msg) => console.log(msg)); // 'Hi'
```

### Callback Hell

Nesting many callbacks makes code hard to read and maintain.
Use Promises or async/await to avoid deep nesting.

Example (bad):

```js
doA((a) => {
  doB(a, (b) => {
    doC(b, (c) => {
      console.log(c);
    });
  });
});
```

### Promises (resolve, reject, then, catch, finally)

A Promise represents future result. Use `.then()` for success and `.catch()` for errors.

Syntax/example:

```js
const p = new Promise((resolve, reject) => {
  setTimeout(() => resolve("done"), 10);
});
p.then((r) => console.log(r)).catch((e) => console.error(e)); // 'done'
```

### Async/Await

`async` functions let you `await` a Promise, making code look synchronous and easier to read.

Syntax/example:

```js
async function run() {
  const r = await p; // waits for p
  console.log("awaited", r);
}
run(); // 'awaited done'
```

### Promise Chaining

Chain `.then()` calls to run tasks in sequence without nesting.

Example and output:

```js
Promise.resolve(1)
  .then((x) => x + 1)
  .then((x) => console.log(x)); // 2
```

### Parallel Execution (Promise.all, Promise.race)

Run many Promises together with `Promise.all` (wait all) or `Promise.race` (first one wins).

Example:

```js
const a = Promise.resolve(1);
const b = new Promise((res) => setTimeout(() => res(2), 5));
Promise.all([a, b]).then((r) => console.log(r)); // [1,2]
Promise.race([a, b]).then((r) => console.log("race", r)); // race 1
```

---

## 15. Event Loop and Execution Context

The event loop is the engine that lets JavaScript handle async tasks while staying single-threaded.
It manages the call stack and task queues to run code at the right time.

### Call Stack

The call stack tracks function calls; the top is the currently running function.
When stack is empty, the event loop can run queued tasks.

Example (concept):

```js
function a() {
  b();
}
function b() {
  console.log("in b");
}
a(); // call stack: a -> b -> then empty
```

### Web APIs

Browser APIs (timers, fetch, DOM events) run outside the stack and enqueue callbacks when ready.
These are not part of the JavaScript engine but work with the event loop.

Example:

```js
setTimeout(() => console.log("timer"), 0); // timer handled by browser, callback queued later
```

### Event Loop Mechanism

The event loop checks the call stack and task queues, moving tasks to the stack when it's empty.
This is how asynchronous callbacks eventually run.

### Microtask and Macrotask Queues

Microtasks (like Promise callbacks) run before the next macrotask (like setTimeout).
This ordering often surprises beginners.

Example showing order:

```js
console.log("start");
setTimeout(() => console.log("timeout"), 0);
Promise.resolve().then(() => console.log("promise"));
console.log("end");
// Output order: 'start', 'end', 'promise', 'timeout'
```

### Job Queue

Some platforms use the term "job queue" for microtasks. Jobs run right after the current script and before rendering.
Keep microtasks short to avoid blocking rendering.

---

_Notes:_ ES6+ and Error Handling sections added. Tell me if you want more examples or more topics.\*
