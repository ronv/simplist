---
date: "2014-05-12T00:00:00Z"
description: This is a collection of short CSS snippets I thought might be useful
  for beginners
summary: This is a collection of short CSS snippets I thought might be useful for beginners.
categories:
- article
tags:
- css
title: CSS hacks you may not know
---

This is a collection of short CSS snippets I thought might be useful for
beginners. If you’re experienced with CSS you’ll have seen most of these tips
and tricks before, but who knows maybe you can find one or two you haven’t seen
before.


* Unicode classes

You can use unicode characters for class names in your HTML, and even use write
CSS selectors with those same characters.

```css
.♫ { background: #222; color: #FFF; } 
.ಠ_ಠ { background: #ccc; color: #fff; }
```

* Remove input outline for WebKit browsers

```css
input[type="text"]:focus { outline: none; }
```

And orange outline won’t show up anymore.

* Opacity in all major browsers

As you know older browsers have different ways of controlling the opacity or
transparency.

```css
div { opacity:0.4; -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=40)"; /* IE8 */ filter: alpha(opacity=40); /* IE 5-7 */ }
```

* Property text-decoration is now a shorthand

```css
a { text-decoration: overline red wavy; }
```


Currently works only in Firefox.

* Background new values

Correct syntax for all backgrounds properties are:

```css
div { background: [background-image] 
                  [background-position] 
                  [/ background-size] 
                  [background-repeat] 
                  [background-attachment] 
                  [background-origin] 
                  [background-clip] 
                  [background-color]; 
}
```

* Specifying page breaks for printing using CSS

```css
.page-break { page-break-before: always; }

p { text-transform: capitalize; }
```

* Consistent base font size

```css
body { font-size:62.5%; }
```

Setting the font-size property to 62.5% in body makes 1em equal to 10px.

* Reading HTML attribute values from CSS

```css
a:hover:after { content: attr(title); }
```

* A one-liner to target Webkit browsers

```css
.selector:not(*:root) { property:value; }
```

* A Media Query to target Webkit browsers

```css
@media screen and (-webkit-min-device-pixel-ratio:0) { 
                     .selector { property:value; 
} }
```

* Target old versions of Internet Explorer

Easily target IE8 and older versions. Yes, I know it’s 2014, but I recently used
this hack :D

```css
.element { color: black; 
           color: green\9; /* IE8 and older */ 
           *color: blue; /* IE7 and older */ 
           _color: red; /* IE6 and older */ }
```

* Add a left margin of 10px to all paragraphs in all browsers (except Opera 9 and
below)

```css
p { margin-left: 10px; } html:first-child p { margin-left: 0; }
```

P.S. If you know of any other good ones, please contact me via twitter.
