# Embedding

## Embedding Media

- The process of including _media_ from other sources to your website.

These can include:
- Media Files
	- images, sound, video
- Other HTML
- Ads
- Maps, Graphs, Charts
- Search Boxes

## Interactive Embedding

You can make these interactive using JS.

Example: 
- You can make a Tic Tac Toe game play an audio clip upon the user winning the game.

- If a user moves to a spot on a Google Map, you can use JS to have the locations information printed onto the page

## Embedding Images

`<img src=''>` is the original _embed_

[MDN: img](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

## Where does the media come from?

- Images are served from the same web server as HTML

- Websites host media for free or a small cost
	- images: imgur, flickr, 500px
	- video: YouTube, Vimeo, Wistia
	- audio: SoundClout

- You can also use a CDN
	- Amazon AWS/CloudFront

## Image Types

There are many different types of images

A few common ones are:

- JPGs (or JPEGs)
- PNGs
- SVGs

## jpeg/jpg

- one of the most common image types
- relatively small
- limited features
- no transparency
- no pixel base
- rectangular in shape

## png

- similar size to JPG
- pixel based
- supports transparent
- rectangular in shape

## svg

- VERY small file size
- vector based image type
- scales indefinitely
- can be irregular in shape
- only covers the exact area it appears to cover

## Embedding IFrames

`<ifram>` means "inline frame"

[MDN](https://www.w3.org/Security/wiki/Same_Origin_Policy)

## Malware Vectors

Beware of giving foreign JS access to your page contents and user-input data

## Embedding HTML Snippets

You can use an iframe to load the same HTML into different pages on your site

- such as login boxes

>Warning: iframes can take longer to load than the rest of the page, and can eat up CPU and RAM, so don't overuse them

## Modern Animations

Flash used to be the way to create animations.

Here are a few better options:

- `<canvas>` elements using JS
- Pure CSS animations
- The JS animation API
- Third party animation frameworks such as Snap SGV

## Embedding Video

`<video>` tags are how we can use HTML5 to embed videos

- We can use these while we are hosting our own video media on our own server or CDN
- YouTube and Vimeo provide sample code that you can find and copy into your HTML file

## Embedding Audio

`<audio>` tags are how we can use HTML5 to embed audio

There are key attributes for audio elements:
- Src
- AutoPlay
- Controls
- Loop
- Muted