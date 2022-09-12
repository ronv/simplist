---
comments: true
date: "2019-12-10T00:00:00Z"
description: GIFs and prefers-reduced-motion
summary: GIFs and prefers-reduced-motion
categories:
- article
tags:
- html
title: "GIFs and prefers-reduced-motion"
---

By using `prefers-reduced-motion: reduced`, we can have control over how animation is disabled for this user group, along with honoring the user OS setting and not requiring a browser extension.

```
<picture>
  <source srcset="/images/animated-img.gif" media="(prefers-reduced-motion: no-preference)"></source>
  <img srcset="/images/static-img.png" alt="Description of image contents">
</picture>
```
