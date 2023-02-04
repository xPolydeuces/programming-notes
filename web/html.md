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
* `<em>`: Defines emphasized text. Browser usually display it in italic font. If we wanted to create bold text without greater emphasis, we can use `<i>` instead.
* `<br>`: Inserts a line break

For example:
```html
<h1>Welcome to My Website</h1>
<p>This is a <strong>simple</strong> example of a paragraph of text.</p>
<p>This is a <em>second</em> paragraph of text.</p>
```