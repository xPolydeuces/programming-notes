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