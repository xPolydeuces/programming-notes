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

You can add text to your page using the following elements:
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

You can create links to other pages using the `<a>` element:
```html
<a href="https://www.example.com">Visit Example.com</a>
```
The `href` attribute specifies the URL of the page you want to link to.

## Images

You can add images to your page using the `<img>` element:
```html
<img src="image.jpg" alt="A description of the image">
```

The `src` attribute specifies the URL of the image file, and the `alt` attribute provides a description of the image for accessibility purposes.

## Lists

You can create lists of items using the `<ul>` (unordered) and `<ol>` (ordered) elements, along with the `<li>` element:

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

You can create tables to display data using the `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>` and `<td>` elements:
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