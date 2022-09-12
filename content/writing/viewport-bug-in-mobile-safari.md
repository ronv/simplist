---
title: Viewport bug in Mobile Safari
date: 2020-04-26T20:19:27.960Z
description: How to fix vh(viewport unit) css in mobile Safari?
categories:
- article
tags:
  - css
---
When I first heard of `vh` (viewport height) I was excited and I thought I could use it for fixed height blocks instead of using javascript. Usually the `100vh` height will account for the adjusted height, with is why you'll sometimes see mobile pages go funky when the browser's address bar slides down. If you opened your browser and started to load a website, `1vh` was equal to 1% of your screen height, minus the browser interface. In Safari Mobile if you start scrolling, viewport height is taller than the visible part of the document. This is a [well know issue](https://bugs.webkit.org/show_bug.cgi?id=141832) (at least in Mobile Safari). Here are some solutions how to avoid this issue.

### Solution 1: `-webkit-fill-available`

```css
body {
  min-height: 100vh;
  min-height: -webkit-fill-available;
}
```

### Solution 2: CSS media queries

```css
@media all and (device-width: 768px) and (device-height: 1024px) and (orientation:portrait) {
    .foo {                           
        height: 1024px;                         
    }                       
}   
                                            
/* iPad with landscape orientation. */                       
@media all and (device-width: 768px) and (device-height: 1024px) and (orientation:landscape) {                         
    .foo {                           
        height: 768px;                         
    }                       
}
                                               
/* iPhone 5 
You can also target devices with aspect ratio. */                       
@media screen and (device-aspect-ratio: 40/71) {                              
    .foo {                           
        height: 500px;                         
    }                       
}
```

### Solution 3: Viewport Units Buggyfill

You can make viewport units (vh|vw|vmin|vmax) work properly in Mobile Safari by using [Viewport Units Buggyfill](https://github.com/rodneyrehm/viewport-units-buggyfill). The buggyfill iterates through all defined styles the document knows and extracts those that uses a viewport unit. After resolving the relative units against the viewport's dimensions, CSS is put back together and injected into the document in a `<style>` element.

### Solution 4: Targeting `innerHeight` with Javascript.

Try setting the height of the page (using javascript) with the `window.innerheight` property.

```javascript
window.onresize = function() {
    document.body.height = window.innerHeight;
}
window.onresize();
```

Let me know if these solutions were helpful to you, and which ones worked best!