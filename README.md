# Pixels.JS
## 70+ Photo Filters for your Browser & Node Projects

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com) 
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/)
[![Documentation Status](https://readthedocs.org/projects/pixelsjs/badge/?version=latest)](https://pixelsjs.readthedocs.io/en/latest/?badge=latest)
![GitHub last commit](https://img.shields.io/github/last-commit/google/skia.svg)
![GitHub last commit](https://img.shields.io/badge/filters-71-blue.svg)

![PixelsJS Header](https://github.com/silvia-odwyer/pixels.js/blob/master/pixels_header.PNG "PixelsJS Header")

Pixels.JS is an  image filtering library with over 70 photo filters for use in the browser or with Node.JS.

Image filtering comprises vintage filters, solarizers, inverters, and over ninety more. You can explore these in the Flashback web app, 
which makes use of the library.

## Check Out The Official Website
The official home of PixelsJS is now here! https://silvia-odwyer.github.io/pixels.js/

## Read The Docs [![Documentation Status](https://readthedocs.org/projects/pixelsjs/badge/?version=latest)](https://pixelsjs.readthedocs.io/en/latest/?badge=latest)
For complete PixelsJS documentation: https://pixelsjs.readthedocs.io/en/latest/

## Importing Pixels.JS
### In The Browser
Include the following script tag in your webpage's head tag: 

```html
<script src="https://cdn.jsdelivr.net/gh/silvia-odwyer/pixels.js/dist/Pixels.js"></script>
``` 

### Node.JS
[NOT YET ON NPM; COMING SOON]
`npm install Pixels.JS`

## Using Pixels.JS
### Browser
##### HTML
After you've included a copy of Pixels.JS in your head tag, include an image in your HTML:
```html
<img src="image.PNG" id="img"/> 
```

##### Javascript
Then, in your JavaScript:
```javascript
// Select the image you wish to filter
var img = document.getElementById("img")
// First parameter is the image object, and the second is the filter you wish to apply.
pixelsJS.filterImg(img, "twenties");      
```

#### Node.JS
Usage for Node.JS varies slightly to the browser. Whereas in-browser Pixels.JS automatically replaces the image on the webpage with the newly filtered one, 
in Node, your environment and canvas libraries can differ, so we've kept usage flexible for Node. 

This example uses node-canvas and get-image-data, two NPM modules that make canvas rendering easier, however, you can choose whatever libraries you like; this example merely illustrates using Pixels.js in tandem with node-canvas. 

```javascript
const get-image-data = require('get-image-data');
const Pixels.JS = require("Pixels.JS");
const Canvas = require('canvas')

var canvas = new Canvas(200, 200),
    ctx = canvas.getContext('2d'),

get-image-data('./image.jpg', function(error, info) {
  var imgData = info.data
  
  let newImgData = PixelsJS.filterImgData(imgData, "solange");
  
  ctx.putImageData(imgData, 0, 0);
  
})
```

## Step-By-Step Guide
You can quickly get started with Pixels.JS using the sample code above, but if you're new to web development or want a guided tour, 
just check out the guides below. 

### Browser
1. Include the image on the webpage. `<img src="path/to/image.PNG">`

2. In your JS, select the image you want to add filters to. `var img = document.getElementById("img")`

3. Pass the image into the filter function, and include the name of the filter you want. 
`var filtered_img = Pixels.JS.filterImg(img, "sepia")`

The method filters the image and replaces the current image with the filtered one, so there's no need to append the new image to the DOM, as this is already
done for you. 

### Node.JS
Simply get the image data of the image and pass it to the filterImgData function. The output will be the new image data. 
You can then place this new image data onto your canvas.


!["Usage code for Node.JS"](https://github.com/silvia-odwyer/Pixels.JS/blob/master/node_code.png "Usage code for NodeJS")

## Contributing
Want to contribute? I'm always delighted to work with other developers, so submit a Pull Request if you'd like to add any cool image filters. 
:eyes: 

## Future Plans
- This library currently contains 70 image filters, but I'd like to bring this to 100 in the next few weeks or so. 
- Publish on NPM and the UNPKG CDN.