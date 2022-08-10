# REACT HOOKS

## What is a React Hook?

A hook is a special function that lets you "hook into" various React features. Imagine a function that returns an array with two values:

The first value: a variable with the state.
The second value: a variable with an handler (a function to change the current state).

## When to Use the useState Hook?

To understand when to use this hook, we need to start by learning when we need state.

At first glance, we think that when we need a variable that changes over time, we need to keep it in state. But this is not true, most of the time. I mean, if your variable can be derived from other data, then you don't need state.

- Example:

```js
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

- Declaring multiple state variables

```js
function ExampleWithManyStates() {
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
}
```
