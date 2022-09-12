---
comments: true
date: "2021-12-16T00:00:00Z"
description: Making headings into link targets
summary: Making headings into link targets
categories:
- article
tags:
- hugo
title: Add anchor links to headings in Hugo
---

An anchor link is a link, which allows the users to flow through a website page. When readers land on a page, they want to know instantly if the information it contains is useful or relevant to their search. It helps to scroll and skim-read easily. A named anchor can be used to link to a different part of the same page or to a specific section of another page. They will allow you to "jump" up or down a sizeable passage of text.

This code snippet makes it possible to automatically add linkable anchors to HTML headings in Hugo. The anchors are named based on the heading text and are used to link directly to any element on a web page that has been assigned an `id`. Just replace `{{ .Content }}` with this code snippet in default single layout:

```
{{ .Content | replaceRE "(<h[1-6]\\sid=\"([^\"]+)\"\\s?>)(.+)(</h[1-6]+>)" "${1}<a href=\"#${2}\">${3}</a>${4}" | safeHTML }}
```
