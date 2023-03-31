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

## Running tests one by one
There are many ways to achieve this. One of the better ones is specifying the tests that need to be run as parameters of the *npm test* command.

The following command only runs the tests found in the *tests/note_api.test.js* file:

```npm test -- tests/note_api.test.js```

The *-t* option can be used for running tests with a specific name:

```npm test -- -t "a specific note is within the returned notes"```

The following command will run all of the tests that contain *notes* in their name:

```npm test -- -t 'notes'```

Example test file:

```js
const request = require('supertest');
const app = require('./app');

describe('GET /', () => {
  it('responds with "Hello, world!"', async () => {
    const response = await request(app).get('/');
    expect(response.statusCode).toBe(200);
    expect(response.text).toBe('Hello, world!');
  });
});
```

In this example, we're using the supertest library to make HTTP requests to our application and test the response.

The app we are testing:

```js
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('Hello, world!');
});

module.exports = app;
```