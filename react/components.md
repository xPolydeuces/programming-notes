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