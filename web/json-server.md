# JSON Server

To install, use the following command:
```bash
npm install -g json-server
```
Using `-g` parameter will install it globally.

To run the json-server, use the following command:
```bash
json-server --port 3001 --watch db.json
```
json-server starts running on port 3000 by default and might conflict with other software running (like React apps created with create-react-app, which reserve port 3000), so it's a good idea to use an alternative port with `--port 3001` parameter. `--watch` parameter automatically looks for any saved changes to db.json

If we don't want to use install it globally, the alternative is to use npx command from the root directory of the app, like so:
```bash
npx json-server --port 3001 --watch db.json
```
Another one is to simply install it as a development dependency:
```bash
npm install json-server --save-dev
```