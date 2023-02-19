# JavaScript

*JavaScript* is a powerful programming language that can add interactivity to a website.

*JS* itself is relatively compact, yet very flexible. Developers have written a variety of tools on top of the core *JS* language, unlocking a vast amount of functionality with minimum effort. These include:

* Browser *Application Programming Interfaces* (APIs) built into web browsers, providing functionality such as dynamically creating HTML and setting CSS styles; collecting and manipulating a video stream from a user's webcam, or generating 3D graphics and audio samples.
* Third-party APIs that allow developers to incorporate functionality in sites from other content providers, such as Twitter or Facebook.
* Third-party frameworks and libraries that you can apply to *HTML* to accelerate the work of building sites and applications.

## Variables

In JavaScript there are a few ways to go about defining variables:

```js
const x = 1 // constant, cannot be changed
let y = 5 // variable, can be changed

console.log(x, y)   // 1, 5 are printed
y += 10
console.log(x, y)   // 1, 15 are printed
y = 'sometext'
console.log(x, y)   // 1, sometext are printed
x = 4               // causes an error
```

In *JavaScript* variable's data can be changed during execution. Previously, the only way to declare variables was keyword *var*, which worked like *let*, but not exactly - the scope is different. To summarize:

* `let` - creates a variable that can be changed, it has local scope.
* `const` - creates a constant that cannot be changed, it has local scope.
* `var` - creates a variable that can be changed, it has global scope. **Obsolete, not recommended to use.**

## Arrays

An array and a couple of examples of its use:

```js
const t = [1, -1, 3] // array declaration

t.push(5)

console.log(t.length) // 4 is printed
console.log(t[1])     // -1 is printed

t.forEach(value => {
  console.log(value)  // numbers 1, -1, 3, 5 are printed, each to own line
})
```

Despite being a const, we can see that the array can actually be changed. It's because the array is an object and the variable always points to the same object. The content of the array can change however.

### Useful methods

* `concat` - creates new array with the added item, example: 
```js
const t = [1, -1, 3]

const t2 = t.concat(5)  // creates new array

console.log(t)  // [1, -1, 3] is printed
console.log(t2) // [1, -1, 3, 5] is printed
```
* `map` - creates new array, for which the function given as a parameter is used to create the items, example:
```js
const t = [1, 2, 3]

const m1 = t.map(value => value * 2)
console.log(m1)   // [2, 4, 6] is printed
```
* destructuring statement - helpful way to assign items of the array to new variables, example:
```js
const t = [1, 2, 3, 4, 5]

const [first, second, ...rest] = t

console.log(first, second)  // 1, 2 is printed
console.log(rest)          // [3, 4, 5] is printed
```

## Objects
Objects are declared in JavaScript with `{}`, one of the ways to declare them is using *object literals*, as such:
```js
const object1 = {
  name: 'Arto Hellas',
  age: 35,
  education: 'PhD',
}

const object2 = {
  name: 'Full Stack web application development',
  level: 'intermediate studies',
  size: 5,
}

const object3 = {
  name: {
    first: 'Dan',
    last: 'Abramov',
  },
  grades: [2, 3, 5, 3],
  department: 'Stanford University',
}
```
The values of the properties can be of any type, like integers, strings, arrays, objects etc. The properties of an object are referenced by using the "dot" notation or by using brackets:
```js
console.log(object1.name)         // Arto Hellas is printed
const fieldName = 'age' 
console.log(object1[fieldName])    // 35 is printed
```
It's also possible to add properties after object is created, like so:
```js
object1.address = 'Helsinki'
object1['secret number'] = 12341
```