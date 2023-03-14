## JSX

JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code inside your JavaScript code. It's a popular choice for building user interfaces in React, as it provides a more intuitive way to define the structure and content of your UI components.

Here's an example of JSX code:
```js
import React from 'react';

function MyComponent(props) {
  return (
    <div className="my-component">
      <h1>{props.title}</h1>
      <p>{props.content}</p>
    </div>
  );
}
```
In this example, the `MyComponent` function returns a JSX element that defines the structure and content of the component. The `className` attribute is used to specify the CSS class for the `div` element, while the `title` and `content` props are interpolated using curly braces.

Under the hood, JSX is transformed into regular JavaScript code using a transpiler, such as Babel. For example, the JSX code above would be transformed into the following JavaScript code:
```js
import React from 'react';

function MyComponent(props) {
  return React.createElement(
    "div",
    { className: "my-component" },
    React.createElement("h1", null, props.title),
    React.createElement("p", null, props.content)
  );
}
```
While you can technically use React without JSX and manually write the equivalent JavaScript code, JSX makes the code much more readable and easier to reason about. It also allows you to use the full power of JavaScript inside your templates, such as loops, conditions, and expressions.