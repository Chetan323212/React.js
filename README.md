# React.js Learning Roadmap & Interview Preparation

A structured guide to learning React.js from fundamentals to advanced concepts, with practical exercises, interview questions, and a progress checklist.

> **Goal:** Build a strong React foundation, create real-world projects, and prepare for React.js / MERN Stack fresher and junior developer interviews.

---

## Table of Contents

- [How to Use This Repository](#how-to-use-this-repository)
- [React Learning Roadmap](#react-learning-roadmap)
- [1. React Fundamentals](#1-react-fundamentals)
- [2. JSX and Rendering](#2-jsx-and-rendering)
- [3. Components and Props](#3-components-and-props)
- [4. State and Events](#4-state-and-events)
- [5. Conditional Rendering and Lists](#5-conditional-rendering-and-lists)
- [6. Hooks](#6-hooks)
- [7. Forms and Validation](#7-forms-and-validation)
- [8. Component Composition and Data Flow](#8-component-composition-and-data-flow)
- [9. React Router](#9-react-router)
- [10. API Calls and Async JavaScript](#10-api-calls-and-async-javascript)
- [11. State Management](#11-state-management)
- [12. Context API and Reducers](#12-context-api-and-reducers)
- [13. Performance Optimization](#13-performance-optimization)
- [14. Custom Hooks](#14-custom-hooks)
- [15. Error Handling and Debugging](#15-error-handling-and-debugging)
- [16. Styling in React](#16-styling-in-react)
- [17. Testing](#17-testing)
- [18. Accessibility](#18-accessibility)
- [19. Advanced React Concepts](#19-advanced-react-concepts)
- [20. Tooling and Project Structure](#20-tooling-and-project-structure)
- [Practice Projects](#practice-projects)
- [Interview Preparation Checklist](#interview-preparation-checklist)
- [Common Interview Questions](#common-interview-questions)
- [Recommended Learning Order](#recommended-learning-order)
- [Useful Resources](#useful-resources)

---

## How to Use This Repository

For each topic:

1. **Understand** the concept and why it exists.
2. **Code** a small example without copying blindly.
3. **Practice** by adding the concept to a project.
4. **Explain** the concept in your own words, as if answering an interviewer.
5. **Revise** the important questions and mark the checklist when confident.

**Importance levels**
- ⭐⭐⭐ — Essential: know it well for projects and interviews.
- ⭐⭐ — Important: understand and practise it.
- ⭐ — Further learning: learn after the fundamentals.

## React Learning Roadmap

| Stage | Focus | Outcome |
|---|---|---|
| 1 | JavaScript prerequisites | Be comfortable with arrays, objects, functions, modules, destructuring, promises, and array methods |
| 2 | React fundamentals | Build components and understand props, state, events, and rendering |
| 3 | Hooks and forms | Manage component logic, effects, and user input |
| 4 | APIs and routing | Build multi-page applications that load remote data |
| 5 | Shared state | Share and organize state across components |
| 6 | Performance and testing | Diagnose unnecessary work and test important behaviour |
| 7 | Advanced concepts | Understand rendering, Suspense, lazy loading, and server-rendering concepts |
| 8 | Projects and interviews | Build, explain, and improve complete applications |

---

## 1. React Fundamentals

**Importance:** ⭐⭐⭐

### What to learn
- What React is and which problems it solves
- Declarative UI and component-based architecture
- Single-page application (SPA) basics
- Virtual DOM as a conceptual model; how React updates the UI
- Reconciliation and rendering at a high level
- Creating a project with Vite
- Understanding `src`, `public`, `package.json`, and `node_modules`
- Running the development server and production build

### Why it matters
These ideas help you explain why React is useful and how a React project is organized.

### Practice
Create a small page with a heading, profile card, and reusable button.

### Interview focus
- What is React, and why is it used?
- What is a component-based UI?
- What is the difference between a library and a framework?
- What is the Virtual DOM? Avoid claiming every update is automatically faster than direct DOM manipulation.

---

## 2. JSX and Rendering

**Importance:** ⭐⭐⭐

### What to learn
- JSX syntax and JavaScript expressions inside `{ }`
- JSX attributes such as `className`
- Fragments: `<>...</>`
- Rendering text, elements, and expressions
- Differences between JSX and HTML
- Why components must return valid renderable content
- Basic understanding of how JSX is transformed by build tools

### Why it matters
JSX is the syntax most React developers use to describe UI.

### Practice
Create a product card using dynamic title, price, and availability values.

### Interview focus
- What does JSX stand for?
- Can you use `if` statements directly inside JSX?
- Why do we use `className` instead of `class`?
- What is the purpose of a Fragment?

---

## 3. Components and Props

**Importance:** ⭐⭐⭐

### What to learn
- Function components
- Naming components with a capital letter
- Reusable components and single responsibility
- Passing props from parent to child
- Destructuring props
- Default values for props
- Passing functions and JSX as props
- The special `children` prop
- One-way data flow
- Why props should be treated as read-only

### Why it matters
Reusable components make applications easier to maintain, test, and extend.

### Practice
Build reusable `Navbar`, `ProfileCard`, `ProductCard`, and `Button` components.

### Interview focus
- What are props?
- Props vs state
- What is `children`?
- Can a child component directly modify its parent's props?
- How do you reuse a component with different data?

---

## 4. State and Events

**Importance:** ⭐⭐⭐

### What to learn
- Handling click, input, submit, and other events
- `useState`
- State as a snapshot for a particular render
- Updating state instead of directly mutating it
- Functional state updates
- Why state updates may be batched
- Updating objects and arrays immutably
- Lifting state up when multiple components need the same state

### Why it matters
State allows the UI to respond to user actions and changing application data.

### Practice
Build a counter, toggle button, quantity selector, and editable task list.

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  function increment() {
    setCount(currentCount => currentCount + 1);
  }

  return (
    <button onClick={increment}>
      Count: {count}
    </button>
  );
}

export default Counter;
```

### Interview focus
- What is state?
- Why should state not be mutated directly?
- Why use a functional update such as `setCount(c => c + 1)`?
- Why might logging state immediately after calling a setter show the previous render's value?
- What is lifting state up?

---

## 5. Conditional Rendering and Lists

**Importance:** ⭐⭐⭐

### What to learn
- Conditional UI with `if`, ternary expressions, and `&&`
- Rendering arrays with `map()`
- Filtering and sorting data before rendering
- Why each list item needs a stable `key`
- Why array indexes can be problematic as keys for changing lists
- Empty, loading, error, and success states

### Why it matters
Nearly every practical application displays collections of data and different UI states.

### Practice
Build a searchable task list with filters, an empty state, and delete functionality.

### Interview focus
- How do you render a list in React?
- Why are keys important?
- Why can an array index be a poor key?
- What is the difference between `map()` and `filter()`?
- How do you show a fallback when a list is empty?

---

## 6. Hooks

**Importance:** ⭐⭐⭐

Hooks let function components use React features. Learn the common hooks first, then explore advanced ones as needed.

| Hook | Purpose | Importance |
|---|---|---|
| `useState` | Store local component state | Essential |
| `useEffect` | Synchronize with external systems | Essential |
| `useContext` | Read context values | Essential |
| `useRef` | Hold a mutable value or DOM reference without triggering a render | Important |
| `useReducer` | Manage state transitions with a reducer | Important |
| `useMemo` | Cache a calculated value when appropriate | Important |
| `useCallback` | Cache a function definition when appropriate | Important |
| Custom hooks | Reuse stateful logic between components | Important |
| `useId` | Generate IDs suitable for accessibility relationships | Useful |
| `useTransition` | Mark certain updates as non-urgent | Advanced |
| `useDeferredValue` | Defer updating part of the UI | Advanced |
| `useLayoutEffect` | Run an effect before browser repaint when layout timing requires it | Advanced |
| `useSyncExternalStore` | Subscribe to an external store | Advanced |

### Rules of Hooks
- Call hooks at the top level of a function component or custom hook.
- Do not call hooks inside loops, conditions, or nested ordinary functions.
- Use hooks only from React function components or custom hooks.
- Follow the Rules of Hooks linting guidance.

### Interview focus
- What are hooks?
- What are the Rules of Hooks?
- `useState` vs `useRef`
- `useEffect` vs `useLayoutEffect`
- `useMemo` vs `useCallback`
- When should you avoid adding `useMemo` or `useCallback`?

---

## 7. Forms and Validation

**Importance:** ⭐⭐⭐

### What to learn
- Controlled inputs using state
- Uncontrolled inputs using refs or browser form behaviour
- `value` vs `defaultValue`
- Handling `onChange` and `onSubmit`
- Input validation and helpful error messages
- Required fields, email formats, and password rules
- Checkbox, radio, select, and textarea inputs
- Preventing the default form submission when appropriate
- Form libraries such as React Hook Form (learn after the basics)

### Why it matters
Login, registration, search, checkout, and profile screens all depend on forms.

### Practice
Build a registration form with validation, field-level errors, and a success message.

### Interview focus
- Controlled vs uncontrolled components
- How do you handle form submission?
- How do you validate form data?
- Why is `event.preventDefault()` used in some form handlers?

---

## 8. Component Composition and Data Flow

**Importance:** ⭐⭐⭐

### What to learn
- Parent-to-child data flow through props
- Child-to-parent communication through callback props
- Lifting state up
- Component composition and `children`
- Separating UI from application logic
- Avoiding deeply threaded props when context is a better fit
- Choosing component boundaries

### Why it matters
Good data flow keeps a growing application predictable and easier to debug.

### Practice
Build a shopping cart where product cards call a parent handler to add products to the cart.

### Interview focus
- How can a child communicate with a parent?
- What is prop drilling?
- What does lifting state up mean?
- Composition vs inheritance in React component design?

---

## 9. React Router

**Importance:** ⭐⭐⭐ for multi-page applications

### What to learn
- Installing and configuring React Router
- Routes and route elements
- `Link` and `NavLink`
- URL parameters with `useParams`
- Navigation with `useNavigate`
- Nested routes and layouts
- Query parameters and search parameters
- Not-found routes
- Protected-route patterns and authentication checks
- Loading route data and handling navigation states, where supported by the chosen router setup

### Why it matters
Most real-world applications need multiple screens and URL-based navigation.

### Practice
Build a small store with Home, Products, Product Details, Cart, Login, and Not Found pages.

### Interview focus
- What is client-side routing?
- `Link` vs a normal anchor element
- How do you read a URL parameter?
- How do nested routes work?
- How should protected routes be designed?

---

## 10. API Calls and Async JavaScript

**Importance:** ⭐⭐⭐

### What to learn
- `fetch()` and the basics of Axios
- Promises, `async`, and `await`
- HTTP methods: GET, POST, PUT, PATCH, DELETE
- JSON request and response bodies
- HTTP status codes
- Loading, success, empty, and error states
- `try/catch/finally`
- Effect cleanup and avoiding stale results
- Cancelling requests with `AbortController`
- Basic authentication headers and environment variables
- Pagination, search, filtering, and debouncing
- Avoiding exposure of private secrets in frontend code

### Why it matters
React applications commonly read and update data through backend APIs.

### Example

```jsx
import { useEffect, useState } from "react";

function Users() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState("");

  useEffect(() => {
    const controller = new AbortController();

    async function loadUsers() {
      try {
        const response = await fetch(
          "https://jsonplaceholder.typicode.com/users",
          { signal: controller.signal }
        );

        if (!response.ok) {
          throw new Error("Could not load users");
        }

        const data = await response.json();
        setUsers(data);
      } catch (err) {
        if (err.name !== "AbortError") {
          setError(err.message || "Something went wrong");
        }
      } finally {
        if (!controller.signal.aborted) {
          setLoading(false);
        }
      }
    }

    loadUsers();
    return () => controller.abort();
  }, []);

  if (loading) return <p>Loading users...</p>;
  if (error) return <p role="alert">{error}</p>;

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}

export default Users;
```

### Interview focus
- How do you fetch data in React?
- Why check `response.ok` with `fetch()`?
- How do you show loading and error states?
- Why does an effect sometimes need cleanup?
- How can you prevent a stale request from updating the UI?

---

## 11. State Management

**Importance:** ⭐⭐⭐

### What to learn
- Local state vs shared state vs server state
- Lifting state up for nearby components
- Context API for values shared across a component tree
- `useReducer` for more structured transitions
- Redux Toolkit fundamentals
- When a small app does not need a global state library
- Server-state tools such as TanStack Query (optional, valuable for API-heavy apps)
- Avoiding duplicate state and keeping state minimal

### Why it matters
State management becomes important when multiple screens depend on the same data.

### Practice
Implement a cart shared by product, navbar, and checkout components. Start with lifting state up, then try Context or a reducer.

### Interview focus
- What problem does state management solve?
- Local state vs global state
- Context API vs Redux Toolkit
- Client state vs server state
- When is a global store unnecessary?

---

## 12. Context API and Reducers

**Importance:** ⭐⭐

### What to learn
- Creating context with `createContext`
- Providing values with a context provider
- Reading context with `useContext`
- Creating a reducer function
- `useReducer` with actions and state transitions
- Splitting context by responsibility
- Understanding that context consumers can re-render when the provided value changes

### Why it matters
Context helps avoid passing the same props through many intermediate components. Reducers can make complex state transitions clearer.

### Practice
Build a theme switcher and a cart reducer with `ADD_ITEM`, `REMOVE_ITEM`, and `CLEAR_CART` actions.

### Interview focus
- What is Context API?
- What is prop drilling?
- What are reducers and actions?
- Context vs Redux
- How can context-related re-renders be reduced?

---

## 13. Performance Optimization

**Importance:** ⭐⭐ to ⭐⭐⭐

### What to learn
- Measuring performance before optimizing
- React DevTools Profiler
- `React.memo`
- `useMemo` and `useCallback`
- Avoiding unnecessary state and effects
- Keeping state close to where it is used
- Lazy loading with `React.lazy` and `Suspense`
- Code splitting
- Large-list rendering and virtualization
- Debouncing search inputs
- Stable keys and avoiding needless remounts
- Image and bundle optimization

### Why it matters
Performance knowledge helps you diagnose slow interactions instead of adding optimizations blindly.

### Practice
Create a large searchable list, measure it, and compare the result before and after an appropriate optimization.

### Interview focus
- What causes a component to re-render?
- What does `React.memo` do?
- `useMemo` vs `useCallback`
- What is code splitting?
- What is lazy loading?
- How do you investigate a slow React page?

**Important:** Memoization is not automatically beneficial. Measure first and optimize when there is a real reason.

---

## 14. Custom Hooks

**Importance:** ⭐⭐

### What to learn
- Extracting reusable stateful logic
- Naming custom hooks with `use`
- Using built-in hooks inside custom hooks
- Returning values and handlers from a custom hook
- Keeping hooks focused and predictable

### Why it matters
Custom hooks reduce duplicated logic without forcing unrelated UI into one component.

### Practice
Create `useLocalStorage`, `useDebounce`, `useFetch` (with proper cleanup), or `useOnlineStatus`.

### Interview focus
- What is a custom hook?
- Custom hook vs component
- Can a custom hook share state between separate component instances?
- How do you follow the Rules of Hooks in a custom hook?

---

## 15. Error Handling and Debugging

**Importance:** ⭐⭐

### What to learn
- React Developer Tools
- Browser console and Network tab
- Reading stack traces
- Error boundaries and their purpose
- Handling API errors explicitly
- Empty states and fallback UI
- Strict Mode behaviour during development
- Debugging state, props, keys, and effect dependencies

### Why it matters
Debugging is a daily developer task and a common topic in technical interviews.

### Practice
Intentionally create a missing-key warning, a failed API request, and an invalid component state, then diagnose and fix each issue.

### Interview focus
- What is an error boundary?
- Do error boundaries catch errors in event handlers or ordinary asynchronous callbacks?
- What does Strict Mode help detect?
- How do you debug a component that is not updating as expected?

---

## 16. Styling in React

**Importance:** ⭐⭐⭐

### What to learn
- Regular CSS and CSS Modules
- Conditional class names
- Responsive design and media queries
- Flexbox and CSS Grid
- Tailwind CSS or a component library
- Theme variables and dark mode
- Styling states such as hover, focus, disabled, and invalid
- Avoiding unnecessarily complicated style logic

### Why it matters
A working application should also be responsive, accessible, and consistent.

### Practice
Create a responsive dashboard with navigation, cards, forms, and a mobile layout.

### Interview focus
- What are common ways to style React components?
- CSS Modules vs global CSS
- How do you apply conditional classes?
- How do you make a React page responsive?

---

## 17. Testing

**Importance:** ⭐⭐

### What to learn
- Why tests matter
- Unit, integration, and end-to-end testing
- Vitest or Jest fundamentals
- React Testing Library
- Testing user-visible behaviour
- Testing forms, loading states, and API failures
- Mocking network requests
- Basic end-to-end testing with Playwright or Cypress

### Why it matters
Testing catches regressions and gives confidence when changing application code.

### Practice
Write tests for a counter, registration form, and API-driven user list.

### Interview focus
- Unit testing vs integration testing
- What is React Testing Library?
- Why test behaviour rather than implementation details?
- How would you test a loading state and an API error?

---

## 18. Accessibility

**Importance:** ⭐⭐

### What to learn
- Semantic HTML
- Labels for form controls
- Keyboard navigation
- Visible focus indicators
- Accessible button and link names
- Useful alternative text for images
- ARIA only when native HTML is not sufficient
- Accessible validation and error messages
- Colour contrast and reduced-motion preferences

### Why it matters
Accessible interfaces are easier for more people to use and generally have better structure.

### Practice
Navigate your project using only a keyboard and check form labels, focus states, and image alternatives.

### Interview focus
- What is semantic HTML?
- Why should a clickable action usually be a button rather than a clickable `div`?
- When should you use ARIA?
- How do you make a form accessible?

---

## 19. Advanced React Concepts

**Importance:** ⭐ to ⭐⭐⭐ depending on the role

Learn these after you are comfortable building complete applications.

- **Rendering and reconciliation:** how React decides what needs updating.
- **State preservation and component identity:** how component position and keys affect state.
- **Portals:** render UI in another part of the DOM, often for dialogs.
- **Suspense:** show a fallback while supported work is not ready.
- **Lazy loading:** load component code when it is needed.
- **Transitions:** mark certain updates as non-urgent.
- **Refs and imperative handles:** expose limited imperative behaviour when necessary.
- **Hydration:** attach React behaviour to server-rendered HTML.
- **Server-side rendering (SSR) and static generation:** understand the concepts and their trade-offs.
- **React Server Components:** understand the server/client boundary in frameworks that support them.
- **Frameworks such as Next.js:** routing, rendering strategies, data loading, and deployment.
- **Security basics:** avoid rendering untrusted HTML and understand that frontend code cannot keep secrets.

### Interview focus
Prioritize rendering, keys, refs, Suspense/lazy loading, and performance first. Learn framework-specific server rendering and Server Components when the role requires them.

---

## 20. Tooling and Project Structure

**Importance:** ⭐⭐⭐ for day-to-day development

### What to learn
- npm and package scripts
- Vite development server and production builds
- ES modules: `import` and `export`
- Environment variables and `.env` conventions
- ESLint and formatting tools
- Git and GitHub workflow
- Browser DevTools
- React Developer Tools
- Organizing components, hooks, pages, services, and utilities
- Deployment and build-time configuration

### Example structure

```text
src/
├── assets/
├── components/
├── pages/
├── hooks/
├── context/
├── services/
├── utils/
├── App.jsx
└── main.jsx
```

Adapt the structure to the size of the project; small projects do not need every folder.

### Interview focus
- What is Vite?
- What is the purpose of `package.json`?
- Named exports vs default exports
- How do you configure environment variables?
- What is the difference between development and production builds?

---

## JavaScript Prerequisites

Before going deep into React, make sure you can use:

- `let`, `const`, data types, operators, and scope
- Function declarations, arrow functions, and callbacks
- Arrays and objects
- `map`, `filter`, `find`, `reduce`, and `forEach`
- Destructuring, spread syntax, and rest parameters
- Template literals and optional chaining
- ES modules and imports/exports
- DOM and event basics
- Promises, `async/await`, and `try/catch`
- Basic HTTP, JSON, and REST API concepts
- Immutability and reference types

**Self-check:** Can you fetch an array of objects, filter it, and render it with `map()`? If not, practise that before moving to API-driven React projects.

---

## Practice Projects

Build projects in increasing difficulty. Add a README, screenshots, setup steps, and a clear list of features to each repository.

| Level | Project | Concepts to practise |
|---|---|---|
| Beginner | Counter and theme switcher | Components, events, state |
| Beginner | Todo list | Lists, keys, forms, filters, local storage |
| Beginner | Profile/product cards | Props, composition, reusable UI |
| Intermediate | Weather dashboard | API calls, loading, errors, search |
| Intermediate | Expense tracker | Forms, derived data, charts, persistence |
| Intermediate | Movie search app | API calls, routing, pagination, debouncing |
| Intermediate | Admin dashboard | Routing, reusable components, responsive UI |
| Intermediate | Shopping cart | Shared state, reducers/context, cart totals |
| Advanced | E-commerce application | Authentication flow, routes, API integration, cart, checkout UI |
| Advanced | MERN task manager | React, Node.js, Express, MongoDB, validation, REST APIs |
| Advanced | AI code-review interface | Forms, API integration, loading/errors, review history |

For portfolio projects, document the problem, key features, technical decisions, challenges, and what you learned. Do not claim features or results you have not implemented.

---

## Interview Preparation Checklist

Use this checklist to track your progress.

### Fundamentals
- [ ] I can explain React and component-based architecture.
- [ ] I can write JSX and explain fragments.
- [ ] I can build reusable components and pass props.
- [ ] I understand props vs state.
- [ ] I can handle events and update state immutably.
- [ ] I can render, filter, and update lists with stable keys.

### Hooks and Forms
- [ ] I can use `useState` and explain functional updates.
- [ ] I can explain `useEffect`, dependencies, and cleanup.
- [ ] I know the Rules of Hooks.
- [ ] I can explain `useRef`, `useContext`, and `useReducer`.
- [ ] I can build and validate a controlled form.
- [ ] I can create a custom hook.

### APIs and Routing
- [ ] I can use `fetch` with `async/await`.
- [ ] I can handle loading, success, empty, and error states.
- [ ] I understand HTTP methods and common status codes.
- [ ] I can create routes, nested routes, and URL parameters.
- [ ] I can explain authentication-related UI and protected routes.

### Shared State and Performance
- [ ] I understand lifting state up and prop drilling.
- [ ] I can explain Context API vs Redux Toolkit.
- [ ] I understand `React.memo`, `useMemo`, and `useCallback`.
- [ ] I can use React DevTools to investigate re-renders.
- [ ] I understand lazy loading and code splitting.

### Professional Readiness
- [ ] I can explain at least two projects without reading the code.
- [ ] I can debug a broken component.
- [ ] I can use Git and publish a project on GitHub.
- [ ] I can write basic component tests.
- [ ] I can build a responsive and accessible interface.
- [ ] I can explain trade-offs rather than only memorizing definitions.

---

## Common Interview Questions

Prepare a short answer, a practical example, and any relevant trade-offs for each.

1. **What is React?**  
   React is a JavaScript library for building user interfaces from reusable components.

2. **What is JSX?**  
   JSX is a JavaScript syntax extension that lets developers describe UI with markup-like syntax.

3. **What are props?**  
   Props are read-only inputs passed to a component, commonly from a parent component.

4. **What is state?**  
   State is data React tracks for a component; updating it can cause React to render the component again.

5. **Props vs state?**  
   Props are supplied to a component; state is managed by the component or its state-management logic.

6. **Why are keys used in lists?**  
   Keys help React match list items between renders. Stable, unique keys help preserve the correct item identity.

7. **What is `useEffect` used for?**  
   It synchronizes a component with external systems, such as subscriptions, timers, or network-related effects. It is not needed for every calculation or event.

8. **What is the dependency array in `useEffect`?**  
   It tells React which reactive values the effect depends on. The effect re-synchronizes when a dependency changes.

9. **What is prop drilling?**  
   Prop drilling is passing data through intermediate components that do not otherwise need it.

10. **What is Context API?**  
    Context allows components to read a value provided higher in the component tree without manually passing it through every level.

11. **What is a controlled component?**  
    A controlled input gets its current value from React state and updates that state through an event handler.

12. **What is a custom hook?**  
    A custom hook is a JavaScript function starting with `use` that composes React hooks to reuse logic.

13. **What is the difference between `useMemo` and `useCallback`?**  
    `useMemo` caches a calculated value; `useCallback` caches a function definition. Use them when there is a meaningful benefit.

14. **What is `useRef` used for?**  
    It holds a value across renders without causing a render when changed, and it can reference a DOM element.

15. **How do you handle API errors?**  
    Check the response status, catch failures, maintain loading and error state, and show useful feedback to the user.

16. **What is React Router?**  
    It is a routing library commonly used to map URLs to UI in React applications.

17. **What is an error boundary?**  
    An error boundary displays fallback UI when descendant components throw during rendering or certain lifecycle work. It does not catch every event-handler or asynchronous error.

18. **How do you improve React performance?**  
    Measure first, then address unnecessary rendering, expensive calculations, large bundles, or large lists using appropriate techniques.

19. **What is `React.memo`?**  
    It can skip re-rendering a component when its props are unchanged, subject to React's behaviour and the component's other inputs.

20. **What is the difference between client state and server state?**  
    Client state belongs to UI behaviour, such as an open menu; server state is data fetched from and kept in sync with a backend.

21. **What is `useReducer`?**  
    It manages state through a reducer function that receives the current state and an action and returns the next state.

22. **What is the purpose of Strict Mode?**  
    In development, it helps reveal certain bugs by checking components and effects more rigorously. Some work may run an extra time during development checks.

23. **What is lazy loading?**  
    Lazy loading delays loading a component's code until it is needed, often using `React.lazy` and `Suspense`.

24. **Why should state not be mutated directly?**  
    React relies on updates and identity comparisons; mutating existing state can lead to incorrect or missed UI updates and makes changes harder to reason about.

25. **How does a React frontend connect to a MERN backend?**  
    The frontend sends HTTP requests to API endpoints exposed by a Node.js/Express backend. The backend validates requests, works with MongoDB, and returns responses that React uses to update the UI.

---

## Recommended Learning Order

1. JavaScript prerequisites
2. JSX, components, and props
3. State, events, lists, and conditional rendering
4. Hooks: `useState`, `useEffect`, `useRef`
5. Forms and validation
6. API integration and async JavaScript
7. React Router
8. Context API and `useReducer`
9. Custom hooks and local persistence
10. Performance fundamentals
11. Testing and accessibility
12. Advanced concepts and Next.js as needed
13. Build and deploy two or three complete projects
14. Practise interview questions and explain your projects aloud

**Study tip:** For every topic, write one example yourself, explain it in simple language, and apply it to a project. Understanding when and why to use a feature is more valuable than memorizing its definition.

---

## Useful Resources

- [React Official Documentation](https://react.dev/learn)
- [React API Reference](https://react.dev/reference/react)
- [React Router Documentation](https://reactrouter.com/)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Vite Documentation](https://vite.dev/guide/)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
- [Vitest Documentation](https://vitest.dev/guide/)
- [Redux Toolkit Documentation](https://redux-toolkit.js.org/)
- [TanStack Query Documentation](https://tanstack.com/query/latest/docs/framework/react/overview)
- [Next.js Documentation](https://nextjs.org/docs)

---

## Final Goal

By completing this roadmap, aim to be able to:

- Explain React fundamentals clearly in an interview.
- Build reusable, responsive components.
- Manage state, forms, routing, and API requests.
- Debug and test common application behaviour.
- Make sensible performance and accessibility decisions.
- Build and explain complete projects that demonstrate your skills.

**Keep learning, keep building, and update this README as you complete each topic.**
