# Writing tests

## Test environment
The convention in Node is to define the execution mode of the application with the NODE_ENV environment variable, like so:

```js
{
  // ...
  "scripts": {
    "start": "NODE_ENV=production node index.js",
    "dev": "NODE_ENV=development nodemon index.js",
    "test": "NODE_ENV=test jest --verbose --runInBand" // The runInBand option prevents Jest from running tests in parallel.
  },
  // ...
}
```

However, it won't work on Windows. We can change it by installing the cross-env package as a development dependency:

``` npm install --save-dev cross-env ```

