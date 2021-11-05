# Cookies...yum
a cookie is a piece of data that is set by the web server but is stored by the web client which sends it back to the server on every request

## Cookie Uses
tracking users (of the same browser) across time
storing data without allocating server space
an early version of LocalStorage for storing arbitrary objects on the client

## Cookie Limitations
Not very secure
- can be encrypted
- can be specified "httponly" or "secure"
Not a lot of bytes
Cross-origin limitations
- the server specifies which other domains/hosts/sites to share this cookie with
- but the client can restrict it further
User can erase them at any time

## Cookie Sessions
Cookie data on the client is not very secure, limited in size and format, & unstable (it might be deleted, or edited, at any moment)
So a cookie is often used not to store data directly, but as a key to a larger, long-term server-side database or this is called a "session cookie" (yet another meaning of the term "session")
Often that key identifies a currently logged-in user with a lot of related long-lived database records this is how web sites implement "Remember Me" login checkboxes

## Cookie Headers
response: `Set-Cookie: ice_cream=chocolate`
request: `Cookie: ice_cream=chocolate; fruit=banana`

## `Set-Cookie` Header
set on the server response to the client
asks the client to create or modify a cookie for this
`name=value`, plus other options for this cookie separated by ;s

## Cookie Header
set on the client request to the server
tells the server "here are all the cookies I know about for you"
name=value pairs separated by ;s

## Fetch API vs Cookies
the Fetch API does not always send cookies (it's part of "same origin policy", enforcement of which is often draconian) to send them you may need to set `credentials: 'include'` like this
```
fetch('/articles.json', {credentials: 'include'})
  .then(
```

## Express Cookie Code
In Express, the incoming request's Cookie header is available (`via request.headers.cookie`), but it isn't pretty. Like URL-encoded parameters, it has to be parsed before it's useful.

Fortunately, Express has a middleware component called cookie-parser that parses the Cookie header and puts all available cookies into an object at `request.cookies`.
```
const express = require('express');
const cookieParser = require('cookie-parser');
const app = express();
app.use(cookieParser());
app.get('/', function(request, response) {
  console.log('Cookies: ', request.cookies)
})
```

To set a cookie, use the method response.cookie():
`response.cookie('cart', ['milk', 'cheese', 'dog food'])`

Express will take care of encoding the value into JSON, and then URI-encoding that, to satisfy the arcane demands of the Cookie spec.
