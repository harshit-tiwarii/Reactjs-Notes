# ⚛️ React.js Complete Notes

This repository is a **complete reference for React.js**, covering all essential concepts, APIs, hooks, and patterns for beginners to advanced developers.

---

## 📌 Table of Contents

1. [Introduction to React](#1-introduction-to-react)
2. [JSX](#2-jsx)
3. [Components](#3-components)
4. [Props](#4-props)
5. [State](#5-state)
6. [Event Handling](#6-event-handling)
7. [Conditional Rendering](#7-conditional-rendering)
8. [Lists & Keys](#8-lists--keys)
9. [Forms](#9-forms)
10. [useState Hook](#10-usestate-hook)
11. [useEffect Hook](#11-useeffect-hook)
12. [Custom Hooks](#12-custom-hooks)
13. [Context API](#13-context-api)
14. [useReducer Hook](#14-usereducer-hook)
15. [useRef Hook](#15-useref-hook)
16. [React Router](#16-react-router)
17. [Lifting State Up](#17-lifting-state-up)
18. [Code Splitting & Lazy Loading](#18-code-splitting--lazy-loading)
19. [Error Boundaries](#19-error-boundaries)
20. [Forward Refs](#20-forward-refs)
21. [Higher Order Components (HOC)](#21-higher-order-components-hoc)
22. [Controlled vs Uncontrolled Components](#22-controlled-vs-uncontrolled-components)
23. [React.memo, useMemo, useCallback](#23-reactmemo-usememo-usecallback)
24. [Performance Optimization](#24-performance-optimization)
25. [React DevTools](#25-react-devtools)
26. [React with TypeScript (optional)](#26-react-with-typescript-optional)
27. [React + Backend (API Integration)](#27-react--backend-api-integration)
28. [Testing in React](#28-testing-in-react)
29. [Best Practices](#29-best-practices)
30. [Useful Resources](#30-useful-resources)

---

## 1. Introduction to React

- Library for building UI
- Component-based architecture
- Virtual DOM
- Declarative programming

---

## 2. JSX

- JavaScript XML syntax
- Must return a single parent element
- Can embed expressions: `{ 2 + 2 }`

---

## 3. Components

```jsx
function Welcome() {
  return <h1>Hello, React!</h1>;
}
```

---

## 4. Props

- Passed from **parent to child**
- Props are **read-only**

```jsx
function Greet({ name }) {
  return <h1>Hello, {name}</h1>;
}
```

---

## 5. State

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>Clicked {count} times</button>;
}
```

---

## 6. Event Handling

```jsx
function App() {
  const handleClick = () => {
    alert("Button clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
}
```

---

## 7. Conditional Rendering

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 8. Lists & Keys

```jsx
const items = [{ id: 1, name: "Item A" }, { id: 2, name: "Item B" }];

<ul>
  {items.map(item => (
    <li key={item.id}>{item.name}</li>
  ))}
</ul>
```

---

## 9. Forms

```jsx
function Form() {
  const [input, setInput] = useState("");

  const handleChange = (e) => setInput(e.target.value);

  return (
    <form>
      <input type="text" value={input} onChange={handleChange} />
    </form>
  );
}
```

---

## 10. useState Hook

```jsx
const [value, setValue] = useState(initialValue);
```

---

## 11. useEffect Hook

```jsx
useEffect(() => {
  console.log("Component mounted or updated");
  return () => console.log("Cleanup on unmount");
}, [dependency]);
```

---

## 12. Custom Hooks

```jsx
function useCounter() {
  const [count, setCount] = useState(0);
  const increment = () => setCount(prev => prev + 1);
  return { count, increment };
}
```

---

## 13. Context API

```jsx
const ThemeContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Child />
    </ThemeContext.Provider>
  );
}
```

---

## 14. useReducer Hook

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

---

## 15. useRef Hook

```jsx
const inputRef = useRef();
<input ref={inputRef} />
```

---

## 16. React Router

```jsx
<BrowserRouter>
  <Routes>
    <Route path="/" element={<Home />} />
    <Route path="/about" element={<About />} />
  </Routes>
</BrowserRouter>
```

---

## 17. Lifting State Up

Move shared state to the nearest common ancestor.

---

## 18. Code Splitting & Lazy Loading

```jsx
const LazyComponent = React.lazy(() => import('./Component'));
```

---

## 19. Error Boundaries

```jsx
class ErrorBoundary extends React.Component {
  componentDidCatch(error, info) {}
}
```

---

## 20. Forward Refs

```jsx
const FancyInput = React.forwardRef((props, ref) => (
  <input ref={ref} {...props} />
));
```

---

## 21. Higher Order Components (HOC)

```jsx
const withLogger = Component => props => {
  console.log('Rendering:', Component.name);
  return <Component {...props} />;
};
```

---

## 22. Controlled vs Uncontrolled Components

- Controlled: React manages value via state
- Uncontrolled: Value managed by DOM, useRef used

---

## 23. React.memo, useMemo, useCallback

```jsx
const MemoComponent = React.memo(Component);
const memoizedValue = useMemo(() => computeExpensiveValue(), [dep]);
const memoizedCallback = useCallback(() => { ... }, [dep]);
```

---

## 24. Performance Optimization

- Avoid unnecessary re-renders
- Use lazy loading
- Use memoization

---

## 25. React DevTools

Install React DevTools browser extension.

---

## 26. React with TypeScript (optional)

```tsx
type Props = { title: string }
const Header: React.FC<Props> = ({ title }) => <h1>{title}</h1>
```

---

## 27. React + Backend (API Integration)

```jsx
useEffect(() => {
  axios.get('/api/data').then(res => setData(res.data));
}, []);
```

---

## 28. Testing in React

```jsx
test('renders text', () => {
  render(<Component />);
  expect(screen.getByText('Hello')).toBeInTheDocument();
});
```

---

## 29. Best Practices

- Use functional components & hooks
- Split code by features/modules
- Use `.env` for secrets
- Use error boundaries
- Keep components small and focused

---

## 30. Useful Resources

- [React Docs](https://reactjs.org/docs/getting-started.html)
- [React Patterns](https://reactpatterns.com/)
- [React GitHub](https://github.com/facebook/react)
- [Awesome React](https://github.com/enaqx/awesome-react)

---

## 🙌 Contribution

Feel free to fork and contribute!

## 📄 License

MIT
