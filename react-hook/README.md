# REACT HOOKS

## What is a React Hook?

A hook is a special function that lets you "hook into" various React features. Imagine a function that returns an array with two values:

The first value: a variable with the state.
The second value: a variable with an handler (a function to change the current state).

## When to Use the useState Hook?

To understand when to use this hook, we need to start by learning when we need state.

At first glance, we think that when we need a variable that changes over time, we need to keep it in state. But this is not true, most of the time. I mean, if your variable can be derived from other data, then you don't need state.

## What do we pass to useState as an argument?

The only argument to the useState() Hook is the initial state. Unlike with classes, the state doesn’t have to be an object. We can keep a number or a string if that’s all we need. In our example, we just want a number for how many times the user clicked, so pass 0 as initial state for our variable. (If we wanted to store two different values in state, we would call useState() twice.)

## What does useState return?

 It returns a pair of values: the current state and a function that updates it. This is why we write const [count, setCount] = useState(). This is similar to this.state.count and this.setState in a class, except you get them in a pair. If you’re not familiar with the syntax we used, we’ll come back to it at the bottom of this page.


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
