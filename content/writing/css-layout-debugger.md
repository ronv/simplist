---
title: CSS layout debugger
date: 2020-03-23T07:49:26.187Z
description: Debugger for visualizing your CSS layouts
categories:
- article
tags:
  - css
---
Here is one-line version of CSS layout debugger to paste in your DevTools. Outlines every DOM element on your page a random (valid) CSS hex color.

```
$$('*').map((A,B)=>A.style.outline=`1px solid hsl(${B*B},99%,50%`)
```