---
date: "2019-12-04T00:00:00Z"
description: How to add dark mode to your website.
summary: How to add dark mode to your website.
categories:
- article
tags:
- css
title: Dark mode for your website
---
Easiest way to add dark mode to your website would be to by using Media Queries Level 5 `prefers-color-scheme` media feature. It is currently supported in all major browsers. Chrome/Edge since release 76, Firefox since 67 and Safari (since version 12.1).

```css
@media (prefers-color-scheme: dark) {
  body {
    background-color: #333;
    color: #fff;
  }
}
@media (prefers-color-scheme: light) {
  body {
    background-color: #fff;
    color: #333;
  }
}
```

The `prefers-color-scheme` CSS media feature is used to detect if the user has requested the system use a light or dark color theme. The method by which the user expresses their preference can vary. It might be a system-wide setting exposed by the Operating System, or a setting controlled by the User Agent. 

`prefers-color-scheme` CSS media feature works with the following values:

* `no-preference`: Indicates that the user has made no preference known to the system.
* `light`: Indicates that the user has notified the system that they prefer a page that has a light theme.
* `dark`: Indicates that the user has notified the system that they prefer a page that has a dark theme.

As dark mode is reported through a media query, you can easily check if the current browser supports dark mode by checking if the media query `prefers-color-scheme` matches at all. You can optionally check if the browser supports it using Javascript.

```javascript
if (window.matchMedia('(prefers-color-scheme)').media === 'not all') {
  console.log('Browser doesn't support dark mode');
}
```

### Using custom properties (--*): CSS variables for theming

To define a variable, you can use the `--variable-name: value` format.

```css
:root {
  --page-background: #fff;
  --page-title: #333;
  --page-text: #333;
}

@media screen and (prefers-color-scheme: dark) {
  :root {
    --page-background: #333;
    --page-title: #fff;
    --page-text: #fff;
  }
}

body {
  background: var(--page-background);
  color: var(--page-text);
}

h1 {
  color: var(--page-title);
}

p {
  color: var(--page-text);
}
```

Not all browsers support CSS variables. But with a little help of JavaScript you can make it work. Just make a class to apply on body and override styles in any element within that `body` you want to change and toggle that one class on `body`.

```css
body[theme="dark"] {
  background: #333;
  color: #fff;
}
```

You may also use `currentColor` to save you some CSS. Basically you should change main styles on html/body and that should be enough for most simple cases if you just want to invert colors.

### Dark mode for SVG

You can use `prefers-color-scheme` media feature and CSS variables to style colors inside of SVG, just like your other elements.

```html
<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
  <style>
    circle {
      fill: white;
      stroke: black;
      stroke-width: 3px;
    }
    @media (prefers-color-scheme: dark) {
      circle {
        fill: black;
        stroke: yellow;
      }
    }
  </style>
  <circle cx="50" cy="50" r="47"/>
</svg>
```

### Are there any benefits of using dark mode?

It saves energy, mainly if the device uses an OLED or AMOLED screen. Doesn’t strain your eyes too much at night. But keep in mind that dark mode are not always better for eye strain. In bright light conditions, the text appears washed out, increasing eye fatigue.
