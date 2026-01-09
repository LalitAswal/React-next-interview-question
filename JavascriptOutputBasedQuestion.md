# 🚀 JavaScript Output Questions

---

## 🔹 Question 1: String Immutability

### ❓ Code
```js
let a = 'jscafe';
a[0] = 'c';
console.log(a);
```

###### Output
```js
jscafe
```

## 🔹 Question 2: Function Scope vs Global Scope

### ❓ Code
```js
var x = 10;

function foo() {
  var x = 5;
  console.log(x);
}

foo();
console.log(x);
```
###### ✅ Output
```js
5
10
```

### 🔹 Question 3: Event Loop Execution Order

### ❓ Code
```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
});

Promise.resolve().then(() => console.log("Promise"));

console.log("End");

```

##### ✅ Output
```
Start
End
Promise
Timeout
```

### 🔹 Question 4: `try...catch...finally` with `return`

### ❓ Code
```js
function func() {
  try {
    console.log(1);
    return;
  } catch (e) {
    console.log(2);
  } finally {
    console.log(3);
  }
  console.log(4);
}

func();
```

#### ✅ Output
```
1
3
```

### 🔹 Question 5: `forEach()` and `break`

#### ❓ Code
```js
const nums = [1, 2, 3, 4, 5, 6, 7];

nums.forEach((n) => {
  if (n % 2 === 0) {
    break;
  }
  console.log(n);
});

```
##### ❌ Output
```
SyntaxError: Illegal break statement

```

## 🔹 Question 6: Promise Rejection & Chaining

### ❓ Code
```js
function job() {
  return new Promise((resolve, reject) => {
    reject();
  });
}

let promise = job();

promise
  .then(() => {
    console.log("1111111111");
  })
  .then(() => {
    console.log("22222222222");
  })
  .catch(() => {
    console.log("3333333333");
  })
  .then(() => {
    console.log("4444444444");
  });
```

#### ✅ Output

```
3333333333
4444444444
```

## 🔹 JavaScript `typeof` Output Questions

The `typeof` operator is commonly asked in interviews to test understanding of **JavaScript data types** and some of its **well-known quirks**.

---

### ❓ Code
```js
## 🔹 JavaScript `typeof` Output (Inline)

```js
typeof [1, 2, 3, 4];   // object
typeof null;           // object
typeof NaN;            // number
typeof 1234n;          // bigint
typeof 3.14;           // number
typeof Symbol();       // symbol
typeof "John";         // string
typeof 33;             // number
typeof true;           // boolean
typeof undefined;      // undefined
```
