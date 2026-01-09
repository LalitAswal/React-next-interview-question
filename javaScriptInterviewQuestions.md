# 🚀 Frontend Interview Questions List

Frontend interviews usually focus on **core JavaScript knowledge, problem-solving ability, and framework expertise**.  
Based on recent interview patterns, the interview process is generally divided into **two main rounds**, but the questions fall into the following **core categories**.

---

## 📌 Interview Coverage Areas

1. **JavaScript Core Concepts**
2. **JavaScript Output-Based Questions**
3. **Data Structures & Algorithms (DSA)**
4. **React / Next.js Questions**

---

## 🟡 1. JavaScript – Commonly Asked Topics

These topics are almost **mandatory** in frontend interviews. Interviewers use them to judge how strong your fundamentals are.

---

## 🔹 Variables & Scope

### `var` vs `let` vs `const`

| Feature | `var` | `let` | `const` |
|------|------|------|------|
| Scope | Function scoped | Block scoped | Block scoped |
| Re-declare | ✅ Yes | ❌ No | ❌ No |
| Re-assign | ✅ Yes | ✅ Yes | ❌ No |
| Hoisting | Yes (`undefined`) | Yes (TDZ) | Yes (TDZ) |

```js
var a = 10;
let b = 20;
const c = 30;

b = 25;     // allowed
// c = 40;  // ❌ error

```
🔹 Hoisting
What is Hoisting?

Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their scope during the compilation phase.

⚠️ Only declarations are hoisted, not initializations.

Hoisting with var
```js

console.log(a); // undefined
var a = 10;
console.log(a); // 10
```
🔹 Promises & Async JavaScript
What are Promises?
A Promise represents the eventual completion or failure of an asynchronous operation.

```js

const promise = new Promise((resolve, reject) => {
  if (success) {
    resolve("Operation successful");
  } else {
    reject("Operation failed");
  }
});

```
## Promise States
- Pending
- Fulfilled
- Rejected

## Promise Methods Comparison

## Use Case
- **`Promise.all`** 	All succeed	Any fails	Dependent async tasks
- **`Promise.allSettled`**	All settle	Never	Show all results
- **`Promise.race`**	First settles	First fails	Timeouts
- **`Promise.any`**	First success	All fail	Fallback APIs

## Debouncing & Throttling

**`Debouncing`** ensures a function runs only after a delay, once the event stops firing.

### Use Cases
- Search input
- Form validation
- Button clicks

```js
function debounce(fn, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}
```
**`Throttling`** ensures a function runs at most once in a fixed interval, even if the event fires continuously.

### Use Cases
- Scroll events
- Window resize
- Mouse movement

```js
Copy code
function throttle(fn, limit) {
  let isThrottled = false;

  return function (...args) {
    if (!isThrottled) {
      fn(...args);
      isThrottled = true;
      setTimeout(() => isThrottled = false, limit);
    }
  };
}
```
##  Event Handling & Event Loop

- The event loop enables JavaScript to handle asynchronous operations while remaining single-threaded.

Core Components
- Call Stack
- Web APIs
- Microtask Queue (Promises)
- Task Queue (Timers, events)

```js
Copy code
console.log("start");

setTimeout(() => console.log("timeout"), 0);

Promise.resolve().then(() => console.log("promise"));

console.log("end");

Output
start
end
promise
timeout
```

## Event Emitters & Pub-Sub Pattern
Used for event-driven architecture and decoupled communication.

```js

class EventEmitter {
  constructor() {
    this.events = {};
  }

  on(event, fn) {
    (this.events[event] ||= []).push(fn);
  }

  emit(event, data) {
    this.events[event]?.forEach(fn => fn(data));
  }
}
```

## Objects & Memory

Ways to Create Objects

```js

// Object literal
const user = { name: "SKYLTT", age: 28 };

// new Object()
const user2 = new Object();

// Object.create()
const proto = { greet() { console.log("Hello"); } };
const user3 = Object.create(proto);

// ES6 Class
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

```

## Object.freeze() vs Object.seal()


