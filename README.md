html2canvas enhanced
===========

## JavaScript HTML renderer ##

The script allows you to take "screenshots" of webpages or parts of it, directly on the users browser. The screenshot is based on the DOM and as such may not be 100% accurate to the real representation as it does not make an actual screenshot, but builds the screenshot based on the information available on the page.

## How does it work? ##

The script renders the current page as a canvas image, by reading the DOM and the different styles applied to the elements.

It does **not require any rendering from the server**, as the whole image is created on the **client's browser**. However, as it is heavily dependent on the browser, this library is *not suitable* to be used in nodejs.

## Browser compatibility ##

The library should work fine on the following browsers (with `Promise` polyfill):

* Firefox 3.5+
* Google Chrome
* Opera 12+
* IE9+
* Safari 6+

## Installation ##

```shell
npm install html2canvas-enhanced
```

### NPM package aliasing ###

```json
{
    "dependencies": {
        "html2canvas": "npm:html2canvas-enhanced"
    }
}
```

## Usage ##

To render an `element` with html2canvas, simply call:

```ts
html2canvas(element[, options]);
```

The function returns a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) containing the `<canvas>` element. Simply add a promise fulfillment handler to the promise using `then`:

```ts
html2canvas(document.body).then((canvas: HTMLCanvasElement) => {
    document.body.appendChild(canvas);
});
```

## CSS supported properties ##

As each CSS property needs to be manually built to be supported, there are a number of properties that are not yet supported.

Below is a list of all the supported CSS properties and values.

 - background
   - background-clip (**Does not support `text`**)
   - background-color
   - background-image
       - url()
       - linear-gradient()
       - radial-gradient()
   - background-origin
   - background-position
   - background-size
 - border
   - border-color
   - border-radius
   - border-style
   - border-width
 - bottom
 - box-sizing
 - content
 - color
 - display
 - flex
 - float
 - font
   - font-family
   - font-size
   - font-style
   - font-variant
   - font-weight
 - height
 - left
 - letter-spacing
 - line-break
 - list-style
    - list-style-image
    - list-style-position
    - list-style-type
 - margin
 - max-height
 - max-width
 - min-height
 - min-width
 - opacity
 - overflow
 - overflow-wrap
 - padding
 - paint-order
 - position
 - right
 - text-align
 - text-decoration
   - text-decoration-color
   - text-decoration-line
   - text-decoration-style (**Only supports `solid`**)
 - text-shadow
 - text-transform
 - top
 - transform (**Limited support**)
 - visibility
 - white-space
 - width
 - webkit-text-stroke
 - word-break
 - word-spacing
 - word-wrap
 - z-index
