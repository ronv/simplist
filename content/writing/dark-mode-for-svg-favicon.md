---
title: Dark mode for SVG favicon
date: 2020-04-22T08:33:53.792Z
description: Light and dark themed SVG favicon
categories:
- article
tags:
  - svg
---
You can embed CSS within an SVG with a `<style>` element. This means that you can style your icon with inline `prefers-color-scheme`. 

```css
<!-- icon.svg -->
<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
  <style>
    circle {
      fill: white;
      stroke: black;
      stroke-width: 2px;
    }
    @media (prefers-color-scheme: dark) {
      circle {
        fill: black;
        stroke: white;
      }
    }
  </style>
  <circle cx="50" cy="50" r="47"/>
</svg>
```

For Safari, it’s a bit different. You need to add a `mask-icon`. It’s also an SVG, but it has to be made of a single colour and placed on a transparent background. You specify the color, so there is no opportunity there for a dark mode situation.

```html
<link rel=”mask-icon” href=”mask-icon.svg” color=”#000000">
```