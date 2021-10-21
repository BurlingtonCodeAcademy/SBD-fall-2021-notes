# AJAX

## AJAX

- Loads data into your webpage from an external site
- after page loads

## AJAX Examples

- Loads information later on so that the page can render faster
- Check for new information on comments to reload if there are new ones
- infinate scrolling page
- dynamic search results as the user types their search

## AJAX Definition

**Asynchronous JavaScript And XML**

- request from an external source
- parse the data
- load the data withour refresh
- Data formats that are common:
    - JSON
    - HTML fragments
    - XML

## AJAX Advantages/Disadvantages

### Advantages
- Page components can be loaded individually
- Data loaded asynchronously
- User Interacts with the page and sees results faster

### Disadvantages
- Uses JS
- Adds complexity to JS
- Potential page state bloat
    - Memory Leaks
- Screen-readers are unable to read the whole page
- Reloading the page can change the content drastically

## XMLHttpRequest(Old Way)

- XHR interface is complicated
- Must construct an XHR object, set properties, call `open()` then `send()`
- Response handler must track `readyState` 
    - error checking is cumbersome

## Browser Fetch API

- `fetch()` takes at least one argument, the URL of what we are fetching
- `fetch` returns a *Promise* which takes *callbacks* using `.then`
-`fetch` calls the server
- after `fetch` calls the callbacks in order
- server then passes the *Response* into the **first** callback function

## Why Two Thens?

- first `then` gets called for the *HTTP Headers*
    - the body wont be ready yet
- take the first response and call `response.text()` which returns **another** promise
    - immediately return that new promise
- the second `then` gets called after the body has been recieved

## Browser Fetch API - JSON

- `response.json()` is an alternative to `response.text()`
- `response.json` parses the body of the respons as JSON and returns real JS objects
- the second `then` recieves a *proper JS Object* which is the result of calling `JSON.parse()`

## Browser Fetch API - Local

- You can use a partial URL to request data from a **local** webserver

## Browser Fetch API -  Errors

- use `.catch(function(error) {do_something_here})`
- Server responses like "404 Not Found" are not considered errors by Fetch, only network errors trigger a `catch`

## JSON (JavaScript Object Notation)

### Example:

```
{"userID": 1,
    "id": 1,
    "title": "My most amazing post",
    "body": "This is my first post, isn't it great? Maybe I'll write some more."
}
```

### Note:
- No comments
- No functions
- Only data is allowed
    - Objects, Arrays, Numbers, Booleans, Strings

## Parsing & Producing JSON

- Fetch API converts text to JSON for you if you call `response.json()`
    - you can do it yourself with `JSON.parse` to turn a string into an object:

`let data = JSON.parse(string)
