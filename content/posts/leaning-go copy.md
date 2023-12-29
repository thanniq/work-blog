+++
author = "Thanni"
title = "React Hooks"
date = "2023-12-28"
description = "Learning React"
tags = [
    "react",
]
categories = [
    "Tutorial",
]
series = ["FrontEnd Development"]
+++

Learn the fundamentals of React, exploring its syntax, features, and practical applications.

<!--more-->

## Hook Rules

1. Only Call Hooks at the Top Level
2. Only Call Hooks from React Functions
3. Use Hooks in the Same Order
4. Custom Hooks Should Start with "use"

## useState Hook

The `useState` hook is fundamental in React for adding state to functional components. It returns an array with two elements: the current state value and a function to update it. Key points about `useState` include:

1. **Managing Component State:**

   - `useState` allows functional components to have local state, enabling them to manage and respond to changes.

2. **Defining State and Updaters:**

   - Use array destructuring to define state variables and their corresponding updater functions.

   ```jsx
   const [count, setCount] = useState(0);
   ```

3. **Immutable State Updates:**

   - State updates must be performed immutably, either by using the previous state value or a callback function.

   ```jsx
   setCount((prevCount) => prevCount + 1);
   ```

4. **Initializing State:**

   - Pass the initial state as an argument to `useState`.

   ```jsx
   const [isOpen, setIsOpen] = useState(false);
   ```

5. **Multiple State Variables:**

   - You can use multiple `useState` calls to manage different pieces of state.

   ```jsx
   const [name, setName] = useState("");
   const [age, setAge] = useState(0);
   ```

Example usage:

```jsx
import React, { useState } from "react";

function Counter() {
  // Defining state variable 'count' and its updater 'setCount'
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      {/* Updating state on button click */}
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```

The `useState` hook provides a simple and effective way to introduce and manage state in functional components, enabling dynamic and interactive UIs.

## useEffect Hook

The `useEffect` hook is essential for performing side effects in functional components. It allows you to execute code in response to component lifecycle events. Key points about `useEffect` include:

1. **Lifecycle Events:**

   - `useEffect` is used to manage side effects in functional components, such as data fetching, subscriptions, or manually changing the DOM.

2. **Component Did Mount:**

   - Code inside `useEffect` runs after the initial render, mimicking the behavior of `componentDidMount` in class components.

   ```jsx
   useEffect(() => {
     // Code to run after the initial render
   }, []);
   ```

3. **Component Did Update:**

   - `useEffect` also runs after every update, similar to `componentDidUpdate`. You can conditionally execute code based on changes in specific dependencies.

   ```jsx
   useEffect(() => {
     // Code to run after each render/update
   }, [dependency]);
   ```

4. **Component Will Unmount:**

   - Clean-up code can be placed inside `useEffect` to run when the component is about to unmount, similar to `componentWillUnmount`.

   ```jsx
   useEffect(() => {
     return () => {
       // Clean-up code
     };
   }, []);
   ```

5. **Async Operations:**

   - `useEffect` supports asynchronous operations. You can declare an asynchronous function inside it and perform async tasks.

   ```jsx
   useEffect(() => {
     const fetchData = async () => {
       // Async code
     };

     fetchData();
   }, []);
   ```

Example usage:

```jsx
import React, { useEffect, useState } from "react";

function DataFetcher() {
  // State to hold fetched data
  const [data, setData] = useState(null);

  // Fetch data after the component mounts
  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch("https://api.example.com/data");
        const result = await response.json();
        setData(result);
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    };

    fetchData();
  }, []);

  return (
    <div>
      <h1>Fetched Data</h1>
      {data ? <p>{data}</p> : <p>Loading...</p>}
    </div>
  );
}

export default DataFetcher;
```

The `useEffect` hook provides a flexible way to handle side effects in functional components, making it a powerful tool for managing the lifecycle of your components.

## useRef Hook

Ref always stores the current value and it doesn't re-render. The hook can be used to:

1. Access DOM Elements
2. Hold Mutable Values without Triggering Re-renders
3. Store and Persisting Values Across Renders

Example usage:

```react
import React, { useRef, useEffect } from 'react';

function MyComponent() {
  // Creating a ref to store a reference to an input element
  const inputRef = useRef(null);

  // Using useEffect to focus on the input element after the component mounts
  useEffect(() => {
    inputRef.current.focus();
  }, []);

  return (
    <div>
      <label>
        Type something:
        {/* Associating the input element with the useRef */}
        <input ref={inputRef} type="text" />
      </label>
      <p>Click outside the input to see the focus effect.</p>
    </div>
  );
}

export default MyComponent;
```

## useMemo Hook

It's all about memoization in performance gain. It works like useEffect.

```react
import React, { useState, useMemo } from 'react';

function SquareCalculator({ number }) {
  // State to hold the input value
  const [input, setInput] = useState(1);

  // Memoized function to calculate the square of a number
  const calculateSquare = useMemo(() => {
    console.log('Calculating square...');
    return () => {
      return input * input;
    };
  }, [input]);

  return (
    <div>
      <h2>Square Calculator</h2>
      <label>
        Enter a number:
        <input
          type="number"
          value={input}
          onChange={(e) => setInput(parseInt(e.target.value, 10))}
        />
      </label>
      <p>
        Square of {input}: {calculateSquare()}
      </p>
    </div>
  );
}

export default SquareCalculator;

// The calculateSquare function is memoized using useMemo. It will only be recalculated when the input value changes.

```

## useCallback Hook

It works like useMemo, but to memoize functions

```react
import React, { useState, useCallback } from 'react';

function ParentComponent() {
  const [count, setCount] = useState(0);

  // Without useCallback, this function would be recreated on every render
  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]); // Dependency array specifies that the function depends on 'count'

  return (
    <div>
      <p>Count: {count}</p>
      {/* ChildComponent receives the memoized handleClick function */}
      <ChildComponent onClick={handleClick} />
    </div>
  );
}

// ChildComponent renders a button that triggers the onClick function
function ChildComponent({ onClick }) {
  console.log('ChildComponent rendered');
  return <button onClick={onClick}>Increment</button>;
}

export default ParentComponent;

```

## Custom Hooks

The primary purpose of a custom hook is to encapsulate and reuse logic in functional components. Custom hooks provide a way to extract and share stateful logic, side effects, or any other functionality between multiple components without duplicating code.

Here's a simple example of a custom hook that manages a piece of state and provides a function to toggle its value:

```react
import { useState } from 'react';

// Custom hook for managing a toggle state
function useToggle(initialValue = false) {
  const [value, setValue] = useState(initialValue);

  const toggle = () => {
    setValue((prevValue) => !prevValue);
  };

  return [value, toggle];
}

export default useToggle;

```

You can then use this custom hook in your components:

```react
import React from 'react';
import useToggle from './useToggle'; // Importing the custom hook

function ToggleComponent() {
  // Using the custom hook to manage a toggle state
  const [isToggled, toggle] = useToggle(false);

  return (
    <div>
      <p>Toggle State: {isToggled ? 'On' : 'Off'}</p>
      <button onClick={toggle}>Toggle</button>
    </div>
  );
}

export default ToggleComponent;
```

<mark>Learning in progress</mark>
