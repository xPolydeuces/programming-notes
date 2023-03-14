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