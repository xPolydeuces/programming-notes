# Express

Express is a popular web framework for Node.js that makes it easier to build web applications and APIs. Express provides a simple and flexible way to handle requests and responses, middleware for handling common web application tasks, and more.

To install express, use following command:
```bash
npm install express
```

Here's an example of using Express to create a simple web server that responds to HTTP requests:
```js
const express = require('express');
const app = express();

// Define a route that responds to GET requests at the root URL
app.get('/', function(req, res) {
  res.send('Hello, World!');
});

// Start the server
app.listen(3000, function() {
  console.log('Server started on port 3000');
});
```

In this example, we use the `express` module to create an instance of the Express application. We define a route using the `app.get()` method that responds to GET requests at the root URL. When a client makes a request to the server, Express calls the callback function with two arguments: the `req` object representing the request and the `res` object representing the response. We use the `res.send()` method to send a response back to the client.

We then start the server by calling the `app.listen()` method and passing in the port number to listen on. When the server starts, we log a message to the console.

Express also provides middleware, which are functions that can be chained together to handle requests and responses. Here's an example of using middleware to log all incoming requests:
```js
const express = require('express');
const app = express();

// Define middleware to log incoming requests
app.use(function(req, res, next) {
  console.log(`${req.method} ${req.url}`);
  next();
});

// Define a route that responds to GET requests at the root URL
app.get('/', function(req, res) {
  res.send('Hello, World!');
});

// Start the server
app.listen(3000, function() {
  console.log('Server started on port 3000');
});
```

In this example, we define middleware using the `app.use()` method. The middleware function takes three arguments: the `req` object representing the request, the `res` object representing the response, and the `next` function to call the next middleware function in the chain. We use `console.log()` to log the HTTP method and URL of each incoming request, and then call `next()` to pass control to the next middleware function.

We then define the same route as before using `app.get()`, and start the server using `app.listen()`.

These are just a couple of examples of how to use Express with Node.js. Express provides many other features and capabilities for building web applications and APIs.