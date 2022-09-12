---
comments: true
date: "2018-07-19T00:00:00Z"
description: Using the aria-current attribute
summary: Using the aria-current attribute
categories:
- article
tags:
- html
title: "Using the aria-current attribute"
---

The `aria-current` attribute should be used to identify the current item in a set of items. It can take multiple values, specifically: `page`, `step`, `location`, `date`, `time`, `false`, `true`.

```
/* Indicates the current page */
<a href="/home" aria-current="page">Home</a>
```