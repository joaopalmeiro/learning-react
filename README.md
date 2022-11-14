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
- Use `React.memo` or the `React.PureComponent` class to define pure components. This way, React will not re-render the component unless its props change.
