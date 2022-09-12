---
comments: true
date: "2019-08-11T00:00:00Z"
description: CSS :empty Selector
summary: CSS :empty Selector
categories:
- article
tags:
- css
title: "CSS :empty Selector"
---

The CSS `:empty` pseudo-class selects any element that has no children or text.

```
/* Background color of every empty div element */
div:empty {
  background-color: #000;
}

<div>
  <p>Some text</p>
</div>

<div>
  <!-- No text, background #000 -->
</div>
```
MDN's definition:
> The `:empty` CSS pseudo-class represents any element that has no children. Children can be either element nodes or text (including whitespace). Comments, processing instructions, and CSS content do not affect whether an element is considered empty.