| Feature | `freeze` | `seal` |
|--------|----------|--------|
| Add    | ❌       | ❌     |
| Modify | ❌       | ✅     |
| Delete | ❌       | ❌     |


```js
const user = { name: "skyLTT", age: 25 };

Object.freeze(user);

user.name = "Aman";   // ❌ Not allowed
user.city = "Delhi"; // ❌ Not allowed
delete user.age;     // ❌ Not allowed

console.log(user); // { name: "Lalit", age: 25 }

object.seal()
const user = { name: "Lalit", age: 25 };

Object.seal(user);

user.name = "Aman";   // ✅ Allowed
user.city = "Delhi"; // ❌ Not allowed
delete user.age;     // ❌ Not allowed

console.log(user); // { name: "Aman", age: 25 }
```
## Shallow Copy vs Deep Copy

```js

// Shallow copy
const copy = { ...obj };

// Deep copy
const deepCopy = JSON.parse(JSON.stringify(obj));
```

## Collections
## 🔹 Map vs Set

`Map` and `Set` are ES6 collection types used to store data efficiently, but they serve **different purposes**.

#### 📌 Map
A **Map** stores data as **key–value pairs**.

```js
const map = new Map();
map.set("name", "skyLTT");
map.set(1, "One");

console.log(map.get("name")); // skyLTT
```
#### 📌Set
A **`Set`** stores unique values only **(no duplicates).**
```js
const set = new Set([1, 2, 2, 3]);
console.log(set); // Set {1, 2, 3}
```

## 🔹WeakMap vs WeakSet

**`WeakMap`** and **`WeakSet`** are special collections designed for **memory-efficient object tracking**.

#### Key Characteristics
 
- Keys (or values) must be objects
- Entries are automatically garbage collected
- Not iterable
- No .size property


#### 📌 WeakMap

Stores key–value pairs, where keys must be objects.

```js
const wm = new WeakMap();

let user = { name: "SKyLTT" };
wm.set(user, "private data");

user = null; // eligible for garbage collection

```

##### 📌 WeakSet

Stores objects only as values.

```js
const ws = new WeakSet();

let obj = { id: 1 };
ws.add(obj);

obj = null; // eligible for garbage collection

```
### 🚀 JavaScript Array Methods

Array methods are **one of the most frequently asked topics** in frontend interviews.  
Interviewers use them to test your understanding of **immutability, performance, and problem-solving skills**.

This file covers the **most commonly asked array method differences** with **clear explanations and examples**.

---

### 🔹 `map()` vs `forEach()`

| Feature | `map()` | `forEach()` |
|------|--------|-------------|
| Returns new array | ✅ Yes | ❌ No |
| Mutates original array | ❌ No | ❌ No |
| Use case | Transform data | Side effects |

```js
const arr = [1, 2, 3];

const result = arr.map(x => x * 2); // [2, 4, 6]
arr.forEach(x => console.log(x));   // logs each value
```

### 🔹 `filter()` vs `find()`

Both `filter()` and `find()` are used to **search elements in an array**, but they differ in **return value** and **use case**.

---

### 🔍 Key Differences

| Feature | `filter()` | `find()` |
|------|-----------|---------|
| Returns | Array | Single element |
| Matches | All matching items | First matching item |
| Use case | Multiple results | One result |
| Stops after match | ❌ No | ✅ Yes |



### 🧪 Example

```js
const nums = [1, 2, 3, 4];

nums.filter(n => n > 2); // [3, 4]
nums.find(n => n > 2);   //

```

## 🔹 `slice()` vs `splice()`

Both `slice()` and `splice()` are used to extract elements from an array, but they differ in **mutability** and **purpose**.

### 🔍 Key Differences

| Feature | `slice()` | `splice()` |
|------|----------|------------|
| Mutates original array | ❌ No | ✅ Yes |
| Return value | New array | Removed elements |
| Use case | Extract / copy elements | Add / remove elements |

### 🧪 Example

```js
const arr = [1, 2, 3, 4];

arr.slice(1, 3);   // [2, 3]
arr.splice(1, 2);  // removes [2, 3]
```