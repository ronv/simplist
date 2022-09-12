---
comments: true
date: "2017-08-11T00:00:00Z"
description: Interaction Media Features
summary: Interaction Media Features
categories:
- article
tags:
- css
title: "Interaction media features"
---

You can detect touch screens, stylus-based screens or touchpads.

```
/* Make radio buttons and check boxes larger if we have an inaccurate primary pointing device */
@media (pointer:coarse) {
  input[type="checkbox"], input[type="radio"] {
    min-width:30px;
    min-height:40px;
    background:transparent;
  }
}
```