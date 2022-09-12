---
title: Dark mode images without javascript
date: 2020-05-04T16:02:08.183Z
description: How to implement light or dark mode for images.
categories:
- article
tags:
  - css
---
The `<picture>` element supports media query matchers and if you want to specify a different image for dark mode, you can use a different `<source>`. So, if there are no suitable matches or if the browser doesn’t support the `<picture>` element, then the default `src` attribute is selected.

```html
<picture>
  <source srcset="dark.png" media="(prefers-color-scheme: dark)">
  <img src="light.png">
</picture>
```

If dark mode is enabled, the `dark.png` image will be used as the source for the `img` tag.