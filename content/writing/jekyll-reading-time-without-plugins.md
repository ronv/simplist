---
date: "2018-09-20T00:00:00Z"
description: The reading time indicator for your website
summary: The reading time indicator for your website.
categories:
- article
tags:
- jekyll
title: Jekyll reading time without plugins
---

This script calculates the reading time based on a configurable reading speed (180 words per minutes by default).

```html
<p> 
  {% assign words = content | number_of_words %}
  {% if words < 360 %}
    1 min 
  {% else %}
    {{ words | divided_by:180 }} mins
  {% endif %}
  read
</p>
```