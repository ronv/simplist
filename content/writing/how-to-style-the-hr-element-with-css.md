---
comments: true
date: "2019-12-30T00:00:00Z"
description: How to style the hr (horizontal rule) element with CSS
summary: How to style the hr (horizontal rule) element with CSS
categories:
- article
tags:
- css
title: How to style the hr element with CSS
---

The default appearance of horizontal rule lines does not look good. To make them look nicer, add CSS to adjust the visual appearance of these elements to be in line with how you want your site to look. Originally the `<hr>` element was styled using attributes. Nowadays, in HTML5, the `<hr>` tag defines a thematic break in an HTML page: for example, a change of scene in a story, or a shift of topic within a section and we need to use CSS to style `<hr>` element.


Some examples of adding different styles to horizontal lines:

```
/* Gradient */

hr {
    border: 0;
    height: 1px;
    background: #333;
    background-image: linear-gradient(to right, #ccc, #333, #ccc);
}
```

```
/* Two-color dashed line */

hr {
    border: 0;
    border-bottom: 1px dashed #ccc;
    background: #999;
}
```

```
/* With glyph */

hr {
    overflow: visible; /* For IE */
    padding: 0;
    border: none;
    border-top: medium double #000;
    color: #000;
    text-align: center;
}
hr:after {
    content: "§";
    display: inline-block;
    position: relative;
    top: -0.8em;
    font-size: 1.6em;
    padding: 0 0.3em;
    background: white;
}
```






