---
title: Emojis as favicon
date: 2020-03-21T07:38:35.920Z
description: >-
  Now that all modern browsers support SVG favicons, here's how to turn any
  emoji into a favicon
categories:
- article
tags:
  - svg
---
Since browsers have started supporting SVG you can finally have emoji as favicon. Here's the one-liner in use: 

```html
<link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>😉</text></svg>">
```

This works in Firefox and Chrome. Safari only does those "mask" style icons in SVG so this doesn't work there.