---
date: "2018-01-17T00:00:00Z"
description: Obtaining the word count from a post in Jekyll
summary: Obtaining the word count from a post in Jekyll.
categories:
- article
tags:
- jekyll
title: Showing the word count in Jekyll
---

If you want to count word in a string, use ```number_of_words``` liquid filter.

```html
<p> 
{% assign wordCount = post.content | number_of_words %}
</p>
```