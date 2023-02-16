# React

## Create a React app

The easiest way (but not the best one, and actually not recommended to use by professionals) to create a React app is by using a tool called `create-react-app`. To initialize it, you can do it by writing the following command in the console:
```bash
npx create-react-app app-name
```
and run it with this command:
```bash
npm start
```

It should open the freshly created React app in your default browser on `http://localhost:3000`.

## Component

One of the main things in React are *Components*. The default component, created when using `create-react-app` is called `App` and looks something like this:

```js
const App = () => (
  <div>
    <p>Hello world</p>
  </div>
)

export default App
```

And the `index.js` file, that renders our React app to the website, uses such line to render our `App` component.
```js
ReactDOM.createRoot(document.getElementbyId('root')).render(<App />)
```

The app will render *div*-tag, which wraps a *p*-tag containing the text *Hello world*.