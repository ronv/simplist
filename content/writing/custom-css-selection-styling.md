---
comments: true
date: "2017-09-17T00:00:00Z"
description: Custom CSS selection styling
summary: Custom CSS selection styling
categories:
- article
tags:
- css
title: "Custom CSS selection styling"
---

The `::selection` CSS pseudo-element allows you to apply styles to your text when it’s highlighted (such as clicking and dragging the mouse across text).

```
p::selection {
  background: blue;
  color: white;
}
```