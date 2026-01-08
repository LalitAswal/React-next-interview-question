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

### 🔹 Variables & Scope
- `var` vs `let` vs `const`
- Block scope vs function scope
- Temporal Dead Zone (TDZ)

---

### 🔹 Hoisting
- What is hoisting?
- Hoisting behavior of:
  - `var`
  - `let` / `const`
  - functions vs arrow functions

---

### 🔹 Promises & Async JavaScript
- What are Promises?
- Promise states (`pending`, `fulfilled`, `rejected`)
- Promise chaining
- `async` / `await`
- Difference between `Promise.all`, `Promise.allSettled`, `Promise.race`, `Promise.any`

---

### 🔹 Debouncing & Throttling
- What is debouncing?
- What is throttling?
- Key differences between debouncing and throttling
- Real-world use cases (search input, scroll, resize)
- Implement debouncing and throttling **with code**

---

### 🔹 Event Handling & Event Loop
- What is the JavaScript event loop?
- Call stack, task queue, microtask queue
- `setTimeout` vs `Promise`
- Event emitters and pub-sub pattern

---

### 🔹 Objects & Memory
- Different ways to create objects:
  - Object literal
  - `new Object()`
  - Constructor function
  - `Object.create()`
  - ES6 classes
- `Object.freeze()` vs `Object.seal()`
- Shallow copy vs deep copy

---

### 🔹 Function Context
- `call`, `apply`, and `bind`
- Differences between them
- Real-world examples and use cases

---

### 🔹 Collections
- `Map` vs `Set`
- `WeakMap` vs `WeakSet`
- Key differences:
  - Garbage collection
  - Key types
  - Use cases

---

## 🟡 2. JavaScript Output-Based Questions

These questions test **how well you understand JavaScript internals**.

Common patterns:
- Closures
- Hoisting
- Scope
- Async behavior
- `this` keyword

Example:
```js
console.log(typeof null);
```

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

---

## 🟡 3. Data Structures & Algorithms (DSA)

Usually **1–2 questions**, mostly **easy to medium** level.

### Common Topics
- Arrays & strings
- Hash maps
- Sliding window
- Two pointers
- Basic recursion

### Common Questions
- Two Sum
- First non-repeating character
- Longest substring without repeating characters
- Maximum subarray sum
- Reverse a string or array

👉 Focus more on **approach and optimization**, not just the final code.

---

## 🟡 4. React / Next.js Interview Questions

### 🔹 React Basics
- What is React?
- Props vs state
- Controlled vs uncontrolled components
- Component re-rendering
- Virtual DOM

---

### 🔹 React Hooks
- `useState`
- `useEffect`
- `useMemo`
- `useCallback`
- `useRef`
- Custom hooks

---

### 🔹 Performance Optimization
- Preventing unnecessary re-renders
- Memoization
- Lazy loading
- Code splitting

---

### 🔹 Next.js Concepts
- CSR vs SSR vs SSG
- `getServerSideProps`
- `getStaticProps`
- Routing in Next.js
- SEO in Next.js
- Image optimization

---

## ⭐ Key Interview Tip

> **Always start with a simple solution, then optimize it step by step.**

This approach helps you:
- Use interview time effectively
- Show clear thinking
- Demonstrate real-world experience

---

## 📘 Final Notes

Frontend interviews are not only about writing code.  
They are about:
- How you think
- How you explain
- How you improve your solution

Strong fundamentals + clear communication = interview success 🚀