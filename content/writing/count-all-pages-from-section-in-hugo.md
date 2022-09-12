---
comments: true
date: "2022-01-16T00:00:00Z"
description: Display the total number of pages in Hugo
summary: Display the total number of pages in Hugo
categories:
- article
tags:
- hugo
title: Count all pages from section in Hugo
---

If you want to display the total number of content pages that Hugo generated from a particular section use `where` to filter section pages:

```
<p>Total number of pages in the /articles/ section:
	{{ len (where .Site.RegularPages "Section" "==" "articles") }}.
</p>
```




