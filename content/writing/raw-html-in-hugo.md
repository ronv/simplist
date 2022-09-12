---
comments: true
date: "2022-04-19T00:00:00Z"
description: How to render raw html in Hugo
summary: How to render raw html in Hugo
categories:
- article
tags:
- hugo
title: Raw HTML in Hugo
---

From Hugo V.0.60, the default markdown renderer is the Goldmark. By default it will not render raw HTML. To override Hugo’s default markup settings, use a markup nested map in your project’s config file. Example `config.yaml`:

```
markup:
  goldmark:
    renderer:
      unsafe: true
```

The solution enables the Markdown renderer to use Goldmark render to consider raw HTML with configuration.