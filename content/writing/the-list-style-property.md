---
comments: true
date: "2020-05-03T00:00:00Z"
description: The list-style-type CSS property
summary: The list-style-type CSS property
categories:
- article
tags:
- css
title: The list-style-type CSS property
---

The `list-style` property is a shorthand for the following properties: `list-style-type`,  `list-style-position` and `list-style-image`. The `list-style` property can be applied to `<ol>`, `<ul>` or `<li>` tags. You can provide one or all of the values and they can be provided in any order. If one of the values are missing, the default value for that property will be used.

```
ul {
  list-style: <list-style-type> | <list-style-position> | <list-style-image>;
}
```

Here’s an example:

```
ul {
  list-style: square outside none;
}
```

Same as the following longhand version:

```
ul {
  list-style-type: square;
  list-style-position: outside;
  list-style-image: none;
}
```




