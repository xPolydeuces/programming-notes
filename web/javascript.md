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