---
comments: true
date: "2021-01-18T00:00:00Z"
description: Nested Media Queries
summary: Nested Media Queries
categories:
- article
tags:
- css
title: "Nested Media Queries"
---

You can nest media queries in native CSS, as long as you’re doing it from the root:

```
@media not print {
  @media (min-width: 0) {
    p {
      background: blue;
    }
  }
}
```