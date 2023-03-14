## State Hooks
State is an important concept that refers to the current data and values used to render a component. State can change over time, and when it does, React automatically updates the component to reflect those changes. In modern React, we can use state hooks to manage state within functional components.

State hooks are functions that allow us to add state to a functional component. The most commonly used state hook is the `useState` hook, which is used like so:
```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  function increment() {
    setCount(count + 1);
  }

  return (
    <div>
      <p>You clicked the button {count} times.</p>
      <button onClick={increment}>Click me</button>
    </div>
  );
}
```
In this example, we import the `useState` hook from the `react` library. We then define a functional component called `Counter`. Inside the component, we use the `useState` hook to add state to the component. We call the `useState` function with an initial value of `0`, which sets the initial value of the `count` state to `0`. The `useState` function returns an array with two values: the current value of the state (`count` in this case), and a function to update the state (`setCount` in this case).

We then define a function called `increment` that calls the `setCount` function to update the `count` state. Finally, we render the current value of the `count` state and a button that calls the `increment` function when clicked.

When the button is clicked, the `increment` function is called, which in turn calls the `setCount` function to update the `count` state. When the state is updated, React automatically re-renders the component to reflect the new state value.