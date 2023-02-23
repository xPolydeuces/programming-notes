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

* `slice()` - returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included).
```js
const numbers = [1, 2, 3, 4, 5];
const subArray = numbers.slice(2, 4);
console.log(subArray); // [3, 4]
console.log(numbers); // [1, 2, 3, 4, 5]
```
* `splice()` - changes the contents of an array by removing or replacing existing elements and/or adding new elements.
```js
const numbers = [1, 2, 3, 4, 5];
numbers.splice(2, 1, 'a', 'b');
console.log(numbers); // [1, 2, 'a', 'b', 4, 5]
```
* `concat()` - returns a new array that is a concatenation of two or more arrays.
```js
const numbers1 = [1, 2, 3];
const numbers2 = [4, 5, 6];
const allNumbers = numbers1.concat(numbers2);
console.log(allNumbers); // [1, 2, 3, 4, 5, 6]
```
* `map()` - creates a new array with the results of calling a provided function on every element in the calling array.
```js
const numbers = [1, 2, 3, 4, 5];
const squaredNumbers = numbers.map(num => num ** 2);
console.log(squaredNumbers); // [1, 4, 9, 16, 25]
```
* destructuring statement - helpful way to assign items of the array to new variables.
```js
const t = [1, 2, 3, 4, 5]

const [first, second, ...rest] = t

console.log(first, second)  // 1, 2 is printed
console.log(rest)          // [3, 4, 5] is printed
```
* `reduce()` - applies a function to each element of an array to reduce the array to a single value.
```js
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue);
console.log(sum); // 15
```
* `filter()` - creates a new array with all elements that pass the test implemented by the provided function.
```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

## Objects
In modern JavaScript, objects are a fundamental data type used to store and organize data. Objects are collections of key-value pairs, where each key represents a property name and each value represents the value of that property.

Here are some key features of objects in modern JavaScript:

* Object literals: Objects can be created using object literals, which are enclosed in curly braces {} and contain a list of property-value pairs separated by commas. For example:
```js
const person = {
  name: 'John',
  age: 30,
  isStudent: true
};
```
* Accessing properties: Object properties can be accessed using dot notation (objectName.propertyName) or bracket notation (objectName['propertyName']). For example:
```js
console.log(person.name); // 'John'
console.log(person['age']); // 30
```
* Adding and updating properties: Object properties can be added or updated by assigning a value to a new or existing property. For example:
```js
person.city = 'New York';
person.age = 31;
```
* Object methods: Objects can also contain methods, which are functions that are properties of an object. For example:
```js
const person = {
  name: 'John',
  age: 30,
  isStudent: true,
  greet() {
    console.log(`Hello, my name is ${this.name}!`);
  }
};

person.greet(); // 'Hello, my name is John!'
```
* Object destructuring: Object destructuring is a syntax for extracting properties from an object and assigning them to variables. For example:
```js
const { name, age } = person;
console.log(name); // 'John'
console.log(age); // 30
```
* Object methods and "this": When an object method is called, the this keyword refers to the object itself. This allows methods to access and manipulate the object's properties. For example:
```js
const person = {
  name: 'John',
  age: 30,
  isStudent: true,
  greet() {
    console.log(`Hello, my name is ${this.name}!`);
  },
  celebrateBirthday() {
    this.age++;
  }
};

person.celebrateBirthday();
console.log(person.age); // 31
```
Objects are a powerful and versatile data type in modern JavaScript, and they are used extensively in web development to represent and manipulate data. Understanding how to work with objects is essential for building complex and dynamic applications.

## Functions
In modern JavaScript, functions are an essential part of the language and are used for a wide range of tasks, from simple calculations to complex event handling and application logic.

Here are some key features of functions in modern JavaScript:

* Function declaration: Functions can be declared using the function keyword followed by the function name and a set of parentheses that may contain parameters, and then a set of curly braces that contain the function body. For example:
```js
function addNumbers(a, b) {
  return a + b;
}
```
* Arrow functions: Arrow functions are a shorthand syntax for declaring functions that was introduced in ES6. They use a => syntax and can omit the function keyword, return keyword (if the function body is a single expression), and even the parentheses for a single parameter. For example:
```js
const addNumbers = (a, b) => a + b;
```
* Function parameters: Functions can accept zero or more parameters, which are declared within the parentheses after the function name. Parameters are separated by commas and can have default values. For example:
```js
function greet(name = 'World') {
  console.log(`Hello, ${name}!`);
}

greet(); // Hello, World!
greet('John'); // Hello, John!
```
* Function return values: Functions can return a value using the return keyword. If a function does not explicitly return a value, it will return undefined. For example:
```js
function addNumbers(a, b) {
  return a + b;
}

const sum = addNumbers(2, 3);
console.log(sum); // 5
```
* Higher-order functions: Functions can be passed as arguments to other functions or returned from functions, allowing for the creation of higher-order functions. These functions can be used to compose more complex behavior out of simpler functions. For example:
```js
function multiplyBy(factor) {
  return function (number) {
    return number * factor;
  }
}

const double = multiplyBy(2);
console.log(double(3)); // 6
```
* Anonymous functions: Functions can be declared anonymously and assigned to a variable or passed as an argument to another function. For example:
```js
const sayHello = function () {
  console.log('Hello!');
};

sayHello(); // Hello!
```
Functions are a crucial part of modern JavaScript, and understanding their features and capabilities is essential for developing effective and efficient code.

## Object methods and "this"

In JavaScript, objects are a powerful tool for storing and manipulating collections of data. Objects can have properties and methods, and methods are simply functions that are attached to an object. When a method is called on an object, it has access to the object's properties and can modify them if needed. The `this` keyword plays an important role in object methods, as it refers to the object on which the method was called.

Here is an example of an object with a method:
```js
const person = {
  firstName: 'John',
  lastName: 'Doe',
  fullName() {
    return `${this.firstName} ${this.lastName}`;
  }
};

console.log(person.fullName()); // "John Doe"
```

In this example, `person` is an object that has two properties: `firstName` and `lastName`. It also has a method called `fullName` which returns the full name of the person by concatenating the `firstName` and `lastName` properties. Inside the `fullName` method, `this` refers to the `person` object, so we can access the `firstName` and `lastName` properties using `this.firstName` and `this.lastName`.

The `this` keyword can be used in other ways as well. For example, if we want to create a method that modifies an object's properties, we can use `this` to refer to the object itself:
```js
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
  celebrateBirthday() {
    this.age++;
  }
};

console.log(person.age); // 30
person.celebrateBirthday();
console.log(person.age); // 31
```

In this example, the `celebrateBirthday` method increments the `age` property of the `person` object by 1. Inside the method, `this` refers to the `person` object, so we can modify the `age` property using `this.age++`.

Using `this` in object methods allows us to write more reusable and dynamic code. Instead of hard-coding property names or values, we can reference them dynamically using `this`. 