# Page Navigation

- Finding the way around a site can be challenging without guidance
- There are tools which can help the end user locate parts of the site



## Navigation Bars
- Common component of web pages
- Shape the way users think about the site
- Several ways to build them
- Flexbox makes building these much easier

## Anchors

- Two opposite purposes
    - Link
        - `<a href="">`
    - Name
        - `<a name="">`
        - Using Anchor tags to name things is less common
        - `id=""` attributes do the same thing as using a name tag
    
## Anchor Links

- Anchor tags create links to other locations
    - sometimes within the same page
        - `href="#someId"`
    - other pages within the same site
        - `href=/somePage.html`
    - sometimes external pages
        - `href="https://www.example.com"`


# Responsive Layout

Responsive development is a technique that displays content well regardless of the device it is being viewed on, *Responsive* means that the layout changes and responds based on the width of the screen. 50+% of web traffic goes through mobile devices.

## Media Queries

Media queries are the backbone of front-end responsive development with HTML and CSS. CSS3 introduced media queries, which allow developers to apply CSS properties to devices which match rules.

Media Queries `@media (some_condition) { }` cause different CSS rules to be applied on different screens
```
.nav { // Default position layout
  position: absolute;
}
@media print { // Print media only layout
  .nav {
    position: relative;
  }
}
```

## Media Features
Each feature is a characteristic of the user-agent

width - the width of the viewport
all - TRUE if the device responds to media queries
resolution - Pixel density of the output device
color - Number of bits per color component of the device
pointer - Is the primary input mechanism a pointing device
hover - Does the primary input mechanism allow the user to hover

## Media Querys

Only change the layout to `position: relative;` when
The media is `screen` &&& The `screen` width is greater than or equal to 768 pixels
```
@media screen, (min-width:768px) {
  .nav {
    position: relative;
  }
}
```

## Mobile-First Development
MFD means first styling your web page for mobile devices, then modifying for desktop layout. The result of this is modifying your CSS as screen sizes increase, rather than modifying your CSS as screen sizes decrease. In other words, your media queries will be written for minimum widths, not maximum widths
Tip: You can also set media queries in-between two screen sizes