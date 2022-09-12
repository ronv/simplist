---
comments: true
date: "2021-12-22T00:00:00Z"
description: The CSS :has() selector
summary: The CSS :has() selector
categories:
- article
tags:
- css
title: The CSS :has() selector
---

The `:has()` CSS pseudo-class represents an element if any of the selectors passed as parameters match at least one element. 

In earlier revisions of the CSS Selectors Level 4 specification, `:has` had a limitation that it couldn't be used within stylesheets. Instead, it could only be used with functions like `document.querySelector();` this was due to performance concerns. This limitation has been removed because no browser implemented it that way. Instead, browsers currently only support the use of `:has()` within stylesheets.

For example, the following selector matches only `<a>` elements that contain an `<img>` child:

```
a:has(> img)
```

When selector matches a `<dt>` element immediately followed by another `<dt>` element:

```
dt:has(+ dt)
```

When selector matches `<section>` elements that don’t contain any heading elements:

```
section:not(:has(h1, h2, h3, h4, h5, h6))
```
Or swapping the nesting of the two pseudo-classes:

```
section:has(:not(h1, h2, h3, h4, h5, h6))
```

Safari Technology Preview Release 137 is now available for download and enabled support for `:has()` pseudo-class by default. The Chromium is not supported right now, but they currently working on implementing it. Firefox is not supported right now.