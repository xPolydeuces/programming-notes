## Promises

In JavaScript, promises are used to handle asynchronous operations. A promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

Promises have three states:
* Pending: The initial state of a promise, indicating that the operation has not yet completed.
* Fulfilled: The state of a promise when the operation has completed successfully, resulting in a value.
* Rejected: The state of a promise when the operation has failed, resulting in an error.

Promises are created using the `Promise` constructor. The constructor takes a function as an argument, which has two parameters: `resolve` and `reject`. The `resolve` function is called when the operation is successful and the `reject` function is called when the operation fails.

Here is an example of creating a promise:

```js
const myPromise = new Promise((resolve, reject) => {
  // Do some asynchronous operation
  if (/* Operation is successful */) {
    resolve('Operation completed successfully.');
  } else {
    reject('Operation failed.');
  }
});
```

Once a promise is created, you can use the `then` method to handle the fulfilled state and the `catch` method to handle the rejected state. The `then` method takes a callback function that is called when the promise is fulfilled, and the `catch` method takes a callback function that is called when the promise is rejected.

Here is an example of using the `then` and `catch` methods:

```js
myPromise.then((result) => {
  console.log(result); // Output: 'Operation completed successfully.'
}).catch((error) => {
  console.error(error); // Output: 'Operation failed.'
});
```
Promises can also be chained using the `then` method, which returns a new promise. This allows you to perform a series of asynchronous operations in a sequence.

Here is an example of chaining promises:
```js
const myPromise = new Promise((resolve, reject) => {
  resolve(1);
});

myPromise.then((result) => {
  return result + 2;
}).then((result) => {
  console.log(result); // Output: 3
}).catch((error) => {
  console.error(error);
});
```
In this example, the first promise resolves to the value `1`. The first `then` method adds `2` to the result and returns a new promise. The second `then` method logs the final result (`3`) to the console. If there was an error in any of the promises, the `catch` method would be called instead.