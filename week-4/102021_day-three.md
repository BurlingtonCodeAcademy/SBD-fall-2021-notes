# URLs

## URL

- Uniform
- Resource
- Locator

## URL Breakdown

`protocol://host:port/path?query#fragment

## Protocol

- `http` - the basic
- `https` - "s" means "Secure"
- `file` - local filesystem

## Host

- Host is the domain name
- in `http://www.example.com`, `www.example.com` is the host

## Port

- in `http://localhost:8080`, `8080` is the port number

## Path

- in `http://musical-notes.com/band/heart`, the path is `/band/heart`
- the path helps the service locate the specific resource the client is looking for 

## Queries

- in `http://musical-notes.com/bands/search?heart`
    - the path is `/bands/search`
    - the query is `?heart`

## Query Parameters

- use the same URL slot as normal queries, but use a particular format to encode multiple parameters into a single string

- `&` to separate parameters form eachother
- `=` to separate individual parameter names for values

in `http://musical-notes.com/bands/search?category=fold&date=1977`

the query is `?category=folk&date=1977`

the parameters are
    - category - `folk`
    - date - `1977`

## Percent Encoding

Weird characters in a URL are "escaped" as hexadecimal using percent-encoding

- space turns into `+` or `%20`
- plus signs `%2B`
- percent signs `%25`

## Query Parameter Encoding

Combining query parameters and percent-encoding can be confusing.

- in `http://musical-notes.com/bands/search?category=80%27s+Rock+Bands&page=2`

- query is `?category=80%27s+Rock+Bands&page=2`
    - first parameter is `category80%27s+Rock+Bands`
        - the `%27` is an 'apostrophe'
        - the `+` means space

## Fragment

- `http://example.com/users/alex#profile
    - `#profile` is called a fragment or anchor

- fragments are for the browser, and is not sent to the server with the rest of the URL
    - normal pages, it scrolls to a spot inside the page
    - Single Page Apps, it displays a pseudo-page

## Reading the Anchor Fragment

`document.location.hash` returns the URL's fragment(everything after the `#`)

- normal webpages scroll to an element with a matching `id` or `class`
- SPA's (Single Page Apps) use the anchor to redraw the page and call it "routing".