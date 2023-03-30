# CORS

CORS (Cross-Origin Resource Sharing) is a security mechanism that allows a web page from one domain or origin to access resources on another domain. It is a browser-based mechanism that allows web servers to explicitly allow cross-origin requests, rather than rejecting them by default for security reasons.

By default, web browsers prevent JavaScript code running on a web page from making requests to a different domain than the one the page came from. This is called the same-origin policy, and it is an important security feature that prevents malicious scripts from accessing sensitive data on other websites.

However, sometimes it is necessary for web pages to access resources from different domains, such as when making AJAX requests to web APIs. In these cases, the web server hosting the resources must explicitly allow requests from other domains by setting the appropriate CORS headers in its HTTP responses.

CORS works by adding an extra HTTP header to the response sent by the server that allows the browser to make cross-domain requests. The most important CORS headers are:

* Access-Control-Allow-Origin: specifies which domain or domains are allowed to access the resource.
* Access-Control-Allow-Methods: specifies which HTTP methods (e.g. GET, POST) are allowed when accessing the resource.
* Access-Control-Allow-Headers: specifies which HTTP headers are allowed when accessing the resource.
It's important to note that CORS only affects browser-based requests, not server-to-server requests made using tools like cURL or Postman.