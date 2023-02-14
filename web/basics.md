# Basics of Web apps

## The 1st rule of web development: 
Always keep the Developer Console open on your web browser.

## HTTP
*HyperText Transfer Protocol (HTTP)* is an application-layer protocol for transmitting hypermedia documents, such as HTML.

### Important HTTP Request Methods

* GET - requests a representation of the specified resource. Requests using `GET` should only be used to request data (they shouldn't include data),
* PUT - creates a new resource or replaces a representation of the target resource with the request payload,
* POST - sends data to the server. The type of the body of the request is indicated by the `Content-Type` header;

### Important headers

* Content-Type: provides us with the actual content type of the returned content.

## DOM
*Document Object Model (DOM)* is an *Application Programming Interface (API)* that enables programmatic modificiation of the element trees corresponding to web pages.

DOM hierarchy example:
```html
<!doctype html>
<html>
  <head></head>
  <body>
    <div class="container">
      <h1>Notes</h1>
      <div id="notes">
        <ul class="notes">
          <li>HTML is easy</li>
          <li>Browser can execute only Javascript</li>
          <li>Most important methods of HTTP-protocal are GET and POST</li>
        </ul>
      </div>
      <form action="/new_note" method="POST">...</form>
    </div>
  </body>
</html>
```