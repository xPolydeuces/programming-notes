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