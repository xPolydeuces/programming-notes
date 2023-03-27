# Nodemon

Nodemon is a utility tool for Node.js that monitors changes in your source code and automatically restarts the server when it detects any changes. This is useful when you are developing your application and want to see the changes you make without having to manually restart the server every time.

Here's an example of how you can use nodemon with Node.js:

1. Install nodemon as a dev dependency using npm:
```bash
npm install --save-dev nodemon
```

2. Create a simple Node.js server file named `server.js`:
```js
const http = require('http');
const port = process.env.PORT || 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World!');
});

server.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

3. Start the server using nodemon:
```bash
nodemon server.js
```

Now, every time you make changes to `server.js`, nodemon will automatically restart the server and you'll see the changes without having to manually restart the server.

Here are a few more examples of how you can use nodemon with different configurations:

1. Ignore specific directories or files:
```bash
nodemon --ignore public/ server.js
```
This will ignore the `public` directory and any files inside it, so changes to those files won't trigger nodemon to restart the server.

2. Set a delay before restarting the server:
```bash
nodemon --delay 1000ms server.js
```

This will set a delay of 1000 milliseconds (1 second) before nodemon restarts the server. This can be useful if you have multiple files changing at the same time and you want to avoid multiple restarts.

3. Monitor multiple directories for changes:
```bash
nodemon --watch src/ --watch config/ server.js
```

This will monitor the `src` and `config` directories for changes, so any changes to files inside those directories will trigger nodemon to restart the server.