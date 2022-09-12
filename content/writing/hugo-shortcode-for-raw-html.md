---
comments: true
date: "2022-02-15T00:00:00Z"
description: How to render raw html in Hugo markdown files with shorcode
summary: How to render raw html in Hugo markdown files with shorcode
categories:
- article
tags:
- hugo
title: Hugo shortcode for raw HTML
---

Sometimes we need to add raw HTML content in markdown files. We can do it before or after, the content. And in the middle of content using shortcodes. Here is how to create your own one-line custom shortcode to make that possible.

Create html file located in `/layouts/shortcodes/rawhtml.html`.

```
<!-- raw html -->
{{.Inner}}
```

And then you can use the shortcode in your markdown file e.g:

```
{{ < rawhtml > }}
  <p>Hello World!</p>
{{ < /rawhtml >}}

```