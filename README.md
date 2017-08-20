# Website Performance Optimization

###### Project Overview

Project #4 of Udacity's [Front-End Web Developer Nanodegree](https://www.udacity.com/course/front-end-web-developer-nanodegree--nd001). 
The task was to optimize [Cameron's portfolio website](https://github.com/udacity/frontend-nanodegree-mobile-portfolio) to get at least 90 for Mobile and Desktop PageSpeed score for `index.html`. Second task was to optimize views/js/main.js and views/pizza.html to render with a consistent frame-rate at 60fps when scrolling.

###### Preview

Live preview (non-compressed css and js files) available with [GitHub Pages](https://kshpikat.github.io/frontend-nanodegree-mobile-portfolio/).
Also online [PageSpeed score](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fkshpikat.github.io%2Ffrontend-nanodegree-mobile-portfolio%2F&tab=mobile)

###### Local

###### 1. Get Sources

```
$ git clone https://github.com/kshpikat/frontend-nanodegree-mobile-portfolio.git
````

###### 2. Open the application in the browser

```
<path_to_app>/index.html
```

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



