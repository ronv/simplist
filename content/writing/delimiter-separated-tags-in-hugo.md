---
title: Delimiter separated tags in Hugo
date: 2020-06-09T11:19:02.424Z
description: How to delimiter separated tags in Go Hugo.
categories:
- article
tags:
  - hugo
---
The example below uses tags with comma as delimiter.

```html
<strong>{{ Tags: }}</strong>
{{ range $key, $value := .Params.tags }}
   <a href="/tags/{{ $value | urlize }}">{{ $value }}</a>{{ if ne $key (sub (len $.Params.tags) 1) }}, {{ else }}{{ end }}
{{ end }}
```