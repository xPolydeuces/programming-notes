**DISCLAIMER: This setup is what I use and by no means is an industry standard or the "right way" to initialize the app. This is only a reminder for myself to keep consistency.**

## To create a React app:
```bash
npx create-react-app app-name
```

## ESlint configuration
```bash
npm install eslint --save-dev
npx eslint --init
```
### For React app
Choose the following options: (2000a10111010)
* `How would you like to use ESLint?` **>To check syntax, find problems, and enforce code style**
* `What type of modules does your project use?` **>JavaScript modules (import/export)**
* `Which framework does your project use?` **>React**
* `Does your project use TypeScript?` **>No**
* `Where does your code run?` **>Browser + Node**
* `How would you like to define a style for your project?` **>Answer questions about your style**
* `What format do you want your config file to be in?` **>JavaScript**
* `What style of indentation do you use?` **>Spaces**
* `What quotes do you use for strings?` **>Single**
* `What line endings do you use?` **>Windows**
* `Do you require semicolons?` **>No**

You will be asked if you want to install `eslint-plugin-react@latest` plugin, choose **>Yes**
* ` Which package manager do you want to use?` **>npm**