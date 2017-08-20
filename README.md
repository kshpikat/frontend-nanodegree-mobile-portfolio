# Website Performance Optimization

## Part 1: How index.html was optimized for PageSpeed

* images were optimized in Abode Photoshop to have according image size and quality
* CSS for printing was tagged with `media="print"` attribute 
* CSS was minified with https://cssminifier.com/
* main CSS file and font CSS from google was moved into index.html to reduce turnover 
* for Google Analytics and `perfmatters.js` scripts loading lines `async` attribute was added
* Google Analytics init script was moved to the bottom of index.html 
* `perfmatters.js` script was minified with https://jscompress.com/
* `index.html` was minified with https://www.willpeavy.com/minifier/ 

## Part 2: Optimize Frames per Second in `views/pizza.html` & `views/js/main.js`

* images were optimized in Abode Photoshop to have according image size and quality
* move .mover items to the separate layer with `transform: translateZ(0);` to avoid re-painting
* uses `mover.style.transform = translateX()` instead of changing `mover.style.left` to avoid re-painintg
* get DOM selection calls and expensive calculations out of big loops
* reduced the number of 'mover' class objects created from 200 to a smaller amount (approx 30-50) based on the browser window size.
* used style `transformX()` to animate the `mover` class objects as it is a composite-only operation and is GPU accelerated on some browsers



