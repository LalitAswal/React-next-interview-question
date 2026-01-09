# 🚀 React  Interview Questions with Solutions

This document contains **20 frequently asked React & Next.js interview questions** with **clear explanations and practical code examples**, aligned with **2025 frontend interview trends**.

---

## 1️⃣ What is React and why is it used?

### ✅ Answer
React is a **JavaScript library for building user interfaces**, mainly used for single-page applications.

**Why React?**
- Component-based architecture
- Reusable UI components
- Virtual DOM for better performance

---

## 2️⃣ What is the Virtual DOM?

### ✅ Answer
The Virtual DOM is a **lightweight copy of the real DOM**. React compares changes (diffing) and updates only the required parts (reconciliation), improving performance.

---

## 3️⃣ What are Props in React?

### ✅ Answer
Props are **read-only data** passed from parent to child components.

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}</h1>;
}
```

### 4️⃣ What is State in React?
### ✅ Answer

State is mutable data managed inside a component to control UI behavior.
```
const [count, setCount] = useState(0);
```


### 5️⃣ Difference between State and Props?

| Feature | State | Props |
|-------|-------|-------|
| Mutable | ✅ Yes | ❌ No |
| Owned by | Component | Parent |
| Controlled by | Component itself | Parent component |
| Purpose | Manage UI logic & local data | Pass data to child components |
| Can trigger re-render | ✅ Yes | ✅ Yes (when props change) |


### 6️⃣ What are React Hooks?
### ✅ Answer

Hooks allow using state and **`lifecycle features in functional components`**.

Common hooks:

useState

useEffect

useContext

useMemo

useCallback

### 7️⃣ What is useEffect?
### ✅ Answer

useEffect is used to handle side effects such as API calls, subscriptions, or DOM updates.
```
useEffect(() => {
  fetchData();
}, []);
```

### 8️⃣ What is the dependency array in useEffect?
#### ✅ Answer

It controls when the effect runs.
```
useEffect(() => {
  console.log(count);
}, [count]);
```

### 9️⃣ What is useMemo?
### ✅ Answer

useMemo memoizes expensive calculations to prevent unnecessary re-computation.
```
const total = useMemo(() => calculateTotal(items), [items]);
```

### 🔟 What is useCallback?
### ✅ Answer

useCallback memoizes functions, preventing unnecessary re-renders.
```
const handleClick = useCallback(() => {
  setCount(c => c + 1);
}, []);
```

#### 1️⃣1️⃣ What is the Context API?
#### ✅ Answer

Context API helps avoid prop drilling by sharing data globally.
```    
const ThemeContext = createContext();
```

####1️⃣2️⃣ What is Prop Drilling?
#### ✅ Answer

Passing props through multiple component levels unnecessarily.

Solutions:

Context API

State management libraries (Redux, Zustand)

#### 1️⃣3️⃣ What causes unnecessary re-renders?

### **Causes**

- Inline functions
- New object/array references
- Context updates
- Missing memoization

### **Prevention**

- React.memo
- useMemo, useCallback
- Proper state colocation

#### 1️⃣4️⃣ Why does React Strict Mode render twice?
#### ✅ Answer

To detect:

Side effects

Unsafe lifecycle usage

📌 Happens only in development mode.
