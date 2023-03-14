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