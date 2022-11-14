# learning-react

## Why React Re-Renders by Josh W. Comeau

> [Blog post](https://www.joshwcomeau.com/react/why-react-re-renders/)

- "Every re-render in React starts with a state change."
- "The point of a re-render is to figure out how a state change should affect the user interface. (...) we need to re-render all potentially-affected components to get an accurate snapshot."
- Misconceptions:
  - "The entire app re-renders whenever a state variable changes." → "Re-renders only affect the component that owns the state + its descendants (if any)."
  - "A component will re-render because its props change." → "When a component re-renders, it tries to re-render all descendants, regardless of whether they're being passed a particular state variable through props or not."
- "A pure component (...) always produces the same UI when given the same props."
  - Think of a pure component as a _constant_ component (even if parameterized).
- React's main goal is to ensure that the UI is in sync with the application state. "(...) React will err on the side of too many renders. It doesn't want to risk showing the user a stale UI."
- Pure components:
  - Use `React.memo` or the `React.PureComponent` class to define pure components. This way, React will not re-render the component unless its props change.
  - Context is like "invisible/internal props".
- React Developer Tools:
  - Highlight re-renders with flashing green rectangles around components: Chrome DevTools > _Profiler_ > Gear icon > _General_ > Check _Highlight updates when components render._
- React components are JavaScript functions. "When we render a component, we're calling the function. (...) anything defined inside a React component is re-created on every single render."
  - Each time we render the `App` component below, we create a new object. The `DogProfile` component will re-render whether we use `React.memo` or not.

```jsx
function App() {
  const dog = {
    name: "Kanu",
    breed: "Rafeiro do Alentejo",
  };

  return <DogProfile dog={dog} />;
}
```

---

## How React Reconciliation Works by Kingsley Silas

> [Blog post](https://css-tricks.com/how-react-reconciliation-works/)

- Reconciliation: "(...) process through which React updates the DOM."
- [Documentation](https://reactjs.org/docs/reconciliation.html)

---
