# React

## Create a React app

The easiest way (but not the best one, and actually not recommended to use by professionals) to create a React app is by using a tool called `create-react-app`. To initialize it, you can do it by writing the following command in the console:
```bash
npx create-react-app app-name
```
and run it with this command:
```bash
npm start
```

It should open the freshly created React app in your default browser on `http://localhost:3000`.

## Component

One of the main things in React are *Components*. React official site describes them as 
> Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. This page provides an introduction to the idea of components. You can find a detailed component API reference here.

> Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.
The default component, created when using `create-react-app` is called `App` and looks something like this:

```js
const App = () => (
  <div>
    <p>Hello world</p>
  </div>
)

export default App
```

And the `index.js` file, that renders our React app to the website, uses such line to render our `App` component.
```js
ReactDOM.createRoot(document.getElementbyId('root')).render(<App />)
```

The app will render *div*-tag, which wraps a *p*-tag containing the text *Hello world*.

You can pass data to Components using so-called *props*, like this:
```js
const Hello = (props) => (
  <div>
    <p>Hello {props.name}</p>
  </div>
)

const name = 'Bart'

const App = () => (
  <div>
    <Hello name='Simon' /> // result: "Hello Simon"
    <Hello name={name} /> // result: "Hello Bart"
)
```
One important thing is to **always** capitalize Components' names. Otherwise React will recognize them as the built-in HTML elements or throw an error.

## JSX

The syntax used inside the React `App` is not HTML, despite looking like it. It actually is *JSX*, a syntax extension to JavaScript, used for describing what UI should look like. The important difference while writing it is that the tags have to **always** be closed. While `<br>` would work in HTML, it wouldn't in our React app and we need to change it to `<br />` for it to actually work.

## Helper functions

```js
const Hello = (props) => {
  const bornYear = () => {
    const yearNow = new Date().getFullYear()
    return yearNow - props.age
  }

  return (
    <div>
      <p>
        Hello {props.name}, you are {props.age} years old
      </p>
      <p>So you were probably born in {bornYear()}</p>
    </div>
  )
}
```
 The helper function is defined inside of another function that defines the behavior of our component. In Java programming, defining a function inside another one is complex and cumbersome, so not all that common. In JavaScript, however, defining functions within functions is a commonly-used technique.

 ## Destructuring

 When passing data to a component as `props`, it always is an object, for example
```js
props = {
  name: 'John Doe',
  age: 35,
}
```
and the example use of props
```js
const Hello = (props) => {
  return (<p>Hello {props.name}, you are {props.age} years all.</p>)
}
```
There are several ways to make it look more "clean", for example by assigning the values to different variables:
```js
const Hello = (props) => {
  const name = props.name
  const age = props.age
  return (<p>Hello {name}, you are {age} years all.</p>)
}
```
It makes think clearer, but even better way to do it is by **destructuring**. There are two places we can destructure `props`:
```js
// 1st approach
const Hello = (props) => {
  const { name, age } = props
  return (<p>Hello {name}, you are {age} years all.</p>)
}
```
```js
// 2nd approach
const Hello = ({ name, age }) => {
  return (<p>Hello {name}, you are {age} years all.</p>)
}
```
In the first approach, destructuring happens already inside a component, while in the second one the data passed is already destructured.

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

## Event Handling
In React, event handlers are defined as functions that are called when a specific event occurs, such as a button click or a form submission.

To add an event handler to a React component, we can use the `onClick` attribute for a button element or the `onSubmit` attribute for a form element, like so:
```js
import React from 'react';

function Button(props) {
  function handleClick() {
    console.log('Button clicked!');
  }

  return (
    <button onClick={handleClick}>
      {props.label}
    </button>
  );
}

function Form() {
  function handleSubmit(event) {
    event.preventDefault();
    console.log('Form submitted!');
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" name="name" />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```
In this example, we define two functional components: `Button` and `Form`. The `Button` component renders a button with a label, and adds an event handler function called `handleClick` to the `onClick` attribute. When the button is clicked, the `handleClick` function is called and logs a message to the console.

The `Form` component renders a form with a text input and a submit button. It adds an event handler function called `handleSubmit` to the onSubmit attribute of the form. When the form is submitted, the `handleSubmit` function is called and logs a message to the console. Note that we also call `event.preventDefault()` to prevent the form from being submitted in the traditional way, which would cause the page to refresh.

Event handling in React is similar to event handling in regular JavaScript, but with some additional features and considerations. Overall, event handling is an important part of creating dynamic and interactive user interfaces in React.

## Forms

Forms in modern React are used to collect data from users, such as text input, checkboxes, and radio buttons. React provides several built-in components for working with forms, including `input`, `textarea`, and `select`, as well as the `form` component itself.

To use a form in React, we typically define a component that renders the form and handles form submission, like so:
```js
import React, { useState } from 'react';

function Form() {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  const [message, setMessage] = useState('');

  function handleSubmit(event) {
    event.preventDefault();
    console.log(`Name: ${name}, Email: ${email}, Message: ${message}`);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input
          type="text"
          value={name}
          onChange={(event) => setName(event.target.value)}
        />
      </label>
      <label>
        Email:
        <input
          type="email"
          value={email}
          onChange={(event) => setEmail(event.target.value)}
        />
      </label>
      <label>
        Message:
        <textarea
          value={message}
          onChange={(event) => setMessage(event.target.value)}
        />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```
In this example, we define a `Form` component that uses the useState hook to manage three pieces of state: `name`, `email`, and `message`. We also define a `handleSubmit` function that logs the form data to the console when the form is submitted.

Inside the `return` statement, we render a form with three inputs: a text input for the name, an email input for the email address, and a textarea for the message. We use the `value` attribute to set the value of each input to the corresponding state variable, and we use the `onChange` attribute to update the state variable when the user types into the input.

Finally, we render a submit button that calls the `handleSubmit` function when clicked. We also add the `onSubmit` attribute to the form itself, which calls the `handleSubmit` function when the form is submitted.

## Effect Hooks
In React, effect hooks are a way to add side effects to a component's rendering cycle. Side effects are operations that modify something outside the component's scope, such as updating the DOM, fetching data, or subscribing to an external event.

Effect hooks are declared using the `useEffect()` function, which takes two arguments: a function that performs the side effect, and an optional array of dependencies that control when the effect should run.

Here's an example of a component that fetches data from an API and displays it in a list:
```js
import React, { useState, useEffect } from 'react';

function MyComponent() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://myapi.com/data')
      .then(response => response.json())
      .then(data => setData(data))
      .catch(error => console.log(error));
  }, []);

  return (
    <ul>
      {data.map(item => <li key={item.id}>{item.name}</li>)}
    </ul>
  );
}
```
In this example, the `useEffect()` function is used to fetch data from an API and update the component's state with the retrieved data. The second argument of `useEffect()` is an empty array, which means that the effect will only run once when the component mounts. If we had passed an array of dependencies, the effect would run whenever any of those dependencies changed.

Effect hooks are a powerful tool in React that allows you to perform side effects in a declarative way, without having to worry about the details of when to run them. However, it's important to use them correctly to avoid performance issues and bugs.