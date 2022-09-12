---
title: Tag cloud snippet for Hugo
date: 2020-12-09T20:56:04.701Z
description: Tag cloud snippet without Javascript
tags:
  - hugo
---
Simple solution for tagcloud in your Hugo website.

```
{{ $tags := $.Site.Taxonomies.tags.ByCount }}
{{ $v1 := where $tags "Count" ">=" 3 }}
{{ $v2 := where $v1 "Term" "not in" (slice "hugo" "tags" "rss") }}
{{ range $v2 }}
{{ if .Term }}
{{ $tagURL := printf "tags/%s" .Term | relURL }}
<a href="{{ $tagURL }}">{{ .Term }} ({{ .Count }})</a>
{{ end }}
{{ end }}
```