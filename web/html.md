# HTML

**HTML** stands for *HyperText Markup Language* and is used to create the structure and content of web pages.

## Basic Structure

A basic HTML document has the following structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Page content goes here -->
  </body>
</html>
```
The `<!DOCTYPE html>` declaration specifies that this is an HTML5 document. The `<html>` element is the root element of the page and it contains all other elements.

The `<head>` element contains metadata about the document, such as the title of the page, which is displayed in the browser's title bar or tab. The `<body>` element containts the content of the page, such as text, images and links.

## Text Content

There are several ways to format text in HTMl. Here are the most commonly used elements:
* `<p>`: Defines a paragraph of text
* `<h1>` to `<h6>`: Defines headings of different levels
* `<strong>`: Defines text of strong importance. Browsers usually display it in bold font. If we wanted to create bold text without greater importance, we can use `<b>` instead.
* `<em>`: Defines emphasized text. Browsers usually display it in italic font. If we wanted to create bold text without greater emphasis, we can use `<i>` instead.
* `<br>`: Inserts a line break

For example:
```html
<h1>Welcome to My Website</h1>
<p>This is a <strong>simple</strong> example of a paragraph of text.</p>
<p>This is a <em>second</em> paragraph of text.</p>
```

## Links

We can create links to other pages using the `<a>` element:
```html
<a href="https://www.example.com">Visit Example.com</a>
```
The `href` attribute specifies the URL of the page we want to link to.

## Images

We can add images to the page using the `<img>` element:
```html
<img src="image.jpg" alt="A description of the image">
```

The `src` attribute specifies the URL of the image file and the `alt` attribute provides a description of the image for accessibility purposes.

## Lists

We can create lists of items using the `<ul>` (unordered) and `<ol>` (ordered) elements, along with the `<li>` element:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

The `<ul>` element creates a bullet-point list, while the `<ol>` element creates a numbered list.

## Tables

We can create tables to display data using the `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>` and `<td>` elements:
```html
<table>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Column 1</td>
      <td>Row 1, Column 2</td>
    </tr>
    <tr>
      <td>Row 2, Column 1</td>
      <td>Row 2, Column 2</td>
    </tr>
  </tbody>
</table>
```
The `<thead>` element defines the header section of the table, while the `<tbody>` element defines the body of the table. The `<tr>` element defines a row and the `<th>` and `<td>` elements define header and data cells, respectively.

## Forms

We can create forms to collect data from users using the `<form>`, `<input>`, `<select>`, `<textarea>` and `<button>` elements:
```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <label for="message">Message:</label>
  <textarea id="message" name="message"></textarea>

  <button type="submit">Submit</button>
</form>
```
* `<form>`: defines a form,
* `<input>`: create input fields, such as text, email, password, radio buttons, checkboxes and more,
* `<select>`: create a dropdown list,
* `<textarea>`: create a multi-line input field,
* `<button>`: used to submit the form,
* `<label>`: can be used to associate a text description with form control.

# HTML5 specific features

## Semantic Elements

HTML5 provides new semantic elements that provide a meaningful description of the structure and content of a web page. These elements include: 

* `<header>`: Represents the header of a document or section
* `<nav>`: Represents a section of a page that contains navigation links
* `<article>`: Represents a self-contained composition in a document
* `<section>`: Represents a standalone section of a document
* `<aside>`: Represents a section of a page that contains content aside from the main content
* `<footer>`: Represents the footer of a document or section

## Multimedia elements

HTML5 includes new elements for embedding multimedia content directly into web pages:

* `<audio>`: Embeds audio content in your web page
* `<video>`: Embeds video content in your web page

## Canvas

The `<canvas>` element provides a way to draw graphics, animations, and other visual content using JavaScript.

## Forms

HTML5 introduces several new form-related features, including:

* New form input types with built-in validation
* New attributes for form elements that provide additional validation and user-friendly features
* A new form attribute, `autocomplete`, for specifying whether the browser should automatically fill in form values

## Local Storage

HTML5 Local Storage is a key-value store that can be used to store data in a web browser. It allows web applications to store data locally within the user's browser, instead of having to send data back and forth to a server, which makes it a more efficient way to store data compared to cookies.

Local storage is implemented as a property of the `Window` object and is accessed using the `localStorage` property. The data stored in local storage is persistent, meaning that it will still be available even after the browser has been closed and reopened.

Here are some key features of HTML5 local storage:

* Maximum storage: Each origin (a combination of scheme, host, and port) has a maximum storage limit of around 5-10 MB, depending on the browser. This limit is high enough for most web applications, but it's important to keep it in mind when designing your application.

* Data types: Local storage can only store strings. If you need to store other data types such as numbers or objects, you will need to convert them to strings before storing them, and then convert them back to their original data type when retrieving the data.

* API: The local storage API provides methods for adding, retrieving, and removing data. Here are some of the most commonly used methods:
  * `setItem(key, value)`: Adds a key-value pair to the local storage. If the key already exists, its value will be overwritten.
  * `getItem(key)`: Retrieves the value for a given key from the local storage. If the key does not exist, `null` will be returned.
  * `removeItem(key)`: Removes the key-value pair for a given key from the local storage.
  * `clear()`: Clears all key-value pairs from the local storage.
* Security: As with all client-side storage solutions, it is important to keep in mind that local storage data is accessible by any JavaScript code running on your page. This means that data stored in local storage should not contain sensitive information such as passwords or credit card numbers.

## Web Workers

HTML5 Web Workers are a way to run scripts in the background, separate from the main JavaScript execution thread. This allows you to perform long-running or intensive operations without freezing the user interface, making your web pages more responsive and improving overall performance.

A Web Worker is a separate JavaScript file that runs in its own thread, with its own global scope and context. You can start a worker by creating a new instance of the `Worker` object, passing it the URL of the worker script:

```js
var worker = new Worker("worker.js");
```

You can communicate with the worker using messages. You can send data to the worker using the `postMessage` method, and the worker can send data back to the main thread using the `postMessage` method as well:

```js
worker.postMessage("Hello Worker");

worker.onmessage = function(event) {
  console.log("Worker says: " + event.data);
};
```
Web Workers have several limitations compared to the main JavaScript thread:

* They don't have access to the DOM
* They don't have access to certain browser APIs, such as `window`, `document`, and `location`
* They can't modify the page's URL

However, they can use a subset of JavaScript and several APIs, such as `XMLHttpRequest`, `IndexedDB`, and `WebSockets`, to perform their tasks.

In summary, HTML5 Web Workers provide a way to run JavaScript in the background, separate from the main execution thread, improving the responsiveness of your web pages and enabling you to perform long-running or intensive operations without affecting the user experience.